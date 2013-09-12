# Nurse-Family Partnership Home-Visits Calculator

At the beginning of the fellowship, [we met local NFP nurses to learn about their experiences and to gain insight into the program](http://dssg.io/2013/06/28/redefining-which-problems-matter.html).  We learned that one of their tedious tasks involves calculating how many visits they need to make for each client before she gives birth based on the week of her pregnancy.  NFP calls for a visit every week for the first four weeks a woman is enrolled and a visit every other week after that, and to meet NFP standards the nurses need to make at a minimum 80% of those recommended visits.  

To address this problem, we created a simple [Shiny](http://www.rstudio.com/shiny/) application that does the calculation for the nurses.  The nurses enter the week of gestation into an input box, and the program calculates the minimum number of visits they need to make.  

<a href="http://spark.rstudio.com/jtwalsh0/NFP/"><img src="https://github.com/dssg/nfp/blob/master/for_wiki/home_visits_calculator.gif" align="center"></a>

<img src="https://github.com/dssg/nfp/blob/master/for_wiki/home_visits_calculator.gif" align="center">

[![NFP](http://spark.rstudio.com/jtwalsh0/ShinyApps/NFP/home_visits_calculator.png)](http://spark.rstudio.com/jtwalsh0/NFP/)

[RStudio](http://www.rstudio.com/) has graciously donated space on a web server to host the application.  You can find the application [here](http://spark.rstudio.com/jtwalsh0/NFP/).  

There are two working files in this directory.  The first, `server.R`, performs the calculations; and the second, `ui.R`, generates the user interface.  You can employ these scripts on the web with a Linux server and the Shiny Server software.  For more details, please see the Shiny webpage using the link provided above.