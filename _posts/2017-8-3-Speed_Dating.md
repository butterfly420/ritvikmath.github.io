---
layout: post
comments: true
title: Salary Dynamics in the University of California
---

<figure>
<center>
   <a href="/images/sankey.jpg"><img width="100%" src="/images/sankey.jpg"></a>
</center>
</figure>

<center>
<font size="5"><b>Exploring Salaries throughout the UC System</b></font>
</center>

<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
  tex2jax: {
    inlineMath: [['$','$'], ['\\(','\\)']],
    processEscapes: true
  }
});
</script>
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML">
</script>

---

<html>
<head>
<script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      google.charts.load('43', {'packages':['sankey', 'table', 'timeline']});
      google.charts.setOnLoadCallback(drawChart);
      google.charts.setOnLoadCallback(drawTable);
      google.charts.setOnLoadCallback(drawTimeline);

      function drawChart() {
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'From');
        data.addColumn('string', 'To');
        data.addColumn('number', 'Cash Flow ($)');
        data.addRows([
			['Prefers Shared Interests', 'Chose Shared Interests', 1],
['Prefers Fun', 'Chose Sincerity', 4],
['Prefers Fun', 'Chose Attractiveness', 8],
['Prefers Attractiveness', 'Chose Fun', 22],
['Prefers Shared Interests', 'Chose Ambition', 1],
['Prefers Fun', 'Chose Fun', 2],
['Prefers Shared Interests', 'Chose Sincerity', 3],
['Prefers Attractiveness', 'Chose Attractiveness', 76],
['Prefers Sincerity', 'Chose Shared Interests', 1],
['Prefers Intelligence', 'Chose Sincerity', 30],
['Prefers Attractiveness', 'Chose Shared Interests', 3],
['Prefers Ambition', 'Chose Fun', 1],
['Prefers Sincerity', 'Chose Attractiveness', 41],
['Prefers Intelligence', 'Chose Shared Interests', 4],
['Prefers Ambition', 'Chose Intelligence', 3],
['Prefers Sincerity', 'Chose Ambition', 9],
['Prefers Shared Interests', 'Chose Attractiveness', 4],
['Prefers Intelligence', 'Chose Fun', 7],
['Prefers Sincerity', 'Chose Fun', 11],
['Prefers Intelligence', 'Chose Attractiveness', 37],
['Prefers Attractiveness', 'Chose Sincerity', 69],
['Prefers Sincerity', 'Chose Sincerity', 32],
['Prefers Attractiveness', 'Chose Intelligence', 63],
['Prefers Sincerity', 'Chose Intelligence', 25],
['Prefers Intelligence', 'Chose Ambition', 4],
['Prefers Attractiveness', 'Chose Ambition', 12],
['Prefers Fun', 'Chose Intelligence', 10],
['Prefers Ambition', 'Chose Sincerity', 1],
['Prefers Shared Interests', 'Chose Intelligence', 1],
['Prefers Fun', 'Chose Ambition', 2],
['Prefers Intelligence', 'Chose Intelligence', 35]
        ]);

        // Sets chart options.
        var options = {
          width: 725,
		  sankey:{
			  node: {
				label: {
				  fontSize: 12,
				  bold: true
				}},
	
			link: {colorMode: 'source',
				color: {fillOpacity: 1,  strokeWidth: 1}
			}
			}
		  
        };
        
        

        // Instantiates and draws our chart, passing in some options.
        var chart = new google.visualization.Sankey(document.getElementById('sankey_basic'));
        chart.draw(data, options);
      }
      
      
      
      
      function drawTable() {
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'Campus');
        data.addColumn('string', 'Top Paid Position');
        data.addColumn('number', '2015 Salary');
        data.addRows([
          ['Berkeley', 'Head Coach' , {v: 2038733, f: '$2,038,733'}],
          ['Davis', 'CEO Medical Center' , {v: 1114446, f: '$1,114,446'}],
          ['Irvine', 'Professor - Health Sciences' , {v: 1234771, f: '$1,234,771'}],
          ['Los Angeles', 'Head Coach' , {v: 3514771, f: '$3,514,771'}],
		  ['Merced', 'Chancellor' , {v: 404896, f: '$404,896'}],
		  ['Riverside', 'Dean - School of Medicine' , {v: 698608, f: '$698,608'}],
		  ['San Diego', 'Professor - Health Sciences' , {v: 1569475, f: '$1,569,475'}],
		  ['San Francisco', 'Health Sciences Clinical Instructor' , {v: 1753731, f: '$1,753,731'}],
		  ['Santa Barbara', 'Professor in Residence' , {v: 468571, f: '$468,571'}],
		  ['Santa Cruz', 'Chancellor' , {v: 392076, f: '$392,076'}],
		  ['Office of the President', 'Chief Investment Officer' , {v: 1106688, f: '$1,106,688'}]
        ]);

        var table = new google.visualization.Table(document.getElementById('table_div'));
		
        table.draw(data, {allowHtml: true, showRowNumber: false, width: '100%', height: '150%', alternatingRowStyle: true});
		
      }
      
      
      
      
      
      function drawTimeline() {
        var container = document.getElementById('timeline-tooltip');
        var chart = new google.visualization.Timeline(container);
        var dataTable = new google.visualization.DataTable();

		dataTable.addColumn({ type: 'string', id: 'ID' });
        dataTable.addColumn({ type: 'string', id: 'Campus' });
		dataTable.addColumn({ type: 'string', role: 'tooltip' });
        dataTable.addColumn({ type: 'date', id: 'Start' });
        dataTable.addColumn({ type: 'date', id: 'End' });
        dataTable.addRows([
          ['1','UCLA', 'Total Income: $74,758', new Date(2010,0,1), new Date(2011,11,31) ],
          ['2','UCSB', 'Total Income: $123,109',      new Date(2011,0,1),  new Date(2014,11,31) ],
          ['3','UCI', 'Total Income: $218,884',  new Date(2013,0,1),  new Date(2015,11,31) ]]);
		  
		  var options = {
			width: 700,
			colors: ['red', 'blue', 'green'],
			
			timeline: { 
				showRowLabels: false,
				barLabelStyle:{
				fontName: 'Arial',
				fontSize: 14}
				
				
				}
				};
		  

        chart.draw(dataTable, options);
      }
    </script>
</head>
</html>


# Disclaimer

The raw data used for this analysis is publically available and contains names, job titles, and salaries for all University of California Employees from 2010 until 2015. Before performing any analysis on the data, this author encrypted all names. If this data is released, the encryption will remain in place and no names will be published.

Although all the data is available online, there is a fundamental difference between having to search for data, point by point, in a database and having all the data aggregated into a spreadsheet where searching is much more simple. 

---


Quick Links: 

* [Background](#back)  
* [The Data](#data)
* [Who is paid the most at each school?](#highpay)
* [How do UC campuses compare globally?](#global)
* [What is the distribution of salaries for each campus?](#distr)
* [How does value flow between UC schools?](#transfers)
* [How does salary correlate with other things?](#correl)
* [Notes](#notes)

---

<a name="back"></a>

# Background

The University of California (UC) system is a public university system comprising of ten campuses, with the oldest being UC Berkeley, founded in 1868 and the newest being UC Merced, founded in 2005. Nine of the ten schools in the UC system admit both undergraduate and graduate students, with the exception of UC San Francisco, which admits only graduate students. 

The UC System was allocated a budget of **\\$25.5 billion** in 2015, **\\$13.1 billion** of which went towards paying its around **180,000 employees**. Of course, there are various factors that impact each individual employee's salary such as position and years of experience. 

But, there may be more, underlying, factors which impact employee salary, all else held constant, such as UC Campus, city unemployment rate, and cost of living. This post aims to dive deep into the intricacies of the distribution of salaries throughout the UC system, offering an interactive way to explore the key dynamics at play.

---

<a name="data"></a>

# The Data

The data for this analysis came from the <a href="https://ucannualwage.ucop.edu/wage/" target="_blank">Compensation at the University of California</a> website. The data includes employee names, campus of employment, job title, and gross pay. A snapshot of the data is shown below.

<figure>
<center>
   <a href="/images/data_sal.jpg"><img width="100%" src="/images/data_sal.jpg"></a>
</center>
</figure>

The data spans the years **2010 until 2015** and includes all ten UC Schools as well as the University of California Office of the President. In total there are about **1.5 million rows** in the table, where each row corresponds to a particular employee in a particular year. 

## Brief Notes on the Data

* Employees who are concurrently students have their names listed as '*****' in order to protect their privacy. For this reason, we will use them when calculating summary statistics for each campus, but must remove them when we try and track certain employees through time since we have no unique identifier for them.
* The job titles are not very specific and usually are limited to things like 'COACH' or 'PROF' without much more detail about which sport, department, etc. the employee is a part of.
* There are a few missing values in the data for salaries. This author chose to use median imputation to fill in these missing values. Basically, missing values for any column are filled in with the median of existing entries in that column.

---

<a name="highpay"></a>

# Who is paid the most at each school?

One of the burning questions readers probably have is *"Who is paid the most at each campus?"* Let's answer this question before going much deeper into the data as a whole.

<html>
<style>
.google-visualization-table-td {
text-align: center !important;
}
</style>
<body>
<center>
<div id="table_div"></div>
</center>
</body>
</html>


By clicking on the column names, you can sort the table by salary, position, or campus. 

Perhaps the most striking thing about this table is that the sum of the five lowest salaries still is less than the top salary, that of a head coach at UC Los Angeles. 

Let's now step back and look at our plethora of data as a whole.

---

<a name="global"></a>

# How do UC campuses compare globally? 

There are inherent disparities between salaries at UC campuses and moreover, these disparities change over time. 

Use the tool below to explore for yourself some of these differences in salaries over time and between campuses. 

<br><br><br><br>

<center>
<div>
<iframe src="https://ritvikmath.shinyapps.io/NewBubble/" style="border: none; width: 850px; height: 700px"></iframe>
</div>
</center>

There are a few key points about this global data:

* Number of students and employees generally goes up over time, the UC system is growing.
* There is actually a huge difference between median and mean salary. For example, UC Merced's mean salary in 2015 is around \\$28,000 but its median salary is only \\$8,850. Big differences between medians and means usually indicate strong presence of outliers (high salary earners) pulling the mean to high values.
* The fact that UC San Francisco is a graduate school really shows as it has few students but has by far the highest mean and median salaries.
* There seems to be a somewhat positive correlation between number of students / employees and mean / median campus salary.
* There seems to be a somewhat negative correlation between number of students / employees and unemployment rate. Hmm .... more on this later.

---

<a name="distr"></a>

# What is the distribution of salaries for each campus?

Let's zoom in a bit and look at the distribution of salaries within each campus and over time. As you play with the tool below think about questions like *"Does the salary distribution shift over time towards higher or lower earners?"*, *"Which campus has the most equality in pay?"*, *"Are there intermediate peaks or valleys in these distributions?"*

If there is no graph, give it a second. 1.5 million rows of data takes a bit of time to load!

<br><br><br><br>

<center>
<div>
<iframe src="https://ritvikmath.shinyapps.io/TestShiny/" style="border: none; width: 900px; height: 575px"></iframe>
</div>
</center>

<br><br><br><br>

There is a lot to be said about these distributions but let's note some of the more prevalent points:

* In general the histograms display an expected exponential decay-like pattern, with many employees having lower salaries and with fewer and fewer employees having high salaries. 
* Most UC schools such as UC Los Angeles and UC Davis have a "middle-earner" bump around \\$50,000 in 2015.
* This bump is most profound in UC San Francisco, which has a very unique salary distribution compared to all the other schools. In fact, most employees at UC San Francisco earn around \\$50,000, much higher than at other UC schools.
* Many UC schools, such as Irvine, went from having clear twin peaks in 2010-2011 to having much smoother distributions. That second peak around \\$30,000 seems to have been absorbed into lower salary brackets over time.
* The UC Office of the President (UCOP) displays a very unique salary pattern with many more employees earning in higher salary brackets than at the main UC campuses.

---

<a name="transfers"></a>

# How does value flow between UC schools?

So far, we have been looking at each UC campus individually, independent of their connections to other UC campuses. But, there are fundamental links between campuses though which value flows over time. Let's elaborate a bit.

There are many employees in our dataset who work at multiple UC campuses over our six year period. Employees may transfer from one UC campus to another for a variety of reasons: better pay, geographic relocation, a new job, etc. 

Furthermore, there are many employees who are employed at multiple UC campuses within a year. How can this be? It is best explained as a symptom of the fact that our data is annual. For example, if an employee works at UC Riverside for the first half of 2012 and UC Merced for the second half of 2012, she will be recorded as working at both Riverside and Merced in 2012.

Let's look at a real employee from the data. Hover over each bar to see salary information.

<br>

<html>
<style>
.google-visualization-table-td {
text-align: center !important;
}
</style>
<center>
   <div id="timeline-tooltip" style="height: 240px;"></div>
</center>
</html>

This employee started off at UC Los Angeles in 2010 and worked there for two years. In 2011, when the employee was still employed in Los Angeles for some part of the year, he began working at UC Santa Barbara. He continued to work there through 2014. In 2013, he started to work at UC Irvine and continued to work there into 2015. We see that this employee's total income at each consecutive UC school went up over time.

If we assume that salary is a measure of how much value a campus gains from an employee, when an employee leaves a campus they reduce the net value of that campus by the amount of their salary. For example, if an employee makes \\$50,000 at UC Irvine in 2013 and then accepts a position at UC San Diego in 2014, UC Irvine effectively loses \\$50,000 worth of value via the loss of that employee. Note however, that this does not mean UC San Diego gains \\$50,000 since they may value this employee differently.

Let's take a look at how much value each UC school lost to each other UC school in our six year period. Hover over each link to explore the value flows between UC schools.

<br><br>
<html>



<div id="sankey_basic" style="width:400px; height: 500px;"></div>

</html>
<br><br>

Some notes about this chart:

* UC Berkeley is generally ranked the highest in university rankings such as the US News & World Report rankings. While it is up to debate whether these rankings are at all accurate, they do definitely sway public opinion. This is a likely reason that in our chart, UC Berkeley loses very little value for a school of its size but is the target for a lot of value from other UC schools.
* We see that UC Los Angeles and UC San Francisco serve as the major sources of value loss with most of UC Los Angeles' lost value going to UC Davis and UC Berkeley and most of UC San Francisco's lost value going to UC Los Angeles and UC Berkeley. 
* It is perhaps worth noting that geographic proximity might affect where lost value goes. For example, UC Irvine and UC Los Angeles are relatively close, which might be why most of UC Irvine's lost value goes to UC Los Angeles. Employees perhaps look for jobs close to where they already are. We see a similar pattern with most of UC Davis' lost value going to UC Berkeley.

<a name="correl"></a>

---

# How does salary correlate with other things?

As we started to talk about at the start of this post, salary is a function of many factors. The key questions are then "*What are those factors?*" and "*How strongly do they correlate with salary?*"

The tool below will help answer some of those questions. You can pick between three potential factors which might (or might not) correlate with salary and look at how these patterns change over time and also by job title. 

Again, we're pulling 1.5 million rows here, so if there isn't a chart there, it'll show up soon!

<br><br><br><br>

<center>
<div>
<iframe src="https://ritvikmath.shinyapps.io/NewScatter/" style="border: none; width: 930px; height: 700px"></iframe>
</div>
</center>

A few takeaways:

* There seems to be a (if only a slight) positive correlation between years of experience and salary, which we expect
* There seems to be a (again if only slight) negative correlation between city unemployment rate and salary. The logic is likely as follows. If unemployment rate in a city is high, employees are not as picky about how much they are paid to work. Knowing that jobs are scarce, employers also have less incentive to offer bigger salaries since they know employees don't have many other options.
* The most fun of these graphs to explore is the graph of past year's salary vs. this year's salary. We see a very strong positive correlation, pretty much no matter what job we subset by.
* Here's an interesting exploration. Pick 2015 and choose 'nurse' as the job title. Set your max displayed salary to something around \\$250,000. Notice that for lower salary levels, there's a much greater variability between last year's salary and this year's salary than for higher salary levels, where the relationship is much more linear. It seems like your salary is more stable the higher it is (at least for nurses).

<a name="notes"></a>

---

# Notes

* There are a lot of combinations of charts, graphs, and plots you can generate using the tools in this post, but it is important to remember the old adage: "correlation does not imply causation". The relationships we talked about in this post are based on a mixture of past research, data, and intuition but may very well not be causal. 
* The chart showing flow of value through the UC system has many assumptions including that salary is actually a measure of value to each UC school, that few employees were fired, and that each UC school is willing to hire employees who work part time at that UC school and part time at another UC school.
* If you are having trouble finding position titles, it is likely because they are so vague. Your best bet is probably to go to the UC Compensation website linked in the Data section of this post and look for the position title you want and then enter it into the tool. 

Thanks for reading and please leave comments!




