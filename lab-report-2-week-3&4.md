# Lab 2 Report - Week 3 & 4
* **First Code Change**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss2.png)
The test file [test-file.md](https://github.com/taniachen/markdown-parse/blob/e71c46bda6f809a89e17bfdaec6f5b9bf2c1d223/test-file.md) produced this symptom.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss4.png)
The bug was that the test method could not access the MarkdownParse class or its methods. The symptom is shown in the screenshot above - MarkdownParse could not be found; it was produced when attempting to compile using ```javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java``` after writing this tester method:
    ```
    public void testGetLinks() throws IOException{
        Path fileName = Path.of("test-file.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> linkOne = getLinks(contents);
        ArrayList<String> linkOne = MarkdownParse.getLinks(contents);
        assertEquals("[https://something.com, some-page.html]", linkOne.toString());
    }
    ```
    To test those methods, I copied them over to the tester file and accessed them that way.

* **Second Code Change**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss3.png)
The test file [testFile3.md](https://github.com/taniachen/markdown-parse/blob/e71c46bda6f809a89e17bfdaec6f5b9bf2c1d223/testFile3.md) produced this symptom.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss5.png)
The bug was the getLinks() method being unable to grab everything within the parantheses that kept a link inside. This was because it only grabbed the first closing parantheses that occurred after an opening parantheses. This tester method:
    ```
    public void testGetLinksFe() throws IOException{
        Path fileName = Path.of("testFile3.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> linkOne = getLinks(contents);
        assertEquals("[https::look parentheses()]", linkOne.toString());
    }
    ```
    uses the aforementioned test file, which has two closing parantheses, causing the error of discluding the second parantheses.

* **Third Code Change**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss6.png)
The test file [testFile4.md](https://github.com/taniachen/markdown-parse/blob/e71c46bda6f809a89e17bfdaec6f5b9bf2c1d223/testFile4.md) produced this symptom.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab2-ss7.png)
The bug was similar to the previous bug - the getLinks() method could not grab everything in the first opening parantheses and last closing parantheses in one line, resulting in faulty returns. The test file used in this method:
    ```
    public void testGetLinksFour() throws IOException{
        Path fileName = Path.of("testFile4.md");
	    String contents = Files.readString(fileName);
        ArrayList<String> linkOne = getLinks(contents);
        assertEquals("[www.youtube.com, www.google.com, www.amazon.com()()()()()()()()()()()()]", linkOne.toString());
    }
    ```
    brought out the issues because it has a ton of closing brackets. This was fixed by changing the code to detect new lines and multiple parantheses on the last line, changing the return value if there were.