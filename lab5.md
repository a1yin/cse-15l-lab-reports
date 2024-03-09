# Part 1 - Debugging Scenario

## 1. Edstem Post
For my autograder script, my original script works on my native terminal, but when I try to run the same script on the Edstem workspace, I get this error about 'cannot find symbol'. How do I fix this and why am I getting this error? - Student
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/4b1a8ac4-8bab-471e-822f-dda78ef7f822)

- The test java file I'm using for the script
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/9a4f280b-0da8-473e-b783-2d53c73212f9)

- The bash script that I am running
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/bc87b6bf-3887-44e6-b22d-a3d433ce3585)

## 2. TA Response
Hello Student,
It seems there is an issue with your JUnit class path. Remember, the Edstem space uses the Mac version of the JUnit class path. Please refer to https://ucsd-cse15l-w24.github.io/week4/index.html for more information on how to set up JUnit in your script - TA

## 3. Description of Bug
The student went to the link and switched the JUnit path in lines 21 and 33 to the one detailed for MAC users: 
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/62c59f5d-1a81-4cb5-96cd-aedd586808f2)
The resulting running of the script:
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/e69475f0-997f-40a5-a536-1d0b910ae831)
Yay it works! The bug was the result of using the Windows path to JUnit on a Mac machine, which caused the script to not import JUnit correctly and resulting in errors where certain JUnit specific classes and methods to not be found.

# Part 2 - Reflection
One thing I thought was interesting was bash scripting and using libraries like JUnit to incorporate for instance the autograding script. I thought the intersection of these topics really demonstrates the possibilities of writing scripts for automation and other applications to make life easier. 
