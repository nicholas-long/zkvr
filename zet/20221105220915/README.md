# add recurring timers using github cron actions

- new subcommand to insert content `zet/20221027011800/zc-insertcontent`
- add unique item every week
- example github action crons in seclists

```
./zetcli insertcontent -b -l "do laundry - $(date --iso)" 20221027011800

cp zet/20221105220915/action.yaml .github/workflows/todo.yml
```

` zet/20221105220915/README.md `

# Related

- [20221105222236](/zet/20221105222236/README.md) cron syntax
- [20221027011800](/zet/20221027011800/README.md) zetcli bash wrapper subcommand implementation
- [20221101052020](/zet/20221101052020/README.md) TODO: Your to-do list
- [20221009095853](/zet/20221009095853/README.md) finished

Tags:

    #idea #program #feature #cron #zet
