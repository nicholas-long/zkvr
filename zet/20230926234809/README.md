# a non-platform-specific find command script for executable files

- concept of `a non-platform-specific find command script for executable files`
- need to replace find executable commands within here to work on mac os
- first uncovered this issue testing on mac os with the short cmd directory script not finding executables
- script name `zet/20230926234809/find-executable`

- usage
```bash
┌──(parallels㉿kali-linux-2022-2)-[~/environment]
└─$ find-executable . -type f -name autoexec_enrich
./zet/20221012144502/autoexec_enrich
./zet/20221006032546/autoexec_enrich
./zet/20221026064448/autoexec_enrich
./zet/20221006213953/autoexec_enrich
./zet/20221008063052/autoexec_enrich
./zet/20230925055222/autoexec_enrich
./zet/20221009192000/autoexec_enrich
```

- original fix
```bash
# need to check if find command supports executable parameter
if find --help | grep '[-]executable' >/dev/null; then
  findcommandmods="-type f -executable"
else
  # if it doesn't, there's a non-portable alternative for mac os
  findcommandmods="-perm +111 -type f"
fi
```

` zet/20230926234809/README.md `

# Related

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd

Tags:

    #shortcmd #bash #command #script
