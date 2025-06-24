# NBA Team Performance and Formation Analysis

## Project Overview

This project is a comprehensive machine learning analysis of NBA player performance data to optimize team formations and predict team impact scores. The system uses advanced clustering algorithms and predictive modeling to identify the best 5-player combinations that maximize team performance.

## Key Features

- **Player Clustering**: Uses K-Means and Hierarchical clustering to group players based on performance metrics
- **Dimensionality Reduction**: Implements PCA (Principal Component Analysis) to reduce feature complexity
- **Team Formation Optimization**: Finds optimal 5-player combinations using combinatorial analysis
- **Impact Score Prediction**: Random Forest model to predict team performance impact scores
- **Comprehensive EDA**: Extensive exploratory data analysis with visualizations
- **Performance Metrics**: Advanced basketball analytics including offensive/defensive ratings, usage rates, and more

## Dataset

The project analyzes NBA player data from 2000-2022, including:
- **Advanced Metrics**: Offensive/Defensive Ratings, Net Rating, Assist %, etc.
- **Usage Statistics**: Usage rates for rebounds, assists, turnovers, steals, blocks
- **Performance Indicators**: Various basketball performance metrics
- **Temporal Data**: Year-wise player performance tracking

## Technologies Used

- **Python 3.x**
- **Machine Learning**: scikit-learn, Random Forest, K-Means, Hierarchical Clustering
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Dimensionality Reduction**: PCA
- **Model Evaluation**: MSE, R² Score, Silhouette Score

## Project Structure

```
SML-TeamPerformanceandFormation/
├── Dataset/                     # Raw and processed data files
│   ├── all_data.csv            # Main dataset
│   ├── EDA.ipynb               # Exploratory Data Analysis
│   └── *.xlsx                  # Processed datasets
├── code/                       # Clustering analysis
│   ├── Clustering.ipynb        # Main clustering notebook
│   └── *.png                   # Visualization outputs
├── mastercode/                 # Core modeling
│   ├── model.ipynb             # Main prediction model
│   └── *.xlsx                  # Model datasets
├── results/                    # Analysis outputs
│   ├── *.xlsx                  # Cluster results
│   └── Merge.ipynb             # Results consolidation
├── src/                        # Production code structure
│   ├── components/             # ML pipeline components
│   ├── pipeline/               # Training and prediction pipelines
│   ├── exception.py            # Custom exception handling
│   └── logger.py               # Logging functionality
├── requirements.txt            # Python dependencies
├── setup.py                    # Package configuration
└── README.md                   # This file
```

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd SML-TeamPerformanceandFormation
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Setup the package**
   ```bash
   pip install -e .
   ```

## Usage

### 1. Exploratory Data Analysis
```bash
# Navigate to Dataset directory and run EDA notebook
cd Dataset
jupyter notebook EDA.ipynb
```

### 2. Clustering Analysis
```bash
# Navigate to code directory and run clustering notebook
cd code
jupyter notebook Clustering.ipynb
```

### 3. Model Training and Prediction
```bash
# Navigate to mastercode directory and run model notebook
cd mastercode
jupyter notebook model.ipynb
```

### 4. Results Analysis
```bash
# Navigate to results directory and run merge notebook
cd results
jupyter notebook Merge.ipynb
```

## Methodology

### 1. Data Preprocessing
- **Feature Engineering**: Created comprehensive player performance metrics
- **Data Cleaning**: Handled missing values and outliers
- **Standardization**: Normalized features for clustering

### 2. Dimensionality Reduction
- **PCA Implementation**: Reduced 50+ features to 13 principal components
- **Variance Explained**: Captured 95%+ of data variance
- **Feature Selection**: Identified most important performance indicators

### 3. Clustering Analysis
- **K-Means Clustering**: Grouped players into 10 clusters based on performance
- **Hierarchical Clustering**: Alternative clustering approach for comparison
- **Silhouette Analysis**: Evaluated clustering quality
- **Elbow Method**: Determined optimal number of clusters

### 4. Predictive Modeling
- **Random Forest Regressor**: Predicted team impact scores
- **Feature Importance**: Identified key performance drivers
- **Model Validation**: Used train-test split with R² and MSE metrics

### 5. Team Formation Optimization
- **Combinatorial Analysis**: Evaluated all possible 5-player combinations
- **Impact Score Prediction**: Predicted performance for each team combination
- **Optimal Team Selection**: Identified best performing team formations

## Results

### Model Performance
- **Validation R² Score**: 0.4446
- **Validation MSE**: 33.4351
- **Feature Importance**: PCA_1 (14.03%), PCA_2 (11.18%), PCA_6 (10.78%)

### Key Findings
- **Player Clustering**: Successfully grouped players into 10 distinct performance clusters
- **Team Optimization**: Identified optimal 5-player combinations for maximum impact
- **Performance Prediction**: Reliable prediction of team performance scores

## Applications

- **Sports Analytics**: NBA team management and player selection
- **Fantasy Sports**: Optimize fantasy team selections
- **Recruitment**: Identify players with complementary skills
- **Performance Analysis**: Understand team chemistry and synergy

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

**Ansh Motwani**
- Email: ansh.motwani.2@gmail.com

## Acknowledgments

- NBA for providing comprehensive player statistics
- Scikit-learn community for excellent ML tools
- Basketball analytics community for insights and methodologies

---

**Note**: This project is for educational and research purposes. All NBA data used is publicly available and for analysis purposes only.