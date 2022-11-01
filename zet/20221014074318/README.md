# important choices of tech stack

- platform = unix
  - text files = programs
  - exit code = status code for error handling
  - text output of program = result
  - filesystem directory structure and files on disk = actual data, not just a path to look up stuff in contents
  - unix shell scripting has been around, in some form or another, since the late 70s, so i'm comfortable using that as a platform.
    - programs = files
    - the outputs of programs = files
    - files = variables
    - big functions = programs
    - piping data from one place to another is kind of like `.map` or `.Select` in js and .NET
  - don't bother reimplementing functionality that's already provided by an existing program or platform if you can reasonably integrate it by changing it or scripting it using the most trivial of text processing techniques
- platform += markdown
  - markdown is becoming standardized in some ways, and used across platforms
    - will this iteration last forever? probably not. but you can fix a whole bunch of plain text files really easily with sed and awk.
  - you could run this in a docker somewhere easily - it's kind of cool that they can run code for us, for instance, but i can do that myself too if i have to.


```
```

` zet/20221014074318/README.md `

# Related

- [20221014074726](/zet/20221014074726/README.md) use appropriate language for the job
- [20221003150067](/zet/20221003150067/README.md) vim
- [20221008215400](/zet/20221008215400/README.md) file
- [20221008213254](/zet/20221008213254/README.md) file path
- [20221003151350](/zet/20221003151350/README.md) awk and bash scripting
- [20221014073148](/zet/20221014073148/README.md) reasoning behind choices for tech stack - finding dependable and long lasting technology
- [20221006033248](/zet/20221006033248/README.md) rwxrob
- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd
- [20221008214406](/zet/20221008214406/README.md) sharing programming projects with zettelkasten
- [20221031192031](/zet/20221031192031/README.md) all cards required for implementation

Tags:

    #idea
