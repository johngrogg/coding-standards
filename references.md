# References

## References & Useful Tutorials/Documentation
- [Golang](https://golang.org/)
- [Visual Studio Code cross-platform text editor](https://code.visualstudio.com/)
- [Git Actions Visualizer](https://onlywei.github.io/explain-git-with-d3/)
- [Spectacles Window Management App for macOS](https://www.spectacleapp.com/)

## Useful Git Tools
WIP/UnWIP aliases: add the following to your `~/.gitconfig` file.
```
[alias]
    wip = !git add -N . && git commit -am WIP
    unwip = !git log -1 --oneline | grep WIP > /dev/null && git reset --soft @^ && git reset .
```

Install https://github.com/pivotal/git_scripts and then add a `~/.pairs` file in the following format. Note, if you are using SourceTree, be sure to turn off the “Allow SourceTree to modify your global Mercurial and Git configuration files” setting.
```
# .pairs - configuration for 'git pair'
pairs:
  # <initials>: <Firstname> <Lastname>[; <email-id>]
  jg: John Grogg; john.grogg
  mk: Michael Kero; michael.kero
  as: Andrew Salveson; andrew.salveson
email:
  prefix: pair
  domain: wework.co
  no_solo_prefix: true
global: true  # Set to true for git-pair to change git configuration for all your projects
```

## Useful Visual Studio Code Packages and Settings
- [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Partial Diff](https://marketplace.visualstudio.com/items?itemName=ryu1kn.partial-diff)
- [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify)
- [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Project Manager](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)