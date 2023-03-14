# Lab Report 5

## Lab Report 4 Redone with a Bash Script

After logging into ieng6, I can run a bash script with the commands that complete each of the challenge tasks. This would be much faster than manually entering all the commands needed for the challenge tasks, as everything is automatically run through the script.

These commands would include git commands, such as git clone and git commit, file editor commands, such as sed -i, and the commands needed to run the junit tests in ListExamplesTests.java

The bash script I created to complete the challenge tasks looks like this:

    git clone git@github.com:YashRavipati1/lab7Y.git
    cd lab7Y

    javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

    java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

    sed -i .bak "s/result.add(0, s);/result.add(s);/" ListExamples.java
    sed -i .bak '43s/.*/index2+=1;/' ListExamples.java

    javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

    java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

    git add ListExamples.java
    git commit -m "hello"
    git push


This was the terminal output from running the bash script: 
![image](https://user-images.githubusercontent.com/63521936/224871887-da20c27f-a934-4af8-b31b-9a6255b7484c.png)

The total runtime was about 4 seconds, with most of this time due to the git clone and git push commands (as these have to interact with the remote repository).
This was much faster than my time during the competition, proving how useful bash scripts can be in improving efficiency/speed.
