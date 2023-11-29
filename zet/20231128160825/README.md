# cross platform scripts to implement broken zkvr features on mac os

- need to make custom scripts in order to implement certain features on mac os
  - `sed` does not have working implementations of the `-e` or `-i` arguments on Mac OS
- this script became required once changes were implemented in zetcmd

## things to implement
- [x] add tags
- [x] delete tags
- [x] spawn from template and replace content
  - script `zet/20231128160825/createtemplate` to edit the template after spawning
- [x] include changes in zkvr

```bash
$ ./addtag macos README.md
# unchanged
$ ./addtag newtag README.md
# new tag added
```

` zet/20231128160825/README.md `

# Related

- [20230925193834](/zet/20230925193834/README.md) testing on mac os
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20221012171100](/zet/20221012171100/README.md) recently created nodes hub
- [20230922214602](/zet/20230922214602/README.md) things i want to implement in zkvr after working on the environment

Tags:

    #script #macos
