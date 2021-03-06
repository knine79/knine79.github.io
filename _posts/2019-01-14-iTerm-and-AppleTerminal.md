---
title: A Tip to use both Apple Terminal and iTerm
date: 2019-01-14 14:24:28 +0900
---

I set up iTerm and zsh last week on my Mac and I was totally satisfied with it except for one thing.
(Set-up referenced [https://beomi.github.io/2017/07/07/Beautify-ZSH/](https://beomi.github.io/2017/07/07/Beautify-ZSH/), [https://wayhome25.github.io/etc/2017/03/12/zsh-alias/](https://wayhome25.github.io/etc/2017/03/12/zsh-alias/))

# Problem
That is a slightly ugly color on Apple Terminal against iTerm.
Because Apple Terminal supports only 256 colors. So I wanted to use bash on Apple Terminal.
![](/assets/compare-color.png)

# How to Solve
So I added following lines in `~/.zshrc` file.
```bash
if [ $TERM_PROGRAM != "iTerm.app" ]; then
  bash
fi
```
It means 'Execute bash shell when terminal is not iTerm'.

Ok, pretty terminal is back.:heart_eyes:
![](/assets/pretty-terminal.png)

But this solution causes a troublesome problem.
It causes alert like below when closing window.:disappointed_relieved:
![](/assets/alert-on-close.png)
It's because of bash we make execute when launching terminal window.

So I tried to find some proper property on Apple Terminal preferences.
And fortunately found it.:kissing_heart:
I can configure to `Ask before closing`, `Only if there are processes other than the login shell and:` **bash** like following:
![](/assets/configure.png)

# Note
In fact, I wanted to branch off at the point where I started running the shell(zsh or bash). But I could not find the shell starting point. I think somebody may knows. Then I hope to let me know.
