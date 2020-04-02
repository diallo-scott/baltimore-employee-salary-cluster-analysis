# Baltimore City Employee Salary Cluster Analysis
  There have been numerous reports of scandals involving the salaries in various departments of Baltimore city's payroll.  From the police department where in 2018 they spent more than 3 times their overtime budget to the school district where principal's at underprivileged schools reportedly made six figures,  there have been numerous examples of certain employees and departments being overpaid.  With this knowledge I wanted to perform a cluster analysis on all 650+ city departments to find groupings of departments based upon annual salary, gross salary, and tenure based off of the Baltimore fiscal year 2019.  My goal was to see if there are clusters of departments that are overpaid, paid adequately, or underpaid. 
  
## Results
  In order to run the cluster analysis I standardized my data and created 5 different clusters.  The final result of this analysis produced the following 5 groupings:
  ![cluster output](https://github.com/diallo-scott/baltimore-employee-salary-cluster-analysis/blob/master/Cluster%20Analysis%20Output.png)
 
 This allows us to describe the five groupings based off of annual salary, gross salary, and tenure.  The 1st group with the cluster node being the Housing and Community Development department can be described by having annual and gross salaries just below the mean, and their tenure is almost one standard deviation below the mean.  This shows us that the 1st group seems to receive an adequate gross salary, since tenure and annual salary are both below mean.  
 
 The 2nd group with the cluster node being the Police Department is described by having annual salary more than 1 standard deviation from the mean.  Although their annual salary is above the city mean, gross salary and tenure are both almost 1 standard deviation above the mean as well.  This implies that this second group is one that is higher paid in terms of gross salary, but is still not overpaid since they have often worked for longer and their contracted annual salaries are also high.  
 The cluster node of the 3rd group is Highway Transportation department.  This group has annual and gross salaries that are below the mean by 0.8 and 0.5 standard deviations respectively, but they have a tenure that is more than 1 standard deviation above the mean.


## Sources
https://foxbaltimore.com/news/project-baltimore/fox45-finds-more-six-figure-payroll-problems-at-city-schools
https://www.wbaltv.com/article/dollar47m-spent-on-police-overtime-in-baltimore-top-recipients-names-released/23480417#
