# IBM Watson Studio Recommendation System

A comprehensive recommendation system that analyzes user interactions with articles on the IBM Watson Studio platform and provides personalized article recommendations using multiple recommendation techniques.

![IBM Watson Studio Platform](https://via.placeholder.com/800x300/1f77b4/ffffff?text=IBM+Watson+Studio+Platform)

## Project Overview

This project implements a complete recommendation pipeline that combines multiple approaches to recommend relevant articles to users based on their interaction history. The system uses real data from the IBM Watson Studio platform to build and evaluate different recommendation strategies.

## Recommendation Techniques

The project implements five distinct recommendation approaches:

### 1. **Exploratory Data Analysis (EDA)**
- Comprehensive analysis of user-article interactions
- Identifying patterns, trends, and data characteristics
- Understanding user behavior and article popularity distributions

### 2. **Rank-Based Recommendations**
- Recommends articles based on popularity (most interactions)
- Ideal for new users (cold start problem)
- Simple yet effective baseline approach

### 3. **User-User Collaborative Filtering**
- Identifies similar users based on their interaction patterns
- Recommends articles that similar users have interacted with
- Provides personalized recommendations based on user similarity

### 4. **Content-Based Recommendations**
- Analyzes article content using NLP techniques
- Clusters similar articles together
- Recommends related content based on article similarity

### 5. **Matrix Factorization (SVD)**
- Machine learning approach using Singular Value Decomposition
- Decomposes user-item interaction matrix
- Predicts user preferences for unseen articles
- Evaluates recommendation quality and accuracy

## Project Structure

```
dsnd-recommendation-systems-project/
│
├── data/                                    # Dataset directory
│   └── user-item-interactions.csv          # User-article interaction data
│
├── notebooks/                               # Jupyter notebooks
│   └── Recommendations_with_IBM.ipynb      # Main analysis notebook
│
├── tests/                                   # Test files and validation
│   ├── project_tests.py                    # Unit tests for solutions
│   ├── top_5.p                             # Test data (pickled)
│   ├── top_10.p                            # Test data (pickled)
│   └── top_20.p                            # Test data (pickled)
│
├── .gitignore                              # Git ignore file
├── LICENSE.txt                             # Project license
├── requirements.txt                        # Python dependencies
└── README.md                               # This file
```

## Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Jupyter Notebook or JupyterLab

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/dsnd-recommendation-systems-project.git
   cd dsnd-recommendation-systems-project
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Open the main notebook**
   - Navigate to `notebooks/Recommendations_with_IBM.ipynb`
   - Run cells sequentially to execute the analysis

## Dataset

The project uses the **IBM Watson Studio user-article interactions dataset**, which contains:
- **45,993** user-article interactions
- **5,149** unique users
- **714** unique articles
- No explicit ratings (interactions are implicit feedback)

### Data Files

- `data/user-item-interactions.csv`: Contains user IDs, article IDs, and interaction records

## Key Features

✨ **Multiple Recommendation Strategies**: Implements 5 different approaches for comprehensive coverage

📊 **Detailed Analysis**: Extensive exploratory data analysis with visualizations

🤖 **Machine Learning**: Matrix factorization using SVD for predictive recommendations

🎯 **Cold Start Handling**: Rank-based recommendations for new users

🔍 **Content Analysis**: NLP-based content similarity for article clustering

## Testing

The project includes automated tests to validate your implementations.

### Running Tests

```python
# Inside the Jupyter notebook
from tests.project_tests import sol_1_test, sol_2_test, sol_4_test, sol_5_test

# Test your solutions
sol_1_test(sol_1_dict)
sol_2_test(top_articles)
sol_4_test(sol_4_dict)
sol_5_test(sol_5_dict)
```

## Implementation Tasks

### Task 1: Exploratory Data Analysis
- Analyze dataset structure and statistics
- Identify patterns in user-article interactions
- Visualize data distributions

### Task 2: Rank-Based Recommendations
- Identify most popular articles
- Implement popularity-based recommendation function
- Handle cold start problem for new users

### Task 3: User-User Collaborative Filtering
- Calculate user similarity scores
- Find similar users based on interactions
- Generate recommendations from similar user preferences

### Task 4: Content-Based Recommendations
- Extract article content features
- Apply NLP techniques (TF-IDF, etc.)
- Cluster articles by content similarity

### Task 5: Matrix Factorization
- Build user-item interaction matrix
- Apply Singular Value Decomposition (SVD)
- Predict ratings and evaluate performance
- Analyze recommendation accuracy

## Technologies Used

- **Python 3.8+**: Core programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Scikit-learn**: Machine learning algorithms (SVD, TF-IDF, clustering)
- **Matplotlib & Seaborn**: Data visualization
- **Jupyter Notebook**: Interactive development environment

## Results & Insights

The project demonstrates:
- **Rank-based recommendations** work well for new users but lack personalization
- **Collaborative filtering** provides personalized recommendations but suffers from cold start
- **Content-based recommendations** help discover similar articles
- **Matrix factorization** offers the most sophisticated predictive approach
- **Hybrid approaches** combining multiple methods yield the best results

## Future Enhancements

- [ ] Implement hybrid recommendation system combining multiple approaches
- [ ] Add real-time recommendation API
- [ ] Include temporal dynamics (time-based recommendations)
- [ ] Implement deep learning approaches (Neural Collaborative Filtering)
- [ ] Add A/B testing framework for recommendation evaluation
- [ ] Deploy as web application with user interface

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the terms specified in the [LICENSE.txt](LICENSE.txt) file.

## Acknowledgments

- **IBM Watson Studio** for providing the dataset
- **Udacity Data Science Nanodegree** for project framework
- Community contributors and reviewers

## Contact

For questions or feedback, please open an issue in the repository.

---

**Note**: This project is part of the Udacity Data Science Nanodegree program and is intended for educational purposes.
