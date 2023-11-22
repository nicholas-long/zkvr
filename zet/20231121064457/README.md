# merge note functionality for zkvr

- concept of `merge note functionality for zkvr`
- in obsidian, i like to merge notes to help clean things up. it would be good to have this functionality here.
- actually, if i just concatenate the 2 files together and delete the old note, the backlinks will update
  - need an awk script to combine the related sections
    - read any number of files
    - combine related sections and tags into one
  - enrich step will update backlinks in all other files to point to the correct place by reinserting them after the files are merged
- any note you want to merge should be linked to the current note. i think that is a reasonable restriction. if you want to merge one quickly, then you can add a link.
- when merging, the existing note should come first
- [x] one potential issue is that if you end up with duplicate tags, this might break the tag index file
  - created script `zet/20231121064457/fix-duplicate-tags` to remove the duplicate tags on the last line
- [x] fix weird broken file
  - a weird file was being created because i reused a variable `selection` in the code. it was important, and reusing it within the code was causing undefined behavior.
- 2023-11-21 i got this working in zkvr

## procedure
- select a link to merge into
- write to a temp file
- call this script to merge the destination readme and the source readme into temp file
- remove self references from resulting file
- copy temp file to dest readme
- set current document to point to dest readme
- delete source directory
- enrich to update all backlinks

```bash
zet/20231121064457/merge-markdown-related-links zet/20231121064457/README.md zet/20230922214602/README.md
./merge-markdown-related-links ../20231121064457/README.md ../20230922214602/README.md
./merge-markdown-related-links ../20230905015223/README.md ../20230916132320/README.md | bat --language=md
```

` zet/20231121064457/README.md `

# Related

- [20221013021614](/zet/20221013021614/README.md) zkvr terminal graph browser
- [20230922214602](/zet/20230922214602/README.md) things i want to implement in zkvr after working on the environment
- [20221012171100](/zet/20221012171100/README.md) recently created nodes hub

Tags:

    #zet #zettelkasten #markdown #zet
