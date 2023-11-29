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

# yq binaries

- concept of `yq binaries`
- included MIT `LICENSE` file from yq
- store here for symlinks
- 2023-09-22 i looks like i didn't actually get around to using yq in queries, so i didn't tie zkvr to a particular architecture by including the amd binaries.
- i have things in the install scripts now that could install this interactively and let the user pick the architecture

```

mv yq_binaries/* zet/20221028173620/
rm -rf yq_binaries/
ln -s zet/20221028173620/bin yq_binaries

grep -R yq zet
grep: zet/20221028173620/bin/yq_linux_amd64: binary file matches
zet/20221028173620/README.md:# yq binaries
zet/20221028173620/README.md:- concept of `yq binaries`
zet/20221028173620/README.md:- included MIT `LICENSE` file from yq
zet/20221028173620/README.md:mv yq_binaries/* zet/20221028173620/
zet/20221028173620/README.md:rm -rf yq_binaries/
zet/20221028173620/README.md:ln -s zet/20221028173620/bin yq_binaries
grep: zet/20221011145143/bat_0.22.1_amd64.deb: binary file matches
zet/20221006032546/README.md:- [20221028173620](/zet/20221028173620/README.md) yq binaries
zet/20221024215216/README.md:  - could just hook up yq syntax and apply to all cards in working set buf
```

` zet/20221028173620/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221014025416](/zet/20221014025416/README.md) clone a subsection of a graph by tag boundaries
- [20221009095853](/zet/20221009095853/README.md) finished
- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd

Tags:

    #scripting #yaml #feature #util #fixed #idea #program #bug #tui
