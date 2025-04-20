# Regime-Detection-Via-unsupervised-Learning
 Regime Detection via Unsupervised Learning
This project applies unsupervised learning techniques to identify market regimes (e.g., Trending, Mean-Reverting, Volatile) from order book (depth20) and trade volume (aggTrade) data. The analysis includes custom feature engineering, K-Means clustering, UMAP visualization, and Markov chain-based regime transition modeling.

📁 Project Structure
bash
Copy
Edit
.
├── depth20_dummy.csv             # Sample depth data
├── aggTrade_dummy.csv           # Sample aggregated trade data
├── regime_detection.ipynb       # Jupyter Notebook with code & results
├── Regime_Clustering_Report.pdf # Analytical report of the project
├── Regime_Clustering_Report_Table.csv # Tabular version of the report
└── README.md                    # This file
⚙️ Workflow
1. Data Preparation
Load and parse timestamped order book and trade volume data.

Join and align data as necessary.

2. Feature Engineering
Custom features are engineered to capture market microstructure:

mid_price, spread, microprice

imbalance_lvl1, cum_bid_qty, cum_ask_qty

log_return, volatility_2, volatility_3

volume_imbalance, vwap, vwap_shift

depth_slope_bid, depth_slope_ask

3. Normalization
All numerical features are scaled using StandardScaler for better clustering performance.

4. Clustering
K-Means with n_clusters=3

Clustering quality is evaluated using Silhouette Score.

Each data point is labeled with a regime_label.

5. Regime Transition Modeling
Markov Chain transition matrix estimates the probability of moving between regimes.

Transition probabilities offer insight into temporal regime dynamics.

6. Visualization
Regime evolution over time (line plot).

2D regime projection using UMAP (scatter plot with cluster labels).

📈 Outputs
Silhouette Score: Measures clustering quality.

Transition Matrix: Regime-to-regime probability table.

UMAP Plot: Visual representation of clustering.

Regime Timeline: How regimes change over time.

🧠 Insights
Certain regimes tend to persist while others frequently transition.

Regimes often correspond to distinct market behaviors (e.g., low volatility vs. high imbalance).

This method can inform algorithmic trading strategies, risk management, and market microstructure studies.

📄 Report
Detailed report is provided in PDF and CSV format.

Includes feature explanations, clustering technique, evaluation metric, and insights.

📌 Dependencies
bash
Copy
Edit
pip install pandas numpy matplotlib seaborn scikit-learn umap-learn
✍️ Author
Saugata Malakar

B.Tech, Civil Engineering @ IIT Kharagpur

