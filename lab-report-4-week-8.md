# Lab 2 Report - Week 3 & 4
[My markdown-parse repository](https://github.com/yi113/markdown-parse.git)
& 
[The one I reviewed](https://github.com/iireneliao/markdown-parse.git)

## Test One
**Should produce:** ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss1.png)

**Links in the file:** google.com, google.com, ucsd.edu

**JUnit Test Code**:
``` 
    public void testTestOne() throws IOException{
        Path fileName = Path.of("lab8-test1.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> links = MarkdownParse.getLinks(contents);
        assertEquals(List.of("google.com", "google.com", "ucsd.edu"),links);
}
```

**My Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss4.png)
This test did not pass for my implementation.

**Reviewed Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss7.png)
This test did not pass for the reviewed implementation.

## Test Two
**Should produce:** ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss2.png)

**Links in the file:** a.com, a.com(()), example.com

**JUnit Test Code:**
```
    public void testTestTwo() throws IOException{
        Path fileName = Path.of("lab8-test2.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> links = MarkdownParse.getLinks(contents);
        assertEquals(List.of("a.com", "a.com(())", "example.com"),links);
    }
```

**My Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss5.png)
This test did not pass for my implementation.

**Reviewed Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss8.png)
This test did not pass for the reviewed implementation.

## Test Three
**Should produce:** ![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss3.png)

**Link in the file:** https://ucsd-cse15l-w22.github.io/

**JUnit Test Code**:
```
    public void testTestThree() throws IOException{
        Path fileName = Path.of("lab8-test3.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> links = MarkdownParse.getLinks(contents);
        assertEquals(List.of("https://ucsd-cse15l-w22.github.io/"),links);
    }
```

**My Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss6.png)
This test did not pass for my implementation.

**Reviewed Implementation:**

Output for this test:
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab4-ss9.png)
This test did not pass for the reviewed implementation.