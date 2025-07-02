# **Car Data Scraping and Analysis with BeautifulSoup**

**Developed by:** [Muhammad Aqeel Zafar](https://github.com/maqeelzafar047)

---

## 📌 **Project Overview**

This project showcases the complete pipeline of **scraping, cleaning, analyzing, and visualizing car listings data** from [Cars.com](https://www.cars.com) using Python. Built entirely in **Jupyter Lab**, the notebook guides users through extracting meaningful information from multiple pages of real-time car listings, preparing it for analysis, and generating visual insights.

---

## 🧠 **Key Features**

-  Web scraping with `requests` and `BeautifulSoup`
- Data transformation and cleanup with `pandas`
- Exploratory data analysis using `matplotlib` and `seaborn`
- Export of structured data to CSV for future use
- Supports scaling to multiple pages (up to 500)



## 🧰 **Technologies Used**

- **Python 3**
- **Libraries:** `pandas`, `requests`, `beautifulsoup4`, `matplotlib`, `seaborn`
- **Jupyter Lab** or **Jupyter Notebook**



## ▶️ **How to Run This Notebook**

1. Open the notebook in **Jupyter Lab** or **Jupyter Notebook**
2. Ensure the following libraries are installed:
   ```
   pip install pandas requests beautifulsoup4 matplotlib seaborn
   ```
3. Run all cells sequentially
4. Review and analyze the output and graphs

---

## ⚙️ **How the Code Works**

### 1. **Web Scraping**

Scrapes multiple pages of car listings:

```python
for page in range(1, 500):
    url = f"https://www.cars.com/shopping/results/?page={page}..."
    response = requests.get(url, headers=headers)
    soup = BeautifulSoup(response.content, 'html.parser')
    # extract desired fields
```

Extracted fields include:

- Car Name
- Mileage
- Dealer Name
- Dealer Rating
- Review Count
- Price
- Location

### 2. **Creating the DataFrame**

```python
car_data = pd.DataFrame({
    'Name': names,
    'Mileage': mileage,
    'Dealer': dealers,
    'Rating': ratings,
    'Reviews': reviews,
    'Price': prices,
    'Location': location
})
```

### 3. **Cleaning and Preprocessing**

- Removed dollar signs, commas, and text from numerical fields
- Handled missing/null values gracefully

### 4. **Exporting the Data**

```python
car_data.to_csv("car_data_scraping.csv", index=False)
```

- Cleaned dataset saved locally for further analysis

### **5. Visualizing Insights**

```python
sns.histplot(car_data['Price'], bins=30)
plt.title("Distribution of Car Prices")
```

- Distribution of prices
- Relationship between mileage and price
- Fuel type and brand breakdowns (if extended)

---

## 📊 Summary of Findings

- Popular brands and their price distribution
- Mileage trends across listings
- Dealer reputation impact on pricing
- Data suggests how users can filter high-value deals

---

## **Disclaimer**

This project is created by M Aqeel Zafar and is intended for educational purposes only. It is not affiliated with or endorsed by bikez.com. Do not use this script for any commercial or abusive activities. Always respect websites' terms of service.

---

