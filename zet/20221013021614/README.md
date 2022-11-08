# zkvr terminal graph browser

- concept of `terminal graph browser`
- zkvr
- text user interface ( TUI ) to follow links
  - interfaced based on workflow from using web browser and github markdown preview to traverse links
  - add and remove links quickly with fzf
  - preview window shows document always, menu picks options, option to visit links
- menu options documentation
  - `goto ...`    - follow link
  - `tab`         - if running in tmux, open multiple other links in new tmux windows (like browser tabs)
  - `mkfile`      - touch a file and optionally `chmod +x`
  - `tagindex`    - browse by tags
  - `workdir`     - open new tmux window in working directory of current card if run within tmux
  - `addtags`     - add multiple tags to card
  - `deltags`     - remove multiple tags from card
  - `spraytag`    - add a tag to multiple links on a card at once. select with fuzzy search.
  - `edit ...`    - edit card or attachments in vim
  - `/deep`       - deep keyword search combining links, titles, content, and fzf fuzzy finding. launches new tmux windows if tmux is running.
  - `~`           - return to home page
  - `spawn`       - create a new zettel card linked to here. enter title at prompt. new card is available to navigate and edit immediately.
  - `clone`       - copy a template card in, replacing current card. copy entire linked network of cards with tag `#template`. capable of creating large structures of notes.
  - `copy...`     - if running in tmux, select text to copy from snippets with fzf
  - `copypath`    - if running in tmux, copy the current markdown file path to tmux buffer
  - `xfer`        - copy between cards or attached files easily by selecting files or cards to open alongside `README.md` in vim tabs
  - `fxfer`       - copy files between cards
  - `link`        - insert many links with fzf fuzzy finder
  - `unlink`      - select one link to remove. will remove from target zettel card as well.
  - `stat`        - git status preview, colorized. launches lazygit if selected.
  - `gitlog`      - view git log history of current card and attachments, with paging
  - `diff`        - git diff interactive commit selector
  - `back`        - go back, like a browser
    - if you edit links in cards you are working on, you could get trapped and need to hop back to previous card
  - `enrich`      - insert backlinks and other various cleanup scripts. runs automatic scripts in cards
    - consider the security implications of automatic scripts
  - `quit`        - exit program. i like q as a hotkey so this is good in fzf.
  - `zkcopy`      - copy cards from other zettelkasten (experimental)

```
ln -s zet/20221013021614/ browser

zet/20221013021614/getcopycontent zet/20221013021614/README.md

```

- changed preview hotkeys to page up and page down to match lazygit hotkeys
- added ability to list and edit attachments
- added tag features: quick tag add, del
- added auto git add after enrich - no auto commit
- added: copy anything in a code tag into tmux clipboard
- added: spraytag and nuketag features - fzf menu to add/del a hashtag to multiple links out of current node
  - TODO: filter out the ones that have it?
- todo
  - spawn multiple things at once - launch editor, each line is a title of a new card
  - add images / "figures" with preview using tesseract to OCR
  - record sequences of actions as scripts
    - replay if they exist
    - show script in preview
    - record the actual zc commands and replace ID?
  - select N options if tmux and open tabs if more than one goto?
  - quick git ops - push pull commit - implement here instead of lazygit
  - toggle hide preview panel

` zet/20221013021614/README.md `

# Related

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221028172836](/zet/20221028172836/README.md) symlink dockerfile
- [20221014215609](/zet/20221014215609/README.md) finished, but with ongoing related work
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page
- [20221025024238](/zet/20221025024238/README.md) enumerate tags
- [20221101043303](/zet/20221101043303/README.md) important features and workflow tricks to mention on main page
- [20221101163755](/zet/20221101163755/README.md) fix clone
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries
- [20221011145143](/zet/20221011145143/README.md) bat command pretty printer
- [20221105021715](/zet/20221105021715/README.md) git diff picker feature
- [20221027011800](/zet/20221027011800/README.md) zetcli bash wrapper subcommand implementation
- [20221105224810](/zet/20221105224810/README.md) launch browser to current card on github

Tags:

    #tui #program #zettelkasten
