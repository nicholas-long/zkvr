# copy or jump to recently edited files feature

- concept of `jump to recently edited files feature or copy their filenams`
- created script `zet/20231129161540/modified-file-timestamps`
- created `zet/20231129161540/get-recent-file` to run fzf and return a file
- after selecting a file, zkvr should ask what you want to do: copy the path, edit the file, navigate there, etc.

```bash
#!/bin/bash
find /path/to/directory -type f -print0 | xargs -0 ls -lt

find zet -type f -print0 | xargs -0 ls --full-time

# simple find recent
find zet -type f -print0 | xargs -0 ls --full-time | awk '
{
  gsub(/^[^ ]* *[^ ]* *[^ ]* *[^ ]* *[^ ]* */,"")
  print
}
' | sort
```

- version for mac and linux
```bash
if [[ $(uname) =~ Darwin ]]; then
  find zet -type f -print0 | xargs -0 stat -f $'%m\t%N'
else
  find zet -type f -print0 | xargs -0 stat -c $'%Y\t%n'
fi | sort
```

` zet/20231129161540/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221008061845](/zet/20221008061845/README.md) workflow

Tags:

    #script #enhancement #workflow
