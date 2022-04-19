## CSE15L Lab Reports (Spring 2022)

# Lab Report 2 W4
This lab report will cover bug fixes to a previous git project.

# Change No.1
The first thing that our group thought of was what would happen if the link had a parentheses. As to be expected when passing in [this file](https://github.com/Badflar/markdown-parser/blob/main/test-file2.md), we get the following output

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20150424.png?raw=true)

And so to remedy this, we added a check to make sure that the next character was either a space or an open bracket as a link cannot have a space and the open bracket signifies a new embed.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20145627.png?raw=true)

# Change No.2
A more simpliar problem that if the [markdown file](https://github.com/Badflar/markdown-parser/blob/main/test-file3.md) had no links, there would be an out of bounds error.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20151324.png?raw=true)

To fix this we just added a simple line of code that would break the loop if it could not find anything that would signify the start of a link.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20152714.png?raw=true)

# Change No.3

Finally if there was just [text in brackets but no link](https://github.com/Badflar/markdown-parser/blob/main/test-file4.md), the code would also break by going out of bounds again.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab2/Screenshot%202022-04-19%20153356.png?raw=true)

So to fix this we did a similar thing as in "Change No.2" but skip if theres no open parentheses after a closed bracket.
