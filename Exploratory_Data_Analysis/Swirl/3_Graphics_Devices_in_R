| Run the R command ?Devices to see what
| graphics devices are available on your
| system.

> ?Devices

| Nice work!

  |========                             |  21%

| R Documentation shows you what's available.

> with(faithful, plot(eruptions, waiting))

| All that hard work is paying off!

  |===========                          |  30%

| See how R created a scatterplot on the
| screen for you? This shows that relationship
| between eruptions of the geyser Old Faithful
| and waiting time. Now use the R function
| title with the argument main set equal to
| the string "Old Faithful Geyser data". This
| is an annotation to the plot.

> title(main = "Old Faithful Geyser data")

| Excellent job!

  |============                         |  33%

| Simple, right?  Now run the command
| dev.cur(). This will show you the current
| plotting device, the screen.

> dev.cur()
RStudioGD 
        2 

| That's the answer I was looking for.

  |=============                        |  36%

| The second way to create a plot is to send
| it to a file device. Depending on the type
| of plot you're making, you explicitly launch
| a graphics device, e.g., a pdf file. Type
| the command pdf(file="myplot.pdf") to launch
| the file device. This will create the pdf
| file myplot.pdf in your working directory.

> pdf(file="myplot.pdf")

| You are doing so well!

  |===============                      |  39%

| You then call the plotting function (if you
| are using a file device, no plot will appear
| on the screen). Run the with command again
| to plot the Old Faithful data. Use the up
| arrow key to recover the command and save
| yourself some typing.

> with(faithful, plot(eruptions,waiting))

| Your dedication is inspiring!

  |================                     |  42%

| Now rerun the title command and annotate the
| plot. (Up arrow keys are great!)

> title(main = "Old Faithful Geyser data")

| You got it!

  |=================                    |  45%

| Finally, when plotting to a file device, you
| have to close the device with the command
| dev.off(). This is very important! Don't do
| it yet, though. After closing, you'll be
| able to view the pdf file on your computer.

  |==================                   |  48%

| There are two basic types of file devices,
| vector and bitmap devices. These use
| different formats and have different
| characteristics. Vector formats are good for
| line drawings and plots with solid colors
| using a modest number of points, while
| bitmap formats are good for plots with a
| large number of points, natural scenes or
| web-based plots.

...

  |===================                  |  52%

| We'll mention 4 specific vector formats. The
| first is pdf, which we've just used in our
| example. This is useful for line-type
| graphics and papers. It resizes well, is
| usually portable, but it is not efficient if
| a plot has many objects/points.

  |=====================                |  58%

| The last two vector formats are
| win.metafile, a Windows-only metafile
| format, and postscript (ps), an older format
| which also resizes well, is usually
| portable, and can be used to create
| encapsulated postscript files.
| Unfortunately, Windows systems often donâ€™t
| have a postscript viewer.

...

  |======================               |  61%

| We'll also mention 4 different bitmap
| formats. The first is png (Portable Network
| Graphics) which is good for line drawings or
| images with solid colors. It uses lossless
| compression (like the old GIF format), and
| most web browsers can read this format
| natively. In addition, png is good for plots
| with many points, but it does not resize
| well.

 |========================             |  64%

| In contrast, jpeg files are good for
| photographs or natural scenes. They use
| lossy compression, so they're good for plots
| with many points. Files in jpeg format don't
| resize well, but they can be read by almost
| any computer and any web browser. They're
| not great for line drawings.

...

  |=========================            |  67%

| The last two bitmap formats are tiff, an
| older lossless compression meta-format and
| bmp which is a native Windows bitmapped
| format.

  |===========================          |  73%

| The currently active graphics device can be
| found by calling dev.cur(). Try it now to
| see what number is assigned to your pdf
| device.

> dev.cur()
pdf 
  5 

| That's a job well done!

  |============================         |  76%

| Now use dev.off() to close the device.

> dev.off()
RStudioGD 
        2 

| Great job!

  |=============================        |  79%

| Now rerun dev.cur() to see what integer your
| plotting window is assigned.

> dev.cur()
RStudioGD 
        2 

| Nice work!

  |==============================       |  82%

| The device is back to what it was when you
| started. As you might have guessed, every
| open graphics device is assigned an integer
| greater than or equal to 2. You can change
| the active graphics device with
| dev.set(<integer>) where <integer> is the
| number associated with the graphics device
| you want to switch to.

  |=================================    |  88%

| Just for fun, rerun the with command again,
| with(faithful, plot(eruptions, waiting)), to
| plot the Old Faithful data. Use the up arrow
| key to recover the command if you don't feel
| like typing.

> dev.copy(png, file = "geyserplot.png")
png 
  5 

| All that hard work is paying off!

  |==================================== |  97%

| Don't forget to close the PNG device! Do it
| NOW!!! Then you'll be able to view the file.

> dev.off()
RStudioGD 
        2 

| Keep working like that and you'll get there!

  |=====================================| 100%

| Congrats! We hope you found this lesson
| deviced well!
