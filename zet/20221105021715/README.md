# git diff picker feature

- concept of `git diff picker feature`

```
git log -- zet/20221003150098

git log -- zet/20221003150098 | awk '
$1 == "Date:" { gsub(/Date: */,""); date = $0 }
$1 == "commit" { c = $2 }
/^    / {
  msg = $0
  gsub(/^ */,"",msg)
  gsub(/ *$/,"",msg)
  print c, date, msg
}
'

```

` zet/20221105021715/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221009095853](/zet/20221009095853/README.md) finished

Tags:

    #idea #feature #tui
