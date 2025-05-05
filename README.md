
# Classical_model-Dashboard

 

## Problem Statement

This dashboard helps the company to  understand about their sales and revenue better. It helps the company to  know that which product are best seller and about best margin products also . Through different things, they get to know their improvement area, & thus they can improve their sales by identifying these area. It also lets them know the stock of the products, thus since by using this dashboard they have identified this problem, they can further work on factors responsible for these unwanted less stock products. 

Also since selling their products in less places , thus they must try to increace it.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : It was observed that in none of the columns errors & empty values were present.
- Step 4 : For calculating profit, null values were not taken into account as only less than 1% values are null in this column.
- Step 5 : In the report view, under the view tab, theme was selected.
- Step 6 : Visual filters (Slicers) were added for four fields named "revenue", "profit", "stock quantity" & "Total Orders".
- Step 7 : four card visuals were added to the canvas,  representing total sales , profit , total Orders ,  most Ordered product
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.
        
- Step 8 : New measure was created to find total Orders.

Following DAX expression was written for the same,
        
       Total_orders = sum(order_details[quantityOrdered])
        
A card visual was used to represent count of customers.


![Snap_Count](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20143021.png?raw=true)

        
 - Step 9 : New measure was created to find Total_sales,
 
 Following DAX expression was written to find % of customers,
 
         Total_sales = sum(order_details[sales])
 
 A card visual was used to represent this Number.
 
 Snap of Total_sales
 
 ![Snap_Count](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20143033.png?raw=true)

 
 - Step 10 : New measure was created to calculate total profit & a card visual was used to represent total profit.
 
 Following DAX expression was written to find total profit,
 
         Total_Profit = SUM(order_details[profit])
    
 A card visual was used to represent this total profit.
 
 
 ![Snap_3](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20143112.png?raw=true)


- step 11 : New Measure was created to calculated most Ordered Product . 
Following DAX expression was written to find Most Ordered Product ,
MostOrderedProduct = 
    SELECTCOLUMNS(TOPN(1,SUMMARIZE('products',products[productName],"TotalOrdered",SUM('order_details'[quantityOrdered])),[TotalOrdered],DESC),"MostOrderedProduct",'products'[productName]) 

A card visual was used to represent the most ordered product name .

![Snap_3](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20143104.png?raw=true)

 

# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20152653.png?raw=true)

 
 # Report Snapshot (Power BI DESKTOP)

 
![Dashboard_upload](https://github.com/ArpitJain2004/test/blob/main/Screenshot%202025-05-05%20152932.png?raw=true)

# Insights

A single page report was created on Power BI Desktop and other pages contain tool tips of this report.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Orders = 105.52K

   Total  sales  = ₹9.6M

   Total Profit  = ₹ 3.83M

   Most Ordered product = 1992 Ferrari 360 Spider Red
           

  
  These ratings will change if different visual filters will be applied.  
  
  
 

