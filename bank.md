# The Finance Project - World Bank Group International Development Association's Projects and Programs in Pakistan


In the summer of 1981 my family packed up our household in rural Idaho and flew around the world to a new home and adventure in Islamabad, Pakistan. My father's new role in USAID/Pakistan's Office of Acriculture and Rural Development would keep us there for the next six years. I saw, first hand, the benefits of many World Bank projects. Tarbela Dam, the worlds largest earth-filled dam, was one of them that I saw on a school field trip. The World Bank has funded a few projects to expand the hydroelectric production. (Sorry for my poor photography skills.)  

<img src="images/bankingtarbelafill.tif?raw=true"/><img src="images/bankingtarbelaspillway.tif?raw=true"/><img src="images/bankingtarbelagates.tif?raw=true"/>

Some World Bank projects - like the On-Farm Water Management Program - also had support and bilateral funding from USAID. While the World Bank and USAID have distinct roles, they often collaborate and coordinate their efforts to maximize the impact of their development projects. These are a few photos of countryside and irrigation rehab activities taken by my father in 1983.

<img src="images/bankingprojectroller.tif?raw=true"/><img src="images/bankingprojectscrapers.tif?raw=true"/>


### The Data and Initial Observations

The dataset is from the World Bank -- specifically, [The International Development Association (IDA) Statement of Credits and Grants - Historical Data](https://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx) updated July 10, 2023. It is a listing of all development credits, grants, and loans provided to countries by the World Bank Group. 
- Data as of 30 June 2023
- 1.19M Rows & 30 Columns
- Each row represents a monthly statement mentioning a specific single credit or grant

Considering my history and personal experience in Pakistan I will be focusing my analysis on IDA credits and grants to Pakistan.

### Insights
The first step in my analysis was to identify all credits or grants for Pakistan. My first query retrieves the specified columns, perform the necessary aggregations for each group (to eliminate duplicate entries caused by multiple statements), and then order the results based on the "Original Principal Amount (US$)" column in descending order for each unique combination of "Project ID" and "Credit Number" in the "banking_data" table where the country is 'Pakistan'.
From these results I can quickly see there are 310 projects loans or credits
They range from US$803,970.92 to US$600,000,000.

<img src="images/q-listedprojectcredits.png?raw=true"/>
<img src="images/qr-listedprojectcredits.png?raw=true"/>

Next, I wanted to see the same information for any projects related to Tarbela Dam. I added a line to the query to find where the "Project Name" contains the case-insensitive substring 'tarbela'.

<img src="images/q-tarbelalist.png?raw=true"/>
<img src="images/qr-tarbelalist.png?raw=true"/>

<img src="images/q-sumlistedprojectcredits.png?raw=true"/>
<img src="images/qr-sumlistedprojectcredits.png?raw=true"/>

<img src="images/q-avgminmaxservicecharge.png?raw=true"/>
<img src="images/qr-avgminmaxservicecharge.png?raw=true"/>


### Conclusions


Thank you for taking the time to read my article! Your support and engagement is appreciated and I welcome your feedback and ideas. What can I do better?
