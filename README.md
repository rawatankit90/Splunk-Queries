# Splunk-Queries

Ex. of creating table after extracting data

 index="xyx" namespace=qa container_name="xys" "search_message" | rex field=_raw "regular_expr:(?<Id>\d+)\: "| rex field=_raw "BODY=\"(?<input_json>.*)" |table Iid input_json
 
 Ex. of creating table after extracting data and applying filter
 
 index="xyz" source="abc.log" "search_message" earliest=-1d | rex field=_raw "regular_expr:(?<Id>\d+)"| transaction Id| where duration>0|table Id duration _time
