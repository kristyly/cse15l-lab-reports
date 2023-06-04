# Lab Report 5
## Part 1 – Debugging Scenario
What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?

I am on the Windows operating system, VSCode.

Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.

![Image](4.13.jpg)

I get an error on all of my JUnit tests.

Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.

The failure-inducing input is the JUnit compiler for all files ending in .java in lab3. `javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java` I have all of lib in my lab and I am currently logged into my ieng6 computer.

