# launch browser to current card on github

- remote URL is available in `.git/logs/refs/remotes/origin`
- firefox or chromium?
- specific branch?

```bash
# get current git remote URL
currentRemoteUrl=$(awk '{print $NF}' .git/logs/refs/remotes/origin/HEAD)
currentBranch=$(git branch --show-current)
```

` zet/20221105224810/README.md `

# Related

- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser

Tags:

    #idea #git #web #zet
