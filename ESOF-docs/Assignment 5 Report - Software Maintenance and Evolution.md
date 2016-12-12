#ESOF 2016/2017 - Assignment 5: Software Maintenance/Evolution

##Software Maintainability using the SIG metrics 
[![BCH compliance](https://bettercodehub.com/edge/badge/Fr0sk/ESOF-DuckDuckGo-Android-App)](https://bettercodehub.com)

To analyse the software mainatinability we resort to an online code analysis tool called [Better Code Hub](https://bettercodehub.com). With it we could easily see the weak spots of your project concerning bad coding practices. 

Starting with writing short and concise units of code, with functionality well defined and splitted, our project got a negative score. While the tool states that units should be less of 15 lines of code, we think that for an android application, in some cases it's easy to pass that mark, specially in event handlers with anonymous functions. Still, arround 60 units had more than 30 lines of code, with the worst having 139 lines, which is a big concerning and should be reviewed in order to get a better code organization. This would also improve unit tests that could focus on smaller and more specific tasks with smaller pieces of code.

![Short Units of Code](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/Short%20Units%20of%20Code.PNG)

<br>

Continuing in a related topic, the score this project got on simple units of code was also negative. In simple units of code it's expected to keep branch points (for, if, while, etc) below 5 per unit. We think this could be easily achivable, splitting the logic through several different units. The worst unit has 26 branch points, which is a lot more than it should.

![Simple Units of Code](https://github.com/Fr0sk/ESOF-DuckDuckGo-Android-App/blob/master/ESOF-docs/resources/SIG%20Metrics/SImple%20Units%20of%20Code.PNG)

##Report evolution process:

##Link to pull request:


##Contributions:
Filipe Coelho ( @Fr0sk ) has contributed in:


Luís Cruz ( @Luis-bcruz ) has contributed in:


Shivam Agrawal ( @shivam-agr ) has contributed in:

Vinicius Ferretti ( @ViniciusFerretti ) has contributed in:
