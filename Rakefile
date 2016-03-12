# Magnus Eriksson
# Modified from Jason Heppler
# Modified from Jeff McFadden:
# http://jeffmcfadden.com/blog/2011/04/13/rsync-your-jekyll/

# Requirements
require 'rake'       # For the rake tasks
require 'yaml'       # For reading the configuration file
require 'fileutils'  # For creating recursive directories
require 'rubygems'
require 'optparse'

# Load the configuration file
config = YAML.load_file("_config.yml")

# Set "rake watch" as default task
task :default => :list

## -- Config -- ##
source_dir  = "_site"
draft_dir   = "_drafts"
posts_dir   = "_posts"
stash_dir   = "_stash"
server_port = "4000"


##############
# Deploying  #
##############

## Push

desc 'push master to blay.se and github via git'
task :push, :message do |t, args|
  message = args[:message]
  branch  = config["git"]["branch"]

  if message.nil? or message.empty?
    message = "auto"
  end
  if branch.nil? or branch.empty?
    raise "Please add a branch."
  else
    puts 'PUSHING MASTER TO OMXI AND GITHUB'
    system "git checkout #{branch}"
    system "git add ."
    system "git commit -m \"#{message}\""
    system "git push origin #{branch}"
    system "git push github #{branch}"
    puts 'Done!'
  end
end


desc 'push dev to blay.se and github via git'
task :pushdev, :message do |t, args|
  message = args[:message]
  branch  = config["git"]["branch_dev"]

  if message.nil? or message.empty?
    message = "auto"
  end
  if branch.nil? or branch.empty?
    raise "Please add a branch."
  else
    puts 'PUSHING DEV TO OMXI AND GITHUB'
    system "git checkout #{branch}"
    system "git add ."
    system "git commit -m \"#{message}\""
    system "git push origin #{branch}"
    system "git push github #{branch}"
    puts 'Done!'
  end
end

## Transfer

desc "Transfer the site to the remote server"
task :transfer do
  command     = config["transfer"]["command"]
  source      = config["transfer"]["source"]
  destination = config["transfer"]["destination"]
  settings    = config["transfer"]["settings"]

  if command == "rsync"
    Rake::Task[:build].invoke

    system "rsync #{settings} #{source} #{destination}"
    puts "Your site was transfered."
  else
    raise "#{command} isn't a valid file transfer command."
  end
end

desc "Transfer the dev site to the remote server"
task :transferdev do
  command     = config["transfer"]["command"]
  source      = config["transfer"]["source"]
  destination = config["transfer"]["destination_dev"]
  settings    = config["transfer"]["settings"]

  if command == "rsync"
    Rake::Task[:build].invoke

    system "rsync #{settings} #{source} #{destination}"
    puts "Your site was transfered."
  else
    raise "#{command} isn't a valid file transfer command."
  end
end

#######
# All #
#######

desc 'Build, Push, Transfer'
task :all => ["push", "transfer"]


desc 'Build, Push, Transfer Dev'
task :alldev => ["pushdev", "transferdev"]

#######################
# Working with Jekyll #
#######################

desc 'list: list available rake tasks'
task :list do
	puts 'Try one of these specific tasks:'
	sh 'rake --tasks --silent'
end

# rake build
desc "Generate the site (no server)"
task :build do
  system "jekyll build"
end

desc "nuke and rebuild"
task :nuke do
    sh 'rm -rf _site'
    system "jekyll"
end

# rake watch
# rake watch[number]
desc "Generate and watch the site (with an optional post limit)"
task :watch, :number do |t, args|
  number = args[:number]

  if number.nil? or number.empty?
    system "jekyll serve"
  else
    system "jekyll serve --limit_posts=#{number}"
  end
end

# rake preview
desc "Launch a preview of the site in the browser"
task :preview do
  require 'Launchy'

  puts "Launching browser for preview..."
  sleep 2

  Thread.new do
    Launchy.open("http://localhost:4000/")
  end

  Rake::Task[:watch].invoke
end

#########
# Posts #
#########

## Creating Posts

desc "Create a new post with a title"
task :np do
  OptionParser.new.parse!
  ARGV.shift
  title = ARGV.join(' ')

  path = "_posts/#{Date.today}-#{title.downcase.gsub(/[^[:alnum:]]+/, '-')}.md"

  if File.exist?(path)
	  puts "[WARN] File exists - skipping create"
  else
	  File.open(path, "w") do |file|
		 file.puts YAML.dump({'layout' => 'post', 'title' => title, 'tags' => 'english research tldr meta', 'summary' => '','image' => 'feature:'})
	     file.puts "---"
	  end
  end
  `atom #{path}`
  # `rm -f #{path}`
  exit 1
end

## Isolating and Integrating

desc "Move all other posts than the one currently being worked on to a temporary stash location (stash) so regenerating the site happens much quicker."
task :isolate, :filename do |t, args|
  stash_dir = "#{stash_dir}"
  FileUtils.mkdir(stash_dir) unless File.exist?(stash_dir)
  Dir.glob("#{posts_dir}/*.*") do |post|
    FileUtils.mv post, stash_dir unless post.include?(args.filename)
  end
end

desc "Move all stashed posts back into the posts directory, ready for site generation."
task :integrate do
  FileUtils.mv Dir.glob("#{stash_dir}/*.*"), "#{posts_dir}/"
end
