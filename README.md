Download Link: https://assignmentchef.com/product/solved-csci-3287-design-and-analysis-of-data-systems-assignment-5-data-warehouse-analysis
<br>
<h1>Overview</h1>




This Project is worth 100 points (out of 1000) toward your final grade. It is due on Sunday November 24th, at 11:59 p.m.




Your assignment submission should be a document saved and submitted as a PDF file via the link found in the assignment section of “Week Twelve” in Moodle which is the same place where you found this file.




This assignment will give you hands-on practice in working with a realistic data warehouse.




<h1>Objectives</h1>

<ul>

 <li>Create a connection to the Adventureworks Data Warehouse (“aw”) on a shared server</li>

 <li>Examine the Adventureworks Data Warehouse to become familiar with the structure of a realistic star schema data warehouse</li>

 <li>Using a SQL query editor (such as MySQL Workbench)

  <ol>

   <li>Study the database and answer questions about its structure</li>

   <li>Create and run queries against the warehouse to answer questions about the content of the warehouse</li>

   <li>Create and run queries against the warehouse to analyze Adventureworks’ business.</li>

  </ol></li>

</ul>

Submission Requirements:

<strong> </strong>

<ol>

 <li>Compose answers to the questions assigned below in a document. Answers must be clearly identified and numbered according to the questions below.</li>

 <li>Where the question requires SQL, submit both your SQL code and your answer set.</li>

 <li>Where the question requires a written answer, please submit proper sentences explaining your answer to the question.</li>

 <li>Save the document as a PDF and submit your PDF using the Homework # 5 link in the Moodle page for assignment section of “Week Twelve” in Moodle which is the same place where you found this file.</li>

</ol>




NOTES:




You may work with a partner on completing this assignment.  However, this is an <strong>individual</strong> assignment; each one must submit your own final deliverable for this assignment.  If you did work with a partner, be sure to specify your partner’s name on the document you submit.




Assignment Problems:

<table width="623">

 <tbody>

  <tr>

   <td width="96"></td>

   <td width="527"></td>

  </tr>

  <tr>

   <td width="96">NOTE: </td>

   <td width="527">This     is         a          Linux  server and      Linux  commands     are            typically          case     sensitive.                    If          you      attempt            a          query  and      it          looks   right    but      doesn’t           work,            be        sure    that     the       case     used    in         naming            database         objects            in         your    SQL     exactly            matches          object  names on        the       server.</td>

  </tr>

  <tr>

   <td width="96">NOTE:</td>

   <td width="527">Be        sure    to         read    “Hints  regarding       the       data”   on        page            4          of         this      document       prior   to         attempting      to            answer           these   questions.</td>

  </tr>

 </tbody>

</table>




<ol>

 <li>How many rows are there in each of the dimension tables in this star schema? List the dimension table name and its row count.</li>

</ol>




<ol start="2">

 <li>Use the information_schema to find out how many rows there are in the internet_sales_fact</li>

</ol>




Hints:

<ul>

 <li>use information_schema;</li>

 <li>There is a table within information_schema called</li>

 <li>The TABLES table contains columns TABLE_NAME and</li>

 <li>The row count for each table is in TABLES.</li>

</ul>

<ol start="3">

 <li>What standard table naming convention did the AdventureWorksDW database designers use to differentiate dimension tables from fact tables in this star schema data warehouse?</li>

</ol>




<ol start="4">

 <li>What do you think is the purpose of the recursive relationship on DimEmployee?</li>

</ol>




<ol start="5">

 <li>What are the three model types (EnglishProductSubCategoryName) of bikes sold by AdventureWorks?</li>

</ol>




<ol start="6">

 <li>List and compare the total sales dollar amounts of the three model types of bikes sold by AdventureWorks for the years 2001 – 2004. In what year were the sales of RoadBikes the highest?</li>

</ol>




<ol start="7">

 <li>List and compare the total sales quantities of bikes sold (all model types) by customer gender by year and month. In which year and month were bike sales to females the highest?</li>

</ol>




HINT:  you can format the output of a numeric column like this:  format(sum(UnitPrice),2)




<ol start="8">

 <li>For the year 2003, which model of bike (ModelName) yielded the highest margin for AdventureWorks?</li>

</ol>







Appendix A – Background on the Company:




The <strong>AdventureWorks </strong>data warehouse is based on a fictitious bicycle manufacturing company named Adventure Works Cycles.  Microsoft created this company and its databases (an OLTP database and a Star Schema Data warehouse) to assist people in learning about database technologies.




Adventure Works produces and distributes metal and composite bicycles to North American, European, and Asian commercial and consumer markets. The base of operations is located in Bothell, Washington with about 500 employees, and several regional sales teams are located throughout their market base.




Adventure Works sells products wholesale to specialty shops and to individuals through the

Internet. For the data warehouse exercises, you will work with the <strong>AdventureWorksDW</strong> Internet sales tables, which contain realistic patterns that work well for data warehousing exercises.




The Internet Sales star schema contains a fact table with data regarding customer purchases of bicycles via the web.




The Internet Sales star schema contains information on several thousand customers. These customers live in several countries, which are combined into three regions:

<ul>

 <li>North America (83%)</li>

 <li>Europe (12%)</li>

 <li>Australia (7%)</li>

</ul>




The database contains sales data covering several fiscal years.

The products in the database are broken down by subcategory, model, and product.




AdventureWorks does business in multiple countries, so some attributes in the data warehouse contain descriptions in multiple languages.

In 2000, Adventure Works Cycles bought a small manufacturing plant, Importadores Neptuno, located in Mexico. Importadores Neptuno manufactures several critical subcomponents for the Adventure Works Cycles product line. These subcomponents are shipped to the Bothell location for final product assembly. In 2001, Importadores Neptuno, became the sole manufacturer and distributor of the touring bicycle product group.

Coming off a successful fiscal year, Adventure Works Cycles is looking to broaden its market share by targeting their sales to their best customers, extending their product availability through an external Web site, and reducing their cost of sales through lower production costs.




As a bicycle manufacturing company, Adventure Works Cycles has the following four product lines:

<ul>

 <li>Bicycles that are manufactured at the Adventure Works Cycles company.</li>

 <li>Bicycle components that are replacement parts, such as wheels, pedals, or brake assemblies.</li>

 <li>Bicycle apparel that is purchased from vendors for resale to Adventure Works Cycles customers.</li>

 <li>Bicycle accessories that are purchased from vendors for resale to Adventure Works Cycles customers.</li>

</ul>

At Adventure Works Cycles, the purchasing department buys raw materials and parts used in the manufacture of Adventure Works Cycles bicycles. Adventure Works Cycles also purchases products for resale, such as bicycle apparel and bicycle add-ons like water bottles and pumps.




The AdventureWorks Data Warehouse is updated by an ETL process that periodically pulls data from the OLTP database and loads it into the data warehouse.




Hints regarding the data:




Granularity:  A row in the FactInternetSales table represents the sale of one item by

AdventureWorks.  The item sold might be a bike, an article of clothing, a biking accessory (like a helmet), or a repair/replacement part for a bike. For this exercise, we will only look at bike sales.




For analysis of sales in FactInternetSales, use the column UnitPrice to reflect the dollar amount of sales. Use the column OrderQuantity to reflect the number of items sold.  Use the OrderDateKey to determine the date of the sale.




The column ProductStandardCost holds the dollar amount that it cost AdventureWorks to build or obtain a bike.  UnitPrice minus ProductStandardCost represents how much profit or margin AdventureWorks made on the sale.




DimProductSubcategory.EnglishProductSubcategoryName contains a description that identifies which type of item was sold.  This columns holds a grouping of model types.




DimProduct.ModelName and DimProduct.EnglishProductName further identify more detailed product/model information regarding the item sold.  DimProduct.ModelName holds the specific model of bike sold.






















<h1>Appendix B – Creating your connection to the aw data warehouse</h1>




Steps to Connect the aw MySQL instance to your query editor.




To complete this assignment, you must connect your MySQL Workbench (or query editor of your choice) to an instance of MySQL running on a VM within the CU Boulder Computer Science department.  The server name is <strong>elra-04.</strong>  You will  connect to the server using the SSH protocol. Then while connected to that server, you will establish a connection to the instance of MySQL running on that server.




<u>Prerequisites:</u>

SSH Hostname:           <strong>elra-04.cs.colorado.edu</strong>

SSH Username:           your CU Identikey username (ex. <strong>niri0478</strong>)

SSH Password:           your CU Identikey password

MySQL Username:  your CU Identikey username (ex. <strong>niri0478</strong>)

MySQL Password:      “password”




Step 1:







This is the first screen you will see when you open MySQL Workbench. Navigate to the upper left corner and click on  “<strong>+</strong>” icon to create a new connection.













Step 2:







The setup new connection dialog window will pop up.  Navigate to the dropdown menu titled

“Connection Method” and select <strong>Standard TCP/IP over SSH</strong>







Step 3:







Fill in the <strong>SSH Hostname</strong> as<strong> elra-04.cs.colorado.edu</strong> and enter your identikey as your <strong>SSH Username</strong>.




Then click the button labeled “Store in Keychain” for <strong>SSH Password</strong> and type in your identikey password when prompted.




Step 4




Leave the first two fields in the red box as is. Then enter your MySQL login credentials:




Enter your CU Identikey name in the username. Then, select “Store in Keychain” and when prompted, type in the password “password”.







Step 5




<strong> </strong>

You must give your new connection a name.  Call it anything you like.  For example, “aw”, “HW5” or “AdventureworksDW” or something similar.







Step 6:










Test the connection by clicking “Test Connection”. If you have followed the steps correctly the window shown above will appear.




Once it does, click “OK” on the popup window, then “OK” on the configuration window.







Step 6:










Your list of connections will now display the new one you just created.




Click on the new connection to launch a MySQL Workbench query editor session against your connection to the “aw” instance of MySQL on elra-04.




<h1>Appendix C – AdventureWorks Data Warehouse Data Model</h1>







<strong> </strong>