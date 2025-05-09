# TE IT DSBDA PRACTICALS

This repository contains all the practicals for Third Year Information Technology - Data Science and Big Data Analytics Lab.

## Prerequisites
- Hadoop 2.x or 3.x
- Java 8 or higher
- Python 3.x with required libraries
- Hive
- R Studio
- MongoDB
- Jupyter Notebook

## Detailed Assignment List

### Assignment 1: Basic Statistics and Data Preprocessing
**Location**: `1st/`
**Objective**: Learn data preprocessing techniques and basic statistical operations
**Steps to Run**:
1. Environment Setup:
```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```
2. Dataset Preparation:
   - Use provided dataset or your own dataset
   - Ensure dataset is in CSV format
   - Place dataset in `1st/` directory

3. Running the Analysis:
   - Open Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
   - Navigate to `1st/` directory
   - Open the notebook file

4. Operations Covered:
   - Data loading and inspection
   - Handling missing values
   - Statistical measures (mean, median, mode)
   - Data normalization
   - Feature scaling
   - Outlier detection
   - Data visualization

### Assignment 2: MapReduce Programming
**Location**: `2nd/`
**Objective**: Implement MapReduce program for analyzing sales data
**Prerequisites**:
1. Hadoop Setup:
   ```bash
   # Start Hadoop daemons
   start-dfs.sh
   start-yarn.sh
   ```

2. File Structure:
   - `SalesMapper.java`: Contains mapping logic
   - `SalesReducer.java`: Contains reducing logic
   - `SalesCountryDriver.java`: Main driver class
   - `access_log_short.csv`: Input data file

3. Compilation Steps:
   ```bash
   # Set HADOOP_CLASSPATH
   export HADOOP_CLASSPATH=$(hadoop classpath)

   # Compile Java files
   javac -cp $HADOOP_CLASSPATH SalesMapper.java SalesReducer.java SalesCountryDriver.java

   # Create JAR
   jar -cvf SalesAnalysis.jar *.class
   ```

4. Running MapReduce Job:
   ```bash
   # Create input directory in HDFS
   hadoop fs -mkdir /input
   hadoop fs -put access_log_short.csv /input

   # Run the job
   hadoop jar SalesAnalysis.jar SalesCountryDriver /input/access_log_short.csv /output
   ```

5. View Results:
   ```bash
   hadoop fs -cat /output/part-r-00000
   ```

### Assignment 3: NoSQL Database Operations
**Location**: `3rd/`
**Objective**: Working with MongoDB for NoSQL operations

1. MongoDB Setup:
   ```bash
   # Start MongoDB service
   sudo service mongod start
   ```

2. Database Operations:
   ```javascript
   // Connect to MongoDB
   mongosh

   // Create database
   use studentDB

   // Insert documents
   db.students.insertMany([...])

   // Perform CRUD operations
   db.students.find()
   db.students.updateOne()
   db.students.deleteOne()
   ```

3. Aggregation Operations:
   - Group by operations
   - Filtering
   - Sorting
   - Projections

4. Implementation Details:
   - Refer to `ass3_implementation.pdf`
   - Theory concepts in `ass3_theory.pdf`

### Assignment 4: Text Analytics
**Location**: `4th/`
**Objective**: Text preprocessing and sentiment analysis

1. Setup Environment:
```bash
pip install nltk textblob wordcloud pandas numpy matplotlib seaborn
```

2. NLTK Setup:
```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')
```

3. Text Processing Steps:
   - Tokenization
   - Stop word removal
   - Lemmatization
   - Part-of-speech tagging
   - Named Entity Recognition

4. Sentiment Analysis:
   - Using TextBlob for sentiment scoring
   - Visualization of sentiment distribution
   - Word cloud generation

### Assignment 5: Air Quality Analysis
**Location**: `5th/`
**Objective**: Statistical analysis of air quality data

1. Dataset Setup:
   - Download air_quality.csv separately (>50MB)
   - Place in `5th/` directory

2. Analysis Components:
   - Time series analysis
   - Correlation analysis
   - Statistical hypothesis testing
   - Visualization of pollution trends

3. Running Analysis:
```python
python air_quality_analysis.py
```

4. Visualization Types:
   - Line plots for time series
   - Heatmaps for correlation
   - Box plots for distribution
   - Bar charts for comparisons

### Assignment 6: Data Visualization
**Location**: `6th/`
**Objective**: Advanced data visualization techniques

1. Libraries Used:
```bash
pip install plotly dash seaborn matplotlib pandas
```

2. Visualization Types:
   - Interactive dashboards
   - Statistical plots
   - Geographic visualizations
   - Custom plot styling

### Assignment 7: Association Rule Mining
**Location**: `7th/`
**Objective**: Market basket analysis

1. Setup:
```bash
pip install mlxtend pandas numpy
```

2. Analysis Steps:
   - Data preprocessing
   - Apriori algorithm implementation
   - Association rule generation
   - Rule visualization

### Assignment 8: Classification Techniques
**Location**: `8th/`
**Objective**: Implementation of classification algorithms

1. Algorithms Covered:
   - Decision Trees
   - Random Forest
   - Support Vector Machines
   - K-Nearest Neighbors

2. Implementation Steps:
   - Data preprocessing
   - Model training
   - Cross-validation
   - Performance evaluation

### Assignment 9: Clustering Analysis
**Location**: `9th/`
**Objective**: Implementation of clustering algorithms

1. Algorithms:
   - K-Means
   - Hierarchical Clustering
   - DBSCAN

2. Analysis Steps:
   - Feature selection
   - Algorithm implementation
   - Cluster visualization
   - Evaluation metrics

### Assignment 10: Big Data Analytics
**Location**: `10th/`
**Objective**: Big data processing and analysis

1. Tools Used:
   - PySpark
   - Hadoop
   - Hive

2. Implementation:
   - Big data processing
   - Distributed computing
   - Data warehousing
   - Analytics pipeline

## Hive Installation and Setup
**Location**: `Hive installation/`

1. Prerequisites:
   - Hadoop installed and running
   - Java 8 or higher
   - Proper environment variables set

2. Installation Steps:
   ```bash
   # Download Hive
   wget https://downloads.apache.org/hive/hive-x.x.x/apache-hive-x.x.x-bin.tar.gz

   # Extract and set environment variables
   export HIVE_HOME=/path/to/hive
   export PATH=$PATH:$HIVE_HOME/bin
   ```

3. Configuration:
   - Configure `hive-site.xml`
   - Initialize Metastore
   - Start HiveServer2

4. Verification:
   ```bash
   hive --version
   ```

## Important Notes
1. Large Files:
   The following files need to be downloaded separately:
   - `hadoop.tar.gz` (204.76 MB)
   - `hive.tar.gz` (142.67 MB)
   - `air_quality.csv` (59.64 MB)

2. Best Practices:
   - Always create virtual environment
   - Keep datasets in appropriate directories
   - Follow proper naming conventions
   - Document any changes

## Troubleshooting
1. Hadoop Issues:
   - Check logs in `$HADOOP_HOME/logs`
   - Verify JAVA_HOME setting
   - Check port availability

2. Python Dependencies:
   - Use `requirements.txt`
   - Check Python version compatibility
   - Verify library versions

## Contributing
1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create Pull Request

## Contact
For queries:
- Course Instructor
- Lab Assistants
- Department Coordinators

## License
This project is licensed under standard academic usage terms. Please check with your institution for specific terms of use. 