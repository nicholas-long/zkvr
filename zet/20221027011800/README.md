# zetcli bash wrapper subcommand implementation

- concept of `testing bash wrapper subcommand implementation`
- helpful utility functions to add
  - get title
  - get tags
  - get content?
- copying some concepts from zet cmd
- remaining subcommands to re-implement
  - `preview`
  - `unlink`
  - `rm`
  - `addref`
  - `enrich_links_single`
  - `fixspaces`
  - `enrich`
- rename zetwrap to `zetcli` and update symlink

```
ln -s zet/20221027011800/zetwrap zetcli

./zc new
./zetcli id

```

` zet/20221027011800/README.md `

# Related

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221103162623](/zet/20221103162623/README.md) move zetcmd to wrapper CLI and remove fzf subcommands from CLI
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221105220915](/zet/20221105220915/README.md) add recurring timers using github cron actions

Tags:

    #idea #bash #command #program #filesystem
