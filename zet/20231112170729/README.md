# script to get remote github URL from git repository

- concept of `script to get remote github URL from git repository`
- add as a feature in [zkvr](/zet/20221013021614/README.md)

```bash
grep -R github .git
.git/FETCH_HEAD:ddc65891bb3f1e2c44ba9853d40713281e489846		branch 'main' of https://github.com/nicholas-long/environment
.git/config:	url = https://github.com/nicholas-long/environment

git remote get-url $(git remote)
```

` zet/20231112170729/README.md `

# idea to launch browser to current card on github

- remote URL is available in `.git/logs/refs/remotes/origin`
  - the right way to interface with this data is to use git remote subcommands
- choose firefox or chromium?

```bash
# get current git remote URL
currentRemoteUrl=$(awk '{print $NF}' .git/logs/refs/remotes/origin/HEAD)
currentBranch=$(git branch --show-current)
```

` zet/20221105224810/README.md `

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

- [20230919172630](/zet/20230919172630/README.md) script to get root of repository or obsidian knowledge base
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser

Tags:

    #url #web #feature #script #idea #shortcmd #git #zet
