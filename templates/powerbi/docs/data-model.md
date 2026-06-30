# Data Model

## Architecture

[Diagram or description of dimensional model]

## Star Schema Overview

### Fact Tables

#### FactSales
- **Grain**: Transaction-level (one row per transaction)
- **Dimensions**: Date, Customer, Product, Region
- **Measures**: Amount, Quantity, Discount, Tax

#### FactInventory
- **Grain**: Daily inventory by location
- **Dimensions**: Date, Product, Location
- **Measures**: OnHandQty, ReorderPoint

### Dimension Tables

#### DimCustomer
- **Key**: CustomerID
- **Attributes**: Name, Segment, Region, BirthDate
- **SCD Type**: Type 2 (tracking history)

#### DimProduct
- **Key**: ProductID
- **Attributes**: Name, Category, SubCategory, UnitPrice
- **SCD Type**: Type 1 (overwrites)

#### DimDate
- **Key**: DateID
- **Attributes**: Date, Month, Quarter, Year, FiscalYear
- **Type**: Conformed dimension

## Relationships

[Describe key relationships, many-to-one mappings, etc.]

## Performance Considerations

- [Aggregations and summarization strategy]
- [Incremental refresh setup]
- [Partitioning strategy if applicable]

## Known Limitations

[List any constraints or workarounds needed]
