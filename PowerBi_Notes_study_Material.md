
Power Bi Notes:

youtube:
https://www.youtube.com/watch?v=NAy67LFX3w0

Power BI free course
https://www.microsoft.com/en-in/power-platform/products/power-bi/learning

https://learn.microsoft.com/en-us/training/modules/get-started-with-power-bi/

6 hours video:
https://www.youtube.com/watch?v=bQ-HTp-tx40
https://www.youtube.com/watch?v=bQ-HTp-tx40


Download dataset from here:
https://github.com/Ayushi0214/Datasets/blob/main/classic_models_dataset.zip


First download a Power BI for desktop application for free.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
1.Data set : Used for importing data into power BI tool (or for connectivity)
A) data can be transformed from any source like cloud , database , folder , files like csv, python, jSON , SQL server, EXCEL etc.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
2.Data transformation : Here we do the data minning. Data will seperated or filtered out or sorting data that can solve business problems by analysis.
a) so here we make use of "Power query editor Tool" : first import data like csv files through a folder. If we select folder it will import all csv files at the same time 
and click on "transform data" then a query editor will open.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
3. Text Tools : for data transformation or data cleaning.
a) classicModelsZip.zip : download this file from repository, link given down the video.
After downloading : goto download asn extract this file into a folder. : once saved - it has excel data sheets for customer,employees,offices etc
that we will be using though out our session.
go to dataset --> select folder--> give folder path (all files will be selected here )--> click on transform data --> brings us to "Power Query Editor"

now you will see different columns and rows showing different file.

a). First column will be shown as : Binary
Let's open the files now:
to convert this right click on binary --> click add as new query. It shows a icon "customers.csv" --> double click on it --> it opens the customers file and shows in the form of rows and columns.
chnage name of the file : Right Hand side: Usnder properties --> Name textbox--> put new name here

Contact First Name , Contact Last name : We want to combine both attributes into 1 column.--> select Column 1 , press shift and select Column 2 ---> Menu bar has Transform tab--> select Merge
a popup window opens ---> 1.Seperator : select Space
			  2. Name : Give a name here (Full Name)

APPLIED STEPS : Right hand side shows : a small box of APPLIED STEPS  ---> that shows all steps we performed. Now to rollback/undo any step we will simply click on X or delete that step.

We merged 2 columns but we noticed there are wide spaces in the columns--> Best approach is to first remove those wide spaces and then merge the columns --> now Delete the Merge columns step.
a). Select the column like we select in EXCEL --> go to Transform tab --> select Format --> select Trim (will remove extra/wide space from left and right of the column). Now again perform the column Merge.

b). Email : abc@testing.com --> we want to extract the username before the delimeter and create a new column--> go to menu -->Add Column-->Extract--> Text before delimeter --> pop window opens--> put a delimter here : @ --> ok

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
Module 4:
a) Remove unwanted data or NULL values from data.

i)How to open sheet or extract a table: on left side window shows all excel sheet (header is Queries 9)--> right click on any query and select add as new query.

Example: Delete column Telephone as we don't need that,
	a) select the column and hit delete on keyboard.
	b) or select the column --> right click and select Remove. [or Remove other columns (to remove all other columns)]
ii) In a file that has rows and columns  and we want to use first row as headers then on the menu bar -->we see an option as --> "Use first row as headers"
 	a) on the first column on right side we see a small icon like a spreadsheet ---> right click on it --> select ---> "Use a first row as headers"
iii) Remove Duplicate Data : select column header ---> right click--> Remove duplicates.
iv) NULL Values : Power BI doesn't recognise the null values witten in capital letters --> It only recognizes null in Italin or small letters.
   To update capital NULL values into small case : Go to menu bar --> transform-->Replace values --> a pop up window opens --> replace type NULL to null and press ok

v) Fill null values : example Empno has null --> go to menu bar--> transform--> select Fill --> down. (means copy the above crow value to the lower row.

that means if we have null values like: 
Existing values     Output Values:
1.1135 			1.1135 
2.null			2.1135  --got copied here
3.1136			3.1136
4.null			4.1136  --got copied here
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
Module 5: Numeric Tools , how we use these tools ---> using DAX

i) the column headers --> has drop down --> that has the data type.
ii) Numeric calculations like : sum of a column is not done in power BI editor(because here it does the calculation for whole table.)--> rather it is done using DAX.
iii) Menu bar --> Transform--> sum methods like : Minimum, maximum, median, average, count values.
iV) Table Ordered details --> has 2 columns (1.Each Price  and  2.Ordered Quantity) --> lets calculate the total price by multiplying both columns --> so to do that create a new column. 
Go to file --> select custom column.
a) New column Name: Sales
b) Custom column formula:Price each * quantity ordered.
c) ok

v) In Power BI : if we want to sort/change the order of the column simply picka and drop it where we want.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
Modeule 6 : Date tools
1) Table Orderes -->Column : Shipped Date --> we want to remove NULL rows, best method is to first convert them into errors and the delete. 
Go to menu bar:  transform-->Replace values --> a pop up window opens --> replace type NULL to 0 and press ok , then go to column drop down --> select data type Date. I will give errors for rows having 0 or invalid date.
Then go to menu bar--> remove rows having values 0.
2) go to menu bar : Add column tab--> then Date --> Month --> Name of Month , it then creates a new column with names of the month.

Module 7: How TO create CONDITIONAL COLUMNS:
Table products -->column Quantity in Stock --> Now go to add column -->Conditional column --> a pop up window opens the--Create new column name: More stock
Column: Quantity in Stock-->Operator : Greater than or equal to-->Value: 1000-->Output: Not required
ELSE : Required.
click ok

add clause to add more conditions -- here conditions can be removed or added based on the requirement.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 

Module 7 : Merge or append tables/queries.
i) Lets Merge  two tables OrderDetails and Products ---> column Productcode(is unique key and available in both tables)--> click on OrderDetails table name and--->go to menu bar -->Home--> Merge Queries --> a pop up window opens -->select table from dropdown menu.
Select join kinds : Inner join (matching data from both tables) --> a Table (in the form of column) gets created into Order details --> that has arrows to expand on the drop down , we can here select a columns or specfic columns to be added only.

Appending data:
ii) go to Menu bar --> close and apply -->all our tables started loading here : now lets save it --> go to files --> save :
File Name: ClassicModels_dashboard
Recent loacation : give the folder path
extension for power BI file is : .pbix

This action is not performed always:  Append queries are only performed when we have similar columns (only when all columns are similar) in our files/queries.
Append data : is performed when we have same data in  different files(.csv) having same data, eg sales data of a company --> for 3-4 years data.
a) go to files --> new---> Getdata --> More -->Folder-->Browse --> Desktop-->sales-months-->ok--it shows you many files with binary format --> click on Transform load
Go to column binary --> right click --> add as new query --> table icon appears --> double click on it--> table opens now--> on right hand side properties --> Rename the table here

Both tables gave same number of columns and same name and types of columns. We want to clean the data but lets first combine or append coluns from both tables.
a) Go to menu bar-->Home--> Append queries. --tables(april,March) , select the table name from dopdown--> ok

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Module 8 : Format Tool
How to change the column format ? 

We updated few columns data type by selecting the column then --> by clicking the drop down --> then selecting the data type.
a) Goto --> files--> clase and apply
b) GetData--> more(to open *.csv file)-->select the text file connect -->browse and choose file--> then click Transform data-->ok--> Power query editor opens.
Select a date column --> inital data type shows as ABC --> now we want to convert into date format --> if we directly select the data type as date from drop down , some errors will occur.
Another way is to -->Go to column header --> right click--> change type --> using locale..---> pop up window opens -->
 a) Data type: Date , Locale: english (US)--> ok

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 
Module 9 : CREATE TABLES:
How to create tables in power BI ?
Go to Home : Enter data (Icon looks like a table )--> pop window opens(create table)--> Name:Student_Grades
column names : click and start typing , tab to move on to next column or use + status.
1. St_id,names,grades  --> to go into next row hit enter or + option is available for rows.-----> after entering all data click---> ok

St_id,names,grades
s01,Albert,A+
s02,Michael,B
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Section 10:  PIVOTING and UNPIVOTING of data in PowerBI


Googled UNPIVOTING:Rotates a table by transforming columns into rows. UNPIVOT is a relational operator that accepts two columns (from a table or subquery), along with a list of columns,
and generates a row for each column specified in the list. In a query, 
it is specified in the FROM clause after the table name or subquery.
Googled PIVOTING: to adapt or improve by adjusting or modifying something (such as a product, service, or strategy) I



a)Unpivoting: Is performed to convert a horizontal table into a vertical table.(Go to Tranform --> Unpivoting columns--> Unpivoting Other columns 
OR 
 2. Select first column --> right click--> Unpivoting Other columns

The table will be converted into Vertical form but still the data is not in a complete readable format.

b) PIVOTING  : Performed to bring that table into complete vertical format. select the first column ( Go to Transfomr--> Pivot columns --> it give a dropdown optiona by attribute or by value--> Value.

eg:

Horizontal Table format:
------------------------------------------
Column1 :        Monday  Tuesday wednesday
NoofPeople:     	10	 20	    30
AveragePerctage:	4	 5	    6 

Vertical Table Format:
---------------------------------------
Days   NoofPeople  AveragePerctage
Monday  	10          4
Tuesday  	20		5
wednesday	30		6

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
/***************************************/
	MODULE 3 - DATA MODELING  
/***************************************/

PowerBI- Model view 

Data modeling is done to build relationships between different tables.These tables could be a part of same database.
What is a Primary Key and a foreign key : 
Primary key is a unique Identifier in a table.
Foreign Key : The data of foriegn key depends on the primary key of another table.

Example:

Lead Manager:  Lead code will have unique values here and Leadcode is the primary key in this table. Value for Leadcode cannot appear more than 1 time inn the primary key.
------------------------
Name LeadCode

Abc	L01
Dec   L02
DFG   L03

Manager:   Leadcode in Managers table is foriegn key which has the multiple values of the leadcode. This table has its own primary ket that is Mcode.  

MName MCode LeadCode
----------------------------
A      M01   L01
B      M02   L01
C      M03   L02
D      M04   L03
E      M05   L03
D      M06   L02

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Section 2.   CARDINALITY AND CROSS FILTER DIRECTION.

POwer BI : Report view

In SQL databases, cardinality means the uniqueness of data present in the columns of a table when working with columnar data sets or with query optimization. 

Cardinality : is a relationship between 2 tables. It could be in below forms. ( one to one, one to many , many to one and many to many)
a) 1:1 (Relationship between 1 primary key and another primary Key) 		 eg: student one student can have 1 unique rollNo.  (student---1----Has----1---ROLLNO)
b) 1:* ( Realtionship between Primary key to Foreign key)
c) *:1 (Relationship between foreign key to Primary key)
d) *:* ( relationship between foreign key to foreign Key) -- not often found because a primary key is must for applying relationships between different tables.


PowerBi : shows arrow while joining 2 tables , its called filter Direction.
Cross filter direction: will determine to which direction the filtering will occur. 

Types of filter direction :
a) Single direction : filtering occurs in only one direction.  >   ( always shows 1 to many direct)
b) Both direction :   filtering occurs in both the directions.  <>  (special case we can set the direction to both sides). 

Example for both direction:  Model view-->right click on the reltionship arrow --> properties window shows the --> cross_filterd_irection--> Single or both
eg employees and cutomers have 1 to many Relation.
We can find any details for customers through the employee table. But when we want to find like : Customers country has how many employees ? then we need a both direction filter.
using the visual graph : we dropped the fields of customer: country and Employee : Empno in the graph chart it gives us the graph ot table format visualisation to understand the data.

You can find the option in home tab or in the Report view section that gives us option to --> drag drop the columns or by selection.

eg : 1: *  the arrow will always point to the many's direction.  1-->*

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Section 3:  DATA ANALYSIS EXPRESSION (DAX)

Power Bi is used for calculation(for data analysis) in Power BI and for performing the Pivot in Excel.
It has different function and operators those are used for calculation in can be used in the formula bar.

Where can DAX be used ?
a) To calculate complex formulas and measures.
b) To create custom aggregations.
c) For dynamic grouping or time intelligence functions.
d) For performing custom calculations.

All these tasks will increase the function of your visualization.



Data Analysis Expressions (DAX) is a formula expression language used in Analysis Services, Power BI, and Power Pivot in Excel. DAX formulas include functions, operators, and values to perform advanced calculations and queries on data in related tables and columns in tabular data models.

What are measures ?
What are columns ?
Difference between measures and columns in Power BI ?
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

/******************************************************/
  MODULE 4 - DATA Analysis Expressions (DAX)  
/******************************************************/

FOR INTERVIEW POINT OF VIEW:  READ DAX FUNCTIONS AND FORMULA VERY THOROUGHLY.


We can use DAX to create the below:

a) To create new aggregate values.
b) To create new columns or calculated columns.
c) To create measures.
d) To create new tables , from an existing table.


Aggregate values: SQL aggregation is the task of collecting a set of values to return a single value. It is done with the help of aggregate functions, such as SUM, COUNT, and AVG. For example, in a database of products, you might want to calculate the average price of the whole inventory.

Aggregate functions are often used with the GROUP BY clause of the SELECT statement. The GROUP BY clause splits the result-set into groups of values and the aggregate function can be used to return a single value for each group.

MIN() - returns the smallest value within the selected column
MAX() - returns the largest value within the selected column
COUNT() - returns the number of rows in a set
SUM() - returns the total sum of a numerical column
AVG() - returns the average value of a numerical column
Aggregate functions ignore null values (except for COUNT()).
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SECTION 1.
Let's create a MEASURE :  
i) creating measure - no space can be added in the measure name. Open your file that you worked on. We are not going to open the query editor. Just open file , select a table name on right corner, like customer. Go to menu bar--> Home --> New Measures.

Goto Home : New measures then on the formula bar we can give the formula like 

Measure name= formula can have a column of another table , it will show a drop down here with different tables and their columns. 
TotalSales= SUM(orderdetails[Sales])  

We have used here an aggregate function.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
SECTION :2
How can we create a calculated column.

Home--> add new column   
Go to products table click anywhere then goto--> Home--> Add new Column.


New columnName= formaula , in which we can use a column of any available table.

Stock_Requirement: if(Products[QuantityInstock]> 500,"NO","YES")   --> hit enter , a new column will be added in products table.

MEASURES : Let's suppose we want to calculate  [Total sales] : Now total can be calculated using a sum() that is an aggregate function.


-------------------------------------------------------
Table OrderDetails -->
-------------------------------------------------------


By Add a new column: Wrong way of calculating total sales.
TotalSales= SUM(orderdetails[Sales])   :if we perform this by adding a new column , it will add a new column in the same with same value for each row, which is not correct.


By Add a Measure: correct way of calculation sum of a column (total sum of sales)
TotalSales= SUM(orderdetails[Sales])   : done by adding new Measures
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SECTION 3 :

CREATION OF MEASURES IN Power BI and its Types:

Once we created the measure - we can change the currency type of the measure.

By Add a Measure: correct way of calculation sum of a column (total sum of sales) , Goto Home --> select table where we want to add new Measures --> give new measure name and its formaula.
TotalSales= SUM(orderdetails[Sales])   : done by adding new Measures 

Once we have created a measure : we can see its value in the report view.
Goto Report View : select /insert Graph : here use KPI value graph - 123 picture, it wont work with string as the datatype of the column field is decimal/numeric so we need 123 graph.

Update currency of Measure:
Goto --> Table View --> select Measure we created ----> on the menu bar it gives measures name , its type, formula, currency --> drop down select $ english US. (this will show $ on the graph)

--------------------------------------------------------------------------------------------------------------------------------
What is KPI ? (Key Performance Indicator)
KPI stands for key performance indicator, a quantifiable measure of performance over time for a specific objective. 
--------------------------------------------------------------------------------------------------------------------------------

TYPES OF DAX :
1. Calculated columns.
2. creating new columns in existing data.
3. Creating new table.

4. Time Intelligence Expressions:
5. Text based function available in DAX like calculating : Upper case , Lowercase values in DAX.
6. Information functions : Helps us in retrieving the information regarding the data.
7. Filter data: sumIF() ,countif() , you can filter data based on a condition.   (Eg: The SUMIF function is a premade function in Excel, which calculates the sum of values in a range based on a true or false condition.)
8. Statistical Methods/Functions : such as variance , standard deviation.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SECTION 4:

Understanding the syntax of DAX in PowerBI.

Name of Column or Measure :  1. Should relate to the field/attribute we want to use .
			     2. We should always keep the measure or the coumn in the table that we are using the column from.

EG: TableName : ORDERDETAILS
TotalSales= SUM(orderdetails[Sales])   : done by adding new Measures , always keep/create the measure in OrderDetails table.

SYNTAX:
Column/Measure Name=function(Tablename[ColumnName]) or if() or statistical()

a)functions like: SUM(),COUNT(),AVERGAE()
b)If condition:  if(Products[Profit]>500 "NO","YES")   -- this is if else statement if the profit > 500 then we need NO further orders else yes we need orders.

------------------------------------------------------------------------------------------------------------------------------------------

SECTION 5 :  TYPES OF FUNCTIONS in DAX  (All these functions are used for creating columns and measures)

FOR INTERVIEW POINT OF VIEW:  READ DAX FUNCTIONS AND FORMULA VERY THOROUGHLY.


i) Date & Time  : DATE ,NOW, YEAR                       [for working with date and time values]
ii) Text Function : CONCATENATE , LOWER , UPPER		[Information or working with text values]
iii) Information Functions : ISTEXT and ISTEXT          [Used for obtaining information about data and data types.]
iv) FILTER FUNCTION : FILTER and CALCULATETABLE         [For filtering data based on conditions.]
v) Aggregate Function: SUM,COUNT,AVERAGE		[functions for aggregating data]
VI) Time Intelligence functions : SAMEPERIODLASTYEAR  and TOTALYTD   [functions for working with time based data]
VII) Logical functions : IF , SWITCH			[For working with Logical Values]
VIII) Lookup functions : LOOKUPVALUE and RELATED       [for looking up value in related able]
IX) MATH and Trigonometry functions: ABS and SIN       [for performing mathematical calculations ]
x) Statistical functions :STDEV and PERCENTILE          [used for working with statistical data]
XI) Financial Functions : NPV and IRR.     [for performing financial calculations]
XII) Other functions : NOW and GUID        [functions those don't fit into above categories]

--------------------------------------------------------------------------------------------------------------------------------

SECTION 6: TIME & DATE function + (CHEATSHEET)

Time and Date functions:



a) Order_Year = (Orders[orderDate].[Year] )

.YEAR
.DAY
.MONTH
.QUARTER
.QUATERNO
.DATE

Year is used to find out the year from a date, so we added a new column for only YEAR values.
divide into four equal or corresponding parts.
"peel and quarter the bananas"


b) Added a new column to calculate the difference of days between 2 dates:


DATEDIFF(Table1(Date_column1),Table1(Date_column2),INTERVAL)

INTERVAL here is DAY,YEAR,MONTH

Shipping_Days = (DATEDIFF(Orders[shippedDate],Orders[orderDate],DAY)  this function calculates the difference between 2 dates in days but giving us negative values like -1,-2,-3,-4 etc.


ABS() is absolute(means total and fixed and  non negative) , that converts the negative values into whole numbers eg : -1,-2,-3  to 1,2,3

Shipping_Days = ABS(DATEDIFF(Orders[shippedDate],Orders[orderDate],DAY))

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

SECTION : 07
Text Function : CONCATENATE , LOWER , UPPER  [Information or working with text values]


LEFT: Returns the specified number of characters from the start of a text string.
RIGHT: Returns the specified number of characters from the end of a text string.
LEN: Returns the number of characters in a string.
LOWER : converts all letters in a string to lower case.
MID: Returns string of characters from middle of a string, given a start position and length.
REPLACE: replaces part of a string with different string.
SUBSTITUTE: Replaces existing text with new text in a string.
REPT: Repeats text a given number of times. Use REPT to fill a cell with a number of instances of a text string.

COMBINEVALUES: Combines the given set of operands using a specified delimiter.
CONCATENATE: Join two text strings into one text string.
CONCATENATEX: Evaluate expression for each row on the table, then return the concatenation of those values in a single string result , separated by specified delimiter.
 
EXACT: Checks whether two strings are exactly the same and returns True or False. EXACT - is case sensitive.
FIND: Returns starting position of one text string within another text string. Find is case-sensitive and accent sensitive.
FIXED: Rounds a number to the specified number of decimals and returns the result as text with optional commas.
FORMAT: Converts a value to text in the specified number format.

TOJSON: Converts the records of a table into JSON text.
TRIM: Removes all spaces from a text string except for the single space between words.0
UNICHAR: Returns Unicode character that is referenced by the given numeric value.
UNICODE: Returns the number (code point) corresponding to the first character of the text.
UPPER: Converts a text string to all uppercase letters.
VALUE: Converts a text string that represents a number to a number.
TOCSV : Converts the records of a table into a csv (Comma-separated values) text.

..............................................................................................................................................................................
SECTION : 8

Text functions : functions we applied

City_Country1 = CONCATENATEX(customers,Customers[city], "-", Customers[country])  ---there will be a pop up note appearing on top that gives the syntax of the formula.

Concat_CITY_Country = CONCATENATE(Customers[city],Customers[country]) 

Upper_Fullname = UPPER(Customers[FullName])

Lenght_CustomerName = Len(Customers[FullName])


/*********************************************************
MODULE 4 : Logical functions that are used in PowerBI
********************************************************/

a) IF : Returns a value based on a specified condition.
SYNTAX:
IF(condition,[value_if_true],[value_if_false])  

b) AND : Returns TRUE if all its arguments are TRUE , otherwise returns False.
SYNTAX:
AND (condition1,[condition2],.....)

c) OR : Return TRUE if any of the arguments ate TRUE, otherwise returns FALSE.
SYNTAX:
OR (condition1,[condition2],.....)

d) NOT : Reverses the logical value of its argument.  
Syntax:
NOT(condition) 

e) SWITCH : Returns a value based on the first TRUE expression. 
SYNTAX:
SWITCH(expression,Value1,result1, [default or value2,result2],...)

f)IFERROR: Returns the first argument if it is not an error value, otherwise returns the second argument.
SYNTAX:
IFERROR(Value, Value_if_error)

g) IFNA : Returns the first argument if it is not the #N/A error value, otherwise it returns the second argument.
SYNTAX:
IFNA(value, value_if_NA)   ---> NA is not available


/................................................................................................................................................................./

EXAMPLE : we tried as below : we want to check two conditions and both should be True then output will be "YES" otherwise "NO". Applied on table customers.

Voucher = if(and(Customers[country]="USA",Customers[creditLimit]>=100000),"YES","NO")

/................................................................................................................................................................../

                                              ***********USE OF CHATGPT to CREATE MEASURES (go to : https://chatgpt.com/) **********


SECTION 2:  Using ChatGPT to Measures , it helps us by providing us a sample code template, that we can moditfy a little bit and create a new measure using it. It is basically used when we need to create a bit complex measure , such as when we are checking more than 1 condition in the measure like Name of the product and sum of quantity ordered.

go to : https://chatgpt.com/


Write in chat box:
I have productname in products table and quantityordered in orderdetails table , I want to create a measure in power bi using dax which will allow me to calculate the name of the product which has been ordered the most. ----> hit enter ---> then a solution code will appear as below:

Create measure :1
Total Quantity Ordered = SUM('OrderDetails'[QuantityOrdered])

Create a Measure to Identify the Product with the Maximum Quantity Ordered : 1

Product with Most Orders = 
VAR MaxQuantity = MAXX(
    ALL('Products'),
    [Total Quantity Ordered]
)
RETURN
CALCULATE(
    MAX('Products'[ProductName]),
    FILTER(
        ALL('Products'),
        [Total Quantity Ordered] = MaxQuantity
    )
)
.......................................................................................................................................................................

IF we find the code complex the we can try by giving an easier statement:

Type:  Suggest another easier way to calculate this measure.  ---hit enter


1. Create a Measure for Total Quantity Ordered: First, you still need a measure that calculates the total quantity ordered for each product.

Total Quantity Ordered = SUM('OrderDetails'[QuantityOrdered])

2. Create a Measure to Identify the Product with the Maximum Quantity Ordered: You can use the TOPN function to directly get the product with the highest total quantity ordered.

Top Product = 
VAR TopProduct = 
    TOPN(
        1,
        SUMMARIZE(
            'Products',
            'Products'[ProductName],
            "TotalOrdered", [Total Quantity Ordered]
        ),
        [TotalOrdered],
        DESC
    )
RETURN
    FIRSTNONBLANK(
        TopProduct[ProductName],
        1
    )


SUMMARIZE here means group by clause , that is used with aggregate functions , that we apply on a column. like count() ,  SUM() , average() , to calculate a result from set of values.
........................................................................................................................................................................................

We update the formula a bit as below:  when we hit enter it gives us the error because we want to display the name of the product that has been ordered the most, but here we are
calculating the sum of the quantity ordered and also fetching the name of the product that has been ordered the most. so we are doing 2 things at the same time and getting the error.
We cannot so 2 things in same measure. Measure will need the product name and doesn't care about the value of total quantity ordered because we only want the product name on the report view chart. 


Error: The expression refers to multiple columns. Multiple columns cannot be converted to a scalar value.

go back to chatgpt and paste this error.



GOTO Order details-->New Measure --> paste the below code and hit enter and we get the error listed above.

TOP1 means displaying the top most value int he descending order.

MostOrderedProduct = 
    TOPN(
        1,
        SUMMARIZE(
            'Products',
            'Products'[ProductName],
            "TotalOrdered", Sum(OrderDetails[quantityOrdered])),
        
        [TotalOrdered],
        DESC
    )

/*****************************
FINALL Updated version:  	again go back to the chatGPT and paste the  error and say above formaula is generating this error, please fix the code.
*****************************/

We here got the "SELECTCOLUMNS()" function that will only select the value for product name.


MostOrderedProduct = SELECTCOLUMNS(
    TOPN(
        1,
        SUMMARIZE(
            'Products',
            'Products'[ProductName],
            "TotalOrdered", Sum(OrderDetails[quantityOrdered])),
        
        [TotalOrdered],
        DESC

    ), "MostOrderedProduct", 'Products'[ProductName])     ----> we here gave the name of the column we want the measure to display.


"MostOrderedProduct" is the name of the Measure.


/***********************************************************************************************************************
To check if we got the correct results , we are going to create  table with Product name and SUM of QuantityOrdered.

**************************************************************************************************************************/
Table = SUMMARIZE('Products',Products[productName],"Total_Quantity",SUM(OrderDetails[quantityOrdered]))


...........................................................................................................................................................................

Module 4: OPERATORS used in DAX (Data Analysis Expression)

a) Arithmetic Operators: Used to perform arithmetic operations such as
addition (+) ,subtraction(-),Multiplication(*), and division(/)

b)Comparison Operators: used to compare values and return logical result (True or false).
These include 
equal to(=) ,
less than (<) ,
greater than or equal to(>=) ,
and less than or equal to (<=)

c) Logical Operators: Used to perform logical operations such as AND , OR and NOT.

d) Concatenation Operators : Used to combine text values, such as & and CONCATENATE.
e) Reference Operators: Used to reference cells or ranges , such as [] and [].
f) Parenthesis: Used to control the order of operations in a formula , such as () and [].
g) Miscellaneous Operators : Used for various purposes , such as colon (:) operator used in date time functions
and the semicolon (;) Operator used in switch function. 

.................................................................................................................


SECTION 2 : Different visuals using POWER BI
a) we can add more visuals into our report view. This can be done by loging into the microsoft account. Then you can select any visuals you want to add.
b) Similarly we can delete or remove the visuals/pictures we don't want to keep.

c) go to view --> Visualizations --> format your report page.
 i) This will show you many options such as:
 	a)Page Information
	b)Canvas Settings
	c)canvas background 
	d)Wallpaper
	e)Filter Pane
	d)Filter Cards

canvas background  : we can choose color option here or we can use a picture , but it won't show as it is because we have used the Transparenct option ads 100% , lets reduce it to see
the background color.

........................................................................................................................................................................

MODULE 5:  VISUALIZATION Charts in Power Bi


Representation of bar charts and Pie charts:

To represent Product names and its sales: We use bar charts.
To represent percentage (ProductLine and Sum of Sales) : we use PIE charts. ---> go to format ---> and change value to be in thousands etc.

Format-->Detail Label -->  
a) Position : Outside
b)Label Content: Caategory percent of total.

To add more visuals we can first create account on lowepro and then se it email ID to access more visuals to power Bi.

...................................................................................................................................................................................

SECTION 1: Filtering options in PowerBi


a) Select already created by bar chart. Bar char shows scroll bar with which we can see all the products. We want to filter top 10 products showing on the bar chart.

On right side we see filtering option.

Click on product Name dropdown --> a) filtertype top N 
				   b) Show Items --> Top ,10  

Now we want to do this by value : Sum of Sales. (so we will select OrderDetails[sales] and drop in by value section.

then------> click on apply Filter --> it will show ---> 10 products with sum of sales value in the bar chart.

..............................................................................................................................................................................

FILTER on this PAGE:  we can also apply a filter on the page itself , lets say want to put the filter by sum of sales value:

click anywhere on the report view --> Filter on this page by : drag and drop SALES
Filter type: Advance filter
Show item when the value is : greater than or equal to : 100,000
AND --> is less than or equal to : 50,000  --> apply filter

Now nothing will happens instead all existing chart's values' disappear due to the condition we applied and nothing false into the condition.


Similarly in the pie chart : we can add multiple columns or remove columns as per our preferences. And we will notice that the total Measure profit will show different value according to it. Also the product name changes , clicking on different sections of pie chart.

FILTER on all pages: If we are creating a multiple pages for dashboard. Then we can use this option. Example: we want to apply filter on country : USA for all pages.
It will only display data for USA country for all pages we want to create for dashboard.

.................................................................................................................................................................................

SECTION 2: Exploring MATRIX visuals in Power Bi


Visualization --> has table and matrix charts. Click on previous bar chart and select matrix option. It will show the matrix chart representing Product name and its total sales.

Create a new matrix :
1. ) Add Product line on X column, then we can choose multiple values that it can display like sum of quantity ordered ,sum of Sales and total Profit.

When we click on any attribute/column of matrix --> the data will be sorted into ascending or descending order.
We can also add another value (sub category) under product line that is the product Name.

Eg : ProductLine		 Sum of Quantity Ordered    sum of SALES    PROFIT 
-------------------------------|----------------------------------------------------------
	a)Classic Cars	       |
		i) Honda       |
		ii) Maruti     |
		iii) BMW       |
		iv) Mercedez   |
	b) Motorcycles	       |
	c) Ships	       |


when we click on any columnn headers it can be converted into ascending or descending order.


To create this hierarchy , we can go to data section to add another field : ProductName under the Catergory of ProductLine

		a)Classic Cars	  	--> ProductLine
			i) Honda   	 --> Product Name    
			ii) Maruti  	--> Product Name    
			iii) BMW     	--> Product Name   
			iv) Mercedez  	-->Product Name  


we can go to data section to add another field : Product Name under the Catergory of ProductLine 

Click ProductName --->again right click on it---> select Create Hierarchy.

.................................................................................................................................................................................

SECTION 3: FILTERING data with SLICERS IN POWERBI 

1.) Goto Visuals -->slicer chart with filter sign. We can go in the formatting and update its formatting. SLICER --->SETTINGS-->Between will give a bar to increase/decrease the years.
And various other options can be used here like dropdown.


SLICER Filter Years: Originally it will show like this. Order[Order_Year]
no-blank
2003
2004
2005

Next we used SLICER --->SETTINGS-->TILES,  it will show the data in the form of tiles.

Go to Query Editor ---> Orders --> select Order_YEAR , this is a date field , it had NULL values which we removed, we can delete the remove value step and again replace the value NULL with null. PowerBI reads capital NULL as a string and not as null value. Next we can use option FIll--> down --> to copy the above value to below in the order_year column.

Now one more time go back to the ---> report view -- Slicer filter --> you can see only the years and no blank option.


SLICER Filter Years after the fix:
2003
2004
2005


2.) Add another slicer filter --> to see the Month_Names --> because the order is not sorted we see names in neither asc nor desc order.

Lets go to edit query --> Orders --> add a new column --> Month_Number --> formula: Month_Number =Orders[MonthName].MonthNo
Now go to Table view in Power bi ---> Select column MonthName--> Column tools --> sortbyColumn --A dropdown will show and select --> order by Month_Number.
Make sure Month_Number is in sorted order : ascending or descending. 

Go to Report view : the slicer filter by Month name is now available in sorted order.

.................................................................................................................................................................................

SECTION 4 : NUMERIC and TEXT CARDS

Text card and number card both are same thing: only thing is the value : the value could be text or numeric.


Note: All measures are represented on dashboard using cards.

1.) Goto Reports View--> lets add a new card 123 --> Orderdetails[Sum of QuantityOrdered] --> a report will generate on the dashboard.
a) Its header shows a sum of Quantity Ordered --> we want to remove this header --> go to formatting --Label --> turn off. 
b) Create a Header on top of numeric Card --> Go to --> general--> title --> turn ON -->Text --> Total Orders-->Horizontal align 

c) Row count card --> offices[OfficeCode]--> it will show different office codes but we want its distinct value.
 i)Go to Visualisation-->field --> right click --> select count(distinct) --> it shows 7 office codes.
 ii)Lets add Employee[EmployeeNumber]--> right click --> select count distinct : it shows 23 employees.

d)Row count card --> Customers[CustomerNumbers]--> it will show different customer numbers but we want its distinct value.
 i)Go to Visualisation-->field --> right click --> select count(distinct) 
 ii)Lets add Customers[CustomerNumbers]--> right click --> select count distinct : it shows 122 customers.

.................................................................................................................................................................................

SECTION 5 : KPI Visuals  

for using KPI's it is important to create measures , based on particular month or year.

It has 3 options: 
a)Value
b)Trend Axis
c)Target

KPI cards are used to compare data between  months or years, for example to see if our sales increased than last year or decreased than last year etc.
so lets first create measures , because we cannot use column values here.

A) Go to table view to ---Create measures.
Calculate total sales based on year 2003 and 2004. Measure created in table Orders. so we created 2 separate measures in table orders.
1.Sales_2003 = calculate(sum(OrderDetails[sales]) ,orders[Order_year]=2003)
2.Sales_2004 = calculate(sum(OrderDetails[sales]) ,orders[Order_year]=2004)

B) .Convert the currency to $ --> Now go to table view --> select the measure --> menu bar --> $ drop down --> $ English (united States)

C) Now go to report view :
Create a copy --> ctrl+C and ctrl_V : Now you can change the value to Sales 2004 , by unchecking previous value(sales_2003) and checking new value sales_2004.

d) Now lets take a KPI card : drop values as below. Also convert the output value to millions.

a)Value : select sales_2004 
b)Trend Axis  : Month name
c)Target  :select sales_2003 

format-->Visuals-->Call outs--> display units--> Millions.

.................................................................................................................................................................................

Module 5: VISUALISATING Data with MAPS in Power Bi   (we will use Globe Map and Filled Map)


SECTION 1:

(A) Let's work with Globe MAP: 
a) set location --> go to --> customers--> city 
b) Go to Format section : Controls --> Zoom button--> ON


The map has sections :
i)   Location : City   , we can also use Country instead of city.
ii)  Legend
iii) Latitute
iV)  Longitude
V) Bubble : CustomerNumbers

Bubble section: add CustomerNumbers (Also known as count of customer Numbers) , it will show small bubbles on the map for the customers in different countries.
Hover on the bubbles to see the count of customers in different countries.

Go to formatting --> Style --> Change the style from the dropdown options --> such as GreyScale, Road, dark, light etc
Colors of the bubbles can be changed as well --> we have blue color by default.


(B) Filled Map:  in the
 Location: Country   --this is a filled map so it will automatically show cities under those countries.
 ToolTip : CustomerNumber   --- so when we hover on different counties it will show us it number of customer.

.................................................................................................................................................................................

SECTION 2: CREATING TREE MAP in PowerBi

Pie chart and TreeMap comes under same section:

Pie chart : is used for percentage.
Treemap is used : when we want to represent different values ,it will kind of create tiles in the chart for different products. All tiles will not be of same size. size of the tile depends on the quantity ordered.

Category: ProductLine (Table Productline[ProductLine])
Value : OrderDetails [QuantityOrdered]
Formation : Data Label --> ON  , this will show quantity in thousand at the bottom of the box or tile. 
Color: we can also change the colors for the Treemap in format section.

We can Hover over different boxes and it will show the productLine with their quantity ordered.

.................................................................................................................................................................................

SECTION 3: CREATING TOOLTIPS


A) Lets create a chart on Page1 --> 
x-axis :  Orders[Ordered_Year]
Y-axis : Order_Details [Sum_of_QuantityOrdered]  , set the tooltip on , set the label ON (displays the quantity in Thousanda/Millions).
Now we see that toll tip , shows the ordered year and quantity ordered in a text format. What we want is the ToolTip to display in the form of a chart not text.


B) Go to-->Page2 by clicking + at bottom of page --> formatting --> Page information --> set ToolTip ---> ON
> formatting --> Page information --> Set Name : ToolTip  or TP1, see name coming at bottom

i) You can see the page size has decreased.
ii) Lets create a chart here  , Y axis: ProductLine[ProductLine], X axis : OrderDetails[Sales]  and save it.
ii) Now go back to Page 1 where we created a chart, click on the chart --> go to formatting--> General --> ToolTip-->Page dropdown : TP1
iv) when we hover on the chart created by previously on page1 , it now shows a chart as a tooltip.
V) Go to fomarting --Set data Labels --> ON  (it will show us some of sales for each productLine (category).


C) Similary we created a tooltip :TP2 
a) Disable previous tooltip on previous chart if using same page TP1.
i) The Tp2 is created for the pie chart, we wnat to display ProductNames of top 5 years by their sales.

Click on the chart : go to --> Filters --->on Visual popup window opened on the right side.
			i) FilterType: Top N
			ii) Show Item : Top  , Size : 5 
			ii) by value : Sales ---> apply filter

			

.................................................................................................................................................................................


SECTION : 4   MODIFYING COLORS IN CHARTS AND VISUALS. 

Goto View : Choose any themes ---> those are available color charts.

i) when we select a theme it will change the colors of all the charts availble on the report view section. Deafulting it to the theme we chose.
ii) Select a already created KPI chart ---> on report view --> go to Trend axis --> set color 
Good: Green
Neutral: Blue
Bad: Red

ii) Select any text chart : Go to --- >Formatting--> Callout Value ---> Font Size : 20
iii) Set Label Off ---> and go to General --> set Title : Name of the Header and  ---> set the alignment to Middle/Centered.
iV) Under title --> We have divider : ON --> choose Color : black
V) Header shows options for background color --> and --> font color.
VI) Goto formatting --> general--> titile-->effects-->visualBorder--ON , Also color: Black can be set
VII) Home : has FormatPainter : that can be used to copy / paste the format of one chart to another chart. 


B) Lets create a Mew Measure (Profit_Margin_% ) on Table: OrderDetails ---> display on report view.
Profit_Margin_% = Sum(OrderDetails[Profit])/Sum(OrderDetails[Sales])*100


C) Canvas background color :   
i) by choosing backgrounb color  OR by using a picture.
ii) Set the Transparency to 0 , this way the color at the background will be visible.


D) Slicer Update : click on a slicer -->formatting--> Visuals-->Slicer Settings --> choose dropdown
i) Slicer Value : to change the color of the slicer Tiles and the font.
ii) Slicer Background  : General ---> Fomartting --> background --Color
iii) Disable interactions of slicer with other charts on dashboard: Select slicer ---> go to menu bar--> Format--> Edit Interactions --> now we can see small icons 
on different charts that we can click to disable. Now whenever we click on any button on the slicer it's affect will not be shown on another chart that we disabled.


E) Change color of a Chart: 
i)Formatting --> callout Values --> Font color 
ii) Formatting -->General-->Effect-->Backgroud --> Color


F) Pie Chart :
Set Legend ON --> to display on right corner the product lines/ product categories.
Rest we can use the format painter.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
SECTION : 5  ,  Bookmarks and Buttons in Power Bi

(A) Button to Navigate :  Create a new page --> menu bar --> Insert--> button --> formatting --> Actions : 
i) Type: Page Navigation
ii) Destination : Page Name ( Page 1 , Dashboard , TP1  ... etc)

CTRL+Click on the button --> it will take you to the dashboard page.


(B) BookMark:  Goto page 2 , Create few new charts :

Bar Charts:
1. ProductLine and Sales.
2. ProductName and Sales.
3. ProductLine and QuantityOrdered.
4. ProductName and QuantityOrdred.

 Create a Line Chart 
 5. Order_Date and Sale : It has highrarchy arrows on to to ---> see data by qauarters, months, days etc. ( Drill up and drill down arrows can be used as well)

Go to format painter --> copy the format colors from dashboard to new Page.

i) Stay on Page2 : go to menu bar--> View --BookMark -->add  --> we can also rename here.
ii) Go to Dashboard Page --> let's set bookmark on Pie chart.
iii) Go to Menu bar--> Insert --> Buttons--> information --> a small icon appears  --> drag and drop the icon on the pie chart.
or
iii) Go to Menu bar--> Insert --> Buttons--> Bookmark --> a small icon appears  --> drag and drop the icon on any chart.
iV) Go to : Foarmatting --> Actions 
			    Type : BookMark
			    Bookmark : select the bookmark you created.

Press Ctrl+click on the information icon it takes yo to the page 2 dashboard we created.


V) Similarly we can insert an image into Page 2 and use it to navigate to dasdhboard: Go to Action --> set its properties.
or we can go to new Page and paste the picture there and use it as a bookmark also, based on your requirement.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
MODULE : 5 

AI Visuals in PowerBI   :   We have 4 charts available for AI.

It is an interactive visual used to break down (decompose) data into individual categories and determine the average, sum, high, and low values using different AI functions.
It's also an artificial intelligence (AI) visualization. You can ask it to find the next category, or dimension, to drill down into based on certain criteria.
This is all done to analyse data and root cause of an issue.


Decomposition Tree is useful to see the breakdown of the ordered quantity by the productLine, by coustomerName and by productName.


(A) Decomposition Tree :  set Analyse:  Order_Details[QuantityOrdered] and   Explain by: ProductLine[ProductLine]
In the chart we can see quantity ordered and for the productLine we see a + sign , when we click on it - it gives us 2 values
i) High Value
ii) Low Value.
We can see the highest and lowest value for each product Line.

b) Similarly we can add more fields to explain by section like : Customers[customersName] and again we select by high value.
C) Product[ProductName]  : we added productName as well by high value.


(B) Key Influencer:    It thoroughly analyzes data and ranks the factors that matter which are commonly known as key influencers.
	for example : Product description provides the details, features and advantages of the products that influenced the sales , which lead to increase in product sales.

	Analyse by : OrderDetails[Sales]
	Explain by : Products[ProductDescription]


(C) Q&A : go to dashboard --> add Q&A chart : this will have some questions in it like : what is total profit ---> click on it---> it gives us the total profit value.
     Basically it has questions and answers , we can also put/add more questions to it manually. 
   

(D) Narrative : gives the description of the chart we have created. you can go to dashboard --> click on any chart and create a narrative on it --> it provides you the description.

(E) Line Chart : Always choose date on the X axis.
		X axis : Orders[Order_Date]
		Y axis : Order_Details[Sales]

i) Now go to : X-axis --> and click on  the ordered_date it gives some option: we want to change the hierarchy by date only --> choose option ordered date --> it gives us a different view in chart. Go to Further Analysis --> Find Anomalies --> set ON , so here we see some bubbles on top of the lines in the chart.
ii) Hover over the bubbles it gives us the information like 
						Sum of sales : $109,500
						Expected value : $93,500
						Expected min Value : $86,500
						Expected max Value : $109,500

This anomaly is also an AI feature , that tells us on the basis of days , what value was expected and whether there is an increase or decrease in the sales.

Anomaly is defined as “ an unexpected change within the data patterns, or an event that does not conform to the expected data pattern”.
Anomaly detection helps you enhance your line charts by automatically detecting anomalies in your time series data.
Anomaly detection identifies suspicious activity that falls outside of your established normal patterns of behavior. A solution protects your system in real-time from instances that could result in significant financial losses, data breaches, and other harmful events.


/**************************Right side has 3 sections in POWER BI SCREEN************************************************
(A)Filters : that gives X axis and y axis of the chart we are working on.

(B)Visualization : we have 3 tabs
Visual (Two rectangle box)
format (paint picture)
Further Analysis (Magnifying glass)

(C)Data: this section has all tables we imported through csv files.
******************************************************************************************************************/

Module 5:

Section 2 : Designing for phone Vs desktop report viewer.

go to Dashboard ----> Menu bar--> View --> Mobile layout.

i) A page will appear it will be scrollable , all charts will appear on the right side -- we can drag and drop the charts on the mobile layout page.
ii) The page will show the gridlines , if you want to disable the gridlines --> goto menubar --> view--> uncheck gridlines option.

So here a layout can be created that can be seen on the mobile as well.


******************************************************************************************************************************************************


