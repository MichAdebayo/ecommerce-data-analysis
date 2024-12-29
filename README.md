# **Data Analysis with Pandas**

## Project Overview

This project analyses data scraped from an e-commerce website (Castorama; for IP reasons, the data cannot be shared). The scraped data consists of two CSV files:

- `categories.csv`: Contains information about product categories, page_list status, and urls.

- `products.csv`: Contains product details such as unique_id, categories, subcategories, titles, prices, and urls.

As a Data Analyst/Data Engineer, your role is to clean, prepare, and analyze this data to provide insights into the current state of the company's products.

## Objectives  

- **Load the data** from scraping (the CSV files categories.csv and products.csv).  
- **Clean and prepare** this data (correct formats, handle missing values, manage data types).  
- **Explore the data** and extract key insights (descriptive statistics, groupby, statistics, etc.).  
- **Format variables (where necessary)** to facilitate analysis (category labels, price correction, etc.).  
- **(Bonus 1) Analyze pricing** in more depth by grouping products by categories and calculating statistics (mean, min, max, etc.).  
- **(Bonus 2) Visualize the results** of your analysis through simple graphs (histogram, scatter plot, bar plot, etc.) to better communicate your findings. 

## Project Structure

* `brief_pandas.ipynb`: File to execute data cleaning, data mining, data anlysis, and data vizualization procedures. 

* `requirements.txt`: List of necessary python dependencies.

## Installing dependencies
```bash
pip install -r requirements.txt
```

## Key Processing Techniques and Tools
1. **Initial data exploration and validation**
   - Load data.
   - View data shape, head, summary stats, info, tail.
   - Check for missing values.
   - Check for duplicates.
   - Review data for unusual text or numerical format errors.

2. **Data Cleaning**
   - Normalize texts.
   - Remove text duplicates.
   - Handle encoding issues.
   - Handle NAs vs NaNs issues.
   - Remove diacritic duplicates.
   - Clean category and product dataset texts.

3. **Data Transformation**
   - Remove accents.
   - Standardize text formats.
   - Format variables data types.

4. **Data Mining**
   - Extract insights through grouping, filtering, and exploring categorical and numerical features.
   - Prepare data for analysis.

5. **Visualization**
   - Leveraged Python libraries such as Matplotlib and Seaborn for graphical representation of insights.
   - **Correlation Analysis**: Used statistical methods to identify relationships between product categories and their prices.


## Result summary

In this project, I applied data cleaning and mining techniques on a dataset scraped from an e-commerce website (Castorama). Following this, data analysis was conducted to uncover patterns and insights within the dataset. Key observations are reported below:

### **Dataset Overview**

- The category dataset includes **1372 categories**, each described by attributes such as:
  - `category`: The category of the page. Note that "category" in this context includes both parent and child categories. 
  - `is_page_list`:(bool) States whether a category link is a page list link. A true page_list link is a link that takes you directly to where all products in that category are displayed. 
  - `url`: The website link to that category

- The product dataset includes **28,308 products**, each described by attributes such as:
  - `unique_id`: An id identying each product
  - `category`: Product's parent category
  - `subcategory`: Product's parent 1st-level child
  - `subsubcategory`: Product's parent 2nd-level child
  - `subsubsubcategory`: Product's parent 3rd-level child
  - `title`: Product name
  - `price`: Product price
  - `url`: Link to product page

- Products belong to **16 distinct categories**, **52 subcategories**, **150 subsubcategories**, and **75	subsubsubcategories**.

### **Product Distribution**

- The **"cuisine"** category has the **fewest products (30)**, while **"salle_de_bains_et_wc"** has the **most products (8,450)**.

- These numbers highlight the diversity in product offerings across different categories.

### **Price Analysis**
- **Overall average price**: €145  
  - Minimum price: €0.50  
  - Maximum price: €5,890

- Categories with noteworthy price characteristics:
  - **Lowest average price**: €12 in **"droguerie_entretien_de_la_maison"**.  
  - **Highest average price**: €493 in **"maison_connectee_domotique_et_objet_connecte"**.  
  - **Smallest price range**: **"peinture"**.  
  - **Largest price range**: **"salle_de_bains_et_wc"**.
  - Some of the **cheapest products** include: stamped steel bracket (€0.50), manual filling pump for all fluids (€2.60), and cotton mop head replacements (€1.60).
  - Some of the **most expensive products** include: dual acrylic whirlpool bathtub (€5,890), pellet stove (€3,190), and bottle storage cabinet for wine cellars or wine shops (€3,425).


### **Price Correlations Between Categories**

- Strong correlations were identified between the prices of certain categories:
  - When prices in **"salle_de_bains_et_wc"** increase, prices in **"decoration_interieure"** also tend to rise.
  - Conversely, prices in **"quincaillerie"** tend to decrease as prices in **"salle_de_bains_et_wc"** increase.
- Such correlations may indicate shared market trends, pricing strategies, or complementary product relationships.