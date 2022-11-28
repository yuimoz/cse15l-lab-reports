# **LAB REPORT: GRADING SCRIPT**

In this lab report, I will be demonstrating the behavior of my `grade.sh` grading script on multiple sample student submissions. 

## **PART 1: MY GRADING SCRIPT** 
```
set -e
$CPATH = ".:lib/hamcrest-core-1.3.jar/junit-4.13.2.jar"

rm -rf student-submission
git clone $1 student-submission
cd student-submission/

if [[-f "ListExamples.java"]]
    echo "ListExamples.java submitted! Correct file." + \n +
    "Correct File Submission: 1.0/1.0"
else
    echo "Wrong file submitted. Need to submit ListExamples.java.
    WRONG FILE!" + \n + "Wrong File Submission: 0.0/1.0"
    exit 1
fi

if [[$? -eq 0]]
then 
    echo "COMPILE SUCCESS"
else 
    echo "COMPILE ERROR"
    exit 1
fi 

javac -cp $CPATH *.java
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > results.txt 
```
## **PART 2: DEMONSTRATING BEHAVIOR WITH SAMPLE STUDENT SUBMISSIONS (INCOMPLETE/NOT WORKING)**


* **EXPLAINING THE PART WHERE I GOT STUCK (ERROR 1)**:

![Error1](https://user-images.githubusercontent.com/114317681/204247062-aa6afe4c-9bdd-4019-8dee-9379107b8888.png)

* For this, I tried running my `grade.sh` on a sample student repository, but I kept getting this error about a particular command `'\r'` not found, as we can see in the screenshot. I went on Piazza and saw a post saying what you should do to fix this ( [@507](https://piazza.com/class/l7pbb88wlepvh/post/507) ). I tried doing what the person specified (going on the terminal, clicking the + sign, the down arrow, and selecting `bash` in the terminal.) However, upon doing this, I got yet another error (shown below).


* **EXPLAINING THE PART WHERE I GOT STUCK (ERROR 2)**: 

![Error2](https://user-images.githubusercontent.com/114317681/204248583-4ab19282-15ff-43aa-8b6d-c445a01c7aef.png)

* I am not sure what to do here. I thought it might have been because I was running `grade.sh` in my local server through `bash`, but even if I try switching to the remote server while in `bash`, I will get the error I described above. This is where I got stuck. 





## **➤ EXPECTING COMPLETION AND FIXES!!!**
