# WeGo Public Transit
[WeGo Public Transit](https://www.wegotransit.com/) is a public transit system serving the Greater Nashville and Davidson County area. WeGo provides local and regional bus routes, the WeGo Star train service connecting Lebanon to downtown Nashville, along with several other transit services.

In this project, you'll be analyzing the bus spacing to look for patterns and try to identify correlations to controllable or external factors. Specifically, you'll be using a dataset containing information on the headway, or amount of time between vehicle arrivals at a stop. This dataset contains a column HDWY_DEV, which shows the headway deviation. This variable will be negative when bunching has occurred (shorter headway than scheduled) and will be positive for gapping (longer headway than scheduled). Note that you can calculate headway deviation percentage as HDWY_DEV/SCHEDULED_HDWY.

Goals of this project:
1. How much impact does being late or too spaced out at the first stop have downstream?
2. What is the impact of the layover at the start of the trip (the difference between the first top arrival and departure time)? Does more layover lead to more stable headways (lower values for % headway deviation)?
3. How closely does lateness (ADHERENCE) correlate to headway?
4. What is the relationship between distance or time travelled since the start of a given trip and the headway deviation? Does headway become less stable the further along the route the bus has travelled?
5. How much of a factor does the driver have on headway and on-time performance? The driver is indicated by the OPERATOR variable.
6. How does direction of travel, route, or location affect the headway and on-time performance?
7. How does time of day or day of week affect headway and on-time performance? Can you detect an impact of school schedule on headway deviation (for certain routes and at certain times of day)?
8. Does weather have any effect on headway or on-time performance? To help answer this question, the file bna_weather.csv contains historical weather data recorded at Nashville International Airport. 

As far as hypotheses to test, I would start with looking at how layover at the beginning of a trip affects the headway on that trip, but all of the noted questions are valid and potentially interesting areas of investigation. [These other questions are "Is it of interest to look at how the dwell time along the route affects headway?" and "Is it of interest to look at layover vs. subsequent buses on the same route?"] Note that there is a difference between the scheduled layover (essentially, planned dwell in the schedule) and the actual dwell time.


Michael's comments
Boxplots on slides 2-5:

    Indicate on the slides that outliers are not shown
    On your boxplots, you might add a sentence to call out the most interesting parts. “Route XX generally had higher variability that other routes”, for example.
    It’s kind of interesting that route 22 had a positive adherence value so often. The third quartile is positive. What percentage of the time was it running too early?
    On the days of week ones, I would probably have Monday first so that the weekdays aren’t split up.

Start vs. End Adherences:

    Really like how you made sure that the trips are complete.
    On the start vs end adherence, did you find a regression line? I would guess that it would be close to y = x, but if it’s not, that might be interesting, as it could indicate that, for example, even if you are on time to start, you tend to be late on average at the end.
    There are so many points on this one that you might want to explore alternative ways to plot it. Adjusting the alpha value or converting to a heatmap could potentially work.
    On your later analysis, you split by route. Did you do this for start vs. end adherence to see if there was any difference across routes?

Adherence vs. Headway Deviation:

    Again, with so many points, it might be clearer with some kind of adjustment to the scatterplot.
    Did you find a stronger or weaker relationship from certain routes or certain days?

Dwell Time vs. Headway

    It looks like on average, headway deviation is zero for all values of dwell time. Does the variability in headway shrink as dwell time increases? It almost looks like that, but that might also just be that longer dwell times are less common.

Trip Duration vs. Headway

    Again, it looks like on average headway deviation is 0, but is there any difference in the variability?