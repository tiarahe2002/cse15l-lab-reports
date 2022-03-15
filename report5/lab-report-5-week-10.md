[Here's](https://github.com/mBookUCSD/markdown-parse/blob/main/MarkdownParse.java) our group's MarkdownParse repository.

First, I cloned the lastest version of code for `MarkdownParse.java` and tests files. We ran `make` and ran `time bash script.sh`. Then we added some code in `script.sh` to display number of each test file. 
We changed the makefile to add compile instructions to my own markdown-parse programmed.
We saved the our output and also given output to files  by using the command `bash script.sh > results.txt` and `bash script.sh > myResults.txt`. We found the tests with different results by using `diff results.txt myResults.text > mydiffsgiven.txt`. We didn't search through manually or other programmatic idea.

## First Test: 496
The content of Test 496 is `[link](foo(and(bar))`
The expect test output is `[]`
The output of our repo is `[foo(and(bar]`
The output of Joe's repo is `[]`

The bug on our repo of this test case is that we didn't check the brackets with in the link. There are brackets within the link. And it is correct if the bracket is closed within the links. For this test case, it contains two openbrackets within the link but the outside brackets doesn't have corresponding closed bracket. And the problem of our repo is it did not detect that they had not been closed. In order to fix it, we need to add code on file to check what we are looking at and if it is an open bracket

## Second Test: 496