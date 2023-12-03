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

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser

Tags:

    #script #macos
