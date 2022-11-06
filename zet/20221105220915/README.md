# add recurring timers using github cron actions

- new subcommand to insert content `zet/20221027011800/zc-insertcontent`
- example github action crons in seclists

```yaml
name: update etc files

# Controls when the workflow will run
on:
  schedule:
    - cron: '30 20 1,15 * *' # run at 8:30p on 1st and 15th

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

jobs:
  updatejob:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest
    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      - uses: actions/checkout@v3

      # Runs a single command using the runners shell
      - name: update wordlist
        run: cd .bin/etc-files-list-update/ && ./update.sh

      - name: print diff
        run: git diff

      # commit and push
      - uses: stefanzweifel/git-auto-commit-action@v4
        with:
          commit_message: '[Github Action] Updated LFI-etc-files-of-all-linux-packages.txt'
```

` zet/20221105220915/README.md `

# Related

- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221105222236](/zet/20221105222236/README.md) cron syntax
- [20221012171100](/zet/20221012171100/README.md) recently created nodes hub
- [20221027011800](/zet/20221027011800/README.md) zetcli bash wrapper subcommand implementation

Tags:

    #idea #program #feature #cron #zet
