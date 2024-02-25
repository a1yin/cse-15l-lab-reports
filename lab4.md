## 4. Log into ieng6
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/3ced4bdc-05fd-4540-acf1-d5f96193042e)
* `<up><up><up><enter>`
* The command: `ssh a1yin@ieng6-201.ucsd.edu` was 3 up in the command history, and since I set up the public key already for this machine, the ieng6 login did not require a password

## 5. Clone your fork of the repository from your Github account (using the SSH URL)
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/24039d65-d1b9-4ebd-85a5-69d6aef2cbfd)
* git clone `<control>` v `<enter>`
* I copied the SSH URL for the repository which was already set up for ieng6, so this is simply cloning that URL.

## 6. Run the tests, demonstrating that they fail
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/53cca20c-d925-43e4-a9c3-1c3ed282897e)
* cd l `<tab>` `<enter>`, bash t `<tab>` `<enter>`
* Here I have to change my working directory to the cloned repository, so I used the cd command then typed only l then <tab> to autocomplete the full directory name. I then did a similar process using the bash command and pressing only t then tab to autocomplete the file `test.sh`

## 7. Edit the code file to fix the failing test
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/60481522-f59e-4c0d-9624-bfa4f7e59904)
* vim L `<tab>` . `<tab>` `<enter>`, ?x `<right-arrow>` r2, :wq
* To vim into `ListExamples.java`, we can type just L, then tab to become ListExamples(since there is another file named `ListExamplesTests.java`, then type . and tab to finish java. In vim, using ?x will find the last instance of the letter x, which will move the cursor directly to index1 that we have to change. Shifting the cursor once to the right, we can press r2 to change the 1 to a 2. Lastly, we use :wq to save and exit the file.

## 8. Run the tests, demonstrating that they now succeed
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/125bd7cd-670c-4eba-a38e-38ec87c17865)
* bash t `<tab>` `<enter>`
* Similar to how we ran the tests the first time, we just have to write the command bash then type t <tab> to autocomplete the file `test.sh` and enter to run the working tests

## 9. Commit and push the resulting change to your Github account (you can pick any commit message!)
![image](https://github.com/a1yin/cse-15l-lab-reports/assets/156368444/1e98733e-5967-4d52-beaf-5519f961d812)
* git add ListExamples.java `<enter>`, git commit -m "ListExamples fix" `<enter>`, git push `<enter>`
* To create a commit we have to first git add the changed file, so that is `ListExamples.java` in this case, we then can create a commit with -m for a message relating to the commit. Lastly, we can git push to the main branch the changes

