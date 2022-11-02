# graph query language for zettelkasten

- `./graphquery`
- simple graph query language implemented with pipelines of transformations and set theory operations
- useful for making scripted cards which interact with or logically query other systems of cards

- documentation
  - all queries return raw IDs. add `--human` flag to return markdown formatted links with readable titles.
  - operations must tokenize as bash arguments
  - the core intrinsic operation of the query syntax is intersection. there is a working set of IDs, and a pipeline of operations are performed in succession to filter or transform this set of IDs.
  - a query starts with a full set of all IDs in the graph and filters them by performing operations.
  - query ends when working set is empty or when operations are complete.
  - all nested queries should be done in subprocesses with bash substitution `<( ./graphquery @meta like this )`. this is a dirty hack was discovered to significantly reduce the effort required to create this reference implementation.
  - operations
    - `@tagname`             - filter to IDs of cards that have tag "tagname"
    - `like PATTERN`         - filter IDs of cards that contain case insensitive grep pattern
    - `id 11111111111111`    - intersect with only a particular ID if present, or none. a monad?
    - `refs` / `:`           - get all of the references of all of these IDs. transform the current working set of IDs into a new set containing all of the references. core operation used to traverse the graph.
    - `file FILENAME`        - load IDs from a file and discard the current working set of IDs, replacing them
    - `FILENAME`             - "and" a raw file or subquery appearing as an operation will intersect the current working set with IDs parsed from the file's text contents
    - `or FILENAME`          - union ( concatenate ) IDs with all IDs appearing in the file or subquery
    - `not FILENAME`         - filter out all IDs appearing in the file or subquery
    - `edges`                - get edges between all nodes in set as pairs. vertex-induced subgraph. terminal operation.
    - `taglist tagA,tagB,C`  - convenient way to union lists of notes from lots of tags

- examples
```
mv ./graphquery zet/20221013221136/
ln -s zet/20221013221136/graphquery ./graphquery

./graphquery README.md not <( ./graphquery @meta ) not <( ./graphquery id $CARD_ID refs ) # all ids on the main page that are not tagged #meta and not referenced in this card
./graphquery id $CARD_ID refs not README.md                             # all references in this card that are not on README.md
./graphquery id $RECENT_MOD refs not $recentids not <( echo $MY_ID )    # everything attached to $RECENT_MOD that does not have an id in the tempfile named $recentids
./graphquery $recentids not <( ./graphquery id $RECENT_MOD refs )       # IDs in tempfile $recentids that are not attached to $RECENT_MOD
./graphquery @DEL | awk '/^[0-9]+$/ {system("rm -rf zet/" $0)}'         # cleanup all zets with a certain tag - not great practice

./graphquery README.md 2>/dev/null

./graphquery README.md edges 2>/dev/null

```

` zet/20221013221136/README.md `

# Related

- [20221023085822](/zet/20221023085822/README.md) implement returning paths or tables in graph query language
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221009095853](/zet/20221009095853/README.md) finished
- [20221006013313](/zet/20221006013313/README.md) zettelkasten
- [20221024215216](/zet/20221024215216/README.md) future enhancements to graph query language
- [20221006084204](/zet/20221006084204/README.md) future enhancements to zet cmd
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries

Tags:

    #idea #todo
