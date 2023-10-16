# my original implementation of zet cmd

name: zc
- command line tool based on <https://github.com/rwxrob/zet>
- uses github actions to automatically enrich content, run scripts, and make references bidirectional
- `browser` - fzf interactive markdown preview browsser that can traverse and edit links
  - [20221013021614](/zet/20221013021614/README.md) terminal graph browser
  - graph data entry and linking tool
  - the full TUI implementation that will be released?
  - can launch new tmux windows if tmux is running
  - fzf selection window to select lots of references or spawn new nodes
- for scripting
  - [20221013221136](/zet/20221013221136/README.md) graph query language
- installing command shortcut to zc - useful for vim filters and as CLI
  - `echo "$(pwd)/zc \$@" > ~/.local/bin/z`
    - make sure `$HOME/.local/bin` is in your path
    - still trying to figure out this shortcut since it's not perfect

- dependencies
  - vim or nvim
  - fzf
  - bat (the real one, not the kali package)
  - lazygit

- help text
```
./zc -h
Usage: ./zc action [ options ]
| action      : [ spawn, search, find, rm, print, enrich, new, refs, preview ]
| | fzf       : [ menu, spawn, search, vilink, viunlink, connectome ]
| | scripting : [ find, addref, addtag, deltag, rm, print, enrich, new, refs, preview, enum, unlink, enrich_links_single, fixspaces ]
Options:
    -m|--multiple
    -p|--print
    -e|--edit
    -f|--file|--forwarding-address
    -q|--query
    -t|--title|--target|--tag
    -r|--reference
    -v|--verbose
    -h|--help
```

- i think the project should be broken into 3 parts
  - in order of dependencies:
  - console utility (collection of scripts)
  - graph query language
  - graph browser, linker, editor, git workflow

- added `saverefs` script for optimization
  - partitions references between nodes into 100 files for quick lookup
  - also because storing 500kb of files every commit is too much
  - disabled saverefs because it produces excess noise now

` zet/20221006032546/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221012144502](/zet/20221012144502/README.md) track modification dates
- https://github.com/naps62/zk - another implementation in bash for reference
- https://www.google.com/search?q=zettelkasten+fzf+vim ?
- [20221027011800](/zet/20221027011800/README.md) zetcli bash wrapper subcommand implementation
- [20221028173620](/zet/20221028173620/README.md) yq binaries
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page
- [20221006013313](/zet/20221006013313/README.md) zettelkasten
- [20221014074318](/zet/20221014074318/README.md) important choices of tech stack
- [20221025024238](/zet/20221025024238/README.md) enumerate tags
- [20221007193324](/zet/20221007193324/README.md) github actions
- [20221008063052](/zet/20221008063052/README.md) autorunning scripts in cards
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries
- [20221011145143](/zet/20221011145143/README.md) bat command pretty printer
- [20221103162623](/zet/20221103162623/README.md) move zetcmd to wrapper CLI and remove fzf subcommands from CLI
- [20230926224444](/zet/20230926224444/README.md) updating scripts to use gawk when possible
- [20230927001343](/zet/20230927001343/README.md) places to update find command to use new executable version in order to be compatible on mac
- [20230929023221](/zet/20230929023221/README.md) testing user interfaces in fzf

Tags:

    #zettelkasten #bash #coding #program #script #command #command #repo
