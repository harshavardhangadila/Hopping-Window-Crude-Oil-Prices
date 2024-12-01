# Hopping-Window-Crude-Oil-Prices

The goal of the analysis was to calculate and visualize hopping window statistics (mean and maximum prices) for daily crude oil prices, specifically the West Texas Intermediate (WTI) dataset. A hopping window divides the data into overlapping windows of a fixed size, with a specified step (hop) between windows. The approach allows insights into local trends and variations within the data.

Dataset Structure and Preprocessing
The dataset contains two key components:

DATE: A chronological record of the dates.
DCOILWTICO: Daily crude oil prices in dollars per barrel.
Upon loading the dataset, we encountered that DATE was already set as the index. This required adjustments in the code to handle the index directly instead of treating DATE as a separate column. Data preprocessing involved:

Ensuring the index (DATE) was converted to a proper datetime format.
Converting DCOILWTICO to numeric values to handle potential non-numeric or missing data.
Dropping invalid rows using dropna() to ensure smooth computations.
Hopping Window Implementation
The hopping window method involves the following parameters:

Window Size: The fixed size of each window, here set to 7 days.
Hop Size: The step size between the start of consecutive windows, here set to 3 days.
For each window:

The mean price (average crude oil price) and the maximum price (highest crude oil price) were calculated.
The start date of each window was recorded for reference.
The resulting statistics (mean and max prices) were stored in a new DataFrame for further analysis.

Visualization of Results
The computed hopping window results were visualized with a dual line plot:

Mean Price: Highlighting average trends within each window.
Max Price: Capturing extreme values within each window.
This visualization effectively shows the fluctuations in crude oil prices over time while providing localized trends that help spot short-term variations.

Challenges Encountered
Index Management:
Initially, the code assumed that DATE was a separate column, but the dataset had DATE as the index. This required updating the logic to work directly with the index.
Data Formatting:
Non-numeric values and missing data in DCOILWTICO were handled using pd.to_numeric and dropna() to ensure clean data for calculations.
Adjusting Window Logic:
Proper handling of start and end indices for window computations to ensure no out-of-range errors.
Outputs and Deliverables
Hopping Window DataFrame:
A table showing the start date, mean price, and max price for each window.
This table was saved as a CSV file (hopping_window_results.csv) for further use.
Visualization:
A plot comparing the hopping window mean and max prices over time.
Insights and Use Cases
Local Trends: The hopping window approach reveals short-term trends that are not visible in broader aggregations like weekly or monthly statistics.
Extreme Values: Tracking maximum prices helps identify price spikes or unusual market conditions.
Dynamic Analysis: This method is ideal for applications requiring localized trend analysis, such as financial forecasting or anomaly detection.
In conclusion, the hopping window implementation provided valuable insights into crude oil price trends while addressing practical challenges in data preprocessing and visualization. The resulting CSV and plots serve as actionable resources for further analysis or reporting.
