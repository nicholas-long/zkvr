# future enhancements to graph query language

- enumerate all reachable nodes from current nodes that exist in a subquery file - duplicate of search N levels?
  - find all reachable within that set
- have queries return tables of the entire trail encoutered while running query, treat the last ID in table as the current set
  - add `--path` flag for trails to not visit the same node twice
  - [20221023085822](/zet/20221023085822/README.md) implement returning paths or tables in graph query language
- add a flag to graphquery to enable path mode and not visit verticies twice
- search N levels from a set of nodes for nodes within another set
  - used to search through neighboring systems
  - maintain visited set for speed to avoid expanding nodes multiple times
  - do all expanding in one place like an awk script
  - could be very bad to combine with the feature for returning all paths - combinatoric expansion
  - the reason this is necessary instead of saying "refs refs refs" is that refs getting expanded do not include the nodes that got expanded
    - otherwise would require chaining a bunch of ORs together, like `refs or (... refs refs) or (.... refs refs refs)` - yuck
- add yaml queries like dataview
  - could just hook up yq syntax and apply to all cards in working set buf
- like relational database from old awk book
- look at graphql for inspiration?
- look at neo4j for inspiration?

```
```

` zet/20221024215216/README.md `

# Related

- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221023085822](/zet/20221023085822/README.md) implement returning paths or tables in graph query language

Tags:

    #todo #zettelkasten #graph #enhancement
