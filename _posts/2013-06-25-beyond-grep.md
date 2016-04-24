---
title: "Beyond Grep"
category : tools
tags : [utilities,perl,ack]
---

### Ack!

What is [Ack!](http://beyondgrep.com) you ask? As the site describes it is a tool like grep, but optimized for programmers. It has become my go to tool for searching any amount of text data, be it source code, gobs of xml configuration, or just my text file notes. There are a few reasons for this.

<!--more-->
Ack is:

  1. Fast
  1. Smart
  1. Works pretty much on every system
  1. Extensible
  1. Open Source
  1. Written in Perl

Ack is super fast, partly because it's smart. It knows to search only the files that make sense. First it ignores version control system directories, like .git, .svn, .cvs etc. Usually one doesn't care about results in there. Second it only searches text files, so no need to worry about excluding so files or other binaries from your text based search. Third, it allows you fine grain what files it searches with it's type system.

Say you want to search all the js and php files in a large project all you run is the following:

    $> ack --js --php 'search terms here'

At first your search terms will be just words or text you are looking for, but this is just scratching the surface of my favorite feature. Since ack is written in Perl, it accepts all the Perl regex syntax for 'search terms here'. This may sound like over kill until you need to find all references to loader in code, but not downloader or uploader. Try that in your favorite IDE and then try the following ack command. It will return all results of loader, but not uploader or downloader in all the php or js files.

    $> ack --php --js '(?<!up)(?<!down)loader'

Thanks Regular Expressions!

![XKCD comic showing someone using Perl regular expressions to save the day](http://imgs.xkcd.com/comics/regular_expressions.png)
-Credit [XKCD](http://xkcd.com/208/)

Ack is also very extensible with it's use of system, user, and directory level ackrc files. The latter of these are called project ackrc files in the documentation. You can easily chnage any and all the defaults, and have different settings depending on the project. For example I found I was searching --php and --js a lot for a current project. Since I was mostly concerned with .phtml files I added the following line to my ~/.ackrc file.

    --type-add=phtml:ext:phtml,js

Now I can run the following which will return all instances of 'showLoader: true' or 'showLoader: false' in any of the phtml or js files. Wow has this saved me a lot of time on a refactoring project I am working on. It would have taken me ages longer to search for all such instances in the code with an IDE, at least any of the one's I've used.

    $> ack --phtml 'showLoader\s*:\s*(?:true|false)'

This tool has saved me so much trouble, to top it all it's open source, so anyone can help make it better, written in Perl by far the best language for something like this, and easy to get installed.

    $> cpanm App::Ack
    $> brew install ack
    $> yum install ack

And if package managers and Perl are not your thing just download the standalone script, all you need to run it is a base install of Perl, which pretty much every Linux & Mac computer come with, and is trivial to install on Windows. For the latter see [cygwin](http://cygwin.com), or [Strawberry Perl](http://strawberryperl.com/)

To get involved join one of the [mailing lists](http://beyondgrep.com/community/) or fork the [code](https://github.com/petdance/ack2) and contribute. I'm finally getting around to giving that a try for the first time. Hoping I can contribute some thing helpful to a utility that has become so critical to my development toolbox.  

    $> ack --thpppt
    _   /|
    \'o.O'
    =(___)=
       U    ack --thpppt!

I'll leave it for you to run the below ;)

    $> ack --bar
