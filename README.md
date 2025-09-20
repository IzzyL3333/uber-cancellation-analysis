# Data Analysis on Uber Data 🚗
This exercise aimed to provide valuable, data-derived insights into Uber data, as it is a common transportation company across 70 countries. As a Data Scientist, I performed basic EDA and data analysis using real Uber data. 

## Table of Contents
- [Data](#data)
- [Work](#work)
- [Results](#results)
- [Future Considerations](#future-considerations)

---

<a id="data"></a>
### Data :books:
The data was originally sourced from <a href="[https://www.chicago.gov/city/en/depts/cdph/supp_info/infectious/west_nile_virus_surveillancereports.html](https://www.kaggle.com/datasets/yashdevladdha/uber-ride-analytics-dashboard)" target="_blank">Kaggle</a>. 

The data consisted of one table of Uber transactions, such as Booking Status, Vehicle Type, and Payment Method. 

**Table: ncr_ride_bookings**
|Column Name| Description|
|---|---|
|Date |Date of the booking|
|Time |Time of the booking|
|Booking ID |Unique identifier for each ride booking|
|Booking Status |Status of booking (Completed, Cancelled by Customer, Cancelled by Driver, etc.)|
|Customer ID |	Unique identifier for customers|
|Vehicle Type |Type of vehicle (Go Mini, Go Sedan, Auto, eBike/Bike, UberXL, Premier Sedan)|
|Pickup Location |	Starting location of the ride|
|Drop Location | Destination location of the ride|
|Avg VTAT |Average time for driver to reach pickup location (in minutes)|
|Avg CTAT |Average trip duration from pickup to destination (in minutes)|
|Cancelled Rides by Customer |Customer-initiated cancellation flag|
|Reason for cancelling by Customer	|Reason for customer cancellation|
|Cancelled Rides by Driver |Driver-initiated cancellation flag|
|Driver Cancellation Reason |Reason for driver cancellation|
|Incomplete Rides |Incomplete ride flag|
|Incomplete Rides Reason |Reason for incomplete rides|
|Booking Value |Total fare amount for the ride|
|Ride Distance|Distance covered during the ride (in km)|
|Driver Ratings|	Rating given to driver (1-5 scale)|
|Customer Rating|Rating given by customer (1-5 scale)|
|Payment Method|Method used for payment (UPI, Cash, Credit Card, Uber Wallet, Debit Card)|

---

<a id="work"></a>
### Work :bar_chart:

Using Python, the following questions were answered.

- What is the shape of the dataframe?
- Pick two categorical columns: What data are they storing? How are they distributed?
- What are the peak hours of Total Bookings across different Vehicle Types?
- What are the peak hours of Total Bookings across different Vehicle Types, excluding Completed Rides?
- During peak hours, what are the common Booking Status across different Vehicle Types?
- During peak hours, what are the common reasons for driver and customer cancellations?  

---

<a id="results"></a>
### Results :eyes:

The shape of the dataframe is **21 columns** and **150,000 rows** in the Uber data.

#### 1st Categorical Column: Vehicle Type
<img width="1003" height="492" alt="image" src="https://github.com/user-attachments/assets/beb3e524-3f23-4f01-b1dd-0de696169258" />

**Auto** is the most common form of Vehicle Type customers use in service with Uber.

#### 2nd Categorical Column: Booking Status
<img width="1005" height="484" alt="image" src="https://github.com/user-attachments/assets/b2331d7e-6e94-40a8-94e4-a16a83c5b338" />

**Completed** is the most common form of Booking Status in service with Uber.  

####  Hourly Total Bookings by Vehicle Type 
<img width="1074" height="360" alt="image" src="https://github.com/user-attachments/assets/7e22d7f9-bc26-4004-98c8-31bc1701672c" />

The peak hour of the total bookings for the DAY is **10:00 (10 am)**, where **Auto** is the most common Vehicle Type.

The peak hour of the total bookings for the NIGHT is **18:00 (6 pm)**, where **Auto** is the most common Vehicle Type.

#### Hourly Bookings by Vehicle Type excluding Completed Rides
<img width="1073" height="364" alt="image" src="https://github.com/user-attachments/assets/daf39f22-f90d-45bb-b021-6a35caf7064a" />

The peak hour of the total bookings excluding Completed Rides for the Day is **10:00 (10 am)**, where **Auto** is the most common Vehicle Type.

The peak hour of the total bookings excluding Completed Rides for the Night is **18:00 (6 pm)**, where **Auto** is the most common Vehicle Type.

#### Booking Status during DAY Peak Hour by Vehicle Type excluding Completed Rides
<img width="853" height="615" alt="image" src="https://github.com/user-attachments/assets/e432d65c-5710-4bba-89fe-53298fc6630f" />

#### Booking Status during NIGHT Peak Hour by Vehicle Type excluding Completed Rides
<img width="880" height="614" alt="image" src="https://github.com/user-attachments/assets/296ce807-3b2f-4f2d-8600-9eaa358bae51" />

Across both DAY and NIGHT peak hours, **Cancellation by Driver** was the common Booking Status across all Vehicle Types, excluding Completed Rides.

#### Reason for Booking Cancellations from Customers
<img width="858" height="622" alt="image" src="https://github.com/user-attachments/assets/401d376f-824d-4af3-8134-14ea4b3d8b53" />


<img width="866" height="625" alt="image" src="https://github.com/user-attachments/assets/fbddfb8c-a871-4a96-b013-1a44efdb2fff" />

For the DAY peak, the reasons for cancellation by customers across all Vehicle Types differ significantly. 
- Primary reason for cancellation by Customer for Bike, Sedan, Premier Sedan: **Driver asked to cancel** 
- Primary reason for cancellation by Customer for Auto, Go Mini: **Driver is not moving towards pickup location**
- Primary reason for cancellation by Customer for Uber XL, eBike: **change of plans**

For the NIGHT peak, the reasons for cancellation by customers across all Vehicle Types differ significantly. 
- Primary reason for cancellation by Customer for Auto: **wrong address** and **change of plans**
- Primary reason for cancellation by Customer for Bike: **Driver is not moving towards pickup location** and **wrong address** 
- Primary reason for cancellation by Customer for Go Mini: **wrong address**
- Primary reason for cancellation by Customer for Go Sedan: **AC is not working** and **Driver is not moving towards pickup location**
- Primary reason for cancellation by Customer for Uber XL: **AC is not working** and **wrong address**
- Primary reason for cancellation by Customer for eBike: **Driver asked to cancel**

#### Reason for Booking Cancellations from Drivers
<img width="861" height="624" alt="image" src="https://github.com/user-attachments/assets/1e462987-b4f4-46a6-aa77-9eb98a2a7d06" />
<img width="858" height="621" alt="image" src="https://github.com/user-attachments/assets/979e9a35-8415-4d44-84d5-c2a41657524e" />

Across both DAY and NIGHT peaks, **Customer related issue** and **More than permitted people in there** were the most common reasons for cancellation by driver across all Vehicle Types.

--- 

<a id="future-considerations"></a>
**Future Considerations**
- Perform statistical analysis to determine the relationship between Vehicle Type and Booking Status.
- Run a linear regression to determine how the independent variables affect the Booking Value. 

Thanks for reading! 🚗
