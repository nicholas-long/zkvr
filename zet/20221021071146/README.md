# delete things marked as #DEL periodically

- concept of `delete things marked as #DEL periodically`

```
./graphquery @DEL | awk '/^[0-9]+$/ {system("rm -rf zet/" $0)}'
```

` zet/20221021071146/README.md `

# Related

- [20221014215609](/zet/20221014215609/README.md) finished, but with ongoing related work
- [20221006013612](/zet/20221006013612/README.md) markdown to zettelkasten conversion project
- [20221017173622](/zet/20221017173622/README.md) report about fixing problem tags in cards
- [20221031192031](/zet/20221031192031/README.md) all cards required for implementation

Tags:

    #workflow #cleanup
