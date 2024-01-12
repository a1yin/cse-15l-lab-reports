```  
[user@sahara ~]$ cd
[user@sahara ~]$
```  
* ```/home```  
* There was no output because the command does not change the working directory as there were no arguments given to the command line, and the command naturally does not output anything anyway.  
* The output is not an error  
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
* The working directory was ```/home``` before it was run, and after it changed to ```/home/lecture1```  
* There was no output because changing directories does not output anything into the terminal  
* It is not an error  
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
* The working directory was ```/home/lecture1```
* There was an output because an error showed for the command
* There is an error because we are attempting to change the directory to the location of a file, which is not a directory  
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
* The working directory was ```/home/lecture1```
* The output included all the files and directories currently in the working directory because no arguments were given
* There is no error  
```
[user@sahara ~/lecture1]$ ls /home
lecture1
```
* The working directory was ```/home/lecture1```
* The output included all the files and directories in the directory of the argument given
* There is no error  
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
* The working directory was ```/home/lecture1```
* The output included just the file that was given as an argument
* There is no error  
```
[user@sahara ~]$ cat

```
* The working directory was ```/home```
* There was no output, but the command line will continue to take keyboard entries and print out a copy of that entry
* There is no error  
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
* The working directory was ```/home```
* There was an output because there was an error message
* There is an error because ```cat``` can only read files not directories  
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
* The working directory was ```/home```
* There was an output of the contents of the code in the file ```Hello.java```
* There is no error
