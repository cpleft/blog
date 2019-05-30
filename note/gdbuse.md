# preliminary use of GNU gdb

We can use gdb for debugging.  GNU gdb is free software developed by Free
Software Foundation, Inc.  And it is a powerful commandline tool for 
debugging in the linux operating system.

Here is a collection of the most frequently used command:

| command            | abbreviation | describe                                                      |
| ---------          | ------       | ----------                                                    |
| list               | l            | list programe source code                                     |
| run                | r            | run the program                                               |
| break [lineNumber] | b            | make a breakpoint                                             |
| step               | s            | execute next line(inside function)                            |
| next               | n            | execute next line(skip function)                              |
| print [variable]   | p            | print the variable value                                      |
| display            | disp         | trace the variable, display its value on each step            |
| continue           | c            | continue to run the program until next breakpoint encountered |
| kill               | k            | terminate the running program                                 |
| quit               | q            | quit                                                          |
