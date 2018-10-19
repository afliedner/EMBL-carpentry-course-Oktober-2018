# EMBL Kurs 16.10.2018-18.10.2018

Gründlichere Notizen befinden sich [hier](https://pad.carpentries.org/2018-10-16-heidelberg). 

Ein Cheatsheat bzgl Markdowns befindet sich [hier](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

Damit es ein markdown sheet wird .md hinten dran hängen.


- Commandline:

Ctrl-C --> quit, stop

Allgemeiner Aufbau von Anweisungen:

command   option(s)   argument(s)

command: tells what to do, classical really short

option(s): how to do it, short - or long --, e.g.: -f or --file both equals filename, you can combine options, e.g.
ls -aF == ls -a -F ( lists all files which are directories

argument(s): on what to operate

help: man (short for manpages) --> doesn't work with git bash for windows
- lists options and examples for command
- quit man page: q

for windos git shell: ls  --help: prints a short overview over the command

##### different commands:

apropos: finds everything which has the keyword in description

clear: clears terminal

reset: all settings back to normal

less: catch output, show it page by page

a | b:output of a as input for b, e.g. ls --help | less

in less:

/-i:searches for -i

n: next

N: previous

q: quit


cat: command to print a file on the screen (or pr, lp, less...)

grep: search for text/string/string pattern, e.g. apropos print | grep file --> filters for file

hostname: where is the shell running

whami: username

pwd: where am I in system

date: date and time

.: current directory

..: previous directory

cd: back to home directory

tab cd D tab: sucht nach Verzeichnissen mit D

ls -l: long listing:

type:
"-"=file
"d"=directory
"l"=symbolic line
permissions: rwx, 3 groups. 1. user(owner)oup. 3. others
owner:username
group
following numer: size of the file
Time of last modification
filename

change permission of a file: chmod g -w filename (g for group, u for user, o for others, w for write, r for read, x for execute, +/-)

touch filename: leere Datei anlegen

echo blabla >> test: schreibt in test (>>: wo solls hingeschrieben werden)
> überschreibt was drin war
>> fügts hinzu

mv test test.zip: umbennen

rm test.zip: remove file

file: determine the type of a file

find: sucht was, e.g. find . -name foo (sucht im current working directory (.) nach allen dateien, die im namen foo tragen

wc -l: wordcount liste

grep -i file: -i--> without caSE SENSITIVITY

mkdir *name*: create directory

mkdir -p *parentdirectory*/*subdirectory*: creates also a parent directory, starting from where I am

cp: copy file

mv -i: interactive, fragt dich, falls eine datei, die du verschieben willst schon da ist, ob du sie wirklich überschreiben willst

cp -r *name* *name2*: copy a directory

rm -r *name*: remove a directory

rmdir *name*: removes a directory but only if it's empty

shell globs:
- ? one character
- * any number
- [...] one of the characters
-[!...] not one of the characters

run a program: either specify whole path or it's where you are

PATH=$PATH/.: current directory

head *name*: first 10 lines

head -n 3 *name*: first three lines

tail *name*: last 10 lines

ls /test 2 > ls.errorlog: redirect errormessage

2> and > are combineable

wc *file*: 1. how many lines, 2. how many words, 3. how many charcaters




#### Jupyter/Python

Alt + Enter: neues Fenster

wenn ein String eine Kommazahl ist, e.g. "1.1" kann man se nicht direkt in eine integer verwandeln, sondern muss sie erst in eine float verwandeln

Listen starten bei 0!!!

numbers[1:2]: von 1 exluding 2, also nur 1

*befehl*?: build in help

dictionairy: keys(sting):values(number), e.g. {'alessio':67,'thomas':45,'maike':32}

nano *name*: opens *name* in nano editor


#### Git/Github

git clone https://github...: ein directory von github auf deinen momentanen Standort e.g. Desktop runterladen

git status: aktueller Status

configure git:

git config --golbal user.email *emailadresse*

git config --global user.name *dein Name*

git config --global core.editor nano

git add: adds to stage

git commit -m *commitmessage*: commits to repository

git push: pushes everything to github

git status: kann man überprüfen, ob man noch was zu adden/committen hat

git log *--oneline*: gibt die log-nachrichten wieder, mit oneline in kürzer

git init: creates directory from folder, you still need to add all files you want to add
you can't add an empty directory

can't commit without a commit message

git diff --staged: what has been addes, what has been removed

git diff: falls die geänderte Datei noch nicht zur stage geadded wurde

git checkout -- *filename*: if i made y change and haven't added it to the stage and want to discard it

git diff *number from log*: see changes since then

git checkout *number from log*: HEAD geht zu früherem Zeitpunkt, master bleibt wo er ist

nano .gitignore: erstellt ein file namens .gitignore

.gitignore *file/directory*: git ignores file, it won't show up in git status

git pull: synchronizes local repository with online github

git fetch: git pull without merge, gleicht nur local and online ab, updated aber nicht automatisch

git merge: merged gefetches

git rm file: direkt löschen anstatt rm + add

git reset: resets working copy and master to previous stage

git reset --hard HEAD~1: HEAD 1 schritt zurück, geht auch 2,3,4...


#### scripts

#!python: tell shell to run this script with python

"""

blaaablablabla

"""

: doc string, to desribe what the script is doing



#### Introduction to using a High-Performance Computing cluster

Referent: @grmbough

ssh: protocol for login into other computer

SLURM: job scheduler, there are different ones and all have different commands, SLURM is free, EMBL uses it

scontrol: show nodes

srun *script*: submits job to cluster

sbatch *script*: submits job but runs in background, to get output ls und nach datei suchen

squeue: checks jobs

sbatch --mem=250: memory hochsetzen, is done in megabytes

sbatch --output=memory.txt: speichert output in memory.txt


#### Snakemake

rulebased: as long as you can it in the shell you can use snakemake

1. rule: every rule has an input and an output, magic happens inbetween

if the magic fails, it delets the output, because we don't want to have corrupted files, then stops


makes a dependency tree, e.g. Schnitzelessen
- Schnitzel
- Salat

if something goes wrong on one branch, it still keeps the rest of the branches

wildcard rules can never be run alone






