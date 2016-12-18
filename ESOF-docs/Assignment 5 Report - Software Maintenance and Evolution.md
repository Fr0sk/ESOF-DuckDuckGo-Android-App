#ESOF 2016/2017 - Assignment 5: Software Maintenance/Evolution

##Software Maintainability using the SIG metrics 
[![BCH compliance](https://bettercodehub.com/edge/badge/Fr0sk/ESOF-DuckDuckGo-Android-App)](https://bettercodehub.com)

To analyse the software mainatinability we resort to an online code analysis tool called [Better Code Hub](https://bettercodehub.com). With it we could easily see the weak spots of your project concerning bad coding practices. 

Starting with writing short and concise units of code, with functionality well defined and splitted, our project got a negative score. While the tool states that units should be less of 15 lines of code, we think that for an android application, in some cases it's easy to pass that mark, specially in event handlers with anonymous functions. Still, arround 60 units had more than 30 lines of code, with the worst having 139 lines, which is a big concerning and should be reviewed in order to get a better code organization. This would also improve unit tests that could focus on smaller and more specific tasks with smaller pieces of code.

![Short Units of Code](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Short%20Units%20of%20Code.PNG)

<br>

Continuing in a related topic, the score this project got on simple units of code was also negative. In simple units of code it's expected to keep branch points (for, if, while, etc) below 5 per unit. We think this could be easily achivable, by splitting the logic through several different units. The worst unit has 26 branch points, which is a lot more than it should.

![Simple Units of Code](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/SImple%20Units%20of%20Code.PNG)

<br>

Regarding code reuse, the project also got a negative score. Having duplicate code is bad because it makes the application bigger, more cluttered and more error prone, since bugs have to be corrected in multiple sides, some of which often get forgot. Going through the duplicates found, we saw some that might not entirely fit in this category, as they perform similar tasks but at different places. So in some cases, one can understand the duplicate code, but sure some work could be done in that way, by dividing in smaller parts that could perform more stripped down tasks and then be reused in the required parts.

![Write Code Once](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Write%20Code%20Once.PNG)

<br>

Next topic is about using several arguments in one method. While this isn't entirely bad, it makes the code harder to read and debug. It also involves more work if the need to add one or more fields appear. This can be avoided by grouping related data members in some kind of data structure. Opting for this way also facilitates debuging, which can be done per object, and even some client/server communications, where entire objects can be parsed at once.
At this topic this project also got a negative score. This score is valid, since there are several methods that have more than 4, with the worst having 12 parameters.

![Keep Unit Interfaces Small](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Keep%20Unit%20Interfaces%20Small.PNG)

<br>

About the separate concerns in modules, the score was one more time negative. Separate concerns in modules avaluates how many calls from different sources are made to a specific object. In the case of this application, it is quite common to have many different modules calling each other, specially for the database class, which was reported as the worst, but a necessary, and somewhat useful "evil".

![Separate Concerns in Modules](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Separate%20Concerns%20in%20Modules.PNG)

<br>

The next validation checks if components do a specific function on themselves and those funcions get called from top level components. When they don't (the lower level components make calls to other low/high level components) testing and maintenance becomes more difficult because the components do not behave isolatedly. This application does that very well, having here it's first positive score from the test.

![Couple Architecture Components Loosely](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Couple%20Architecture%20Components%20Loosely.PNG)

<br>

This next topic evaluates how balanced the number of components its relative size. When this is the case it is much easier to locate code. Relative to the analysis tool, it is better to keep the number of components between 2 and 12, and ensure the components are of approximately equal size (component size uniformity stays below the 0.71). Passed the check with a second positive score.

![Keep Architecture Components Balanced](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Keep%20Architecture%20Components%20Balanced.PNG)

<br>

Another important subject is keeping the codebase small. This improves the software maintainability by having less code to do the same functions. In order to achieve this one should use libraries that are proven to achieve the pretended functionality instead of developing their own from the scratch. According to the analysis tool, this should be kept bellow 20 man-years, which this project is much far away from, granting the 3rd positive score.

![Keep Codebase Small](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Keep%20Codebase%20Small.PNG)

<br>

Automate testing has an important role in software deveolpment, by making code changes less risky and keeping the application more bug-free. At least it can check if new additions or bug fixes don't break something already working before, and thus making it harder to finding the error. This is becoming a common practice, specially in open source projects, and it improves community contribution and development workflow by validating each change everyone makes. At this, the application completely, as it doesn't have any automated testing working, and the only test written is outdated and covers almost nothing of the source code and software functionality.

![Automate Tests](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Automated%20Tests.PNG)

<br>

Writing clean code, in every application, is always the best approach. With clean code, we mean removing useless comments, blocks of old code commented out and stripping down functions that aren't in use anymore. With a cleaner code base the software becomes more maintainable and readable. At this topic, this application barely passes with a positive score.

![Write Clean Code](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Write%20Code%20Once.PNG)

<br>

##Report evolution process:

When analyzing some of the features available in github and some tests in the application, we chose a feature to be implemented (Open Link in the External Browser), because we found interesting and that it would bring some value to an application, which already had references before. The feature that is implemented is intended to open search results pages in an external browser. And to locate the parts in the source code that needed to be modified we looked for the call stack from the web view, and went up level by level until we found where the search method was through where the changes were ment to be done. 

##Link to pull request:
The feature we worked on implementing is listed as <a href="https://github.com/duckduckgo/android/issues/272">#272</a> and the pull request we made in order to implement it is the <a href="https://github.com/duckduckgo/android/pull/277">#277</a>

##Contributions:
Filipe Coelho ( @Fr0sk ) has contributed in:
* Software Maintainability using the SIG metrics 
* Feature Selection
* Feature Implementation
* Link to pull request

Luís Cruz ( @Luis-bcruz ) has contributed in:
* Report evolution process

Shivam Agrawal ( @shivam-agr ) has contributed in:
* Feature Selection
* Report evolution process 

Vinicius Ferretti ( @ViniciusFerretti ) has contributed in:
* Feature Selection
* Report evolution process
