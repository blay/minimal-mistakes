---
layout: post
title: Overview of Scripts for Zettelkasten
tags: meta
summary: Shows the scripts I use for my Zettelkasten note system
image:
  feature: zettel_narrow.png
---

{% include _toc.html %}


This is an overview of scripts that complement the operations of a [Zettelkasten](2015-06-21-living-with-a-zettelkasten.html). Many of these script work in a semi-magical way where they main purpose is not to find exactly what you are looking for (regular Linux commands work for this like ls, grep, find, ack). Instead they are mean to remind you of notes in your archive in a semi-random way and give suggestions and inspiration.

I try to separate the functions of search, process and display in the scripts and instead combine a search script with a process script with a display script. The display if however often taken care of by STDOUT in the terminal, opened in an editor like Vim or Atom, or sent to a file or the clipboard. The most important function in a Zettelkasten is to find the right files. Often the foundation of an operation is a list of files that are interesting to the Zettelkasten for some reason.

Here is a funny example of how to work with select, process, and display:

~~~
# List files according to size with largest last.
#Take this list of files and select only the ones with lines that begin with '#' (markdown headers...)-
# Select the last 5 files of those (the 5 biggest).
# Display the contents and highlight the match where a line begins with '#' (highlights markdown headers and titles).
# Then also display the next two lines (the first paragraph after the header).
ls -Sr|a -xl "^\#"|tail -n5|a -x -A2 "^\#.*"
~~~



# Shellscripts

## al

~~~
(ack -g $1;ack -l $1;)|sort|uniq
~~~

This command searches both filenames and the contents of files in a folder and return a list of where the keyword matches. al is often used to provide a list of files for the other scripts to process.

## aword

~~~
while read line
do
  content+=`sed -e 's/\(.*\)/"\1"/g' | xargs head -n999`
done
echo "$content" |tr -c '[:alpha:]' '[\n*]' |sort -f|gfgrep -viw --file=/Users/svartfax/.shell/stop |uniq -ic | sort -nr |tr '[:upper:]' '[:lower:]'| head  -${1-16}
~~~

This command takes a list of files and find the most frequently used un-common words in the contents of those files (as compared to a stoplist fo common words). This is useful to find other key terms that occur in some clustered list of files. The new key terms can be explored by further searches. Takes number of words to display as input (default 16).

## afile

~~~
#!/bin/bash

if [[ $# -eq 0 ]] ; then
    echo 'pass uid to script, ex 1507030906, or 1407271365'
    exit 0
fi

file=$1

printf "\n# Links to file:\n\n"
ack $file

printf "\n\n# Mutual Links\n\n"
link=$(ack -o "(?<=§)[0-9]*" $file*|sort -n |uniq)

for line in $link
  do
    title=$(ack -g $line)
    printf "\n## $title \n\n"
    ack $line| ack -v $file
  done

printf "\n\n# Mutual References\n\n"
ref=$(ack -o "(?<=\@)[a-z]*\:[0-9]*[a-z]*" $file*|sort -n |uniq)

for line in $ref
  do
    title=$line
    printf "\n## $title \n\n"
    ack -o $line| ack -v $file
  done
# TODO: Match a bit before and after ref
# ack -o "(?<=\.).*(?<=\[\@)[a-z]*\:[0-9]*[a-z]*.{20}"

~~~

Accepts a uid as argument. Searches for links to the note and other notes that link to the same notes and references.

## amark

~~~
sed -e 's/\(.*\)/"\1"/' | xargs head -n${1-32} |perl -pe 's/==>/\n#/g'|perl -pe 's/<==/#\n/g'|ack --passthru "\#(.*?)\#"
~~~

*amark* takes a list of files as input and performs *head -n999* (sed is there to handle spaces in filenames) on them to display their contents, but it also uses some perl functions to replace the output of *head* so that the filenames becomes markdown headers and finally colorize by marching in between #markdown headers # with ack. The output can be displayed or copied to the clipboard and pasted in an editor. The purpose is to combine several files into one markdown formatted text mass. By default it displays the first 32 lines of each file but this can be changed with user input.

## am

~~~
a --passthru  "^\#.*"
~~~

A mini-version of amark. Feed it the contents of files and it highlights every line beginning with a '#' --- that is, markdown headers.

## acol

~~~
column -t -s -|sort -fk${1-3}
~~~

This script is rarely used by allows a list of files to be sorted on various columns where *-* is the separator. My files are often named UID -TAG-CONTEXT-PROJECT-FILENAME, but this is not consistent so the command is only partially useful.

## act

~~~
ack -x "TODO|FIXME|XXX|IDEA|\?\?\?|\!\!\!REF|REQ|HACK|NOTE" \
| ack --flush --passthru --color --color-match="black on_cyan" "TODO" \
| ack --flush --passthru --color --color-match="black on_red" "FIXME" \
| ack --flush --passthru --color --color-match="black on_red" "XXX" \
| ack --flush --passthru --color --color-match="black on_green" "IDEA" \
| ack --flush --passthru --color --color-match="black on_red" "\?\?\?" \
| ack --flush --passthru --color --color-match="black on_green" "\!\!\!" \
| ack --flush --passthru --color --color-match="black on_red" "REF" \
| ack --flush --passthru --color --color-match="black on_yellow" "REQ" \
| ack --flush --passthru --color --color-match="black on_yellow" "HACK" \
| ack --flush --passthru --color --color-match="black on_green" "NOTE" \
~~~

Searches a list of files for codetags that I sprinkle throughout the notes. The tags are colored. Useful to search with find . -mtime -60 | to only find codetags from the last two months. Older than that and its too late.

# acto

~~~
ack -o "(?<=<\!--).*?(?=-->)|(?<=>>).*?(?=<<)" |sort -nr
~~~

Named as such because it's useful together with act to provide a todolist. Selects what's between html comments and critic markdown comments and sorts it.

# au

~~~
uid=$(echo "$@"|ack -o "[0-9]{10}")
printf "$uid"
printf "$uid"|pbcopy
~~~

Strip everything of a string except the uid. Mostly used with full path of a file in Atom.

## an

~~~
time=$(gdate +%y%m%d%H%M)
echo "\"$time $1.txt\"" |pbcopy
echo "\"$time $1.txt\""
~~~

A neat little script that creates a new note according to my timestamp-based UID. A title is matched with a timestamp and an extension and put in the clipboard. The file can be created by doing 'vim cmd+v'.

# Linux commands

Some Linux commands are extra helpful in finding files or content.

## Ack

Ack is recommended as the default search. It is fast, the commands are usually short and the output looks better than grep. Ack -g can be used to find filenames. Ack -x can take a list of files as input, for example from ack -g or from find. A useful trick is to do repeated...

~~~
ack searches |ack -g pipe |ack -x like |ack -x this
~~~

...in order to successively limit search results.

## Find

Fins is most useful to list all files that match a time criteria and then pipe to ack. For example find . -mtime 7 for files modified the last week or find . -mmin -60 for files modified in the last hour. This last command is useful if you are rotating between a couple of files in a working sessions.

# Linux Aliases

~~~
alias vo='vim "`r|tail -n1`"'
alias co='cat "`r|tail -n1`"'
alias a="ack"
alias ag="ack -g"
alias f="find ."
~~~

*f* is most often used with operators such as -mtime -60 (files modified last two months) and -mmin -60 (files modified last two hours).

*ag* is used to find files to open. Often I try to make sure the file I want is the last or only result, because then I can use *co* or *vo* to display the contents of that file, by *r* repeating the last command and *tail* taking the last line of the output. Otherwise I can to copy the UID, paste, and tab to get the filename.

# A few useful functions

~~~
for file in timenotes/15062*.txt; do diff "$file" "modnotes/${file##*/}"; done
~~~

This command allows one ot compare diffs between different notes, for example when doing backups or conflicts have occured.

~~~
for i in `ack -l This *.md`;do perl -i -pe 's/This/That/g' $i;done
~~~

Replace occurences in files. If run on entire folder, all files updates their modification date, not only the ones that are changed. Therefor, search first, the use resulting file list as input.

~~~
cp -p post temp
vim temp
touch -r post temp
cp -p temp post
~~~

Use this to make minor edits in files without changing the modification date. 'Touch -r' touches a file with the modification date of another file. Use it programmatically as such:

~~~
for i in `ack -l This *.md`
do
cp -p $i $i_tmp
perl -i -pe 's/This/That/g' $i_tmp
touch -r $i $i_tmp
cp -p $i_tmp $i
rm $i_tmp
done
~~~

# Editor Functions and Plugins

This is not the place to paste my entire .vimrc and go through its contents and my use of Zotero and Pandoc to generate referenced documents deserves its own post, but I want to give a general idea of the functions I use in editors. I like to have markdown syntax and I tend to make use of clutter-free writing environments that both Vim and Atom can produce. I use keyboard expansions from Textexpander and Keyboard Maestro but I tend to write most things manually, although I have a fancy way of searching and inputting Pandoc citations.

A real life saver and a funny, but provocative, addon is language checkers. I have VimWordy for Vim and linter-write-good for Atom, the latter is based on the write-good library. With these, your text is checked for various words and phrases that you clearly should avoid. These are among others weak or puffery words (such clearly), weasel words (such as various) and passive voice (such as "is checked"). On top of this, VimWordy checks for the less serious business-jargon and art-jargon. I don't always agree with the recommendations of these plugins but it has been a revealing challenge to try to remove weak, puffy or wordy words and reformulate passive voice into an active sentence with a clear subject behind the verbs. I find it difficult to stop using passive voice when writing about technology. Technology makes the subject disappear in phrases such as; "The application can be opened by double-clicking.", "the file was deleted.", "The log can be seen with the command...", and "The computer is operated at the terminal." This occues then the text is written (passive) from the perspective of the computer. A computer is agnostic to the subject. It can't see the subject, only the irritation of the system on the inside to speak Luhmanian. A computer operates on passive objects. The computer performs operations and the object of them are being operated on and can't do anything about it. The computer only has one sequence of operations.
