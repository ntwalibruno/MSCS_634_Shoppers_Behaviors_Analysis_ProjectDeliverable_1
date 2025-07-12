**Author**: Ntwali Bruno Bahongere  
**Course**: Advanced Big Data and Data Mining  
**Project**: Residency Project - Shoppers Behavior Analysis

## Project Overview

This project conducts a comprehensive analysis of online shopping behavior to understand customer patterns and predict revenue generation. Using a dataset of e-commerce website sessions, we perform data cleaning, exploratory data analysis (EDA), and provide insights for future machine learning modeling.

## Dataset Summary

**Source**: [Shoppers Behavior and Revenue Dataset](https://www.kaggle.com/datasets/subhajournal/shoppers-behavior-and-revenue) from Kaggle

**Dataset Characteristics**:
- **Original Size**: 12,330 sessions × 18 features
- **Final Cleaned Size**: 12,205 sessions × 18 features (99.0% data retention)
- **Target Variable**: `Revenue` (Boolean - True/False)
- **Time Period**: 10 months of e-commerce data
- **Data Quality**: Excellent (no missing values, minimal duplicates)

### Feature Categories:
- **Numerical Features (14)**: Page visit counts, session durations, bounce/exit rates, page values
- **Categorical Features (4)**: Month, visitor type, weekend indicator, revenue outcome

## Key Insights Discovered

### 1. Revenue Conversion Patterns
- **Overall Conversion Rate**: 15.6% of sessions result in purchases
- **Class Imbalance**: 5.4:1 ratio (non-revenue to revenue sessions)
- **Weekend Effect**: Weekend sessions convert slightly better (17.5% vs 15.1%)

### 2. Customer Behavior Segmentation
- **New vs Returning Visitors**: New visitors convert better (24.9% vs 14.1%)
- **High-Value Session Characteristics**:
  - 58% longer total session duration
  - 66% more product pages visited
  - 2.4× lower bounce rates
  - 2× lower exit rates

### 4. Feature Relationships
- **Strong Negative Predictors**: ExitRates (-0.237), BounceRates (-0.176)
- **Positive Predictors**: ProductRelated_Duration (+0.188), Administrative features
- **High Correlations**: Page counts strongly correlated with durations (0.7-0.8)

## Data Cleaning and Preprocessing Methodology

### Phase 1: Data Quality Assessment
1. **Missing Values Analysis**: 
   - Comprehensive check across all 18 features
   - No missing values detected in the original dataset
   
2. **Duplicate Detection**: 
   - Identified 125 duplicate records (1.0% of data)
   - Systematic analysis of duplicate patterns
   
3. **Data Type Validation**: 
   - Verified appropriate data types for each feature
   - Ensured numerical and categorical features are properly formatted
   
4. **Outlier Detection**: 
   - Applied IQR method for outlier identification
   - Statistical analysis across all numerical features

### Phase 2: Data Cleaning Implementation
1. **Missing Values Handling**:
   - No missing values required imputation
   - Robust framework implemented for future datasets
   
2. **Duplicate Removal**:
   - Removed 125 duplicate rows using pandas drop_duplicates()
   - Preserved 99.0% of original data integrity
   
3. **Data Validation**:
   - Verified cleaned dataset structure and quality
   - Confirmed data types and statistical properties

### Phase 3: Exploratory Data Analysis Setup
- Created cleaned dataset (`df_cleaned`) for analysis
- Configured visualization environment with matplotlib and seaborn
- Established consistent plotting styles and parameters

## Exploratory Data Analysis (EDA)

### 1. Numerical Features Analysis
- **Distribution Visualization**: Created comprehensive histograms with KDE for all 14 numerical features
- **Statistical Summary**: Generated detailed statistics including mean, median, skewness, and kurtosis
- **Skewness Assessment**: Identified heavily right-skewed distributions requiring transformation
- **Zero-Inflation Detection**: Analyzed features with significant zero values (>10%)

### 2. Categorical Features Analysis  
- **Distribution Analysis**: Visualized all categorical features with appropriate charts
- **High-Cardinality Handling**: Focused on top categories for features like OperatingSystems, Browser, Region
- **Value Frequency**: Detailed breakdown of unique values and their percentages
- **Feature Summary**: Comprehensive statistics for each categorical variable

### 3. Correlation Analysis
- **Correlation Matrix**: Generated comprehensive heatmap for all numerical features
- **High Correlation Detection**: Identified features with correlation >0.7
- **Target Variable Relationships**: Analyzed correlation between features and revenue outcome
- **Statistical Significance**: Applied t-tests to validate feature relationships with revenue

### 4. Advanced Visualizations
- Numerical feature distribution plots with statistical overlays (mean, median, KDE)
- Categorical feature bar charts with frequency analysis
- Correlation heatmap with masked upper triangle for clarity
- Box plots showing feature distributions by revenue outcome
- Statistical significance testing with p-value annotations

## Challenges Encountered and Solutions

### Challenge 1: Class Imbalance
**Problem**: Highly imbalanced target variable (approximately 5.4:1 ratio)
**Solution**: 
- Identified through initial data exploration
- Documented for future modeling considerations
- Recommended appropriate evaluation metrics and sampling techniques

### Challenge 2: Highly Skewed Distributions
**Problem**: Most numerical features heavily right-skewed
**Solution**:
- Used appropriate visualization techniques (histograms with KDE)
- Added statistical interpretation for skewness assessment
- Recommended transformations for future modeling

### Challenge 3: Zero-Inflated Features
**Problem**: Many duration features contain significant zero values
**Solution**:
- Systematic analysis of zero-inflation patterns
- Flagged features with >10% zero values
- Recommended special treatment in modeling phase

### Challenge 4: High-Cardinality Categorical Features
**Problem**: Features like OperatingSystems, Browser, Region have many unique values
**Solution**:
- Focused visualization on top 10 categories
- Provided comprehensive statistics with top 5 breakdowns
- Recommended binning strategies for modeling

### Challenge 5: Data Quality Assessment
**Problem**: Need to ensure data reliability before analysis
**Solution**:
- Implemented systematic quality checks
- Applied IQR method for outlier detection
- Validated data types and structures

### Challenge 6: Visualization Clarity
**Problem**: Complex dataset requires clear, interpretable visualizations
**Solution**:
- Configured consistent plotting styles and parameters
- Added statistical overlays (mean, median lines)
- Used appropriate chart types for different data types

## Technical Implementation

### Libraries Used
- **Data Manipulation**: pandas, numpy
- **Visualization**: matplotlib, seaborn
- **Statistical Analysis**: scipy.stats
- **Data Loading**: kagglehub for dataset download
- **Environment**: warnings management for clean output

### Notebook Structure
1. **Project Header**: Student and course information
2. **Library Imports**: All required packages in single cell
3. **Data Loading**: Kaggle dataset download and CSV import
4. **Data Exploration**: Initial dataset inspection and statistics
5. **Data Quality Assessment**: Missing values, duplicates, outliers, data types
6. **Data Cleaning**: Duplicate removal and validation
7. **EDA Setup**: Visualization configuration and environment setup
8. **Numerical Analysis**: Distribution analysis with statistical interpretation
9. **Categorical Analysis**: Feature analysis with appropriate visualizations
10. **Correlation Analysis**: Comprehensive relationship analysis with target variable

### Key Improvements Made
- **Streamlined Workflow**: Consolidated analysis into focused, logical sections
- **Enhanced Visualizations**: Added statistical overlays (mean, median, KDE) to distributions
- **Comprehensive Statistics**: Detailed statistical summaries with interpretation
- **Better Organization**: Clear separation between data cleaning and analysis phases
- **Professional Presentation**: Consistent formatting and clear documentation


## Project Structure

```
shoppers_behavior_analysis.ipynb    # Main analysis notebook
README.md                           # This documentation file
```

---

*This analysis provides a solid foundation for advanced data mining techniques and predictive modeling in e-commerce analytics.*
