# YAML-JSONForMe
https://kodekloud.com/courses/635226/lectures/11338837
In YML, the key and value are seperated by :<space>
Name: Ravi
# - Indicates its an element of an array/List
Fruits:
	- Orange
	- Mangoe
	- Apple
Vegetables:
	- Spinach
	- Bottleguard
	- Carrot

# Dictionary/Map
Banana:
	Calories: 105
	Fat: .4 g
	Carbs: 27 g
Grapes:
	Calories: 62
	Fat: 0.3  g
	Carbs: 16 g

# To retrieve a value
	Banana.Calories returns [105]
# $ notation to denote the root element
	$.Banana.Calories return [105] 
	$Banana returns [{Calories: 105,Fat: .4 g,Carbs: 27 g}]
Note: The output of any queries above is always a array
	$[0] =105
	$[0]={Calories: 105,Fat: .4 g,Carbs: 27 g}
# To get group of values from an array
["car","bus","truck","van"]
$[0,3] = ["Car","Van"]  //get the list of 1st and 4th element at index 0 and 3 respectively
$[0:3] //gets the list of elements from 1st to 4th elements not including the element itself at index 0 and 2 respectively .here 3 is the number of elements retrived from 0th index
$[-1:0] //gets the last item in the list. Last index is -1 and last but one is -2 etc
$[-3:0] //gets the last 3 items of the list.
$[0:5:4]  //gets [ "Apple", "Facebook"] step 4
[
  "Apple",
  "Google",
  "Microsoft",
  "Amazon",
  "Facebook",
  "Coca-Cola",
  "Samsung",
  "Disney",
  "Toyota",
  "McDonald's"
]


# $. & $[
If the root element is object ({) query as $.
If the root element is array([) query as $[

# Get all items greater than 40

[10,20,30,40,50,60,70,80,90]
$[?(@>40)] //here ? Is conditional statement , @ is like for each items. So print all those items >40
This returns [50,60,70,80,90]
$[?(@==40)] //this will print 40
$[?(@!=40)] //this will print all numbers not equal to 40

#  @ in & @ nin
@ in[40,43,45] // prints all numbers in this range
@ nin[40,43,45] //prints all number not in range

# Json-path criteria


$.car.wheels[@(location=="rear-right")].model //this will print "X236DEM"

# Wild cards
$.car.wheels[*].location //results in  ["front-right", "rear-right", "front-left", "rear-left"]

# Lists


