# Finance Project - Data Analysis with SQL


## World Bank Group International Development Association's Projects and Programs in Pakistan


In the summer of 1981, my family packed up our household in rural Idaho and flew around the world to a new home in Islamabad, Pakistan. I was 9 years old at the time and this was an adventure. My father's new role in USAID/Pakistan's Office of Agriculture and Rural Development would keep us there for the next six years. 

I saw, firsthand, the significant benefits of the World Bank and other development projects. Tarbela Dam, the world's largest earth-filled dam, was probably the first that I saw on a school field trip. The World Bank has funded a few projects there to expand hydroelectric production. (Appologies for my poor photography skills.)  

<img src="images/bankingtarbelafill.tif?raw=true"/><img src="images/bankingtarbelaspillway.tif?raw=true"/><img src="images/bankingtarbelagates.tif?raw=true"/>

Some World Bank projects - like the On-Farm Water Management Program - also had support and bilateral funding from USAID. While the World Bank and USAID have distinct roles, they often collaborate and coordinate their efforts to maximize the impact of their development projects. These are a few photos of irrigation rehab activities taken by my father in 1983.

<img src="images/bankingprojectroller.tif?raw=true"/><img src="images/bankingprojectscrapers.tif?raw=true"/>

-----

### The Data and Initial Thoughts

The dataset provided is from the World Bank Group -- specifically, [The International Development Association (IDA) Statement of Credits and Grants - Historical Data](/tdhttps://finances.worldbank.org/Loans-and-Credits/IDA-Statement-Of-Credits-and-Grants-Historical-Dat/tdwh-3krx) updated July 10, 2023. It is a listing of all development credits, grants, and loans provided to countries by the World Bank Group. 
- Data as of 30 June 2023
- 1.19M Rows & 30 Columns
- Each row represents a monthly statement mentioning a specific single credit or grant

Considering my history and personal experience, I will be focusing my analysis on IDA credits and grants to Pakistan. During my analysis, I will attempt to answer the following questions:
- How many total credits or grants have been extended to the country?
- The range of amounts committed by IDA for projects?
- Which project funding is for Tarbela Dam?
- How much Pakistan has received from IDA and how much has been paid back and still owed?
- The range and average of the service charge rate?

-----

### Insights
The first step in my analysis was to identify all credits or grants for Pakistan. My first query retrieves the specified columns, perform the necessary aggregations for each group (to eliminate duplicate entries caused by multiple statements), and then order the results based on the "Original Principal Amount (US$)" column in descending order for each unique combination of "Project ID" and "Credit Number" in the "banking_data" table where the country is 'Pakistan'.
From these results I can quickly see there are 310 projects loans or credits
They range from US$803,970.92 up to US$600,000,000.

<img src="images/q-listedprojectcredits.png?raw=true"/>
<img src="images/qr-listedprojectcredits.png?raw=true"/>


Next, I wanted to see the same information for any projects related to Tarbela Dam. I added a line to the query to find where the "Project Name" contains the case-insensitive substring 'tarbela'.

<img src="images/q-tarbelalist.png?raw=true"/>
<img src="images/qr-tarbelalist.png?raw=true"/>


I wondered how much Pakistan had received, repaid, and owed to the IDA. This query calculates the sums of various columns from the subquery's results, which aggregates data based on each unique combination of "Project ID" and "Credit Number" in the "banking_data" table where the country is 'Pakistan'. 
As of 30 June 2023, the data shows:
- Total disbursed by IDA US$24,074,944,917.75	
- Total repaid to IDA US$6,301,182,479.36	
- Total due to IDA US$7,964,484,570.26

<img src="images/q-sumlistedprojectcredits.png?raw=true"/>
<img src="images/qr-sumlistedprojectcredits.png?raw=true"/>


Lastly, I would like to find the average, minimum, and maximum service charge rates. This query calculates the average, minimum, and maximum service charge rates based on the subquery's results for each unique combination of "Project ID" and "Credit Number" in the "banking_data" table where the country is 'Pakistan'. The results are rounded to two decimal places using the ROUND function.

<img src="images/q-avgminmaxservicecharge.png?raw=true"/>
<img src="images/qr-avgminmaxservicecharge.png?raw=true"/>


-----

### Conclusions
The World Bank has been involved in various development projects and initiatives in Pakistan supporting: infrastructure development, education and health, water resource management, social safety nets, financial sector reforms, disaster recovery and resillience, governance and public sector management, trade and investment, and environmental sustainability. The data has shown:
- There are 310 projects loans or credits for Pakistan.
- The amounts committed (Original Principal Amounts) range from US$803,970.92 to US$600,000,000.
- Two grants relating to Tarbela Dam for which US$251,155,143.85 and US$35,000,000 has been disbursed.
- Average Service Charge Rate is 1.17%. The rate varies from 0% - 5.86%. (Note that the data dictionary indicates a "0" rate may indicate loans have more than one interest rate.)
- As of 30 June 2023, the data shows:
   - Total disbursed by IDA to Pakistan: US$24,074,944,917.75	
   - Total amount repaid to IDA: US$6,301,182,479.36	
   - Total due to IDA: US$7,964,484,570.26


-----
Thank you for taking the time to read my article! Your support and engagement is appreciated and I welcome your feedback and ideas. What can I do better?
