# Lab 5 Report - Week 10
The two tests from the 652 commonmark-spec tests that I chose are `490.md` and `495.md`. I found these two tests by running `bash script.sh` on both implementations and manually searching for differences.

![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab5-ss1.png)
The output for the provided implementation.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab5-ss2.png)
The output for my implementation.

***

## Test One - 490.md
The file contains contents:
```
[link](<foo
bar>)
```
The provided implementation outputted `[]` for `490.md`, while my implementation outputted 
    `
    [<foo
    bar>]
    `.
The expected/correct output is `[]`, so the provided implementation is correct.

This is because my implementation of MarkdownParse.java fails to recognize that a split up "link" is no longer a link.

```
int openParen = markdown.indexOf("(", nextCloseBracket);
    if(openParen < 0){
        currentIndex = nextCloseBracket + 1;
        continue;
        }
int closeParen = markdown.indexOf(")", openParen);
```
This code grabs the first open parantheses and the closed parantheses after(if they exist). There is code to account for a missing open parantheses, but there is no code to account for when the closed parantheses is on another line. To pass this test, my implementation needs an addition to this code that detects if there is an `/n` (new line).
describe bug:
show code that should be fixed:

## Test Two - 495.md
The file contains contents:
```
[link](foo(and(bar)))

```
The provided implementation outputted `[foo(and(bar))]` for `496.md`, while my implementation outputted `[foo(and(bar]`.
The expected/correct output is `[foo(and(bar))]`, so the provided implementation is correct.

My implementation of MarkdownParse.java produces an incorrect output because it does not contain code that accounts for the fact that a link must have an equal number of open and closed parantheses.

```
if(openParen == -1){
    return toReturn;
}
```

My implementation only accounts for when there is no open parantheses. Instead, it needs to have something like what the provided implementation has:

```
static int findCloseParen(String markdown, int openParen) {
    int closeParen = openParen + 1;
    int openParenCount = 1;
    while (openParenCount > 0 && closeParen < markdown.length()) {
        if (markdown.charAt(closeParen) == '(') {
            openParenCount++;
        } else if (markdown.charAt(closeParen) == ')') {
            openParenCount--;
        }
        closeParen++;
    }
    if(openParenCount == 0) {
        return closeParen - 1;
    }
    else {
      return -1;
    }
}
```

This code ups the number of open parantheses everytime it finds one and decrements this number every time it finds a closed parantheses, ensuring that there is a closed parantheses for every open parantheses. If there is not, the method returns -1, indicating that it does not have a closed parantheses that ends the link.