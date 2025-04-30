# Day 36: Mean & Median Imputation  
**Date:** 29th April, 2025 (Tuesday)  

Today I learnt about **Mean and Median Imputation**, which is a really important concept in **Machine Learning**, especially for handling missing data.

---

## 💡 Why Use It?

We use **mean** or **median imputation** when:

- Data is **missing completely at random (MCAR)**.
- The missing data is **less than 5%** of the dataset.

✨ In **mean imputation**, we replace missing values with the **average (mean)** of the column.  
✨ In **median imputation**, we replace missing values with the **middle value (median)** — **not the highest value**.

---

## 🛠 How to Use It?

### ✅ Using **Pandas**:

First, calculate the mean or median of the column:

```
mean_of_column = X_train[column_name].mean()
median_of_column = X_train[column_name].median()
```

Then, fill missing values:
```
X_train[column_name] = X_train[column_name].fillna(mean_of_column)
X_test[column_name] = X_test[column_name].fillna(mean_of_column)

# or for median
X_train[column_name] = X_train[column_name].fillna(median_of_column)
X_test[column_name] = X_test[column_name].fillna(median_of_column)
```

📊 You can also check how this imputation affects your data’s correlation and covariance:
```
X_train.corr()
X_train.cov()
```

📈 And to visualize the difference before and after imputation, you can plot KDE graphs!

### ✅ Using Scikit-learn:
```
from sklearn.impute import SimpleImputer
from sklearn.compose import ColumnTransformer

# Define imputers
imputer_mean = SimpleImputer(strategy='mean')
imputer_median = SimpleImputer(strategy='median')

# Apply to specific columns
trf = ColumnTransformer([
    ('imputer_mean', imputer_mean, [mean_column_names]),
    ('imputer_median', imputer_median, [median_column_names])
], remainder='passthrough')

# Fit and transform
X_train_transformed = trf.fit_transform(X_train)
X_test_transformed = trf.transform(X_test)
```

To see what values were used to fill in the missing data:
```
trf.named_transformers_['imputer_mean'].statistics_
```

### 🌈 Summary:
✨ Use mean/median imputation when the data is MCAR and the missing percentage is low.
✨ Always calculate the mean/median from X_train only, and apply it to both X_train and X_test.
✨ Imputation can slightly affect correlations, so visualizations (like KDE plots) help analyze the changes.

---
So that’s what I learned today!
Feeling one step closer to being a data scientist 💻🔍
Thank youuuu! 

## Contact Us:
If you have any questions or feedback, feel free to reach out!

Email: [email](muskantariq2003@gmail.com)

LinkedIn: [Muskan Tariq](https://www.linkedin.com/in/muskan-tariq-095a50282/)

Instagram: [AI Enthusiast](https://www.instagram.com/ai_enthusiast86/)

YouTube: [AI Enthusiast](https://www.youtube.com/@ai_enthusiast86)
