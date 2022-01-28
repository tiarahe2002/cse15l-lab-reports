## First Code change

**Screenshoot of code change**

The screenshot below shows the change of `MarkDownParse` code. We added a line to printout the `currentIndex` and causes a infinite loop.
![image](change1.png)

**Link to the test file**

We added several empty lines in [test file 2](https://github.com/tiarahe2002/markdown-parse/blob/main/test-file2.md).  
And the output looks like:
![image](bug1.png)

Because the empty lines will cause the `currentIndex` be less than the length of file so that the while loop is non-stop and keep print out the `currentIndex`. In order to fix this infinite bug, we set a `if` condition so if system didn;t find any more brackets or parentheses after the last closed bracket, the loop will break.

## Second Code change

**Screenshoot of code change**

The screenshot below shows the second change of `MarkDownParse` code. 
![image](change2.png)

**Link to the test file**

We added an fake link in [test file 3](https://github.com/tiarahe2002/markdown-parse/blob/main/test-file3.md). This image link should not appear on the output.
But the output looks like:
![image](bug2.png)


Because the original code get the link according to the position of brackets and parentheses. But an image link contains the same format. The only difference is an image link has "!" before the brackets. So we added an `if` condition to check the "!" before the brackets.

## Third Code change

**Screenshoot of code change**

The screenshot below shows the third change of `MarkDownParse` code. 
![image](change3.png)

**Link to the test file**

We added a fake link in [test file 4](https://github.com/tiarahe2002/markdown-parse/blob/main/test-file4.md). This fake link should not appear on the output too.
But the output looks like:
![image](bug3.png)


Because the original code get the link according to the position of brackets and parentheses. But an fake link contains the same thing. And also the `if` statement before can't detect this fake link. So we add another `if`statement that if the link does't contain `.com` or `.html` between the parentheses, then it will not display on the output.