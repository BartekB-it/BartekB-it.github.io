[Go back](..)

So you want to see what's inside of a file, huh?

Say no more.

The easiest method is to use `cat [path/file]`. The thing with this method is that it gives you the whole file - everything goes right into your terminal.

That's why most people do not use the command.

(I personally use it only, if I am sure that the file is small enough to not overwhelm my terminal)

If you want to just make sure what could be in the file, there is much more useful command: `head [path/file]`. It'll show you first 10 lines of the file.

If you want to see more lines (but still not the whole file at once) you can use `head -[number-of-lines] [path/file]`. So if you want to see *67 lines* you can use `head -67 [path/file]`.

On the other hand, you would want to check the end of a file - for that task you can use `tail [path/file]`. Same as the "head" - it gives you 10 lines, just from the end of the file. Adding a number (e.g. `tail -67 [path/file]`) gives you 67 lines from the end of the file.

Okay, but what if you want to have every line numbered, so it is easier to find a specific line later? Worry not, I got you. There's `nl [path/file]` method that lets you number every not empty line of a file. Especially useful for writing scripts or searching a file for a specific line (more on that in a second).

...

A second passed, so now I can explain.

Meet your best companion, your sword, your shinigami, and your best tool - a tool that will be used far more than all the other commands (allegedly).

Meet `grep`.

To be more specific - meet `grep -n "[pattern]" [path/file]`.

It let's you look for a specific pattern in a file, and also (thanks to the -n attribute) it numberes the lines where the pattern is found.

The output of a file you see in the terminal can be done with another method, when you combine `grep` with "a pipe".

Piping helps you use an output of one command, and use it as an argument for another command.

(BTW - if you've never seen a pipe, look at this: "\|". Pretty cool, huh?)

So the same (well, actually a very simmilar) output as `grep -n [pattern] [path/file]` can be achieved with:

`cat [path/file] \| grep -n [pattern]`

OR

`nl [path/file] \| grep [pattern]`.

(If you do not want the lines numbered, you can always use grep like this: `cat [path/file] \| grep [pattern]`)

Okay, so you are writing a pretty long script and you need to change one word for another. Sounds pretty easy, right?

But what if the file is pretty big and there are 10+ instances of the word hidden throught the file? Again - don't worry, I got you.

`sed s/[old-word]/[new-word]/g" [old-path/old-file] > [new-path-new-file]`

Okay, looks like a bit much, but most of it makes sense, right? (Right???)

But what does the "s" and the "g" mean?

The "s" is for the substitute - pretty self explanatory. It all works like that because of the "s".

So what's going on with the "g".

It stands for global: you change every instance of the word.

You can change it for a number to change the [number]th occurence of the word.

You can also leave it blank instead of the "g" to change the first occurance of the word.

As we are coming to an end of this article, I have to more commands, that make looking at the insides of a file much more pleasant.

`more [path/file]` shows you the file in your terminal, but one page at a time - you can click "space" to see another page, "enter" to go down by a line, and clicking upper arrow lets you go back by a page.

Sounds insanely convenient, right?

Well, look what's next (personally, my favourite command to look through a file):

`less [path/file]` works exactly as "more", but you can click "/", write a word/phrase you are looking for, and click "enter". It goes straight to the first occurence. If you want to see a next occurence, you just click "n" (next).

That's it folks. Now's the time to mess around in your terminal using the commands you've just learned. Enjoy!
