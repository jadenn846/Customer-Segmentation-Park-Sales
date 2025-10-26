# EU Park Customer Segmentation Analysis

## 1. Business Problem
The management team of an EU park wants to move beyond simple sales tracking to truly understand its customers. They need to answer: **"Who are our different customer types, and what do they buy?"**

This project analyzes 1,000 transaction records to segment customers into distinct groups based on their purchasing habits. The goal is to provide actionable recommendations for marketing, inventory, and personalized customer engagement.

## 2. Analytical Approach
The project follows a standard data science workflow:

* **Data Preprocessing:** The dataset (1,000 rows, 30 item columns) was loaded and inspected. It was confirmed to be clean with no missing values or duplicates.
* **EDA:** Statistical distributions for all 30 items were analyzed using boxplots and histograms to understand purchase quantities.
* **Clustering & Validation:** The K-Means algorithm was used. To find the optimal number of clusters (k), two validation methods were applied:
    1.  **The Elbow Method:** Showed a clear "elbow" (point of diminishing returns) at **k=4**.
    2.  **Davies-Bouldin Index:** This metric confirmed **k=4** was the best choice, as it had the lowest score.
* **Visualization:** **Principal Component Analysis (PCA)** was used to reduce the 30 dimensions of the dataset down to 2 principal components to visualize the four distinct customer clusters.

## 3. Key Findings: The 4 Customer Segments
The analysis successfully identified four distinct customer segments of equal size (250 customers each).

| Cluster ID | Segment Persona | Top Purchased Items |
| :--- | :--- | :--- |
| **Cluster 0** | **The "Health-Conscious" Buyer** | `Water`, `Veggie Burger`, `Salad`, `Juice` |
| **Cluster 1** | **The "Snacks & Drinks" Crowd** | `Nachos`, `Cocktail`, `Beer`, `Wine` |
| **Cluster 2** | **The "Classic Fast Food" Fan** | `Cheeseburger`, `Hamburger`, `Fries`, `Soft Drink` |
| **Cluster 3** | **The "Coffee & Cookie" Breaker** | `Cookie`, `Coffee`, `Cupcake`, `Tea` |

## 4. Business Recommendations
Based on these segments, the following data-driven strategies are recommended:

1.  **Targeted Meal Deals:** Stop generic promotions. Create targeted combos for each segment (e.g., a "Classic Combo" for the Fast Food Fans and a "Health Kick" combo with a Veggie Burger + Water).
2.  **Smart Stall Placement:** Place "Coffee & Cookie" stalls near park entrances or rest areas. Place "Snacks & Drinks" stalls near social gathering spots or evening entertainment venues.
3.  **Inventory Optimization:** Ensure stalls are cross-stocked with items their target segment is likely to buy. For example, the fast-food stall (Cluster 2) should be well-stocked with soft drinks, while the salad stall (Cluster 0) should also have plenty of water and juice.

## 5. How to Run This Project

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/jadenn846/Customer-Segmentation-Park-Sales
    cd customer-segmentation-park-sales
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    # On macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    
    # On Windows
    python -m venv venv
    venv\Scripts\activate
    ```

3.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the notebook:**
    Launch Jupyter Notebook and open `Eu-park food sales analysis.ipynb`.
    ```bash
    jupyter notebook
    ```

## 6. Libraries Used
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn (KMeans, PCA, Davies-Bouldin Score)
