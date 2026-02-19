-- Total Alerts for the period
Total Alerts = CALCULATE(COUNTROWS('Table'), 'Table'[alert_triggered] = "TRUE")

-- Success Rate percentage
Success Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('Table'), 'Table'[execution_status] = "success"),
    COUNTROWS('Table')
)
