# True-Safe-Cars

The objective of this ETL project was to provide our client, TrueSafeCars.com, with a database containing a consolidated inventory their cars.  Our client was formed by buying inventory from two major used car dealership chains.  To support their business goals, we were tasked with this ETL project with the following goals:
1.	Consolidate the inventory into a central database 
2.	Assign the inventory to one of TrueSafeCars.com’s five main offices 
3.	Identify which vehicles should be sold at auction (vs. selling to the public) 
4.	Identify which vehicles meet our safety guidelines 
5.	Identify recall information per vehicle 

### Extract Requirements 
Pull vehicle inventory data from the two dealerships we purchased: 
*	Data for purchased dealership #1: Kaggle.com (https://www.kaggle.com/jpayne/852k-used-car-listings)
*	Data for purchased dealership #2: Kaggle.com (https://www.kaggle.com/austinreese/craigslist-carstrucks-data) 

### Transform Requirements 
Once all of the vehicle inventory data has been extracted, perform the following transformations: 
*	Remove duplicate VIN numbers
*	Assign the inventory to one of five main office locations. The client has provided a CSV file with the State-to-Main Office mapping. Our 5 main office locations are: 
    *	Northeast Main Office 
    *	Southeast Main Office 
    * Midwest Main Office 
    * Southwest Main Office 
    * West Main Office 
*	Assign each vehicle an overall safety rating using an API from NHTSA.gov (https://webapi.nhtsa.gov/Default.aspx?SafetyRatings/API/5)
*	Determine the number of open recalls per vehicle using an API from NHTSA.gov  (https://webapi.nhtsa.gov/Default.aspx?Recalls/API/83)

The vehicle inventory should have a column to indicate if the vehicle is ready to be sold to the public or not: 
*	Vehicles 20 years old or older should be sold at auction 
*	Vehicles with an overall poor safety rating should be sold at auction 
*	Vehicles in poor condition (if this information is available in the inventory data) should be sold at auction 

### Load Requirements 
Load transformed data into a central database (NoSQL). The central database should have tables that can be easily queried to retrieve: 
*	Vehicles assigned to each main office 
*	Vehicles that are ready to be sold to the public 
*	Vehicles that should be sold at auction 
*	Overall safety rating for each vehicle 
*	Recalls that apply to each vehicle 

Screenshot of MongoDB Compass: 

![image](https://user-images.githubusercontent.com/61704055/94389334-9dea7600-011d-11eb-85a5-7709cd3b6fb8.png)

Screenshots from the client acceptance website are shown below.  Note that the website features sorting by Mileage, Year, Make, and Price.

![image](https://user-images.githubusercontent.com/61704055/94389382-c2dee900-011d-11eb-9e1b-306a3aa5f5db.png)
![image](https://user-images.githubusercontent.com/61704055/94389404-d0946e80-011d-11eb-952d-8d7ca0d7b69d.png)
![image](https://user-images.githubusercontent.com/61704055/94389432-ddb15d80-011d-11eb-9fc2-e781de1bd4fd.png)
![image](https://user-images.githubusercontent.com/61704055/94389448-e6a22f00-011d-11eb-87ce-97fc0305d338.png)

In addition, the website features routes with JSON output:

![image](https://user-images.githubusercontent.com/61704055/94389486-fc175900-011d-11eb-9e09-f0df176230cf.png)
![image](https://user-images.githubusercontent.com/61704055/94389511-05082a80-011e-11eb-9842-4b3f8cbaa338.png)
![image](https://user-images.githubusercontent.com/61704055/94389521-0f2a2900-011e-11eb-8136-fbe4d53efcb2.png)
![image](https://user-images.githubusercontent.com/61704055/94389536-18b39100-011e-11eb-8c07-b0cabdf5fbfc.png)
![image](https://user-images.githubusercontent.com/61704055/94389551-25d08000-011e-11eb-9f8d-1a27c7d77f91.png)

Link to repository with website code:
https://github.com/SamuelParks/True-Cars-Website


























