# Project 2: Hot Spot Analysis

**Author**: Naveen Kumar Manokaran  
**Student ID**: 1232482864  

---

## ✨ Project Overview
This project focuses on analyzing geospatial data to identify hot zones and hot cells using **Apache Spark**, **Scala**, and **SparkSQL**. The key tasks include:
1. **Hot Zone Analysis**:
   - Identifying rectangles (zones) with the most geospatial points.
2. **Hot Cell Analysis**:
   - Using **Getis-Ord statistics** to determine statistically significant hot cells.

---

## 📚 Reflection

### Key Steps:
1. **Technology Stack Exploration**:
   - Tools: **Apache Spark**, **Scala**, **Java**, **SparkSQL**, and **Hadoop**.
   - Learned how to process geospatial data from CSV files and set up a development environment on Windows.

2. **Project Execution**:
   - **Hot Zone Analysis**:
     - Implemented the `ST_Contains` function in `HotzoneUtils` to check if a point lies within a rectangle.
     - Used group-by and sorting operations in `HotzoneAnalysis` to identify zones with the highest point density.
   - **Hot Cell Analysis**:
     - Implemented `computeAdjacentCell` and `GScore` functions in `HotcellUtils` for calculating the total neighbors and Getis-Ord statistics.
     - Altered `HotcellAnalysis` to calculate mean, standard deviation, and adjacency values to identify hot cells with high G-scores.

---

## 🚀 Methodology

### 1. Hot Zone Analysis
- **Goal**: Identify rectangles (zones) with the highest point density.
- **Implementation**:
  - **`ST_Contains` Function**:
    - Checks if a point lies within a rectangle by comparing coordinates.
  - **Hot Zone Calculation**:
    - Counts points within each rectangle.
    - Sorts zones by point density in descending order to identify hot zones.

### 2. Hot Cell Analysis
- **Goal**: Use **Getis-Ord statistics** to identify significant hot cells.
- **Implementation**:
  - **`computeAdjacentCell` Function**:
    - Calculates the number of neighboring cells in a 3x3 matrix.
  - **`GScore` Function**:
    - Computes the Getis-Ord statistic using the formula:
      \[
      G_i^* = \frac{\sum_j w_{ij} x_j - \bar{X} \sum_j w_{ij}}{S \sqrt{\frac{(n \sum_j w_{ij}^2) - (\sum_j w_{ij})^2}{n-1}}}
      \]
      Where:
      - \( \bar{X} \): Mean
      - \( S \): Standard deviation
      - \( w_{ij} \): Weights (neighboring cells)
      - \( x_j \): Values of neighboring cells
  - **Hot Cell Calculation**:
    - Computes G-scores for all cells and sorts them in descending order.
    - Outputs cells with the highest G-scores as hot cells.

---

## 📝 Lessons Learned
1. **Geospatial Data Processing**:
   - Efficiently processed and analyzed geospatial datasets using SQL and Scala.
2. **Apache Spark**:
   - Set up and worked with Spark for large-scale data processing.
3. **Hot Zone vs. Hot Cell Analysis**:
   - Differentiated between identifying dense zones (hot zones) and statistically significant cells (hot cells).
4. **Getis-Ord Statistics**:
   - Learned to calculate and interpret G-scores for identifying spatial clusters.
5. **Zone-Based Analysis**:
   - Divided geospatial data into zones and analyzed results for each zone.

---

## 📂 Output
### Key Observations:
1. **Hot Zone Analysis**:
   - Successfully identified zones with the highest density of geospatial points.
2. **Hot Cell Analysis**:
   - Used **Getis-Ord statistics** to identify statistically significant hot cells with high G-scores.
3. **Significance**:
   - Higher G-scores indicate cells with more points than the average, highlighting areas of high activity.

### Test Case Results:
- Output results matched the provided test cases for both:
  - **Hot Zone Analysis**
  - **Hot Cell Analysis**

---

## 🛠️ Technologies Used
- **Programming Languages**: Scala, Java
- **Frameworks**: Apache Spark, SparkSQL
- **Environment**: Hadoop ecosystem
- **Algorithms**:
  - **Getis-Ord Statistics**
  - Rectangle-point intersection logic

---

## 📂 How to Run

1. **Set Up Environment**:
   - Install **Apache Spark**, **Hadoop**, and required tools on a Windows machine.
   - Configure the IDE (e.g., IntelliJ IDEA or Eclipse) with Scala and Java support.

2. **Run Hot Zone Analysis**:
   - Modify the `HotzoneUtils` and `HotzoneAnalysis` files as described.
   - Run the Spark job to generate outputs for zones with the highest density.

3. **Run Hot Cell Analysis**:
   - Modify the `HotcellUtils` and `HotcellAnalysis` files as described.
   - Run the Spark job to compute G-scores and identify significant hot cells.

4. **Verify Output**:
   - Compare outputs with the provided test cases to validate functionality.

---

## 🔮 Future Enhancements
1. **Expand Analysis**:
   - Extend functionality to analyze time-based geospatial activity (e.g., daily or hourly trends).
2. **Visualization**:
   - Integrate GIS tools to visualize hot zones and hot cells on a map.
3. **Scalability**:
   - Optimize Spark jobs for larger datasets with millions of geospatial points.

---

## 📜 References
1. **SIGSPATIAL GISCUP 2016 Problem**: [http://sigspatial2016.sigspatial.org/giscup2016/problem](http://sigspatial2016.sigspatial.org/giscup2016/problem)
