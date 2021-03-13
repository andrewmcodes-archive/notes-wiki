# Fixing-Yarn-Global-Commands

I use Yarn to manage my node dependencies instead of npm, mostly because Rails chose it and it was much faster. To be fair, npm has improved since I first made my decision ([the release npm 7 supposedly had some really nice performance enhancements](https://github.blog/2021-02-02-npm-7-is-now-generally-available/) :tada:) but I'm pretty happy with yarn at this point and it is still what the Rails team recommends.

However, where I deviated on my love for yarn was when it came to globally installing packages. For some reason, global installs via yarn never seemed to produce an executable, whereas npm did. I hadn't been able to figure out the reason and I honestly didn't care, I just always globally installed packages via npm.

To illustrate what I mean, I will use
```
npm install -g terminalizer
```
