---
title: "Do Some Things In Clojure"
category : languages
tags : [languages,clojure]
---

### Getting things done and some hobbit violence

Chapter 3 is meatier than the previous one, honestly I skipped chapter 2 as I have no desire to learn emacs. But we jump in quickly to getting enough syntax under our belts to accomplish meaningful tasks. During the first half of the chapter you really get a good feel for the basics, and I'm feeling much more comfortable with the basic style and syntax of Clojure, and feel like it's a little less mysterious. In this article I wanted to write about some of the more interesting aspects, at least to me.

<!--more-->

## Basic Syntax

I know I've seen Clojure before, and some Lisp too, but I don't recall it looking so foreign. I was first linked to the book [Brave Clojure](http://www.braveclojure.com/) it was to chapter 5 on functional programming, but the strangeness of the Clojure syntax made it hard for me to follow. That was part of the driving force to get to learning Clojure was to go through the book. Main take away is lots of parenthesis.

## Recursion

The most fascinating thing to me is the built in recursion. I've always enjoyed recursive programming for many reasons, for example it is usually more concise way of expressing certain types of algorithms. I also met some programmers who shy away from it since they see it as more complex. However, in Clojure it seems that for loops have been foregone in favor of only recursion. The loop syntax at least in this example provides it's functionality via recursion. I suppose as having a purely functional language loops would have to implement looping this way, especially to remain consistently functional.

