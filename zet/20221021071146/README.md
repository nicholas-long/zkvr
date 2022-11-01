# delete things marked as #DEL periodically

- concept of `delete things marked as #DEL periodically`

```
./graphquery @DEL | awk '/^[0-9]+$/ {system("rm -rf zet/" $0)}'
```

` zet/20221021071146/README.md `

# Related

- [20221014215609](/zet/20221014215609/README.md) finished, but with ongoing related work

Tags:

    #workflow #cleanup
