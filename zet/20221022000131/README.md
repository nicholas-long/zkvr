# put tmux and vim rc config in dockerfile

- concept of `put tmux and vim rc config in dockerfile`
- could use some ideas from pen test environ, but not the whole config
  - too many dependencies and vim plugins that are not needed
- custom vim hotkeys or plugins needed
  - open markdown links
  - colors
- enable mouse in vim and tmux
- added docker entrypoint here
- added tmux and vim rc files and put in Dockerfile
- use tmux prefix key ctrl-a to be familiar for people
- add vim hotkey tab to open markdown links

```
touch zet/20221022000131/tmux.conf
touch zet/20221022000131/vimrc

touch zet/20221022000131/entrypoint
chmod +x zet/20221022000131/entrypoint

```

` zet/20221022000131/README.md `

# Related

- [20221009095853](/zet/20221009095853/README.md) finished
- [20221028172836](/zet/20221028172836/README.md) symlink dockerfile

Tags:

    #idea
