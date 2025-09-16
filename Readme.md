# Toronto Crime Data Analysis

A comprehensive data science project that analyzes Toronto's Major Crime Indicator (MCI) dataset using advanced clustering techniques to identify violent and non-violent neighborhoods, providing actionable insights for public safety and law enforcement.

## Project Overview

This project processes over 131,000 crime records from Toronto Police's public portal (2000-2017) to automatically classify neighborhoods based on criminal activity patterns. Using multiple unsupervised learning algorithms, we create data-driven insights that support evidence-based decision making for both authorities and citizens.

## Key Features

- **Multi-Algorithm Clustering**: Implementation and comparison of K-Means, Agglomerative, and DBSCAN clustering
- **Advanced Data Processing**: Comprehensive preprocessing pipeline handling duplicates, redundant features, and data cleaning
- **Dimensionality Reduction**: PCA application for improved visualization and computational efficiency
- **Robust Validation**: Multiple internal validation measures (Silhouette Score, Dunn Index, Calinski-Harabasz Score, Davis-Bouldin Score)
- **Interactive Visualization**: Crime heatmap overlay on Toronto city map using Google Maps API
- **Temporal Analysis**: Time-based crime pattern identification and spatial distribution analysis

## Dataset

- **Source**: Toronto Police Public Portal
- **Records**: 131,000+ major crime indicators
- **Timespan**: 2000-2017
- **Features**: 29 parameters including location, time, crime type
- **Focus Years**: 2015, 2016, 2017 (highest crime frequency)

## Technologies Used

- **Python**: Core programming language
- **Scikit-learn**: Machine learning algorithms and validation metrics
- **Pandas & NumPy**: Data manipulation and numerical computing
- **Matplotlib & Seaborn**: Data visualization
- **Google Maps API**: Geographic visualization
- **PCA**: Principal Component Analysis for dimensionality reduction

## Methodology

### 1. Data Preprocessing
- Removed 17,165 duplicate entries
- Feature selection and redundant data elimination
- Dataset restructuring by neighborhood groupings

### 2. Clustering Algorithms

#### K-Means Clustering
- Optimal k selection using elbow method and silhouette analysis
- k=2 identified for violent/non-violent classification

#### Agglomerative Clustering
- Hierarchical bottom-up approach
- Ward linkage strategy for optimal cluster structure

#### DBSCAN
- Density-based clustering for irregular cluster shapes
- Parameters: eps=1.2, minPoints=4

### 3. Validation & Evaluation
Comprehensive evaluation using four internal validation measures:
- **Silhouette Coefficient**: Cluster cohesion and separation
- **Dunn Index**: Compactness and separation ratio
- **Calinski-Harabasz Score**: Variance ratio criterion
- **Davis-Bouldin Score**: Within/between cluster distance ratio

## Key Results

### Algorithm Performance Comparison (2017 Data)
| Algorithm | Silhouette | Dunn Index | C-H Score | D-B Score |
|-----------|------------|------------|-----------|-----------|
| K-Means | 0.703 | 0.091 | 116.7 | 0.783 |
| DBSCAN | 0.683 | 0.119 | 102.8 | 0.867 |
| **Agglomerative** | **0.721** | **0.150** | **115.5** | **0.775** |

**Winner**: Agglomerative clustering achieved the best overall performance across validation metrics.

### Identified Violent Neighborhoods (2017)
- Annex
- Bay Street Corridor  
- Church-Yonge Corridor
- Islington-City Centre West
- Moss Park
- South Riverdale
- Waterfront Communities-The Island
- Woburn
- York University Heights

## Usage

```python
# Load and preprocess data
python data_preprocessing.py

# Run clustering analysis
python clustering_analysis.py

# Generate visualizations
python visualization.py

# Create interactive map
python crime_heatmap.py
```

## Visualizations

The project generates multiple visualization outputs:
- Cluster scatter plots with PCA components
- Silhouette analysis graphs
- Elbow method plots for k-selection
- Interactive crime heatmap on Toronto city map
- Temporal crime distribution charts

## Impact & Applications

- **Law Enforcement**: Enhanced resource allocation and patrol planning
- **Public Safety**: Informed decision-making for residents
- **Urban Planning**: Data-driven policy development
- **Research**: Methodology applicable to other urban crime analysis

## Future Enhancements

- Integration of socio-economic factors
- Provincial-level analysis expansion
- Real-time crime prediction models
- Mobile application development
- Advanced deep learning techniques

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Toronto Police Services for providing public crime data
- University of Waterloo research team
- Open source community for tools and libraries
