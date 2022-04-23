# Week 4 Lab 2

## First Code Change

![codeChange1](codeChange1.PNG)

[Failure-Inducing Input](https://github.com/Sking56/markdown-parser/commit/ee4f5e52e3371bffd4c01c796502c5bd97b3deb2)

Symptom of failure-inducing input:
```
Exception in thread "main" java.nio.file.NoSuchFileException: new-file.md
```

The issue with the failure-indcuing input was that it had a new line after it's last character. In the original code we had, the while loop would loop infinitely because the current index would not be able to increment past markdown.length due to this new line in the file. 

## Second Code Change

![secondCodeChange](secondCodeChange.PNG)

[Failure-Inducing Input](https://github.com/Sking56/markdown-parser/commit/7f0cdc8f1b319166ae710b8eff0ef7e8116ed04b)

Symptom of failure-inducing input:
```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException:
begin 0, end -1, length 11
```

In the failure-inducing input, the text does not contain any parenthesis after the brackets and thus nothing should output. However, because .indexOf() returns -1 when the character is not present, closeParen is set to -1 and thus results in the symptom of an OutOfBoundsException beacuse -1 is out of bounds when called as an arg for .substring(). 

## Third Code Change

![thirdCodeChange](thirdCodeChange.PNG)

[Failure-Inducing Input](https://github.com/Sking56/markdown-parser/commit/f44b58ba229dbb78ccfec04fb6106581a73ab687)

Symptom from failure-inducing input:

```
[Something]
```

The failure-inducing input is missing a close bracket and thus should not print anything as that is not a proper way to implement a url into a .md file. Because our code will still search for a open parenthesis and close parenthesis even if the close bracket is missing (-1 integer value), the .substring will still find the "something" and output it, even when nothing should output.