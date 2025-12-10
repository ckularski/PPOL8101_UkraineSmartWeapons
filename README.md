# The Cost of Smart Weapons in Ukraine Dataset
A dataset to support a research project at UNC Charlotte investigating the impact of smart weapon use in the conflict between Russia and Ukraine. 

## Technologies Implemented
The data for this project was assembled from various online data sources and then stored in a MariaDB database utilizing MySQL language standards. 

## How to Use
This repository contains a single-file SQL repository. To use this file, establish a connection to a compatible server running any implementation of the MySQL standard, then execute the script. The script will create the database, load the initial data tables, and create derivative views. 

## Core Tables

### missile_attacks_daily
|Column Name |SQL Data Type |R Type	||Description |
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

### warspotting_losses

## Dervived Views

### ukraine_monthly_stats

### un_ukraine_general_monthly