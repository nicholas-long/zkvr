# script for chatGPT prompt to select tags for documents automatically

- concept of `script to select tags for documents automatically using chatgpt`
- script to run to get tags on document `zet/20231114070621/generate-tags`
  - pass in a document as argument

- asking chatgpt to label a document. i chose the [zkvr page](/zet/20221013021614/README.md) to test.
```
┌──(coyote㉿netbook3)-[~/environment/zet/20231114070621]
└─$ ./generate-prompt ../20221013021614/README.md | chatgpt
The appropriate tags for this markdown document are: `#tui`, `#workflow`, `#git`, `#terminal`, `#zettelkasten`.
```

- adding tags programmatically
```bash
$ ./zc addtag -t test 20231114070621
```

` zet/20231114070621/README.md `

# Related

- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page
- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20231121064457](/zet/20231121064457/README.md) merge note functionality for zkvr

Tags:

    #ai #meta
