---
layout: article
title: A Tip to use both Apple Terminal and iTerm
tag: iTerm, zsh, AppleTerminal, bash
mode: immersive
header:
  theme: dark
article_header:
  type: overlay
  theme: dark
  background_color: '#203028'
  background_image:
    gradient: 'linear-gradient(135deg, rgba(34, 139, 87 , .4), rgba(139, 34, 139, .4))'
---

I set up iTerm and zsh last week on my Mac and I was totally satisfied with it except for one thing.<br>
(Set-up referenced [https://beomi.github.io/2017/07/07/Beautify-ZSH/](https://beomi.github.io/2017/07/07/Beautify-ZSH/), [https://wayhome25.github.io/etc/2017/03/12/zsh-alias/](https://wayhome25.github.io/etc/2017/03/12/zsh-alias/))

# Problem
That is a slightly ugly color on Apple Terminal against iTerm.<br>
Because Apple Terminal supports only 256 colors. So I wanted to use bash on Apple Terminal.<p>
![](/_posts/images/compare-color.png)

# How to Solve
So I added following lines in `~/.zshrc` file.
```bash
if [ $TERM_PROGRAM != "iTerm.app" ]; then
  bash
fi
```
It means 'Excute bash shell when terminal is not iTerm'.

Ok, pretty terminal is back.:heart_eyes:<br>
![](/_posts/images/pretty-terminal.png)

But this solution causes a troublesome problem.<br>
It causes alert like below when closing window.:disappointed_relieved:<br>
![](/_posts/images/alert-on-close.png)
It's because of bash we make execute when launching terminal window.

So I tryed to find some proper property on Apple Terminal preferences.<br>
And fortunatedly found it.:kissing_heart:<br>
I can configure to `Ask before closing`, `Only if there are processes other than the login shell and:` **bash** like following:<br>
![](/_posts/images/configure.png)

# Note
In fact, I wanted to branch off at the point where I started running the shell(zsh or bash). But I could not find the shell starting point. I think somebody may knows. Then I hope to let me know.
