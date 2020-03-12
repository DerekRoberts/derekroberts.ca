---
title: Creating Aliases with .bashrc
date: "2014-01-04T01:06"
description: "Want to be able to launch several commands at once or at least shorten some already esiting commands?  We can do that by creating aliases.  I like to use nano, but any text editor will do."
---

![bashrc](https://lh4.googleusercontent.com/2VHGxTAkwSF3Z8RCMagt9JdSdE6TFxZk8ynVb1qYlHY=w966-h428-no)

Using Kubuntu 13.10 x64 and OS X 10.9.

Want to be able to launch several commands at once or at least shorten some already esiting commands? We can do that by creating aliases. I like to use nano, but any text editor will do.

###[**OPTIONAL**] Install nano###

Ubuntu

<pre><code>sudo apt-get install nano
</code></pre>

OS X installs nano with [Xcode](https://developer.apple.com/xcode/).

Here we're editing .bashrc with nano, but keep in mind it won't be pre-installed on all systems.

###Edit .bashrc or .bash_profile###
Ubuntu. Edit/create .bashrc.

<pre><code>nano .bashrc
</code></pre>

OS X. Edit/create .bash_profile.

<pre><code>nano .bashrc
</code></pre>

Go to the bottom of the file and create commands of this form.

<pre><code>alias **ALIAS_NAME**='**COMMAND#1** ; **COMMAND#2**; ... ; **COMMAND#n**'
</code></pre>

Save (crtl+o) and exit (ctrl+x). You'll have to close and reopen the terminal window for this to take effect, but afterwards all those commands will be available just by typing that alias!

[**EXAMPLE**] Update your Ghost blog on OpenShift. This is useful if you came over from my [Ghost/OpenShift](http://www.derekroberts.ca/in-progress-setting-up-a-blog-with-ghost-on-openshift/) post. Add the following to your .bashrc so updating your site is as easy as typing rhc-up! Please make sure to run it from your ghost app directory.

<pre><code>alias rhc-up = 'clear ; git add --all . ; git commit -m '$(date +%Y-%m-%d)@$(date '+%H:%M')' ; git push ; rhc app restart'
</code></pre>

The command has been tweaked to name all commits with the date and time. The entire update and app restart will take up to five minutes, for which time your site will be offline.

[**EXAMPLE**] Run all available updates by typing 'update'. Add this to the end of your .bashrc file.

<pre><code>alias update = 'sudo apt-get update ; sudo apt-get upgrade -y ; sudo apt-get dist-upgrade -y'
</code></pre>

<br>That's it, so enjoy! :D
