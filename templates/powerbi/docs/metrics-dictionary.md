# Metrics Dictionary

## Key Measures

### Revenue
- **Definition**: Total revenue from all sales channels
- **Formula**: SUM(Sales[Amount])
- **Unit**: Currency (USD)
- **Updated**: Daily
- **Owner**: Finance team

### Active Customers
- **Definition**: Unique customers with transaction in last 90 days
- **Formula**: DISTINCTCOUNT(Customers[CustomerID])
- **Updated**: Daily
- **Owner**: Sales team

[Add more metrics...]

## Key Dimensions

### Date
- **Grain**: Daily
- **Range**: [Start date] to Present
- **Calendar**: [Fiscal/Calendar year definition]

### Customer
- **Primary Key**: CustomerID
- **Attributes**: Name, Segment, Region, Channel
- **Owner**: CRM team

### Product
- **Primary Key**: ProductID
- **Attributes**: Name, Category, Sub-Category, Line
- **Owner**: Product team

[Add more dimensions...]

## Calculated Columns

### Profit Margin
- **Definition**: (Revenue - Cost) / Revenue
- **Used In**: Margin analysis report

[Add more calculated columns...]
