# Men’s Fashion Brand Analysis Dashboard | Power BI | Azure SQL server

## Dashboard Link :

https://app.powerbi.com/view?r=eyJrIjoiNTUzMGRkODAtNTZhNC00NzdlLWE2ZWItZGMxZGFiNzIzNTU1IiwidCI6IjA2Y2Q0ZWQ1LTNiN2YtNDdiMC04ZWY2LTI5ZGVlMWM1MDYwYiJ9&embedImagePlaceholder=true

![d1](https://github.com/user-attachments/assets/d0e6a8f5-faaa-4308-8ec2-e0ffa6769660)

![d2](https://github.com/user-attachments/assets/a6d8e2a3-aa70-47d5-885c-9a1e7a7c5633)

(Insert dashboard screenshots here)


## Problem Statement :

This project focuses on analyzing men’s fashion retail data using:

- Azure SQL Database
- SQL Server Management Studio (SSMS)
- Power BI

The objective of the dashboard is to analyze:

- Brand-wise discount trends
- Sales price performance
- Product variety distribution
- Profitability metrics

The project also demonstrates cloud database integration using Azure SQL Database and secure authentication mechanisms for enterprise-level reporting.

## Azure SQL Database Integration

The project follows a cloud-based reporting workflow using:

- Azure Portal
- Azure SQL Database
- SSMS
- Power BI Desktop
- Azure SQL Database Setup

## Database Creation :

**In Azure Portal:**

- Created a Resource Group
- Created an Azure SQL Database
- Configured:
    - SQL Authentication
    - Server details
    - Database deployment settings
- Firewall Configuration

![azure1](https://github.com/user-attachments/assets/f0ecf79c-1212-4452-b522-beee8639cd11)

- Configured Azure SQL firewall access:

    Azure Portal → SQL Database → Set Server Firewall
    → Selected Networks → Add IPv4 Client Address

This enabled secure connectivity between:

- Azure SQL Database
- Local SSMS
- Power BI

![azure2](https://github.com/user-attachments/assets/90191aec-c172-44da-a29e-c4c2c11b1a52)

**SSMS Integration:**

Connected local SQL Server Management Studio (SSMS) with Azure SQL Database using:

Azure server name
SQL authentication credentials
Query Editor Access

![ssms](https://github.com/user-attachments/assets/3baccd54-49d7-478b-baf0-fc9593eba076)

Used:

Azure Portal → Query Editor (Preview)
to execute and validate SQL queries directly inside Azure.

### Microsoft Entra ID Authentication

Initially, Microsoft account login inside Power BI generated:

AADSTS900021: Requested tenant identifier is not valid

Resolved by configuring:

Azure Portal → SQL Servers → Settings
→ Microsoft Entra ID → Set Admin

This enabled secure Microsoft account authentication for Power BI connectivity.

## Dataset Description

The dataset contains men’s fashion retail and pricing information.

**Columns Included :**

- Brand
- Title
- Original Price
- Sale Price

![datasource](https://github.com/user-attachments/assets/e0fb46be-5c36-4c82-8fc9-f81da801feaf)

## Data Preparation & Transformation :



### DAX Calculated Columns

**Discount Percentage :**

    Discount Percentage = 
    DIVIDE(
    'Men Tshirt'[Marked Price] - 'Men Tshirt'[Sales Price],
    'Men Tshirt'[Marked Price]
    ) * 100

**Cost Price :**

    Cost Price = 
    DIVIDE(
    100 * 'Men Tshirt'[Sales Price],
    100 + 'Men Tshirt'[Profit (%)]
    )

**Profit Percentage :**

    `Profit (%) = RANDBETWEEN(2,17)`

## Dashboard Features :

The dashboard includes
Top 5 Brands by:
- Average Discount %
- Average Profit Percentage
- Number of Product Varieties
- Average Sales Price
- Bottom 5 Brands by Profit Percentage
- Interactive brand-level analysis
- Comparative profitability visualization
- Product pricing and discount trend analysis


## Dashboard Design & UI Enhancements :

**Implemented :**
- Custom luxury-themed UI design
- Background image integration
- Transparent visual formatting
- Brand-focused layout styling
- Interactive filtering experience

## Key Insights :

**Discount Analysis :**

Brands such as:
- The Indian Garage Co
- British Club
- U.S. Polo Assn.

offer higher average discount percentages to attract customers.
Aggressive discounting strategies improve customer engagement and sales visibility.

**Profitability Trends :**
Certain premium brands maintain higher average profit percentages despite offering discounts.
Some low-performing brands generate lower profitability due to limited pricing margins.

**Product Variety Insights :**
Brands with a larger number of product varieties demonstrate stronger market presence and customer reach.
Higher product diversification contributes to broader consumer engagement.

**Pricing Analysis :**

Premium fashion brands maintain significantly higher average sales prices.
Luxury and branded apparel categories contribute strongly to revenue generation.

## Business Impact : 

The dashboard helps:

- Compare brand performance
- Analyze discount effectiveness
- Evaluate pricing strategies
- Identify high-profit and low-profit brands
- Support fashion retail business decisions

## Tools & Technologies Used :
- Power BI Desktop
- Azure SQL Database
- SQL Server Management Studio (SSMS)
- Microsoft Entra ID
- DAX
- Data Visualization & Analytics

## Conclusion :

This project demonstrates a complete cloud-based retail analytics workflow involving:

- Azure SQL Database setup
- Secure cloud authentication
- SSMS integration
- Power BI reporting
- Retail pricing and profitability analysis

The dashboard provides valuable insights into fashion brand performance, discount strategies, and profitability optimization.
