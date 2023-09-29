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

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20230922203837](/zet/20230922203837/README.md) get rid of all platform specific binaries from zkvr

Tags:

    #program #yaml #scripting #util
