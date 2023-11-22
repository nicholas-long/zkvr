# zkvr bugs fixed and features added

- concept of `zkvr bugs fixed`

```
```

` zet/20231122205624/README.md `

# fix clone

- cannot clone a single card
- scripts in cards required for cloning implementation were missing
- `zet/20221014025416/clonecardto`
- fixed unrelated bug where cloning was duplicating the `#templatemain` card again

```
```


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
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries
- [20221009095853](/zet/20221009095853/README.md) finished
- [20221012171100](/zet/20221012171100/README.md) recently created nodes hub

Tags:

    #feature #fixed #idea #bug #tui
