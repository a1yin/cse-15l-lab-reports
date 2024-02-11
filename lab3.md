# Part 1
### Failure Inducing Input JUnit Test
```
public void testReversed2() {
    int[] input1 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
```
### Associated Code (from ArrayExamples)
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

### Non-failure inducing Input JUnit Test
```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```
### Output
![image](lab3part1output)

### Bug Before Code
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
### Bug After Code-Fix
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
* This fix addresses the bug in the `reversed()` method because the previous method put the zero elements from the new array to the old array, which should be the opposite where we put the elements from the back of the original list into the beginning of the new array, returning this new array instead of the old one

# Part 2 (find command)

## -type
### Files
```
find ./technical -type f
./technical/plos/pmed.0020237.txt
./technical/plos/pmed.0020238.txt
./technical/plos/pmed.0020239.txt
./technical/plos/pmed.0020242.txt
./technical/plos/pmed.0020246.txt
./technical/plos/pmed.0020247.txt
./technical/plos/pmed.0020249.txt
./technical/plos/pmed.0020257.txt
./technical/plos/pmed.0020258.txt
./technical/plos/pmed.0020268.txt
./technical/plos/pmed.0020272.txt
./technical/plos/pmed.0020273.txt
./technical/plos/pmed.0020274.txt
./technical/plos/pmed.0020275.txt
./technical/plos/pmed.0020278.txt
./technical/plos/pmed.0020281.txt
```
### Directories
```
$ find ./technical -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
* This option will allow us to specify what exactly we are looking for, whether it be files, directories or something else, we can filter out other types we don't need
## -name
### Directories
```
$ find ./technical -name "bio*"
./technical/biomed
```
### Files
```
$ find ./technical -name "*txt"
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-8.txt
./technical/911report/chapter-9.txt
```
* This allows us to search for files or directories with a certain pattern in their names or extensions, we can find all files with an extension or naming pattern
## -size
### Files
```
$ find ./technical -size +100k
./technical/911report/chapter-1.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/biomed/1471-2105-3-2.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/d0269g.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/government/Gen_Account_Office/gg96118.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/im814.txt
./technical/government/Gen_Account_Office/May1998_ai98068.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
```
### Directories
```
$ find ./technical -size -50k -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
* This option allows you to find files and directories based on their size, which can useful if we want to find certain files or directories of a certain range of sizes
## -mtype
### Files
```
$ find ./technical -mtime -7 -type f
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
```
### Directories
```
$ find ./technical -mtime -7 -type d
./technical
./technical/911report
./technical/biomed
./technical/government
./technical/government/About_LSC
./technical/government/Alcohol_Problems
./technical/government/Env_Prot_Agen
./technical/government/Gen_Account_Office
./technical/government/Media
./technical/government/Post_Rate_Comm
./technical/plos
```
* This option allows us to specify the modification time, which can be useful if we want to find something modified something a long ago or recently

# Sources (ChatGPT)
### Prompt
* give me four interesting command-line options for 'find', using examples for files and directories, and explain how they are useful
### Output
```

Sure, let's explore the find command. Here are four interesting command-line options for find:

-type option: This option allows you to specify the type of file you want to search for, such as regular files, directories, symbolic links, etc.

Example 1: Find all regular files in the current directory and its subdirectories:

bash
Copy code
find ./technical -type f
Example 2: Find all directories in the current directory and its subdirectories:

bash
Copy code
find ./technical -type d
This is useful when you want to filter search results based on the type of file.

-name option: This option allows you to search for files with a specific name or pattern.

Example 1: Find all files with the name "README.md" in the current directory and its subdirectories:

arduino
Copy code
find ./technical -name "README.md"
Example 2: Find all files with names starting with "file" in the current directory and its subdirectories:

arduino
Copy code
find ./technical -name "file*"
This is useful when you want to find files with specific names or patterns.

-exec option: This option allows you to execute a command on each file found by find.

Example 1: Print the absolute path of each file found:

bash
Copy code
find ./technical -exec echo {} \;
Example 2: Delete all files with the extension ".tmp":

bash
Copy code
find ./technical -name "*.tmp" -exec rm {} \;
This is useful when you want to perform actions on the files found by find.

-mtime option: This option allows you to search for files based on their last modification time.

Example 1: Find files modified in the last 7 days:

arduino
Copy code
find ./technical -mtime -7
Example 2: Find files modified more than 30 days ago:

arduino
Copy code
find ./technical -mtime +30
This is useful when you want to find files based on their age or recent modifications.
```
### Prompt
* use other options
### Output
```
Certainly! Let's explore two more options for the find command:

-size option: This option allows you to search for files based on their size.

Example 1: Find all files greater than 1 megabyte in size:

sh
Copy code
find ./technical -size +1M
Example 2: Find all files smaller than 100 kilobytes in size:

sh
Copy code
find ./technical -size -100k
This is useful when you want to filter files based on their size, which can help manage disk space or find specific types of files.

-user option: This option allows you to search for files owned by a specific user.

Example 1: Find all files owned by the user "john":

sh
Copy code
find ./technical -user john
Example 2: Find all files owned by the current user:

sh
Copy code
find ./technical -user $(whoami)
This is useful when you want to find files owned by a particular user, which can be helpful for managing permissions or identifying files associated with specific users
```
## How I Used ChatGPT Output
* For each option ChatGPT gave me, I used the command to input into my bash to observe the output
* I also used the description of the options to formulate my understanding of the command to write it's use cases in the lab report
* I asked for more options because the -exec option seemed hard to explain, and because one of the outputs was about deleting files, something I did not want to do

