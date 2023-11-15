# WeGo Dictionary

A trip is defined as one run of the vehicle from one end of the route to another in one direction. Two trips = one round trip. The TRIP_ID field provides a unique indicator for each trip.
​

CALENDAR_ID: Identifier for the date<br>
SERVICE_ABBR: Service Type. indicates the schedule type operating that day. 1 = Weekday, 2 = Saturday, 3 = Sunday. Normally this corresponds to the day of the week, but sometimes Saturday or Sunday service will run on a weekday (i.e. during a holiday).<br>
ADHERENCE_ID: Unique identifier for each record.<br>
DATE: Trip date<br>
ROUTE_ABBR: Route identifier. Routes can be found here <https://www.wegotransit.com/ride/maps-schedules/bus/>. For example, Route 55 is Murfreesboro Pike<br>
BLOCK_ABBR: Indicates the section (block) of the route that the given stop is on<br>
OPERATOR: Indicates the operator (driver)<br>
TRIP_ID: Identifies the trip<br>
OVERLOAD_ID: signifies that the record is from a trip that was added by the dispatcher and was not part of the original schedule for the day. Usually, these are created when one vehicle breaks down and another is covering the same service. As far as the actual value, 0 means that this record was part of the original schedule, and _anything other than 0 means it was added._<br>
ROUTE_DIRECTION_NAME: Which direction the trip is going; Either to downtown or from downtown<br>
TIME_POINT_ABBR:<br>
ROUTE_STOP_SEQUENCE:<br>
TRIP_EDGE: defines whether the stop is the first one on the trip (1), an intermediate stop (0), or the last one on a trip (2)<br>
LATITUDE/LONGITUDE: Location in lat/long<br>
SCHEDULED_TIME: scheduled time<br>
ACTUAL_ARRIVAL_TIME: actual arrival time
ACTUAL_DEPARTURE_TIME: actual departure time<br>
ADHERENCE: Difference between actual departure time and scheduled time; negative indicates departure time after scheduled time and positive indicates departure time before scheduled time.<br>
SCHEDULED_HDWY: Scheduled headway in minutes for the given timepoint crossing record; headway is the difference between the scheduled_time and the previous scheduled time for that stop<br>
ACTUAL_HDWY: Actual headway; Notably, does not exclude overloads, as we want to know about them for actual headway performance<br>
HDWY_DEV: calculates headway deviation in minutes as the difference between actual and scheduled headway. Negative values indicate a shorter headway than scheduled (i.e. bunching) and positive values indicate a longer headway than scheduled (i.e. gapping)<br>
ADJUSTED_EARLY_COUNT:  <br>
ADJUSTED_LATE_COUNT:  <br>
ADJUSTED_ONTIME_COUNT:<br>
STOP_CANCELLED: flags whether a crossing was canceled or waived<br>
PREV_SCHED_STOP_CANCELLED: flags whether the previous timepoint crossing was cancelled or waived. Useful for excluding records where the headway values are extremely high because the bus is just coming off a detour<br>
IS_RELIEF: flags whether a particular crossing is a relief - i.e. the first timepoint crossing of a new driver on the bus/block<br>
BLOCK_STOP_ORDER:<br>
DWELL_IN_MINS: Actual Departure Time - Actual Arrival Time (in minutes)<br>
