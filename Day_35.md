# Complete Case Analysis (CCA) - Learning Summary

### Hello Everyone!

Today is **28th April, 2025**, and the day is **Monday**.  
Today, I learned about **Complete Case Analysis (CCA)**, an important technique in **Machine Learning**.  
I learned that CCA is *easy* but *risky*. It’s essential to first check how much data is missing before applying this technique. If the missing data is less than 5%, then it's okay to use CCA. However, if the missing data is more than 5%, then it's not recommended to apply CCA.

### Steps I used:

1. **Data Loading**  
   I first took a random dataset and uploaded it using Pandas.
   ```python
   import pandas as pd
   df = pd.read_csv('your_dataset.csv')
**Check Missing Data**
I checked the percentage of missing data in each column with the following code:
`df.isnull().mean() * 100`
**Filter Columns with Less Than 5% Missing Data**
I then selected only those columns with missing data of less than 5%. Here's the code:
`col = [var for var in df.columns if df[var].isnull().mean() < 0.05]`
**Check Impact of CCA**
Before applying CCA, I wanted to check how much data would remain. If too much data were removed, I wouldn't proceed with CCA. So, I used this code:
`len(df[col].dropna()) / len(df[col])`
**Apply Complete Case Analysis (CCA)**
After ensuring that enough data would remain, I applied CCA with this simple line:
`new_df = df.dropna()`
**Visualizing the Difference**
To compare the original and CCA datasets, I plotted graphs using Matplotlib to visualize the difference between both datasets.
`import matplotlib.pyplot as plt`

# Plotting original vs. CCA data
`df['column_name'].value_counts().plot(kind='bar', alpha=0.6, label='Original Data')
new_df['column_name'].value_counts().plot(kind='bar', alpha=0.6, label='CCA Data')`

`plt.legend()
plt.title('Comparison of Original Data and CCA Data')
plt.xlabel('Category')
plt.ylabel('Frequency')
plt.show()`
**Concatenate the Original and CCA Data**
I then concatenated the original and CCA datasets to see the difference side-by-side:
`temp = pd.concat([
    df[column_name].value_counts() / len(df[column_name]),
    new_df[column_name].value_counts() / len(df[column_name])
], axis=1)
temp.columns = ['original', 'cca']
print(temp)`
## Conclusion:
That’s all about my learning for today! I’ve learned how to implement Complete Case Analysis (CCA) and how important it is to check the missing data before applying it.
While it’s a simple technique, it’s crucial to ensure that applying it won’t result in losing too much data.
Still learning, still growing! 🌱

## Contact Us:
If you have any questions or feedback, feel free to reach out!

Email: [email](muskantariq2003@gmail.com)

LinkedIn: [Muskan Tariq](https://www.linkedin.com/in/muskan-tariq-095a50282/)

Instagram: [AI Enthusiast](https://www.instagram.com/ai_enthusiast86/)

YouTube: [AI Enthusiast](https://www.youtube.com/@ai_enthusiast86)
