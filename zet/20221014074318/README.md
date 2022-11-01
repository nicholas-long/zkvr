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

- [20221006032546](/zet/20221006032546/README.md) my original implementation of zet cmd

Tags:

    #idea
