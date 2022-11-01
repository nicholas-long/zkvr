# github actions

- intended for build / testing code and dockers
- can do
  - run periodic scripts and crons automatically
    - most frequent cron you can do for free is every 5 minutes
  - run scripts on manual start - button press on action screen by authenticated, permitted user of project
  - run scripts when things happen on github ( commits, pull requests, issues?, etc )
    - scripts that run in commits may be tested on pull requests so be careful about secrets
      - further investigation required
- when you create your access token, it needs the permission checkbox `workflow - Update GitHub Action workflows` checked in order to modify them.
  - security

` zet/20221007193324/README.md `

# Related

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221008063052](/zet/20221008063052/README.md) autorunning scripts in cards

Tags:

    #git
