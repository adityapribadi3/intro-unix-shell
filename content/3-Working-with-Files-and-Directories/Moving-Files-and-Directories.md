+++
title = "c. Moving Files and Directories"
weight = 2
chapter = false
+++


Returning to the `shell-lesson-data` directory,

```Bash
cd ~/Desktop/shell-lesson-data/
```

In our `thesis` directory we have a file `draft.txt`
which isn't a particularly informative name,
so let's change the file's name using `mv`,
which is short for 'move':

```Bash
$ mv thesis/draft.txt thesis/quotes.txt
```

The first argument tells `mv` what we're 'moving',
while the second is where it's to go. In this case,
we're moving `thesis/draft.txt` to `thesis/quotes.txt`,
which has the same effect as renaming the file.
Sure enough, `ls` shows us that `thesis` now contains one 
file called `quotes.txt`:

```Bash
$ ls thesis
```

~~~
quotes.txt
~~~


One must be careful when specifying the target file name, since `mv` will
silently overwrite any existing file with the same name, which could
lead to data loss. An additional option, `mv -i` (or `mv --interactive`),
can be used to make `mv` ask you for confirmation before overwriting.

Note that `mv` also works on directories.

Let's move `quotes.txt` into the current working directory.
We use `mv` once again, but this time we'll use just the name 
of a directory as the second argument to tell `mv` that we want 
to keep the filename but put the file somewhere new. (This is why the 
command is called 'move'.) In this case, the directory name we use is the 
special directory name`.` that we mentioned earlier.

```Bash
$ mv thesis/quotes.txt .
```

The effect is to move the file from the directory it was in to the current working directory.
`ls` now shows us that `thesis` is empty:

```Bash
$ ls thesis
```

~~~
$
~~~


Alternatively, we can confirm the file `quotes.txt` is no longer present in the `thesis` directory
by explicitly trying to list it:

```Bash
$ ls thesis/quotes.txt
```

```
ls: cannot access 'thesis/quotes.txt': No such file or directory
```

`ls` with a filename or directory as an argument only lists the requested file or directory.
If the file given as the argument doesn't exist, the shell returns an error as we saw above.
We can use this to see that `quotes.txt` is now present in our current directory:

```Bash
$ ls quotes.txt
```

~~~
quotes.txt
~~~


## Exercise: Moving Files to a new folder

After running the following commands,
Jamie realizes that she put the files `sucrose.dat` and `maltose.dat` into the wrong folder.
The files should have been placed in the `raw` folder.

```Bash
$ ls -F
 analyzed/ raw/
$ ls -F analyzed
fructose.dat glucose.dat maltose.dat sucrose.dat
$ cd analyzed
```

Fill in the blanks to move these files to the `raw/` folder
(i.e. the one she forgot to put them in)

```Bash
$ mv sucrose.dat maltose.dat ____/____
```
{{%expand "Solution" %}}
```Bash
$ mv sucrose.dat maltose.dat ../raw
```
Recall that `..` refers to the parent directory (i.e. one above the current directory)
and that `.` refers to the current directory.
{{% /expand %}}
