# A Quick Bullshit Meter Improvement

I did a quick weekend project hoping to improve the general public's bullshit
meter when it comes to reading charts. This began with
[this](https://twitter.com/WhiteHouseCEA/status/1039233216308240384) series of
tweets from the White House Council of Economic Advisers, and specifically
[this tweet](https://twitter.com/WhiteHouseCEA/status/1039233534030962691)
which contained the following chart that I found immensely disingenuous:

![Chart in question](https://raw.githubusercontent.com/khwilson/linearproblems/master/badtrend.jpg)

My tweet thread explaining why you should really take this chart with a grain of
salt is [here](https://twitter.com/khayeswilson/status/1042044243706097666), but the summary is thus:
#. be suspicious of extrapolation
#. before extrapolation, the true data should be randomly scattered above and below the trend line
#. don’t trust charts without error bars
#. always ask “why did you choose that smoother.”

## Want to do the other charts?

Many of the other charts suck too. I'd love to see other people (especially students)
take a swing at why they are bad. Here is how you can use these files to take a crack
at them.

### Getting data from the chart

I didn't have time to figure out how to get data out of the BLS website (I'm
sure it's easy enough, but I got a bit lost). So I used a quick little piece of
JavaScript that I keep around for this purpose. To use it, put the image you
want to extract data from in this directory. Then look at line 13 of
[getmouse.html](https://github.com/khwilson/linearproblems/blob/master/getmouse.html).
Change what there is `badtrend.jpg` to the name of your image.

Next, click on each tick on the x axis and each tick on the y axis. You'll see the
coordinates getting added to the text box below your image. You may want to label
these coordinates so you remember which coordinate belonged to which tick.

Then I clicked along the actual data. I didn't worry too much about getting this
evenly spaced since I smoothed it out later.

### Moving data into the notebook

The rest of the miniproject takes place in Python. If you open `Work.ipynb`,
you'll need to change the values of `xticks_raw` to be the collection of points
you collected from clicking on the x ticks, `yticks_raw` to be those from the y
ticks, and `points_raw` to be the rest of your points. You also need to change
the values of `MIN_Y` and `MAX_Y` to the minimum and maximum values on the y
axis of the original chart.

From there, you can run the notebook as is and it should work. However, you can
play around near the bottom with the `make_plot_with_cutoff`s, which lets you
make various adjustments to your charts.

## What do I need to really get started?

You need a working copy of Python with the packages in `requirements.txt`
installed. You also need a web browser to open the one HTML file.

## License

MIT
