# enumerate tags

- concept of `enumerate tags`

```
awk '
{ last = $0 }
ENDFILE {
  gsub(/^ */,"",last)
  gsub(/ *$/,"",last)
  print last
  split(last,arr," ")
  for (n=0;n<=length(arr);n++) {
    if (arr[n] ~ /^#[^ ]/) {
      print arr[n]
    }
  }
} ' zet/20221025024238/README.md

```

` zet/20221025024238/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd

Tags:

    #bash #trick #awk #script #zet
