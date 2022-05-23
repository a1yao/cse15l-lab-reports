# Week 8 Lab 4

My markdown-parse repository [link](https://github.com/Sking56/markdown-parser)

Week 7 markdown-parse repository [link](https://github.com/colecarter96/markdown-parser)

## Snippet 1

Should produce 
```
[`google.com]
```

Code for test:
```
@Test public void labTest1() throws IOException {
        String content = "`[a link`](url.com)\n\n[another link](`google.com)`\n\n[`cod[e`](google.com)\n\n[`code]`](ucsd.edu)";
        assertEquals(List.of("`google.com"), MarkdownParse.getLinks(content));
    }
```
Did not pass on my implementation.
```
java.lang.AssertionError: expected:<[]> but was:<[page.com]>
```


Did not pass on Week 7 implementation.
```
java.lang.AssertionError: expected:<[`google.com]> but was:<[url.com, `google.com, google.com, ucsd.edu]>
```

## Snippet 2

Should produce
```
[a.com(()), example.com]
```

Code for test:
```
@Test public void labTest2() throws IOException {
        String content = "[a [nested link](a.com)](b.com)\n\n[a nested parenthesized url](a.com(()))\n\n[some escaped \\[ brackets \\]](example.com)";
        assertEquals(List.of("a.com(()))", "example.com"), MarkdownParse.getLinks(content));
    }
```

Did not pass on my implementation.
```
java.lang.AssertionError: expected:<[a.com(())), example.com]> but was:<[a.com, a.com((, example.com]>
```

Did not pass on Week 7 implementation.
```
java.lang.AssertionError: expected:<[a.com(())), example.com]> but was:<[a.com, a.com((, example.com]>
```

## Snippet 3

Should produce
```
[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]
```

Code for test:
```
@Test public void labTest3() throws IOException {
        String content = Files.readString(Path.of("C:/Users/antho/OneDrive/Documents/GitHub/markdown-parser/labTest3.md"));
        assertEquals(List.of("https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule"), MarkdownParse.getLinks(content));
    }
```

Did not pass on my implementation.
```
java.lang.AssertionError: expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
    https://www.twitter.com
,
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
, github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



]>
```

Did not pass on Week 7 implementation.
```
java.lang.AssertionError: expected:<[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]> but was:<[
    https://www.twitter.com
,
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
, github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



]>
```

## Answer to Questions:

Yes, there is a code change that would allow my program to work for snippet 1 and all related cases with backticks. I would simply need to impelment code that would check for complete brackets and parenthesis and check if there is anything in front of the brackets. 

Yes, there is a code change that would allow my program to work for snippet 2 and all related cases with nested parentheses, brackets and escaped brackets. I would simply have to implement code that would help me check for correct pairs of open and closed brackets/parenthesis, possibly using a data structure like a stack or a heap. 

Yes, there is  a small code change that would allow my program to work for snippet 3 and all related cases with that have new lines in brackets and parenthesis. Looking at the CommonMark demo site, we can observe that for a hyperlink to properly display in .md formatting, the content inside the brackets and parenthesis can only contain at most one new line. Thus, we can simply parse between our brackets and parenthesis and count the number of `\n` to determine if it is a viable link insertion or not. 



