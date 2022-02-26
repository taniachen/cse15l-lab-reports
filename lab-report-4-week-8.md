# Lab 2 Report - Week 3 & 4
[My markdown-parse repository](https://github.com/yi113/markdown-parse.git)
& 
[The one I reviewed](https://github.com/iireneliao/markdown-parse.git)

## Test One
Should produce: ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss1.png)

Links in the file: google.com, google.com, ucsd.edu

Code:
``` public void testTestOne() throws IOException{
        Path fileName = Path.of("lab8-test1.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> links = MarkdownParse.getLinks(contents);
        assertEquals(List.of("google.com", "google.com", "ucsd.edu"),links);
    }
```

**My Implementation:**

**Reviewed Implementation:**

## Test Two
Should produce: ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss2.png)

Links in the file: a.com, a.com(()), example.com

Code:

**My Implementation:**

**Reviewed Implementation:**

## Test Three
Should produce: ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss3.png)

Link in the file: https://ucsd-cse15l-w22.github.io/

Code:

**My Implementation:**

**Reviewed Implementation:**