## CSE15L Lab Reports (Spring 2022)

# Lab Report 4 W8
This lab report will be covering different implementations of the markdown parser.

My markdown parser: https://github.com/Badflar/markdown-parser

Other's markdown parser: https://github.com/calistajlee/lab6-markdown-parser

## Snippet 1

The output the code should produce is:

[url.com, google.com, google.com, ucsd.edu]

To test the code, I made the following test to both projects:

![ADD IMAGE]

My Code:

![Add IMAGE]

Other's Code:

![ADD IMAGE]

One thing that might help to fix this is instead of relying the there first being an open and closed bracket is to find text inbetween parenthesis and use a regex to test if this string is a link. The regex would be super long but it would still technically be one line of code.

## Snippet 2

The output the code should produce is:

[a.com, b.com, a.com, example.com]

To test the code, I made the following test to both projects:

![ADD IMAGE] 

My Code:

![ADD IMAGE]

Other's Code:

![ADD IMAGE]

This would be a similar solution to Snippet 1; using regex and discarding brackets. The problem here arises with "(a.com(()))." The character index where the link finishes technically is before the clothes parenthesis. So that would take probably more lines of code to test to see where the link properly ends.

## Snippet 3

The output the code should produce is:

[https://www.twitter.com, https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule, https://cse.ucsd.edu/] 

To test the code, I made the following test to both projects: 

![ADD IMAGE]

My Code:

![ADD IMAGE]

Other's Code:

![ADD IMAGE]

This would only take a few lines of code. The problem here is the line breaks and the simple solution would to be to ignore line breaks. 