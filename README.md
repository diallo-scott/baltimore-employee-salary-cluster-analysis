# Baltimore City Employee Salary Cluster Analysis
  There have been numerous reports of scandals involving the salaries in various departments of Baltimore city's payroll.  From the police department where in 2018 they spent more than 3 times their overtime budget to the school district where principal's at underprivileged schools reportedly made six figures,  there have been numerous examples of certain employees and departments being overpaid.  With this knowledge I wanted to perform a cluster analysis on all 650+ city departments to find groupings of departments based upon annual salary, gross salary, and tenure based off of the Baltimore fiscal year 2019.  My goal was to see if there are clusters of departments that are overpaid, paid adequately, or underpaid. 
  
## Results of Cluster Analysis
  In order to run the cluster analysis I standardized my data and created 5 different clusters.  The final result of this analysis produced the following 5 groupings:
  ![cluster output](https://github.com/diallo-scott/baltimore-employee-salary-cluster-analysis/blob/master/Cluster%20Analysis%20Output.png)
 
 This allows us to describe the five groupings based off of annual salary, gross salary, and tenure.  The 1st group with the cluster node being the Housing and Community Development department can be described by having annual and gross salaries just below the mean, and their tenure is almost one standard deviation below the mean.  This shows us that the 1st group seems to receive an adequate gross salary, since tenure and annual salary are both below mean.  
 
 The 2nd group with the cluster node being the Police Department is described by having annual salary more than 1 standard deviation from the mean.  Although their annual salary is above the city mean, gross salary and tenure are both almost 1 standard deviation above the mean as well.  This implies that this second group is one that is higher paid in terms of gross salary, and in some cases they may be overpaid.  Not all in this cluster are overpaid, however, given that they also have longer average tenure.
 
 The cluster node of the 3rd group is Highway Transportation department.  This group has annual and gross salaries that are below the mean, but they have a tenure that is more than 1 standard deviation above the mean.  This could imply that this group is underpaid, since they have longer tenures and lower salaries.  We should consider, however, that this could also show that these jobs are just lower paying due to other factors, such as education level requires, types of jobs available, and number of part-time vs full-time positions.
 
 The 4th grouping has the cluster node of the Parks department.  This group has annual salary, gross salary, and average tenure that are all below the mean.  It appears that gross salaries on average fall below the annual salaries, which implies that this group is either being underpaid or not working to earn the full amount of their contracted salaries.  Given that the tenure is below the mean, it seems that this grouping may actually not be underpaid and there are other factors leading to the comparatively lower gross salaries.
 
 The node of the 5th, and the smallest, grouping is the Fire Department.  This group has gross and annual salaries that are well above the mean and a tenure that is even further above the mean.  It appears that this cluster consists of the highest paying jobs in the city, since the above average tenures suggest that they are not being overpaid.  The higher pay that this group experiences could be due to more management positions being available and the types of jobs that these departments contain.
 
 ## Summary
 We were able to create five different groupings of Baltimore city employees based upon the fiscal year 2019 data on annual salary, gross salary, and tenure.  Of these five groupings two had nodes with above average annual and gross salaries and above average tenure.  There were two groupings with annual salary, gross salary, and average tenure that were below the average. Finally, there was one group that that had annual and gross salaries that were below the mean, but had an average tenure that was above the mean.
 
 These results tell us that we may want to further investigate these clusters to ensure that no one is being neither overpaid nor underpaid.  We would especially want to investigate the groups that had gross salaries far above the mean, such as the one with the node being the Fire Deparment.  Another group of interest would be the the group that had salaries below the mean and tenure above the mean, which had the Highway Transporation department as its node.  We would want to ensure that employees in this group are not being underpaid and that the discrepancy is accounted for by other factors.
 
 ## Step-by-Step Excel Analysis
 1. Gather data for Baltimore City Employee Data from FY 2019
 2. Insert a column for tenure and use use the formula : =Today() - Hire date
 3. Create a pivot table using the data.  Use the DEPTID as the rows and for values use Annual_RT, Tenure, and Gross.  Be usre to change from sum to averages.
 4. Copy data from pivot table, excluding the final row, into a new tab for cluster analysis.  Insert 10-12 rows above the data and add a colum to the left to put in a "Simple" Dept ID and sequentially label each row of data 1,2,3,4,...
 5. In the two cells above each column (Annual salary, tenure, gross salary) calculate the mean (using = Average(column data)) and standard deviation (using =STDEV(column data)) of each column.
 6.  To the right of the data create 3 new columns for the z score of each of the original data columns.  To calculate use the z score use the Standardize function, where you can use the previously calculated means and standard deviations.
 7. In the cells that were previously inserted above the data create a table for the results of the anlaysis.  The first column is cluster id, where you should label each cell sequentially 1-5.  Then in the next column label it simple dept id, and input 5 random values which you created in Step 4.  Then to create the next four columns for DeptID and the z scores for annual salary, gross salary, and tenure you should use VLOOKUP with the simple dept id being the lookup value.
 8. Create five columns to the right of the zscore columns that you made in Step 6 for the distance squared between the z-score values for each dept id and the ones you used in the above table as the random nodes for each of the five clusters.  Use the SUMXMY2 function to do this.
 9. Create another column to the right of the ones created in the last step that calculates the minimum of the distance between that dept id's values and the five nodes.  Use the MIN function to do this.
 10. Create another column to the right of the one created in the last step that tells us which node that dept is closest to.  Use the MATCH function to do this.
 11. In the cell above the minimum distance column create a cell that sums all the minimum distance values.
 12. Finally we can run the solver to generate the final results.  We choose to minimize the value of the cell created in the last step.  For the changing variables we select the simple dept id column in the cluster output table.  We must constrain these values to be between 1 and the largest dept id and to be integer values.  Once we run the solver we will have the nodes to each of our clusters and the analysis is complete.
 
 ## Link to File with Raw and Analyzed Data
 https://github.com/diallo-scott/baltimore-employee-salary-cluster-analysis/blob/master/Baltimore%20Salary%20Cluster%20Analysis%20and%20Raw%20Data.xlsx

## Sources
https://data.baltimorecity.gov/City-Government/Baltimore-City-Employee-Salaries-FY2019/6xv6-e66h
https://foxbaltimore.com/news/project-baltimore/fox45-finds-more-six-figure-payroll-problems-at-city-schools
https://www.wbaltv.com/article/dollar47m-spent-on-police-overtime-in-baltimore-top-recipients-names-released/23480417#
