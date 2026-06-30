# Data Refresh Guide

## Automated Refresh

Power BI refresh is scheduled automatically:
- **Frequency**: [Daily/Multiple times per day]
- **Time**: [UTC times]
- **Gateway**: [Premium/Standard gateway name]

### Refresh Status
Check refresh history:
1. Open Power BI Service
2. Navigate to the dataset settings
3. View "Refresh history"

## Manual Refresh

To refresh manually in Power BI Desktop:
1. Open the `.pbix` file
2. Click "Refresh" in the ribbon
3. Wait for all queries to complete
4. Save the file

## Troubleshooting Refresh Failures

### Connection Errors
- Verify credentials in `.env` file
- Check database availability
- Confirm network connectivity

### Timeout Errors
- Reduce query complexity
- Implement incremental refresh
- Contact DBA for performance tuning

### Data Validation Errors
- Check source data quality
- Verify ETL pipeline status
- Review error logs in Power BI

## Support

For refresh issues:
1. Check Power BI diagnostics logs
2. Contact [Data Engineering team]
3. Create issue with error details and timestamps
