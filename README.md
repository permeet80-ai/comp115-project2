# comp115-project2
# COMP115 Project 2

## Description
This project analyzes housing affordability in British Columbia using 2016 census data.

## Objectives
- Analyze housing affordability
- Identify high rent areas
- Compare rent burden across regions

## Tools Used
- Python
- Pandas
- Matplotlib

## Python Code
```python
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv("bc_census_2016.csv")

high_rent = data[data["shelt_rent_30plus_rate"] > 50]

plt.bar(high_rent["area_name"], high_rent["shelt_rent_30plus_rate"])
plt.xticks(rotation=45)
plt.title("High Rent Areas")
plt.show()

region_avg = data.groupby("region")["shelt_rent_30plus_rate"].mean()

region_avg.plot(kind="pie", autopct="%1.1f%%")
plt.title("Rent by Region")
plt.ylabel("")
plt.show()
```

## Results
High rent burden is mainly seen in coastal areas like Vancouver.

## Conclusion
Housing affordability is a serious issue and varies by region. Better policies are needed.
