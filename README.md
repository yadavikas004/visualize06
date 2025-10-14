Calculations
Basic
Profit Ratio = [Profit] / [Sales]

Aggregate
AVG([Sales]), SUM([Profit])

Row-level discounts
Discounted Price = [Price] * (1 - [Discount])

Table 
RUNNING_SUM(SUM([Sales]))

Logical
IF [Profit] > 0 THEN "Profit" ELSE "Loss" END

Parameters
[Discounted Sales] = [Sales] * (1 - [Discount Percentage])  

Procedure: -  
Part A: Performing Calculations 
1. Open Tableau Desktop and connect to a dataset (e.g., Sample Superstore). 
2. Go to the Data Pane (left side) → Right click → Select Create Calculated Field. 
3. In the calculation editor, write a formula such as: 
    o Profit Ratio = [Profit] / [Sales]. 
    o Or Discounted Price = [Sales] * (1 - [Discount]). 
4. Click OK → The new calculated field appears in the Data Pane. 
5. Drag the calculated field into the Rows/Columns/Marks shelf to use it in visualization. 
Part B: Creating Parameters 
1. In the Data Pane, right click → Select Create Parameter. 
2. In the dialog box: 
    o Name it (e.g., Discount Percentage). 
    o Choose a Data Type (Integer, Float, String, Date). 
    o Provide Allowable values (List, Range, or All). 
    o Example: Range from 0.0 to 1.0 with step size 0.05. 
3. Right click the parameter → Select Show Parameter Control. 
4. Create a calculated field using the parameter. Example: 
    [Discounted Sales] = [Sales] * (1 - [Discount Percentage]) 

 
5. Drag this calculated field to the view → It updates dynamically as you change the 
parameter slider/drop-down. 
Part C: Combining Parameters with Calculations 
1. Create a parameter (e.g., Profit Threshold). 
2. Create a calculation using the parameter: 
    IF [Profit] > [Profit Threshold] THEN "Above Threshold" 
    ELSE "Below Threshold" 
    END 
3. Drag this calculation to Color shelf → Bars/Marks will change color based on user controlled threshold. 
