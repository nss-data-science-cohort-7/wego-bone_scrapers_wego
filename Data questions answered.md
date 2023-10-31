### Data questions answered

#### There are a large number of observations where the actual arrival time is the exact same second as the actual departure time. Are these stops where the bus didn't end up stopping?
- Most mid-trip timepoints will only have a single recorded time, but they may still have stopped. If the bus was there for less than a few minutes, then only one time is recorded.
#### Is there a relationship between headway and adjusted late or early count? Some headway devs are null, but the late count is 1.
- Adjusted late counts are derived from schedule adherence and do not relate directly to headway.
- Buses with adherence values of beyond negative 6 are generally considered late.
#### Besides a bus being the first one on a route, are there any other reasons for a null value in the headway column?
- This value will be null for all records where Trip_Edge = 2 (last stop on trip). This is because we only track headway for departures, and the last stop is an arrival only.
#### Is there an acceptable range for headway deviation?
- Our generally accepted range is 50% to 150% of the scheduled headway. For example, if scheduled headway is 10 minutes, a headway deviation in either direction of 5 minutes or less would be acceptable, even if it isn’t ideal.
#### What is the meaning of the adjusted columns (ADJUSTED_EARLY_COUNT, ADJUSTED_LATE_COUNT, ADJUSTED_ONTIME_COUNT), and how are they being adjusted?
- Adjusted means that some additional logic has been used beyond just the adherence value, where beyond negative 6 is late and beyond +1 is early, with everything in between being on-time.
- This logic includes scenarios where our staff applied waivers to allow early departures, such as an express bus that has already picked up everyone at a park-and-ride lot and is only dropping people off at the remaining stops.
- This logic also allows for early timepoint records for all records where Trip_Edge = 2 (end of trip), since it is not a problem if a bus ends its trip early as long as it didn’t pass other timepoints early along the way.