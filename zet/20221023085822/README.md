# implement returning paths or tables in graph query language

- concept of `implement paths or tables`
- procedure
  - individual operations
    - input: individual IDs
      - get input IDs by taking all unique IDs in the last column of working set
    - output: could be ints if just filter, could be ordered pairs, input ID -> ... -> results
  - joining results to working set involves
    - matching the final column of rows in working set to the first column of result
    - dropping the first column from the result
    - printing it concatenated after the matching rows
  - could have many duplicates by getting all paths?
- what if a file contains paths?
  - beginning column is starting node to join with, final column is result, insert the whole table?
  - join just like other individual operation
  - if importing with `file`, do parsing
  - if concatenating a file that is assumed to be a subquery, do not parse?
- `zet/20221023085822/walkquery`
- or changed to union
  - changed to use paths
  - concatenate other walks to the current walk
  - tested
- added `follow`
  - should append matching paths to current
  - untested
- combine this version of script with graphquery or use a parent script to select them based on syntax?
- idea: could call graphquery as a subprocess within pathquery
  - parent script could sort out who needs to be called?
- yaml queries still need to be implemented in graphquery and here?

```
zet/20221023085822/walkquery

zet/20221023085822/walkquery --human @bash like shell : : @tip
zet/20221023085822/walkquery --human --path @bash like shell : : @tip

zet/20221023085822/walkquery --human --path @file : : like cool : : @tip : @trick

zet/20221023085822/walkquery --human --path id 20221011134623 refs not <( echo 20221011134623)

zet/20221023085822/walkquery --human --path id 20221011181347 refs not <( echo 20221011134623)
got file /dev/fd/62
- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011184954](/zet/20221011184954/README.md) proof, flags, and screenshots #notes #proof
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221014074726](/zet/20221014074726/README.md) use appropriate language for the job #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221014024704](/zet/20221014024704/README.md) list of sparse nodes #list

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221013204452](/zet/20221013204452/README.md) make a video of terminal graph browser and zkvr workflow loop in action #idea #todo

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221013035616](/zet/20221013035616/README.md) fun #noun

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221008061845](/zet/20221008061845/README.md) workflow #workflow #optimization

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221011092421](/zet/20221011092421/README.md) hacking video notes #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221007043259](/zet/20221007043259/README.md) zettelkasten generic ideas #todo #idea #zettelkasten 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221011155715](/zet/20221011155715/README.md) video of how to make a node in my implementation #video

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221008042814](/zet/20221008042814/README.md) WIP #todo

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221008061334](/zet/20221008061334/README.md) concepts #noun #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221009104752](/zet/20221009104752/README.md) stuff to research #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221007185940](/zet/20221007185940/README.md) unsorted nodes #todo

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221003151172](/zet/20221003151172/README.md) active directory domain to try list #to-try-list #hacking #active 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221009172522](/zet/20221009172522/README.md) obsidian #program

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221003151207](/zet/20221003151207/README.md) windows privilege escalation #to-try-list #hacking #privesc #windows #windows 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221006032546](/zet/20221006032546/README.md) my implementation of zet cmd #zettelkasten #bash #coding #program

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221010184202](/zet/20221010184202/README.md) screenshots of github ui graph showing workflow acceleration #todo #idea #image

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221007182026](/zet/20221007182026/README.md) scripts related to zettelkasten conversion #zettelkasten #bash

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221008063052](/zet/20221008063052/README.md) autorunning scripts in cards #zettelkasten #bash

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221009100510](/zet/20221009100510/README.md) concept of finished / being done #done

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221009005402](/zet/20221009005402/README.md) preparing for the OSCP exam #todo #cert

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221007220451](/zet/20221007220451/README.md) hacking notes hub #hacking

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221009102436](/zet/20221009102436/README.md) hacking to try lists #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221007043646](/zet/20221007043646/README.md) findings about implementing zettelkasten #zettelkasten

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221009192000](/zet/20221009192000/README.md) stuff to put on main page #meta
- [20221006013612](/zet/20221006013612/README.md) markdown to zettelkasten conversion project #zettelkasten #project 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221003151147](/zet/20221003151147/README.md) resource based constrained delegation S4U attack powershell commands on target #hacking #windows #ad 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221003150293](/zet/20221003150293/README.md) build custom java minecraft plugin with maven 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221013190422](/zet/20221013190422/README.md) headline exploits #concept #hub #hacking

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221003150426](/zet/20221003150426/README.md) zip slip evilarc.py 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221003150361](/zet/20221003150361/README.md) connect to minecraft server and send chat messages 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221003151030](/zet/20221003151030/README.md) eternalblue MS17-010 - working #exploit #windows #smb

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011183500](/zet/20221011183500/README.md) potential exploits #notes
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181920](/zet/20221011181920/README.md) working notes - foothold #notes
- [20221003151172](/zet/20221003151172/README.md) active directory domain to try list #to-try-list #hacking #active 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181920](/zet/20221011181920/README.md) working notes - foothold #notes
- [20221003151194](/zet/20221003151194/README.md) procedure 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181920](/zet/20221011181920/README.md) working notes - foothold #notes
- [20221009102436](/zet/20221009102436/README.md) hacking to try lists #todo #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181531](/zet/20221011181531/README.md) steps #notes
- [20221003151194](/zet/20221003151194/README.md) procedure 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011182350](/zet/20221011182350/README.md) services #notes
- [20221012153227](/zet/20221012153227/README.md) nodejs #idea

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181629](/zet/20221011181629/README.md) usernames #notes
- [20221015022512](/zet/20221015022512/README.md) password reuse to try list #to-try-list

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea
- [20221003150293](/zet/20221003150293/README.md) build custom java minecraft plugin with maven 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea
- [20221003151029](/zet/20221003151029/README.md) MS08-067 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011181453](/zet/20221011181453/README.md) exploit path #todo #idea
- [20221003151030](/zet/20221003151030/README.md) eternalblue MS17-010 - working #exploit #windows #smb

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011182254](/zet/20221011182254/README.md) ports - enum #notes
- [20221013173355](/zet/20221013173355/README.md) enumeration - the process of enumerating a target #concept #enumeration

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011182254](/zet/20221011182254/README.md) ports - enum #notes
- [20221003150891](/zet/20221003150891/README.md) enumerate open ports if `ss` is not present 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011182016](/zet/20221011182016/README.md) working notes - privesc #notes
- [20221003151207](/zet/20221003151207/README.md) windows privilege escalation #to-try-list #hacking #privesc #windows #windows 

- [20221011181347](/zet/20221011181347/README.md) hacking notes template 1 #notes
- [20221011182016](/zet/20221011182016/README.md) working notes - privesc #notes
- [20221003151210](/zet/20221003151210/README.md) linux privilege escalation #to-try-list #hacking #privesc #linux 


zet/20221023085822/walkquery --human --path id 20221011181347 refs not <( echo 20221011134623) union <( zet/20221023085822/walkquery @awk : @tip )
```

` zet/20221023085822/README.md `

# Related

- [20221013221136](/zet/20221013221136/README.md) graph query language for zettelkasten
- [20221008042814](/zet/20221008042814/README.md) WIP
- [20221024215216](/zet/20221024215216/README.md) future enhancements to graph query language

Tags:

    #idea
