# future enhancements to zet cmd

- move graph browser into zet cmd card
- git submenu in graph browswer instead of "stat"
  - pull
  - commit with message prompt
- put new links on bottom instead of top? -- made card?
- rewrite zet cmd implementation to be plain
  - split up command actions into files like https://github.com/naps62/zk
  - use graph browser with fzf functionality as the whole workflow productivity loop to run
    - split things up into subcommands
- auto commit after enrich ?
  - i think the process of checking the diff after enriching is useful to verify it worked
- archive old cards into tgz file - maybe attach to a speical node to do it?
- add nodes from graph text file like graphviz
- readline vi hotkeys
- track usage with quick addition of tee to a logfile after search
- put timestamps on bottom? `{{date}}`
- make reference template / example implementations

## move these

- parse abstractions out of text using python library - which one?
  - move to experiments
- automatic scripts stored in zettels - done sort of
  - use cases
    - enrich step (quick)
    - cron
  - keep real info and data up to date
  - be careful when importing scripts from other Zettelkasten...
- search multiple words in entire zettel content - done sort of
- git history idea - has card

` zet/20221006084204/README.md `

# Related

- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221012144502](/zet/20221012144502/README.md) track modification dates
- [20221007043646](/zet/20221007043646/README.md) findings about implementing zettelkasten
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221008063052](/zet/20221008063052/README.md) autorunning scripts in cards
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries

Tags:

    #todo
