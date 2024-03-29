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

# important choices of tech stack

- platform = unix
  - text files = programs
  - exit code = status code for error handling
  - text output of program = result
  - filesystem directory structure and files on disk = actual data, not just a path to look up stuff in contents
  - unix shell scripting has been around, in some form or another, since the late 70s, so i'm comfortable using that as a platform.
    - programs = files
    - the outputs of programs = files
    - files = variables
    - big functions = programs
    - piping data from one place to another is kind of like `.map` or `.Select` in js and .NET
  - don't bother reimplementing functionality that's already provided by an existing program or platform if you can reasonably integrate it by changing it or scripting it using the most trivial of text processing techniques
- platform += markdown
  - markdown is becoming standardized in some ways, and used across platforms
    - will this iteration last forever? probably not. but you can fix a whole bunch of plain text files really easily with sed and awk.
  - you could run this in a docker somewhere easily - it's kind of cool that they can run code for us, for instance, but i can do that myself too if i have to.


```
```


# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221012144502](/zet/20221012144502/README.md) track modification dates
- https://github.com/naps62/zk - another implementation in bash for reference
- https://www.google.com/search?q=zettelkasten+fzf+vim ?
- [20221027011800](/zet/20221027011800/README.md) zetcli bash wrapper subcommand implementation
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page
- [20221006013313](/zet/20221006013313/README.md) zettelkasten
- [20221025024238](/zet/20221025024238/README.md) enumerate tags
- [20221007193324](/zet/20221007193324/README.md) github actions
- [20221008063052](/zet/20221008063052/README.md) autorunning scripts in cards
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries
- [20221011145143](/zet/20221011145143/README.md) bat command pretty printer
- [20230926234809](/zet/20230926234809/README.md) a non-platform-specific find command script for executable files
- [20231122205624](/zet/20231122205624/README.md) zkvr bugs fixed and features added
- [20221006084204](/zet/20221006084204/README.md) future enhancements to zet cmd
- [20221007043646](/zet/20221007043646/README.md) findings about implementing zettelkasten
- [20221014215609](/zet/20221014215609/README.md) finished, but with ongoing related work

Tags:

    #meta #linux #script #zettelkasten #command #notes #bash #program #zet #repo #coding
