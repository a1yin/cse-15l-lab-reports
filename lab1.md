```
[user@sahara ~]$ cd
[user@sahara ~]$
```
1. ```/home```
2. There was no output because the command does not change the working directory as there were no arguments given to the command line, and the command naturally does not output anything anyway.
3. The output is not an error
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
1. The working directory was ```/home``` before it was run, and after it changed to ```/home/lecture1```
2. There was no output because changing directories does not output anything into the terminal
3. It is not an error
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
1. The working directory was ```/home/lecture1```
2. There was an output because an error showed for the command
3. There is an error because we are attempting to change the directory to the location of a file, which is not a directory
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
1. The working directory was ```/home/lecture1```
2. The output included all the files and directories currently in the working directory because no arguments were given
3. There is no error
```
[user@sahara ~/lecture1]$ ls /home
lecture1
```
1. The working directory was ```/home/lecture1```
2. The output included all the files and directories in the directory of the argument given
3. There is no error
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
1. The working directory was ```/home/lecture1```
2. The output included just the file that was given as an argument
3. There is no error
```
[user@sahara ~]$ cat

```
1. The working directory was ```/home```
2. There was no output, but the command line will continue to take keyboard entries and print out a copy of that entry
3. There is no error
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
1. The working directory was ```/home```
2. There was an output because there was an error message
3. There is an error because ```cat``` can only read files not directories
```
[user@sahara ~]$ cat lecture1/Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
```
1. The working directory was ```/home```
2. There was an output of the contents of the code in the file ```Hello.java```
3. There is no error
