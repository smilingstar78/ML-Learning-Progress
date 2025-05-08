# Day 44 Using Percentile Technique to Detect Outliers

Today is 8th May, 2025 Thursday and today I am on my 44th Day of Learning ML.

I have uploaded a file and this project demonstrates how to detect and handle outliers in a dataset using the Percentile Method. It includes two key techniques for managing outliers:

Trimming – removes extreme values.

Capping (Winsorization) – limits extreme values to a defined percentile threshold.

## 🧠 Techniques Used
1. Percentile Method
Calculate the lower and upper bounds using percentiles (e.g., 5th and 95th).

Values outside these bounds are considered outliers.

2. Trimming
Completely removes data points that fall outside the chosen percentile range.

✅ Pros: Clean data

❌ Cons: Loses information

3. Capping (Winsorization)
Replaces extreme outlier values with the nearest boundary (e.g., anything below 5th percentile becomes equal to the 5th percentile value).

✅ Pros: Retains all rows

❌ Cons: May distort actual values

🔧 How It Works (Steps)
Load dataset.

Choose percentile thresholds (e.g., 5th and 95th).

## Apply:

Trimming to drop outliers.

Capping to replace them with boundary values.

---

## 📣 Wanna Connect?

Let’s grow and learn together!

- 🔗 [LinkedIn](https://www.linkedin.com/in/muskan-tariq-095a50282)
- 📷 [Instagram](https://www.instagram.com/ai_enthusiast86)
- 🧠 [YouTube](https://www.youtube.com/@ai_enthusiast86?si=bYV1AgkBoCMVUBiK)

---

## ✨ Output
**trimmed**: DataFrame with outliers removed.

**capped**: DataFrame with outliers capped to nearest thresholds

