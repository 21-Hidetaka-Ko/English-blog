
#Excel and Tabelow are dead. Billionaires data analysis on Exploratory, UI for R — Is Europe women-friendly work environments true ?


![](images/excel-difficult.png)

Do you have any idea about this spread sheet data ?

Actually, this is billionaires data all over the world which I downloaded from Forbes.com.

Anyway, you may come up with a few questions about this data now. For example,

- 1.Which country has the highest number billionaire ?
- 2.How come they become billionaires ?
- 3.Which are there more of, men or women?

Moreover, as some articles which I recently read in Japanese, Europe seems countries which have women-friendly work environments. If it is true, Has Europe many women billionaires?


Do, we have a product called Exploratory which can solve such some questions easily and quickly by analyzing data for you. I'm in this project's team in Silicon Valley. I'm grateful for being surrounded by great people who make me want to be better self-everyday. Exploratory Desktop provides an interactive and reproducible real data wrangling and analysis experience powered by R and visualization.

![](images/exploratory.lp.png)

We released β version in May.

We excited that Hadley Wickham, the most famous person in R, retweeted our release.


![](images/Exploratory-tweet.png)


<blockquote class="twitter-tweet" data-lang="ja"><p lang="en" dir="ltr"><a href="https://twitter.com/KanAugust">@KanAugust</a> 1/ this could be a game changer. Especially with <a href="https://twitter.com/hashtag/teaching?src=hash">#teaching</a> <a href="https://twitter.com/hashtag/datascience?src=hash">#datascience</a> <a href="https://twitter.com/hashtag/science?src=hash">#science</a> highlights good/bad practices/data v quickly</p>&mdash; Stephen Newhouse (@s_j_newhouse) <a href="https://twitter.com/s_j_newhouse/status/729327017037053956">2016年5月8日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="en" dir="ltr"><a href="https://twitter.com/KanAugust">@KanAugust</a> Exploratory.io Love it!. Everyone with data should get it: students/teachers and all <a href="https://t.co/f4I6bCLxRi">https://t.co/f4I6bCLxRi</a>  <a href="https://twitter.com/hashtag/rstats?src=hash">#rstats</a></p>&mdash; Stephen Newhouse (@s_j_newhouse) <a href="https://twitter.com/s_j_newhouse/status/729326373454680064">2016年5月8日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Here are many reactions around the world.


![](images/Exploratory-access.png)


###Target Audience: Data Scientists who can do basic R or Python or People Who Know Just Enough R or SQL to Get by or Who are frustrating with Excel or Tabelow for analyzing data,

Before I begin, I’d like to clarify who my target audience is.In this tutorial, I’m targeting the third group I mentioned: people who know just enough R or SQL to get by or Who is frustrating with Excel or Tabelow for analyzing data. Examples of people who might fit in this category would be:

- Data Scientists or Analyst who can do basic R or Python.
- Data Analysts or Analyst Who are frustrating with Excel or Tabelow.
- Beginning developers who have completed basic SQL tutorials online.
- A Beginner who want to learn R but don't know how to learn for their research or static needs.
- Anyone who is interested in gender problem like working environments.

Anyway, let’s get started!

###Time Estimate: 10 minutes

If you go fast, this tutorial should take a bit over 5 minutes. If you go slow, it should take a bit over 10 minutes.

If you’re stuck, do any of the following:

- Comment on the comment box at the very bottom of this page.
- Email me at hidetaka.koh@gmail.com.
- Tweet me at [@SoccerKinki](https://twitter.com/SoccerKinki?lang=ja
)

####Preparing Data

To demonstrate, I’m going to use billionaires data from Forbes.com. I’ve shared it in EDF (Exploratory Data Format) [here]() so that you can quickly import with ‘Import Exploratory Data’ option. If you are interested in the original data you can download it from [here](https://www.dropbox.com/home?preview=Billionaires.xlsx) as well.

##Overview: Has Europe many women billionaires?

Let's reveal the question whether Europe women-friendly work environments are real or not by analyzing data for the introduction of Exploratory. After that, I state my impressions about Making the World Better for Working Women.

- STEP 1: Prepare Project before analyze
- STEP 2: Calculate ratio of billionaires for each country
- STEP 3: Remove outliers
- STEP 4: Is Europe women-friendly work environments real
- STEP 5: One more thing
- STEP 6: Sharing the Chart in Reproducible and Collaborative Way
- Finally: Making the World Better for Working Women


###STEP 1: Prepare Project Before Analyze

First of all, you can create projects from here.

![](images/create-project.png)

You can import data. The dataset is [here](https://www.dropbox.com/home?preview=Billionaires.xlsx) so that You can download it.

![](images/import.png)


####Summary View

![](images/summary-billionaire.png)

Totally different,right ? Thanks to Summary View, we can quickly overview data which we can't recognize data in Excel by importing. For example, this citizenship column represents the number of billionaires for each country. As you can see, United States have the most billionaire all over the world. This self-made column represents how come they become billionaires. When you see gender column, you can understand men's billionaires is much more than women at first glance.


But, we can't analyze data precisely with the way it is now.　Why not?

Let's see year column and the name column.

![](images/year-name.png)


The year column has data of the three years, 2014 and 2000 and 1996. And, We can see Abigail Johnson has "(3)" in the name column. That is because he was counted three times. In other words, Abigail Johnson was counted as one of the billionaires in 2014 and 2000 and 1996 in this data.What we want to know is information about billionaires in Europe now. So, we need to delete other data except 2014's year.

In such case, in contrast to Excel which I need to find where function like a filter is, Exploratory enables us to chose command from there or type code like SQL. Grammer enables you to express anything you want, that's why we can talk/write. Time to learn Grammar for Data Analysis, not tools like Excel or Tabelow!

![](images/exploratory-command.png)

Moreover, You can select the command from the column header dropdown list, which will generate a command like below.

![](images/command-builder.png)

Let's select ‘Filter’ from the column header dropdown list, which will generate a command like below because we want to filter 2014's data.

![](images/filter-20140.png)

Let's specify that year is 2014 and press Run button.

![](images/filter-2014.png)

Then, we can see only 2014's data in Summary View and the number of names become one from three.

In Chart View, we can intuitively understand data powered by visualization.

Let's assign X axis to citizenship and color axis to gender. That is because we want to see a graph of gender for each country. Blue color represents the female and orange color represents the male.

![](images/chart-billionaire2.png)

There are many billionaires and the ratio of men is overwhelmingly higher than the number of women in the world. By only this steps, Exploratory can make the chart so that we can understand data.

That is to say; Exploratory enable us to overview data easily and intuitively by just importing and realize the issues of data and fix it to analyze data.

That’s it for this step1! Not too bad, eh?

###STEP 2: Calculate the ratio of billionaires for each country

Note that to answer the question which is "Has Europe many women billionaires?", We have another problem. We don't know the ratio of billionaires between man and woman for each country because the height of each bar is different.

That's why We want to calculate the ratio of woman billionaires for each country

At First, We can quickly see the data as the table like Excel by going to Table view.

![](images/table-billionaire.png)


We can group citizenship and gender because we need to know the relationship between citizenship and gender by using 'group_by' command. You can construct this command from the column header menu. Click 'Group by' which will generate a command like below. Add 'gender' separating them by a comma. Here is the final command we want to run.

`group_by(citizenship, gender)`

![](images/group_by-gender.png)

You can confirm that citizenship and gender were grouped like below.

We need to divide each of the numbers of men and women by the total of men and women to calculate the ratio. That's why we want to create a column called 'count' which represents each of the numbers of males and females for each country. You can create the new column and aggregate the data by using 'summerize' command.

To make the command line interface work easier for anyone We have Context aware syntax suggestion which recommends a set of a list for function or column because Exploratory Desktop always check which column or function is good in this context like below.

So, you don't have to google the mean for functions which you don't know.

![](images/recommend-billionaire.png)


For example, here you will see a set of ‘aggregate’ functions that can be used in ‘summarize()’ command. If you are not familiar with R, as you can see, this ‘all’ function can be used to return TRUE if the condition is satisfied for all the rows or a group of rows. You can use the mean function in case of average or sum function in case of a total.

This Context aware syntax suggestion is a pretty powerful feature in Exploratory Desktop. Please take a look at [this post](https://blog.exploratory.io/context-aware-syntax-suggestion-d52519c55cf8#.n83k4wes0) for the detail.

Let's use 'n' function because we want to count in this case.

![](images/summarize-billionaire.png)


Look at Australia! They have four female and 25 male. To calculate the ratio of the woman, we need to divide 29 men and female by four women, don't we? Let's make a new column called total. To make a new column, we can use 'mutate'. Why do I need to use 'mutate', not 'summerize' like the previous case in this case? I have an answer for you. The difference is when we aggregate many rows in case of 'summerize' and make a new column with the same row in case of 'mutate'.

Let's 'mutate' command in this case because we want to left each row. And, we can use 'sum' function to calculate a total.

![](images/total-billionaire.png)

Let's create the ratio column because we can create the total column. When we divide count column by total, we can calculate the ratio.

![](images/ratio-billionaire.png)

Let's make 100 times because of 0.1379 and 0.8621.

![](images/ratio-billionaire2.png)

That's why we understand Men and women of the ratio of the billionaire in each of the country.

13% of Billionaires is women and 86% of Billionaires is Men in Australia.

###STEP 3:Remove outliers

Let's go to chart view to understand data more intuitively by visualization.

Let's assign citizenship to X-axis and ratio to Y-axis and gender to color-axis.

![](images/chart-billionaire3.png)

the highest female billionaire ratio is Angola as you can see.

Then, Do you say that Angola is the country that has the highest female billionaire ratio all over the world?

Let's go to Table view to demystifying a situation.

![](images/angola.png)

A total number of billionaires and woman in Angola is only 1. In other words, There is not enough peripheral data because the number of population is too small. So, Let's filter the number of population.

![](images/filter-total.png)

There is only countries which have more than five the number of the population like above.

###STEP 4:Conclusion: Is Europe women-friendly work environments true?

Let's go to viz to understanding data more intuitively by visualization.

![](images/chart-billionaire4.png)

High female billionaire ratio countries are European like Chile, Switzerland, Holland, Peru, Germany, France, Denmark as you can see.

Do you remember a self-made column that means how come they become billionaires as I told before? By using this column, let's see the difference between by inherited and by self-made. So, I want to come back Filter step which assigned year at first.

![](images/filter-selfmade.png)


Oh... When I back to filter step, Ratio in Y-axis come off and the chart is different from the previous one. That is because ratio column doesn't exist at the time of filter step which has blue border. That's why Pin button is here for such problem.

![](images/pin-billionaire.png)


When you click the Pin button, the part which you filter in the last became blue. The chart is fixed to the last blue step. Then, When you come back to filter step in the first with this status, you can see like below.

![](images/pin-billionaire2.png)


Although we change the step now, we can update the past step while fixing the chart to this blue step because I Pin this step. Then, let's filter only billionaires by inherited

![](images/filter-inherited.png)

European countries like Australia, Chile, France, Germany, Spain, Sweden, Switzerland, has a large number of woman billionaires by inherited as you can see.


And, let's filter only billionaires by self-made.


![](images/filter-selfmade2.png)


Wow! Many countries decrease suddenly. That is interesting! The only United States and Switzerland has a large number of woman billionaires by self-made as you can see. Many European countries like France and Germany decrease now.

In conclusion, of course, the number of the female billionaire in Europe is many compared to other nations. But, this is the critical thing, Many of female billionaire are in Europe is by inherited. There are less of the woman billionaire in Europe by self-made. That's why Europe women-friendly work environments are not necessarily right.



###STEP 5: One more thing


This tutorial is almost done. But, I want to show one more thing for you. This is interesting in term of the technical point. And, you will understand why the right step is. Although we can see the ratio per gender, in the next step, why don't see the rate per industry? Then, you can see by back to step for grouping and change just one command. So, let's go the step!

![](images/onemorething-billionaire.png)

Although this chart is Pinned to the last blue step, Exploratory can automatically calculate and visualize the data when you update grouping step.


###STEP 6: Sharing the Chart in Reproducible and Collaborative Way

####Chart with Data Provenance

One of the most frustraing thing about data visualization comes from the power it carries. It can be used to communicate ‘message’ super effectively and quickly regardless of the intention behind the message, therefore if we are not careful, it can fool us easily. And the bad news is, the world is filled with ‘irresponsible’ visualizations.

This is why I’m personally super excited to announce that we have introduced Chart Sharing with Data Steps with our latest Exploratory Desktop With which, not only can you share your chart with others but also publish it with the data wrangling steps so that others can quickly see how the data was prepared. And even better, others can download it, import into Exploratory, and review and evaluate each step of the data preparation interactively. What if someone doesn’t have Exploratory Desktop? Well, you can find an R script on the shared page so that you can reproduce the data in an standalone R environment!

Once you have got a chart you want to share with others, you can click on ‘Share’ button.

![](images/note-billionaire.png)

Inside the dialog you can type Title, Description, and Data Source information. And, you can keep the ‘Share with data’ checkbox checked’ if you like to do so. This will publish your chart with the data preparation steps.


![](images/note.png)

Once you click ‘Share’ button you will see an URL being generated. You can simply click ‘View Shared Chart’ link to open the published page.

![](images/note-publish_before.png)

You can find your chart is now published at [Exploratory Cloud](https://exploratory.io/viz/Hidetaka-Ko/118ab43cf452?cb=1471658236737).

![](images/note-publish.png)

Now, from here, your audience can go to Data view to see not only the underlying data but also the steps it took to prepare the data.

![](images/data-view.png)

Or, if your audience prefers, they can see the ‘easy-to-read’ dplyr chain of the commands in R script view.

![](images/rscript-view.png)

the real power of ‘Sharing Chart with Data and Steps’ becomes obvious when your audience download and import it into their Exploratory Desktop environment.

###Interactive Chart Sharing and Embedding

Medium is a great micro blogging platform where you can share your contents quickly. And you can share your chart as well. Very simple, you just copy and paste the chart URL like below.

[here](https://exploratory.io/viz/Hidetaka-Ko/118ab43cf452?cb=1471658236737)

You can do same thing in Slack, Wordpress, Twitter, Facebook, Tumbler,too.

##Excel is dead. Why Exploratory is Exploratory?

Can you imagine you can do this process from the beginning by Excel?

We want Exploratory Desktop to be an environment where we can focus on analyzing the data, asking questions about the data, and wrangling with the data to explore possible answers, without much worrying about the processes or how to make it reproducible for later use. And of course, we want Exploratory Desktop to take care of making all the exploratory works reproducible behind the scene just in case we might need it later!


##Making the World Better for Working Women


How about Silicon Valley? Silicon Valley which has highly mobile human resources is famous for the merit system. If it is true, Can you explain about below data?

1. 85% of high-tech jobs in Bay Area tech companies are held by men
2. 89% of Bay Area executives are men (National average is 84%)
3. 93% of Bay Area CEOs are men
4. 96% of Bay Area VCs are men

[Data source](https://medium.com/diversify-tech/i-m-a-white-guy-in-silicon-valley-and-i-m-done-buying-the-meritocracy-myth-2cc0ef9f9b60#.lql629j9y)


If you believe that the equation Silicon Valley = The perfect merit system held true, we have no choice but to conclude that Merit of men > Merit of women from this data. But, in fact, it is not true. Silicon Valley is man society. Women are owed ​​a handicap at the carrier.


So, There are many activities like [She++](http://www.sheplusplus.org/) to increase the number of the female engineer in Silicon Vally. I took part in their conference. They insisted “Maybe Woman don’t want to fall behind in their career when they’re pregnant. But She++ think learning to code is so much more practical. You can work remotely as a programmer too, while raising a kid.”


![](images/she++.png)

It’s challenging to be a working woman in Japan, my home country, too. The Economist recently presented their “glass-ceiling index,” which placed Japan among OECD countries with the largest gender gaps in their workplaces. For many Japanese women, returning to the workplace after having a child is often an insurmountable task. Japan should learn from She++, I think.

Although people who belive the perfect merit system like religion among the people who are well-to-do despise the people with poor skills because they are the result of lack of effort, they can't realize Inequality of society in the behind like gender gap. Please don't forget that there is no such complete meritocracy society. If you can not believe my opinion, I recommend you to look at data. I’m sure you can get a new way of thinking by looking data.

##Beta invitation is open

This is still our beta version and we’re just getting started. So there could be some places you might find unpolished, but we would love to hear what you think of it. You can sign up for the beta access from [this page](https://exploratory.io/
)

You can see our tutorial for Exploratory form [this page](http://docs.exploratory.io/tutorials/intro.html
)

[Introducing Exploratory Desktop — UI for R](https://blog.exploratory.io/introducing-exploratory-desktop-ui-for-r-895d94ef3b7b#.4dncgv1rt
) is good article, too!


Thanks for reading. I’d appreciate a click on the “Recommend” button at the end if you liked this article.

