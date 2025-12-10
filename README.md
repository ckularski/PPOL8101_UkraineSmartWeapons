# The Cost of Smart Weapons in Ukraine Dataset
A dataset to support a research project at UNC Charlotte investigating the impact of smart weapon use in the conflict between Russia and Ukraine. 

## Technologies Implemented
The data for this project was assembled from various online data sources and then stored in a MariaDB database utilizing MySQL language standards. 

## How to Use
This repository contains a single-file SQL repository. To use this file, establish a connection to a compatible server running any implementation of the MySQL standard, then execute the script. The script will create the database, load the initial data tables, and create derivative views. 

## Core Tables

### missile_attacks_daily
|Column Name |SQL Data Type |R Type	|Description |
| ----------- | ----------- | ----------- | ----------- |
|ObsID	|int(11) NOT NULL	|integer	|Unique Observation Identifier. This is the primary key.|
|time_start	|datetime	|numeric	|Event/Attack Start Date and Time.|
|time_end	|datetime	|numeric	|Event/Attack End Date and Time.|
|model	|varchar(128)	|character	|Model of weapon in use.|
|launch_place	|text	|character	|Location of weapon launch, if known.|
|target	|text	|character	|Target destination of weapon, if known.|
|target_main	|varchar(128)	|character	|Primary target of attack, if known.|
|launched	|int(11)	|integer	|Number of weapons launched.|
|destroyed	|int(11)	|integer	|Number of weapons destroyed (ex: intercepted).|
|not_reach_goal	|text	|character	|Information on weapons that did not reach their intended target (ex: number of drones).|
|still_attacking	|integer	|integer	|Information on ongoing attacks or weapons that may still be airborne.|
|border_crossing	|text	|complex	|Information regarding weapons that crossed a border.|
|is_shahed	|int(11)	|integer	|Number of Israeli Shahed type drones in the attack.|
|num_hit_location	|int(11)	|integer	|Number of locations hit during the attack.|
|num_fall_fragment_location	|int(11)	|integer	|Number of locations where falling debris or fragments were observed.|
|carrier	|text	|character	|Aircraft model or other transport used for weapon deployment.|
|turbojet	|int(11)	|integer	|Number of turbojets in use.|
|turbojet_destroyed	|int(11)	|integer	|Number of turbojets destroyed.|
|affected region	|text	|complex	|Data object containing impacted regions (ex: a list of provinces/states).|
|destroyed_details	|text	|complex	|Detailed information on destroyed weapons.|
|launched_details	|text	|complex	|Detailed information on launched weapons.|
|launch_place_details	|text	|complex	|Detailed information on the weapon launch location.|
|source	|text	|character	|Original source URL documenting the attack.|

### un_ukraine_casualties
|Column Name	|SQL Data Type	|R Data Type	|Description|
| ----------- | ----------- | ----------- | ----------- |
|ObsID	|int(11) NOT NULL	|integer	|Unique Observation Identifier. This is the primary key for the record.|
|Country	|varchar(128)	|character	|Country name (Expected to be 'Ukraine' for all records).|
|Admin1	|varchar(128)	|character	|Province or first-level administrative division (ex: Oblast name).|
|Admin2	|varchar(128)	|character	|Administrative district or second-level administrative division (ex: Raion name).|
|ISO3	|varchar(24)	|character	|3-Character ISO-3166 Country Code (Expected to be 'UKR').|
|Admin2 Pcode	|text	|character	|P-code (humanitarian operational code) for the Administrative district (Admin2).|
|Admin1 Pcode	|text	|character	|P-code (humanitarian operational code) for the Province (Admin1).|
|Month	|varchar(24)	|character	|Month of event (ex: January, February).|
|Year	|int(11)	|integer	|Year of event.|
|MonthStarting	|date	|numeric	|First day of event month (ex: January 1, 2022).|
|Events	|int(11)	|integer	|Number of attacks/hostile events recorded for the specified region and time period.|
|Fatalities	|int(11)	|integer	|Number of recorded fatalities for the specified region and time period.|

### warspotting_losses
|Column Name	|SQL Data Type	|R Data Type	|Description|
| ----------- | ----------- | ----------- | ----------- |
|id	|int(11) NOT NULL	|integer	|Observation ID. This is the unique identifier for each loss record.|
|date	|datetime	|numeric	|Event date and time when the loss occurred.|
|type	|varchar(128)	|character	|Type of weapon or military asset (ex: Tank, APC, Aircraft).|
|model	|varchar(128)	|character	|Model of weapon or military asset (ex: T-72B3, M2 Bradley).|
|status	|varchar(128)	|character	|Status of the weapon after the event (ex: Destroyed, Captured, Damaged).|
|lost_by	|varchar(128)	|character	|Country losing the asset.|
|nearest_location	|text	|character	|Recognized location nearest the loss event.|
|geo	|text	|character	|Geographic coordinate pair for the loss location.|
|lat	|double	|numeric	|Latitude of the loss location.|
|long	|double	|numeric	|Longitude of the loss location.|
|unit	|text	|character	|Military unit responsible for the weapon/asset.|
|tags	|text	|character	|Text tags for categorization or supplementary context.|
|comment	|text	|character	|Additional comments or narrative regarding the loss event.|
|sources	|text	|character	|Source information, if available.|

## Dervived Views

### ukraine_monthly_stats

### un_ukraine_general_monthly