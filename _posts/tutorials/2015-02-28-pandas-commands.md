---
layout: post
title:  "Top Ten Pandas Commands"
date:   2015-02-26 12:35:38
categories: tutorials
---

As many developers can attest, Pandas is a great tool. It makes analyzing data fast for programmers who don't munge data on a regular basis. However, sometimes looking up googling commands for common tasks can be a tedious venture. Below are the 10 most common Pandas command. Feel free to add commands I missed in the comment section!

## Munging and Cleaning Data

1. Renaming Column Names

{% highlight python %}
df = df.rename(columns={'mon hike': 'Monday_Hike', 
                        'tues run': 'Tuesday_Run',
                        'wed swim': 'Wednesday_Swim',})
                        
{% endhighlight %}

or 

{% highlight python %}

## turning human readable names like DEPT BUDGET to DEPT_BUDGET
df = df.rename(columns=lambda x: x.replace(' ','_'))

{% endhighlight %}
<br>


2. Getting Rid of Duplicates

```
df.drop_duplicates('name_of_column')
```
<br>
<br>

3. Filling NAN with a value

```
df.fillna()
```

or 

{% highlight python %}
## filling missing values in individual rows
df = df.fillna({
'col1': '0',
'col2': 'missing'})
{% endhighlight %}
<br>

4. Selecting Columns
{% highlight python %}
'col_1', 'col_2', 'col_3', 'col_4', 'col_5'
# say you only want 'col_2', 'col_3', and 'col_5'
df = df.column[['col_2', 'col_3', 'col_5']]
{% endhighlight %}

or 

{% highlight python %}
'col_1', 'col_2', 'col_3', 'col_4', 'col_5'
# selecting 'col_2' to 'col_4' 
df = df.column.ix[:,1:3]
{% endhighlight %}
<br>




## Exploratory Analysis


Sources:

http://stackoverflow.com/questions/16616141/deleting-all-columns-except-a-few-python-pandas
http://nbviewer.ipython.org/github/rasbt/python_reference/blob/master/tutorials/things_in_pandas.ipynb#Renaming-Columns