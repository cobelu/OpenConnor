# OpenConnor

If I have data about me that I'm willing to share, then I will upload it here.

Currently, the datasets available are:

## `SmartApt.sql`
* Google Home data over roughly three months. Includes on/off data for all smart plugs and energy usage data from Samsung smart plugs.
* Suggested queries:
    * Total energy usage in kW:
        * `SELECT SUM(EventValue)/1000 AS "Total kW" FROM Home WHERE EventName='power';` 
    * Total energy usage in kWh:
        * `SELECT 5*SUM(EventValue)/(1000*60) AS "Total kWh" FROM Home WHERE EventName='power';`
    * Switches per device:
        * `SELECT device, EventValue, COUNT(*) FROM Home WHERE EventName='switch' GROUP BY device, EventValue;`
