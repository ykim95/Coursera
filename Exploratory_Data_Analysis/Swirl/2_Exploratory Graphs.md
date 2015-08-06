| Exploratory_Graphs. (Slides for this and other
| Data Science courses may be found at github
| https://github.com/DataScienceSpecialization/courses/.
| If you care to use them, they must be
| downloaded as a zip file and viewed locally.
| This lesson corresponds to
| 04_ExploratoryAnalysis/exploratoryGraphs.)

...

  |=                                      |   1%

| In this lesson, we'll discuss why graphics are
| an important tool for data scientists and the
| special role that exploratory graphs play in
| the field.

...

  |=                                      |   3%

| Which of the following would NOT be a good
| reason to use graphics in data science?

1: To understand data properties
2: To find a color that best matches the shirt you're wearing
3: To find patterns in data
4: To suggest modeling strategies

Selection: 2

| Perseverance, that's the answer.

  |==                                     |   4%

| So graphics give us some visual form of
| data, and since our brains are very good at
| seeing patterns, graphs give us a compact
| way to present data and find or display any
| pattern that may be present.
  |==                                     |   5%

| Which of the following cliches captures the
| essence of graphics?

1: A picture is worth a 1000 words
2: A rose by any other name smells as sweet
3: The apple doesn't fall far from the tree
4: To err is human, to forgive divine

Selection: 1

| That's correct!

  |===                                    |   7%

| Exploratory graphs serve mostly the same
| functions as graphs. They help us find
| patterns in data and understand its
| properties. They suggest modeling strategies
| and help to debug analyses. We DON'T use
| exploratory graphs to communicate results.

 |===                                    |   8%

| Instead, exploratory graphs are the initial
| step in an investigation, the "quick and
| dirty" tool used to point the data scientist
| in a fruitful direction. A scientist might
| need to make a lot of exploratory graphs in
| order to develop a personal understanding of
| the problem being studied. Plot details such
| as axes, legends, color and size are cleaned
| up later to convey more information in an
| aesthetically pleasing way.

 |====                                   |   9%

| To demonstrate these ideas, we've copied
| some data for you from the U.S.
| Environmental Protection Agency (EPA) which
| sets national ambient air quality standards
| for outdoor air pollution. These Standards
| say that for fine particle pollution
| (PM2.5), the "annual mean, averaged over 3
| years" cannot exceed 12 micro grams per
| cubic meter. We stored the data from the
| U.S. EPA web site in the data frame
| pollution. Use the R function head to see
| the first few entries of pollution.

> head(pollution)
       pm25  fips region longitude latitude
1  9.771185 01003   east -87.74826 30.59278
2  9.993817 01027   east -85.84286 33.26581
3 10.688618 01033   east -87.72596 34.73148
4 11.337424 01049   east -85.79892 34.45913
5 12.119764 01055   east -86.03212 34.01860
6 10.827805 01069   east -85.35039 31.18973

| You're the best!

  |====                                   |  11%

| We see right away that there's at least one
| county exceeding the EPA's standard of 12
| micrograms per cubic meter. What else do we
| see?

|=====                                  |  12%

| We see 5 columns of data. The pollution
| count is in the first column labeled pm25.
| We'll work mostly with that. The other 4
| columns are a fips code indicating the state
| (first 2 digits) and county (last 3 digits)
| with that count, the associated region (east
| or west), and the longitude and latitude of
| the area. Now run the R command dim with
| pollution as an argument to see how long the
| table is.

> dim(pollution)
[1] 576   5

| All that practice is paying off!

  |=====                                  |  14%

| So there are 576 entries in pollution. We'd
| like to investigate the question "Are there
| any counties in the U.S. that exceed that
| national standard (12 micro grams per cubic
| meter) for fine particle pollution?" We'll
| look at several one dimensional summaries of
| the data to investigate this question.

> summary(pollution$pm25)
   Min. 1st Qu.  Median    Mean 3rd Qu. 
  3.383   8.549  10.050   9.836  11.360 
   Max. 
 18.440 

| You are amazing!

  |======                                 |  16%

| This shows us basic info about the pm25
| data, namely its Minimum (0 percentile) and
| Maximum (100 percentile) values, and three
| Quartiles of the data. These last indicate
| the pollution measures at which 25%, 50%,
| and 75% of the counties fall below. In
| addition to these 5 numbers we see the Mean
| or average measure of particulate pollution
| across the 576 counties.

  |=======                                |  18%

| Half the measured counties have a pollution
| level less than or equal to what number of
| micrograms per cubic meter?

1: 9.836
2: 11.360
3: 10.050
4: 8.549

Selection: 
Enter an item from the menu, or 0 to exit
Selection: 4

| Almost! Try again.

| The median indicates the 50% point.

1: 11.360
2: 10.050
3: 9.836
4: 8.549

Selection: 2

| Nice work!

  |=======                                |  19%

| To save you a lot of typing we've saved off
| pollution$pm25 for you in the variable ppm.
| You can use ppm now in place of the longer
| expression. Try it now as the argument of
| the R command quantile. See how the results
| look a lot like the results of the output of
| the summary command.

> quantile(ppm)
       0%       25%       50%       75% 
 3.382626  8.548799 10.046697 11.356012 
     100% 
18.440731 

| You're the best!

  |========                               |  20%

| See how the results are similar to those
| returned by summary? Quantile gives the
| quartiles, right? What is the one value
| missing from this quantile output that
| summary gave you?

| The minimum is the 0% quantile and the
| maximum is the 100% quantile. The median is
| the 50% quantile. That leaves only one
| choice.

1: the mean
2: the median
3: the minimum value
4: the maximum value

Selection: 1

| Great job!

  |========                               |  22%

| Now we'll plot a picture, specifically a
| boxplot. Run the R command boxplot with ppm
| as an input. Also specify the color
| parameter col equal to "blue".

> boxplot(ppm, col = "blue")

http://127.0.0.1:40443/graphics/plot_zoom_png?width=780&height=900

| You nailed it! Good job!

  |=========                              |  23%

| The boxplot shows us the same quartile data
| that summary and quantile did. The lower and
| upper edges of the blue box respectively
| show the values of the 25% and 75%
| quantiles.

| What do you think the horizontal line inside
| the box represents?

1: the maximum value
2: the median
3: the mean
4: the minimum value

Selection: 2

| You nailed it! Good job!

  |==========                             |  26%

| The "whiskers" of the box (the vertical
| lines extending above and below the box)
| relate to the range parameter of boxplot,
| which we let default to the value 1.5 used
| by R. The height of the box is the
| interquartile range, the difference between
| the 75th and 25th quantiles. In this case
| that difference is 2.8. The whiskers are
| drawn to be a length of range*2.8 or
| 1.5*2.8. This shows us roughly how many, if
| any, data points are outliers, that is,
| beyond this range of values.

| To see this, run the R command abline with
| the argument h equal to 12. Recall that 12
| is the EPA standard for air quality.

> abline(h=12)

| You are quite good my friend!

  |============                           |  30%

| What do you think this command did?

1: drew a horizontal line at 12
2: nothing
3: drew a vertical line at 12
4: hid 12 random data points

Selection: 
Enter an item from the menu, or 0 to exit
Selection: 1

| That's a job well done!

  |============                           |  31%

| So abline "adds one or more straight lines
| through the current plot." We see from the
| plot that the bulk of the measured counties
| comply with the standard since they fall
| under the line marking that standard.

  |=============                          |  32%

| Now use the R command hist (another function
| from the base package) with the argument
| ppm. Specify the color parameter col equal
| to "green". This will plot a histogram of
| the data.

> hist(ppm, col = "green")

http://127.0.0.1:40443/graphics/plot_zoom_png?width=780&height=900

| Great job!

  |=============                          |  34%

| The histogram gives us a little more
| detailed information about our data,
| specifically the distribution of the
| pollution counts, or how many counties fall
| into each bucket of measurements.


  |==============                         |  35%

| What are the most frequent pollution counts?

1: between 12 and 14
2: between 6 and 8
3: between 9 and 12
4: under 5

Selection: 3

| You're the best!

  |==============                         |  36%

| Now run the R command rug with the argument
| ppm.

> rug(ppm)

http://127.0.0.1:40443/graphics/plot_zoom_png?width=780&height=900

| Keep up the great work!
  |===============                        |  38%

| This one-dimensional plot, with its
| grayscale representation, gives you a little
| more detailed information about how many
| data points are in each bucket and where
| they lie within the bucket. It shows
| (through density of tick marks) that the
| greatest concentration of counties has
| between 9 and 12 micrograms per cubic meter
| just as the histogram did.

...

  |===============                        |  39%

| To illustrate this a little more, we've
| defined for you two vectors, high and low,
| containing pollution data of high (greater
| than 15) and low (less than 5) values
| respectively. Look at low now and see how it
| relates to the output of rug.

> high
[1] 16.19452 15.80378 18.44073 16.66180
[5] 15.01573 17.42905 16.25190 16.18358

| Give it another try. Or, type info() for
| more options.

| Type low at the command prompt.

> low
 [1] 3.494351 4.186090 4.917140 4.504539
 [5] 4.793644 4.601408 4.195688 4.625279
 [9] 4.460193 4.978397 4.324736 4.175901
[13] 3.382626 4.132739 4.955570 4.565808

| Your dedication is inspiring!

  |================                       |  41%

| It confirms that there are two data points
| between 3 and 4 and many between 4 and 5.
| Now look at high.

> high
[1] 16.19452 15.80378 18.44073 16.66180
[5] 15.01573 17.42905 16.25190 16.18358

| You got it right!

  |================                       |  42%

| Again, we see one data point greater than
| 18, one between 17 and 18, several between
| 16 and 17 and two between 15 and 16,
| verifying what rug indicated.

 |=================                      |  43%

| Now rerun hist with 3 arguments, ppm as its
| first, col equal to "green", and the
| argument breaks equal to 100.

> hist(ppm, col = "green", breaks = 100)

http://127.0.0.1:40443/graphics/plot_zoom_png?width=780&height=900
| You are doing so well!

  |=================                      |  45%

| What do you think the breaks argument
| specifies in this case?
