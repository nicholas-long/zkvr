# clone a subsection of a graph by tag boundaries

- concept of `clone a subsection of a graph by tag boundaries`
- for example
  - start at a template node
  - grab all neighboring nodes recursively that have `#template` tag
  - clone them, updating all IDs to match
- would be really useful for OSCP AD network to be able to have multiple machine notes that could all be linked together somehow
- could do it with edge induced subgraph notated by a set of edges
  - in the form `11111111111111 22222222222222` the edges between 2 nodes
- procedure
  - use tag `templatemain` to indicate the "main" card that - fuzzy find to start
  - get localgroup with new `tagboundary` script
  - make a new card for each of them and echo IDs to tempfile
  - replace `templatemain` -> current card ID
    - also call sed script for this
  - replace IDs in the new cards with sed
- added test script to try it `zet/20221014025416/testscript`
- script works!

```
# testing cloning

highlevel=20221011182140 # high level machine overview from notes template
zet/20221014025416/clonecardto $highlevel $testid

--------------------------------------------------------------------------------

# tag boundary info
zet/20221014025416/tagboundary

# print all connected nodes marked by notes tag
highlevel=20221011182140 # high level machine overview from notes template
./graphquery --human <(zet/20221014025416/tagboundary $highlevel template)

[diag] refs  20221011184954 
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea #notes #template
- [20221011181531](/zet/20221011181531/README.md) steps #notes #template
- [20221011181605](/zet/20221011181605/README.md) creds #notes #template
- [20221011181820](/zet/20221011181820/README.md) privesc steps #notes #template
- [20221011181920](/zet/20221011181920/README.md) working notes - foothold #notes #template
- [20221011182016](/zet/20221011182016/README.md) working notes - privesc #notes #template
- [20221011182140](/zet/20221011182140/README.md) machine high-level overview notes #notes #template
- [20221011182254](/zet/20221011182254/README.md) ports - enum #notes #template
- [20221011182350](/zet/20221011182350/README.md) services #notes #template
- [20221011182459](/zet/20221011182459/README.md) machine web services #notes #template
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes #template
- [20221011184954](/zet/20221011184954/README.md) proof, flags, and screenshots #notes #proof #template

```

` zet/20221014025416/README.md `

# Related

- [20221006084204](/zet/20221006084204/README.md) future enhancements to zet cmd
- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221009095853](/zet/20221009095853/README.md) finished
- [20221101163755](/zet/20221101163755/README.md) fix clone

Tags:

    #idea
