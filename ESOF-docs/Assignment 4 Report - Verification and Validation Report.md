# Verification and Validation

##Introduction:
Throughout this report, we will be analysing the software testing of our project.

Firstly, we will report to the software Testability and reviews. That is, the controllability, observability, isolateability, separation of concerns, understandability, heterogeneity.

Secondly, we will analyze code statistics about this project, based on a codacy report.

Finally, we will show the process of correcting a bug in our project, followed by the contributions of each member of this group.

##Software Testability and Reviews:

Throughout the analysis of this Project, we gathered some information about it's test capacity.

About controlabillity we can say the the test is fast, but at the same time it's not easy to control the components that are being tested because of the speedy of processing and the dependencies. 

As observability, using the android studio software, is possible to see the operations of test through the “Event Log” and “Gradle Console”.

In isolability we can test the components and functions to see if the software will work right.

The componets that have specific functions for the operation of the program: if they aren’t working right, it may cause problems during the execution of program.

For the comprehensibility of the application it was necessary to exchange emails and information with developers in order to get explanations about the testing suit.

In the end, is possible to conclude that the methods used for the application test are dependent on the technology used, in others words, different test need different approaches.

##Test Statistics and analytics:

Despite saying that new features must have Unit tests that must be passing, we did not find any of those in the repository.
In consequence of that fact, we will be analysing the codacy report of our project.

Our project certification follows a classification of B, which is not bad for an open source project.

![codacy report] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/codacy_report.png)

Despite that fact, there is a very high percentage of unused code (54%), this derives from the fact that there are many unused contructors, private variables which could be replaced by local variables, as we can see in the following images.

![unused code1] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/unused_code1.png)

![unused code2] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/unused_code2.png)

![unused code3] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/unused_code3.png)

Code style follows a high percentage (89%), which is good for an open source project, since there are many people collaborating from different backgrounds, maintaining a code pattern might be difficult and might demand some specification from developers so that this goal can be achieved.

Some of these issues have to do with long methods, package names containing upper case characters. method names starting with capital letters. As seen below:

![code style1] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/code_style1.png)

![code style2] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/code_style2.png)

![code style3] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/code_style3.png)

![code style4] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/code_style4.png)

Although, error prone shows a percentage of 0%, it makes a hole 50% of the Issues Breakdown, consisting in 259 error prone issues, as we can see in the graphic of our codacy report.

Most of this error prone issues are about avoiding unused imports, using explicit scoping instead of the default package private level. As we can see below:

![error prone1] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/error_prone1.png)

![error prone2] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/error_prone2.png)

Finally, we can analyse some grafics about issue severity, and project quality.

Analyzing the issue severity graphic, we can see the percentage of infos (27.2%), related with code styles and how these types of issues can influence the afect the code readability. As we have seen these fact is not very worrisome. We can also see the percentage of warnings (51,9%) and errors (20,8%). These types of errors need more attention since these issues can affect the maintainability of the project.

![issue severity graphic] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/code_severity.png)

Analyzing the project graphic, we see the number of files with the respective grade. As we can see there are a very low percentage of C and D files, and a very high percentage of A graded files (83,3%) which is a very good sign, showing organization and discipline.

![project quality graphic] (https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/project_quality.png)

##Bug Report:
The issue we found and chose to resolve is listed as the <a href="https://github.com/duckduckgo/android/issues/274" target="_blank">#274</a>.

The bug could be reproduced by activating the "Enabling Tor" toggle in the settings page, leaving the settings page and then deactivating it. Through the Orbot notification message we could see that it was still being used.

We updated the code in order to disable the proxy setting when the toggle was disabled. While that was supposed to fix the problem, it seems that the library (Orbot) isn't disabling the proxy correctly once it has been set. So, in order to make it work, a dialog was added informing the user that the application should be restarted in order to completely disable Tor, and adding the option to automatic restart the application.

A pull request was added with the id <a href="https://github.com/duckduckgo/android/pull/275" target="_blank">#275</a>. 

##Contributions:
Filipe Coelho ( @Fr0sk ) has contributed in:
* Software Testability and Reviews
* Identify a new bug and correct a bug
* Bug Report

Luís Cruz ( @Luis-bcruz ) has contributed in:
* Introduction of verification and validation
* Test Statistics and analytics.

Shivam Agrawal ( @shivam-agr ) has contributed in:
* Test Statistics and analytics.

Vinicius Ferretti ( @ViniciusFerretti ) has contributed in:
* Software Testability and Reviews
