## CSE15L Lab Reports (Spring 2022)

# Lab Report 2 W4
This lab report will cover bug fixes to a previous git project.

# Change No.1
The first thing that our group thought of was what would happen if the link had a parentheses. As to be expected when passing in [this file](https://github.com/Badflar/markdown-parser/blob/main/test-file2.md), we get the following output

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20150424.png?raw=true)

And so to remedy this, we added a check to make srue that the next character was either a space or an open bracket as a link cannot have a space and the open bracket signifies a new embed.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20145627.png?raw=true)
