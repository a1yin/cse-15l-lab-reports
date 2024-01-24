# cd no commands

```  
[user@sahara ~/wavelet]$ cd
[user@sahara ~]$
```
  
* `/home/wavelet` changed back to `/home`
* There was no output because changing directories does not output anything into the terminal
* The output is not an error  

# cd directory argument

```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```

* The working directory was `/home` before it was run, and after it changed to `/home/lecture1`  
* There was no output because changing directories does not output anything into the terminal  
* It is not an error  

# cd file argument

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

* The working directory was `/home/lecture1`
* There was an output because an error showed for the command
* There is an error because we are attempting to change the directory to the location of a file, which is not a directory  

# ls no arguments

```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```

* The working directory was `/home/lecture1`
* The output included all the files and directories currently in the working directory because no arguments were given
* There is no error  

# ls directory argument
```
[user@sahara ~/lecture1]$ ls /home
lecture1
```

* The working directory was `/home/lecture1`
* The output included all the files and directories in the directory of the argument given
* There is no error  

# ls file argument
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```

* The working directory was `/home/lecture1`
* The output included just the file that was given as an argument
* There is no error  

# cat no argument

```
[user@sahara ~]$ cat

```

* The working directory was `/home`
* There was no output, but the command line will continue to take keyboard entries and print out a copy of that entry
* There is no error  

# cat directory argument
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```

* The working directory was `/home`
* There was an output because there was an error message
* There is an error because `cat` can only read files not directories  

# cat file argument

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

* The working directory was `/home`
* There was an output of the contents of the code in the file `Hello.java`
* There is no error
