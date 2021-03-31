# Release Management

v2 -> comes in two parts

CLIENT -> (helm cli)
SERVER -> (Tiller)

- if you execute helm install
- helm cli send request to Tiller
- whenever you create or change deployment
- Tiller stores copy of each configuration for future reference
- creating history of chart executions
- Keeping track of all chart executions

> helm upgrade <chartname>
- changes are applied to existing deployment instead of creating a new one