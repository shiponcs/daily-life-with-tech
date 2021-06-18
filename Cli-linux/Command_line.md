

[TOC]





# Linux

Linux is Unix-like operating system. But these two are not the same. Linux is something that ***Linus Trovalds*** did by himself when he tries to make an alternative to Unix as it was not free and hence not accessible to everyone. Linux was heavily inspired by Unix without being Unix, that's why most the things are common.  

But the big part of the Unix's popularity is its Philosophy. 

Two strong branches of **Unix** are **BSD** ( **MacOS** is a downstream of this) and **GNU** (**Linux** is a downstream of this).

Again, Linux is not Unix. These two terms shouldn't be used interchangeably *because their codebase are not same*. Linux can be said ''*Linus Trovalds'* own version **Unix**" and also branched off in his own direction. 

### Why Linux

Read This: https://btholt.github.io/complete-intro-to-linux-and-the-cli/what-is-linux#why-linux

### Ubuntu

It's a downstream of [Debian](https://www.debian.org/)

### How to run Linux

1. Through VM box (Virtualization)
2. Install it as your OS
3. [Multipass](https://multipass.run/), if you're windows home user you have to install VM Box along with this
4. [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10#update-to-wsl-2) (great option if you're using windows)

# Anatomy of CLI command

The *command line* is often called **REPL**, **R**ead **E**valuate **P**rint **L**oop, which is interactive way programming. Just like what you do in case of running **python** in command line i.e. you write one line command feeding data. In case of **Command Line** you do Shell programming. Command line is so powerful that you can everything what you can do with a desktop. 

### How CLI Command or REPL works

> Your shell is running inside some sort of emulator. That emulator could be Terminal.app or iTerm2 if you're on macOS, or it could be the Windows Terminal if you're on Windows 10. This the window that's containing the shell, and you can use that emulator to switch out what shell is running inside of it. For now we want to be on bash (or zsh is basically the same too.) - [Link](https://btholt.github.io/complete-intro-to-linux-and-the-cli/anatomy-of-a-cli-command#shells-and-emulators)

### Shells and Emulators

Some other shells beside Bash: zsh, ash, PowerShell, cmd.exe., fish shell

The shell run inside the emulator like Terminal.app, iTerm2, Windows Terminal, 

### CLI Directories and Arguments

1. **pwd** - *print working directory*
2. **cd** - *Change Directory*
3. **ls** - *list*
4. **echo** - *print*
5. **which**  - *where something lives*

### Flags

Telling the modes how a command should be ran

1. **`--help`** tells the command to run in *helping mode*

2. **`-l`** means long

3. **`-a`** or **`--a`** show me everything- *hidden files*

4. **`-lsah`** combines 4 flags

   

   

   **`--`** (double dashes) are long form, and **`-`**(single dash) is short hand, the reason **`-`**(single dash) exists is that it provides handy way to combine the flags. like- 

   `ls -a -l` can be rewritten as `ls -al`



### CLI search

`matin@DESKTOP-77KDFRO:/mnt/c/Users/admat$` In this command, everything before `$` is called **prompt** and the path after the `:` is your working directory

**Tilda**(`~` )in bash represents ***user's home directory***. Hence `cd ~` will move your working directory to *home directory*.

**Slash** **`/`** means ***root***

Don't forget your **up and down keys**. It cycles through history of the command that you've run. Which means all of your commands are being stored on your Computer. So, be careful when you put your *password* into any command, unless that will be a bad thing because anyone that can see your **bash history** can see your **password**. That can happen in multi-user server. It's possible to modify bash history.

### Tab Completion

Write as few letters as one and press **Tab** bash will complete that for you. 

> Most shells have a relatively robust tab completion system. When I say "tab completion" I mean you start typing something and hit the tab key, the shell will do its best to figure out what you're trying type. An example would be if I'm in a directory with two files, index.html and package.json, and I start typing `cat i` and hit tab, it will know the only file starting with `i` is index.html and will autocomplete your line to `cat index.html`. Saves you a lot of typing.
>
> For another example, imagine you have two files in a folder, index.html and index.js. If you start typing `cat` and hit tab, it'll complete out to `cat index.` because that's as far it can get without assuming which file you want to open. If you hit tab again, it should show you your two options. If you then hit `j` and hit tab it'll complete out `cat index.js` for you.
>
> Some commands are smart enough to know what sort of thing you're looking for. If you have two files, saved.txt and something-else.txt, and a folder called src, if you type `cd s` and hit tab, you'll autocomplete `cd src` because the shell knows you're looking for a folder when you're using `cd`.
>
> Tab completion will always work with the file system. Some commands have tab completion too. Type `git de` and hit tab and it should complete to `git describe` for example. Admittedly I use this far less because I can never remember which commands have tab completion and which don't. The individual programs have to supply that to the shell for it to work.

As for any particular **program** it's totally up to the program to provide the **tab completion**. The program has to provide **bash** with the tab completion so that the bash can support it.

### Reverse Bash history

Press `Ctrl + R`a and start searching, type `Ctrl + R`  repeatedly if want to see further old commands same keyword. And hit `Enter`, that particular command would run.

### !!

This represents the last command.  If you run`!!` the last command would run. But that's its best use case,  it's used when you want to combine your last command with other. Like: `sudo !!`

### CLI Shortcuts

**CTRL is a player man!**

- `CTRL + A` – takes you to the beginning of the line, `Home` does the same if you have it in your keyboard

- `CTRL + E` – takes you to the end of the line, `End` does the same

- `CTRL + K` – "yank" everything after the cursor

- `CTRL + U` – "yank" everything before the cursor

- `CTRL + Y` - "paste" (paste in quotes because it doesn't actually go into your system clipboard) everything you yanked

- `CTRL + L` - clear the screen

- `CTRL + R` – reverse search through history

  

# Signals

1. **CTRL + C - SIGINT** : **Signal Interrupt**

   This signal to any program means **interrupt** what its doing and **stop**

2. **CTRL + D -  SIGQUIT** : 

   

   > Less useful but still good to know nonetheless is what CTRL + D does. Many programs won't respond to a SIGQUIT (some might, it's up to them) but bash itself will. If you're in a bash prompt and it want it to exit (like if you're remotely connected to a bash server for example), if you hit CTRL + D it'll tell the bash session to end. You also could close the window or just type `exit` and it'll exit too.

   Where **CTRL + C ** doesn't work, for example if you're in **python3** **REPL** it'll not responds to **SIGINT**, here you have to apply **SIGQUIT**

3. **SIGTERM**

   > There is no shortcut for SIGTERM but I wanted to make sure you knew it existed. If I use the `kill` program to kill another program, the way it does that is by sending a SIGTERM to the program. The difference is that if the program doesn't exit, kill will still shut down the process. We'll talk later about `kill` but know it's there.

   It's typically your computer that sends **SIGTERM** signal to programs for example when the computer is shutting down it sends this signal to every running program to make them know that the OS is shutting down and it's their time to do their last job. 

4. **SIGKILL**

   It's like assassinating the program. 

   > If you want a program to stop and stop **now**, you can do `kill -9` (or `kill -SIGKILL`) and it will send the SIGKILL which means to the program "don't clean up, just stop as soon as possible.) 

   

# Editors

***"The tool is as good as the master using it"***

## nano

It's a very small and old editor that you'll find in any **unix-like system** and like many other programs it's also maintained by **GNU Project**. It's based on **[Pico](https://en.wikipedia.org/wiki/Pico_(text_editor))**, a text editor integrated with the [Pine e-mail client](https://en.wikipedia.org/wiki/Pine_(email_client)). There was reason and history about how and why Pico was rewritten in **nano**, read it:

> Because Pine was licensed in such a way that Debian wouldn't include it with its distro, Chris Allegretta re-implemented under the name TIP (**T**ip **I**sn't **P**ico, computer scientists love [recursive acronyms](https://en.wikipedia.org/wiki/Recursive_acronym)) it eventually was renamed to nano.
>
> Due its tiny size, light weight, and permissive license, nano is included on just about every Linux/Unix-like OS and is frequently the default text editor, even on tiny little embedded devices where even vim is too much. As such, it's a good tool to have your tool belt if you need to do some light text editing.
>
>  - [source](https://btholt.github.io/complete-intro-to-linux-and-the-cli/nano#nano)

> [GNU](https://en.wikipedia.org/wiki/GNU) nano was first created in 1999 with the name *TIP* (a [recursive acronym](https://en.wikipedia.org/wiki/Recursive_acronym) for *TIP Isn't Pico*), by Chris Allegretta. His motivation was to create a free software replacement for Pico, which was not distributed under a [free software license](https://en.wikipedia.org/wiki/Free_software_license). The name was changed to nano on January 10th, 2000 to avoid a naming conflict with the existing Unix utility *[tip](https://en.wikipedia.org/wiki/Tip_(unix_utility))*. The name comes from the system of [SI prefixes](https://en.wikipedia.org/wiki/SI_prefix), in which [nano](https://en.wikipedia.org/wiki/Nano-) is 1000 times larger than [pico](https://en.wikipedia.org/wiki/Pico-). In February 2001, nano became a part of the [GNU Project](https://en.wikipedia.org/wiki/GNU_Project).
>
> GNU nano implements several features that Pico lacks, including [syntax highlighting](https://en.wikipedia.org/wiki/Syntax_highlighting), line numbers, [regular expression](https://en.wikipedia.org/wiki/Regular_expression) search and replace, line-by-line scrolling, multiple buffers, indenting groups of lines, rebindable key support,[[6\]](https://en.wikipedia.org/wiki/GNU_nano#cite_note-6) and the undoing and redoing of edit changes.[[7\]](https://en.wikipedia.org/wiki/GNU_nano#cite_note-7)  -[source](https://en.wikipedia.org/wiki/GNU_nano)



## vim

 It has long history 

So copied and pasted the text down below:

Dare I say this is the most polarizing text editor of all time. People either will die on a hill protecting its glory or love to rag on how difficult it is to use. I think they're both right to some degree. People who learn vim very well can achieve less friction between their intent and their tool which will make you very productive. However the sort of time you have to invest into your tool to achieve that is on the order of years. If you want to spend years mastering it and customizing it to your perfection, this is the tool for you. In any case, I have elected not to; I love VSCode for its useful middleground of approachable and powerful and for its incredible ecosystem of plugins.

vim has a long history but let's take a brief look at it. The genesis of the ideas that went into vim started with an editor called [ed](https://en.wikipedia.org/wiki/Ed_(text_editor)) (said ee-dee) which itself was inspired by a previous editor called [qed](https://en.wikipedia.org/wiki/QED_(text_editor)). ed was developed by Ken Thompson at Bell Labs in 1969. It is a line-oriented editor and I have no clue how to use it. It's actually rather well known for being pretty user unfriendly. In spite of this, it's still available on most Unix-like systems including Ubuntu and macOS. If you do start it, just know it's CTRL+D a few times to quit it. It's important to note that ed was created in a time where memory was precious, screens were tiny and sometimes just one line at a time, and modems were measured in bits, not even kilobits. It arose at a time when it fit its constraints.

From ed we got [ex](https://en.wikipedia.org/wiki/Ex_(text_editor)) (short for extended). ex was still one of these line editors but it had a nicer face on it and made a bit more friendly. ex itself learned a lot from two previous iterations, en and em. From there, Bill Joy made a screen-oriented mode (as opposed to a line-oriented one) for ex that he called vi (short just for visual). Eventually this became the dominant face of ex so much that vi became the name of the program and ex became a mode inside of vi. To this day ex mode is available in vi and vim. If you run the `ex` program from Ubuntu or macOS, it just opens vim.

And now we arrive to vim iteslf. Tim Thompson made a vi clone for the Atari ST called Stevie that Bram Moolenaar then ported to the Amiga. Bram called this Vi IMitation but later that was change to Vi IMproved. With vim, they made a bunch of quality-of-life improvements and made the product much easier to use to the point that people rarely use vi directly anymore and just use vim. If you run `vi` on macOS or Ubuntu it just runs vim.

That's probably more history than you wanted but I always found the tale fascinating. It wonderfully demonstrates how our industry progresses. The editor I work on, Visual Studio Code, owes a lot of its core ideas to vim, nano, and all the editors before them. - [From](https://btholt.github.io/complete-intro-to-linux-and-the-cli/vim)

**And consider writing `vimtutor` in your shell or `:help tutor` in vim** command 



# Interacting with files

### less; a terminal pager

**less** is for reading a file. `less <file-name>` would open the file in command line in reading mode. Hit `q` for quitting.  It has lots of features and shortcuts like **vim**. It's really great to read long files. Some of its cool features:

```bash
                      SEARCHING(copied form less help doc)
```

```bash
  /pattern          *  Search forward for (N-th) matching line.
  ?pattern          *  Search backward for (N-th) matching line.
  n                 *  Repeat previous search (for N-th occurrence).
  N                 *  Repeat previous search in reverse direction.
  ESC-n             *  Repeat previous search, spanning files.
  ESC-N             *  Repeat previous search, reverse dir. & spanning files.
  ESC-u             *  Undo (toggle) search highlighting.
  &pattern          *  Display only matching lines
```

There a older program of **less** which is **more**. Naming convention of the Computer Scientist is awesome. Ha?

### man

It stand for **Manual**. And it's used to show the manual of  programs. For example `man less` would show the **General Command Manual** for **less**. So, under-the -hood it uses a file reader, fortunately **less**. So everything you know about **less** is applied for **man**. 

But I go for `--help` to learn about the commands available for a particular program because it's summarized and I'm not good at reading lots of lines. On the other hand, manual is so long and depth i.e. it contains everything about the program. Yet, if I'm not wrong you still consider googling what you need instead of reading the whole informative manual page. And yes it's helpful if you don't have internet at any moment. :happy:

N.B: Some programs don't have man page. 



### head / tail

If you need something descriptive like a few lines from the beginning or ending of a file, then here have head / tail for you. 

```bash
head <file-name>
tail <file-name>
```

By default head and tail output 10 lines but you can put parameters to print some specific number of lines like- `head -n 5 myfile.txt` woul output first 5 lines from the file `myfile.txt`.



### Some tricks to keep a file open in terminal to see live update

1. Using **-f** (which stands for follow)  flag in tail / head command

   open the file with this command `tail -f <file-name>` and append some texts to the file from another tab of the terminal app using the command `echo <some-texts> >> file-name`. You will see the update real time.

   But here I've something interseting to teach you. I edit the same file  using any editor then you will not see the update real-time. Why? I asked the question  [here](https://superuser.com/questions/1649921/tail-f-is-not-showing-the-update-of-the-file-when-edited-form-editor/1649934#1649934), read that. But to summarize:

   `tail -f <file-name>` by defaults follow the descriptor. To make it to follow file name write- `tail --follow=name <fie-name>`.

   You may like reading these relevant questions' answer: 

   [tail -f, but when the file is deleted and re-created (not appended)](https://unix.stackexchange.com/questions/410471/tail-f-but-when-the-file-is-deleted-and-re-created-not-appended)

   https://unix.stackexchange.com/questions/18258/file-descriptor-vs-file-name



### mkdir

I creates a new directory. `mkdir new-folder`.

If you want to create nested(multiple) directories you need to pass `-p` option for it to happen.

```bash
mkdir -p new-folder/new-child-folder
```

```
 -p, --parents     no error if existing, make parent directories as needed
```

which means if parent directories doesn't exist, create it first then creates its child directories.



### rm

It stands for **remove**, but it removes files by default. `rm myfile` .

To remove director you need to run `rm -r my-folder-that-contains-garbage`, here `-r` stands for **recursive**-  remove directories and their contents recursively. Another option is `-f` stands for **force**-  ignore nonexistent files and arguments, never prompt. But it requires huge caution. Because, `rm -rf` can ruin your whole system. Because when you `rm`'d something, it doesn't go to trash, it's just gone.

If you want to destroy your/others' whole system, `rm -rf / ` is enough to do so. If you want be 200% carefull you may consider using [trash-cli](https://github.com/andreafrancia/trash-cli). That way, you can trash something before deleting.



### cp  

It stands for copy  paste. If you want copy the content of one file and past it to another file run: `cp one-file.txt another-file.txt`. 

You can even copy a file to another directory keeping the name same in this way: `cp myfile.txt another-directory/`.

` -R, -r, --recursive          copy directories recursively` this is a great option when you need to copy a whole folder and everthing in it.

### mv

mv stands for move. This how you move a file from one place to another, or how you rename a file (which is still moving it in some sense.) Try running `touch file.txt` then `mv file.txt new-name.txt`.

Unlike cp, with mv you don't to do anything special to move a folder. Just do `mv folder-name new-folder-name` and it all works.



### tar

It's short for **tape archive**. In many cases we need to group many files into a single file(which we call [**archive** file](https://en.wikipedia.org/wiki/Archive_file))and even compress to move them from one device to another for example when we need to upload bunch files to any server computer. Tar archive is called tarball,a jargon term.

Let's assume we have a file called  textfile.txta and a folder containing three files file1.txt file2.txt file3.txt. And first we want to archive them to a single file called archive.tar:

```bash
tar -cf archive.tar folder/ textfile.txt
```

`-c` option tells tar to create. `-f` option tells tar that the next argument is the file name of the archive else the output will be passed to output. 

Now it's time to see how we can unpack/extract the file:

```bash
tar -xf archive.tar #-x means extract.
```



 If you run this command it would extract the file to your current working directory. But you may need to set the destination to antother folder. Here we need

```bash
 -C, --directory=DIR
              Change to DIR before performing any operations.  This option
              is order-sensitive, i.e. it affects all options that follow.
```

Command: 

```bash
tar -xf archive.tar -C destination/	
```

However the archive file is not compressed by default, keep that in mind. You need to pass `-z` option to compress.

```bash
tar -zcf archive.tar.gz folder/ textfile.txt 
```

Notice archive.tar.gz is singifcantly smaller than archive.tar.

You may notice if you tried to pass the flags in a different way that the order of the parameters matter here. Here is a discussion on it: [Does parameter order matter with tar? ](https://unix.stackexchange.com/questions/239118/does-parameter-order-matter-with-tar)

# Wildcards & Replacements

### Wildcards

Let's say we have bunch files that ends with `.txt`, if you want to remove all these files you could run command this way: `rm file1.txt file2.txt file3.txt`, but that's time consuming and very naive especially programmer will try to do these in a smarter way writing less number of letters for command. The problem is, to remove anything that ends in "".txt"?

**Astrisk(*)** is the most common wildcards that represents one or more chracters.

so `rm file*.txt` would remove everything that contains **file** in the beginning and **.txt** as extension (file.txt, file1.txt, file2.txt and so on). But there migh have cases where you may not want to remove **file.txt** but **file1.txt file2.txt file3.txt**, here you have **question mark(?)** which represents a  single character. 

try this

```bash
touch file.txt file1.txt file2.txt
ls file*.txt # prints all
ls file?.txt # all but file.txt
```



Finally you can use `[]` to limit your characters too. Let's say you wanted 1-5. So you could say `ls file[1-5].txt`. Or you can say anything that matches not these characters by saying `ls file[^1-5].txt`

Warning: when you run `rm` command using `*`, don't forget to pass `-i`, as

```bash
  -i                    prompt before every removal
```



### Expansion

Let's assume you want to create three files using touch. You may run:

```bash
touch file.txt
touch file1.txt
touch file2.txt
touch file3.txt
```

But that's annoying, it's better to write:

```bash
touch file{,1,2,3}.txt # first empty character cretes file.txt
touch {obama, trump, biden}-profile.txt
```

:slightly_smiling_face: Even better:

```bash
touch file{0..10}.txt
```

Try some more:

```bash
echo {a..z} # prints a to z
echo {z..a} # reverse order
echo {0..100..2} # prints every other (aka even) number from 0 to 100
echo {100..0..5} # prints every 5th number in reverse order from 100 to 0
echo {a..z}{1..5} # prints out a1 a2 a3 a4 a5 b1 b2 b3 <etc>
```



Know it- it's bash that does all these transaltion of `*`, `?` and `{}` not the programs. So when you say `ls file*.txt`, what `ls` actually ends up getting inputted is `ls file1.txt file2.txt file.txt`. That's important because `ls` doesn't have to support anything, which means this works anywhere in bash. 

Last thing, you may need to make some file like, file?.txt, this time you need to put a escape character (`\`)- `touch file\?.txt`. Escape character is really usefull.

 That's all for now, they may not usefull all the time but they can save you a bunch of time. 



# Streams & Pipes

In Linux, all input and outut(whic are text) are actually streams of data/text. Just like plumbing pipes, you can connect disconnect streams of data to redirect to diferent programs. 

## Standard Streams

There are three standard streams, stdin (said standard input or standard in,) stdout (said standard output or standard out,) and stderr (said standard error or standard err.) stdin is an input stream to a program and the other two are output streams. stdout for all non-error text, the normal output. stderr is just for error information.

### stdout

Stdout is normally where all output normally goes and by default goes to terminal (sterr too).  For example when you run `ls`, it writes the contents of the current directory to the output. And, You see the output in the terminal unless you redirect the output to anywhere else. Now let's see how can we redirect the output:

```bash
ls 1> my-file.txt 
cat my-file.txt
```

Istead of printing the contents in the terminal it redirects the output to the file. But you will see some differences like file formatting and colors between the output in terminal for command `ls` and the content written in the file, my-file.txt. Because, ls is aware if the output is sending to a terminal or not.

Also try

```bash
echo "Hello world" 1> my-file.txt
cat new-file 1> my-another-file.txt

```

The `1>` redirect stdout from heading to the terminal and into a file.

 [Difference between 'ls' and 'echo $(ls)'](https://unix.stackexchange.com/questions/283586/difference-between-ls-and-echo-ls)

#### 1> vs 1>>

1> replaces/overwrites the file but 1>> appends to the file.



### stderr

You also see error message in the terminal but that's different from stdout. To examine this, let's run try this:

```bash
cat non-exiting-file.txt 
# cat: non-exiting-file.txt: No such file or directory
cat non-existing-file.txt 1> error.txt
# cat: non-exiting-file.txt: No such file or directory
```

Last command can't redirect the output to error.txt because, `1>`  redirects **stdout** whereas `cat non-existing-file.txt` generates **stderr**. But you would still see error.txt created because it assumes that something is gonna end up there. 

BTW, now

```bash
cat non-existing-file 2> error.txt
cat error.txt
# cat: non-exiting-file.txt: No such file or directory
```

`2>` redirects the **stderr**.

But in practical use cases, you never know if a comamnd is going to produce **stdout** or **stderr** beforehand so you might have to support both cases-

Redirect **stdout** to one file (say, out.txt) and **stderr** to another file(say err.txt):

```bash
cat non-existing-file.txt 1> out.txt 2> err.txt
```

If any stderr redirects to err.txt, the err.txt file will be overwritten with the errror message, and out.txt will be created if doesn't exist already and will be emptied if it already exists and has any content there.

It has some good answers: [What are the shell's control and redirection operators?](https://unix.stackexchange.com/questions/159513/what-are-the-shells-control-and-redirection-operators)

### /dev/null

Sometimes you want to run a program and you don't really care what the output is; you just want to run the program. Say hello to `/dev/null` which is the programming equivalent of the infinite abyss. Anything that gets output to /dev/null is thrown away. Let's say you're running a program that's very noisy and you really only care if there's an error.

```bash
ls -lsah 1> /dev/null # assume this is a very noisy program
```

This will run the command and only print the errors. Everything else gets chucked into the infinite abyss. Useful sometimes

### stdin

First consider

```bash
ls > ls.txt
```

And, try this

```bash
cat < ls.txt
```

This is similar to `cat ls.txt`, "<'' means feeding the data to the cat program and cat prints whatever it gets.

But let's see some usefull application. let's say `ls.txt` is a very large file and you want to search for a specific line.

```bash
grep "my-file.txt" < ls.txt
```

I used to do that when I was doing Competitve Programming, where I was always required to feed my solution poragram lots of test cases and it's quite impossible to type/copy-paste them everytime.

 

### Using stdin and stdout

What if we want to have both stdin and stdout and then throw away the errors?

```bash
grep "error-log.txt" < ls.txt 1> ls2.txt 2> /dev/null
```

Just like that! Order isn't important.



## Pipes

If you have sensed earlies section, it's tideo tedious to store the output of one program in a file first before feeding into anotherr prorgram. But, pipes (vertical bar, `|`) takes output of one program and puts it into the next one. 

Before leverage that, let's take an easy example:

```bash
ls |  grep "myfile.txt"
```

this is usefull when when ls outputs a long text and you need to find a specific file(with it name). `ls` outputs to the **stdout** and `|` will take the output and run that as **stdin** to **grep** and grep find what we need and prints to stdout and it goes to terminal as we're not redirecting to anywhere else.

Let's assume you have node process running and you want to kill  it. You may run`ps aux`  but finding the process id by reading that long process list is hard. 

This command will make your job easier by finding just what you need and leaving rest behind:

```bash
ps aux | grep node
# or even self referential
ps aux | grep aux
```

This way you get the process id easily.

You have been using Unix-like OS, when you were installing some packages you needed to answer `y`(yes) for each packages, that's really boring, you may consider using pip there. I'm showing a analogous command:

 If you do `rm -i *.txt`, it'll try to remove all files with .txt extensions. It'll all confirm with you on each one to say either y for yes or n for no. Try it and say "n" and hit enter for each one. Notice afterwards you won't have deleted anything.

Lots of Linux programs function this way of answering y or n questions. Someone got sick of doing it and wrote a program to just answer `y` nonstop called `yes`. We looked at this before. But now let's yes it. Let's make it say n to all those questions.

```bash
yes n | rm -i *.txt
```

The first command, `yes n` outputs infinite `n`s to stdout. `rm -i *.txt` uses those from stdin to answer `n` to every question it asks.



# Users, Groups, and Permissions

Linux is inherently multi user system. Not all of them is necessarily human users. Many program will create their own users and groups to keep themeselves separte from userspace.  

## Users

Who you are? Run `whoami` and it'll say who you're. If you're using Multipass it's `ubuntu`, in my case it's `matin`, I gave this name as my username when I was intalling Ubuntu. How many users do you have in your OS? run, `cat /etc/passwd`.  There are lots of users, right. You will see some of the programs like `man` and `mail` have their own separate users. Why? Linux generally adheres to the principle of least power: we want programs to be given the least amount of power possible to complete their tasks. That way if they run amok, either accidentally or maliciously, the amount of damage they can cause is as minimal as possible.

## Superuser

Let's go to `/` directory and try to make a directory there.

```bash
mkdir new-dir
# mkdir: cannot create directory ‘new-dir’: Permission denied
```

Because you can't make any change in root (`/`) directory, only supreuser(also called root user) can. As we have stated Linux gives least permission to the users and rootuser has permission to do anything. So you're thinking to change to rootuser to do what you're wanting to do. Right? You can do that, but it's a terible idea and risky to always run as root. You have another way to achieve this- `sudo`.  

## Sudo

Sudo stands for super user do but it means- change user and do. When you don't tell it to change to what user it changes to rootuser. 

```bash
sudo mkdir file-in-root-dir.txt
```

So when we run a command with sudo, we are actually saying the computer to change to root user and run the command and come out again. Can't believe this? Run it:

```bash
sudo whoami
```



## Groups

Just like we can add and subtract permissions from a user in Linux, we can actually do it for whole cohorts of users using groups. This is useful for many reasons. Let's say you have a server that everyone connects to get documents. You could have one cohort of users that just needs to read / download the documents. In this case, we could make a `readers` group and give them read-only permission to all files. They'll never need to (or be able to) create new files. Now if a hacker gets ahold of their credentials, they can only read files and not wreck your server. And when we add a new user, we just add them to the `readers` group and that's it! If we need to later modify it that `readers` can add files to just one directory, we can easily make that happen by adding write permissions to one directory for the readers. See how this can streamline things?

Some groups has special privileges, like the `sudo` group. These users can now `sudo` whenenver they need to. Let's add our user brian to the sudo group. Run `sudo usermod -aG sudo brian` (or `sudo usermod --append --groups sudo brian` if you want the long form) from the ubuntu account. usermod allows you to modify user accounts and `-aG` allows you to append new groups to the user. In this case, we made it so brian is now a sudoer. Try this now.

```bash
su brian
sudo whoami
```

## chown

Okay, so let's modify some stuff then. Switch back to being the ubuntu user if you're still brian (you can run su ubuntu).

Let's make a directory in the root.

```bash
whoami # should say ubuntu
cd /
mkdir hello # permission denied, you don't have permission to do that here
sudo mkdir hello # works, but now hello is owned by root:root
ls -l # notice hello is owned by root:root
touch hello/text.txt # permission denied, you don't own hello
sudo chown ubuntu:ubuntu hello # it's <group>:<user>
ls -l # notice hello is now owned by ubuntu:ubuntu
touch hello/text.txt # works!
```

This is what chown does! It allows you to reassign ownership (**ch**ange **own**er).

In general this is not something you need to do a ton of but it's occasionally useful.



## chmod

chmod syntax is delightfully obtuse. Did you come in prepared to do some binary-to-decimal math in your head? Because here we go.

So chmod allows you to directly change the permissions of the file rather just changing the owners. So instead saying "now ubuntu can write to this folder insetad of brian" we can say "any person in this ground can read from it" or "everyone on this computer can read from it". Let's do a few examples.

So let's try a few

```bash
whoami # should be ubuntu still
cd ~ # go to home directory
sudo touch secret.txt # make a file as root
ls -l secret.txt # -rw-r--r-- so root can read and write but no one else can
echo "very secret message" >> secret.txt # doesn't work, permission denied
sudo chmod u=rw,g=rw,o=rw secret.txt # make it so anyone can read or write to the file
echo "very secret message" >> secret.txt # works this time!
cat secret.txt # should see very secret message
```

So that's the easy-to-remember chmod syntax. Just use u=rwx syntax (omit things you don't want the permission for.) The `u` is for user, `g` is for group, and `o` is for other or everybody else. The `r` is for read, the `w` is for write, and the `x` is for execute.

Okay, so now for binary. There is a shortcut for doing this with number instead of `u=rwx,<etc>` and it involves binary. Instead of saying `chmod u=rwx,g=rwx,o=rwx file.txt` you can say `chmod 777 file.txt` and those mean the same thing. Why? Because someone was feeling very lazy.

The magic formula is that you can add 4 to the number is you want to add read, add 2 for write, add 1 for executable, and set to 0 if you want zero permissions. Then do that for each and put the numbers in the order of user, group, other. So `chmod 640 secret.txt` would make it read+write for the user, read for the group, and no permission for anyone else. Why do I teach you this? Because you'll see `chmod 777 stuff.txt` out on StackOverflow and it's a bad idea. It's a hack. It makes a file accessibile to anyone and that's a bad idea. Going back to our principle of least power, we just want to grant the minimal permissions possible.

One last one you'll see is the use of `+` and `-`. If you want to make a file executable, you can say `chmod +x secret.txt` and it'll add executable to each of the permissions. As you may imagine `chmod -x secret.txt` takes it away. You can use it with w and r too, just that's not super common to do.

And that's it for permission! There's a lot more to learn here but this is a great start for you.



***The above sections 3 sections namely- Groups, chown, chmod- have been copied from Brian Holt's wrinting.***



# Environment

There are already many variables in your current session set by the system. To see the variables set for you :

```bash
printenv
```

You see a varible named `USER`, that's you. You can use it direclty I mean it's accessible generally. 

```bash 
echo The user is $USER
```

You change the variable's value.

```bash
USER=shipon
```

But this will persist only for this session. 

To set a variable permanently, we have several ways to achieve this. 

Set a varible in `/etc/environment`. You will see there some variables already set by the system. I my case I see the `PATH` variable. But if you're using WSL, it will work, read [here](https://askubuntu.com/questions/1046253/http-proxy-not-showing-up-with-printenv-on-wsl)

 

