+++
title = "c. Exercises I"
weight = 2
chapter = false
+++

#### Exploring More `ls` Flags

You can also use two options at the same time. What does the command `ls` do when used 
with the `-l` option? What about if you use both the `-l` and the `-h` option?

Some of its output is about properties that we do not cover in this lesson (such
as file permissions and ownership), but the rest should be useful
nevertheless.

{{%expand "Solution" %}}The `-l` option makes `ls` use a **l**ong listing format, showing not only
the file/directory names but also additional information, such as the file size
and the time of its last modification. If you use both the `-h` option and the `-l` option,
this makes the file size '**h**uman readable', i.e. displaying something like `5.3K`
instead of `5369`.{{% /expand%}}


#### Listing in Reverse Chronological Order

By default, `ls` lists the contents of a directory in alphabetical
order by name. The command `ls -t` lists items by time of last
change instead of alphabetically. The command `ls -r` lists the
contents of a directory in reverse order.
Which file is displayed last when you combine the `-t` and `-r` flags?
**Hint:** You may need to use the `-l` flag to see the
last changed dates.

{{%expand "Solution" %}}
The most recently changed file is listed last when using `-rt`. This
can be very useful for finding your most recent edits or checking to
see if a new output file was written.{{% /expand%}}
