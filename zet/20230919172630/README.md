# script to get root of repository or obsidian knowledge base

- `zet/20230919172630/root-knowledge-base-repo-path`
- pass in filename or directory name as argument
  - if there's no argument, use the current directory
- output: prints the root knowledge base or git repository path containing this file
- traverses up the directory until it finds the root of the thing we are in...
- things i want to find the root of:
  - knowledge base or zettelkasten
    - look for .obsidian directory
  - git repository
    - look for .git directory

```bash
zet/20230919172630/root-knowledge-base-repo-path "/media/psf/zk/books/9780060731335 Freakonomics.md"
/media/psf/zk
zet/20230919172630/root-knowledge-base-repo-path ~/environment/zet/20221003150098/
/home/parallels/environment

```

- testing as short command and invalid files
```bash
# the first example is an invalid file
┌──(parallels㉿kali-linux-2022-2)-[~]
└─$ root-knowledge-base-repo-path zet/20221003150098/README.md
root path not found

┌──(parallels㉿kali-linux-2022-2)-[~]
└─$ root-knowledge-base-repo-path environment/zet/20221003150098/README.md
environment
```

- where could it be useful?
```bash
grep -R ENVIRON_BASEPATH zet
zet/20230906035650/revshell:lhost=$($ENVIRON_BASEPATH/zet/20230906033727/getmyip)
zet/20230906035650/revshell:$ENVIRON_BASEPATH/zet/20230906035236/draw_title_bar "windows rev shell"
zet/20230906035650/revshell:$ENVIRON_BASEPATH/zet/20230906035236/draw_title_bar "linux rev shell"
zet/20230906035744/find-alnum-base64:echo "$1" | $ENVIRON_BASEPATH/zet/20230906035744/space-invader | while read line; do
zet/20230905015120/bashrc:    export ENVIRON_BASEPATH="."
zet/20230905015120/bashrc:  export ENVIRON_BASEPATH="$ENVIRON_PATH"
zet/20230905015120/bashrc:export PATH="$PATH:$ENVIRON_BASEPATH/shortcuts"
zet/20230905015120/README.md:- base path to this repository in env var: `$ENVIRON_BASEPATH`
zet/20230912192810/search-markdown:$ENVIRON_BASEPATH/zet/20230912192810/fuzzy-search-markdown-content | \
zet/20230912192810/search-markdown:# #--preview="$ENVIRON_BASEPATH/zet/20230912192810/markdown-search-preview" 
```

` zet/20230919172630/README.md `

# Related

- [20230919153113](/zet/20230919153113/README.md) obsidian links scripts
- [20230905015120](/zet/20230905015120/README.md) bash rc file and config
- [20231112170729](/zet/20231112170729/README.md) script to get remote github URL from git repository

Tags:

    #bash #script #directory #filepath #shortcmd
