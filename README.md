# Financial Star Schema
*This is a challenge of Data Engineering NTT DATA Bootcamp in [DIO](https://web.dio.me/).* It consists in creating a Star Schema in Power BI using [the financial dataset](https://github.com/GiovanyRezende/sales_report/).

## The Dimension Tables
|Dimension|Description
|-|-|
|dim_product|Describes the products in sales|
|dim_product_details|Describes the products' details|
|dim_discount|Describes the discounts in sales|
|dim_details|Describes other sales' details, like country and segment|
|dim_calendar|A calendar repository|

## The Fact Table
|ft_sales|Describes all the sales and the dataset in general|
|-|-|

## The Origin Table (hidden)
|financials|Has all the columns of the whole schema|
|-|-|

## DAX for dim_calendar
```
dim_calendar = CALENDAR(
  MINX(financials,[Date]),
  MAXX(financials,[Date])
)
```

## Schema Construction
All the dimension tables and the fact table were built over the origin table. Each table in star schema is a transformed form of origin table, except ```dim_calendar```, which was made with DAX.

## Star Schema
![image](https://github.com/user-attachments/assets/a8f00ca0-1595-46cb-b5b5-7e52dfe3c230)


## Dashboard
![image](https://github.com/user-attachments/assets/4bcefc6c-8c84-42bb-97e0-5f58ed25014b)
