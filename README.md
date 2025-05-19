✈️ **Flight Price Dataset Preprocessing**

This project focuses on preprocessing a dataset containing flight price information. The code performs feature engineering to transform raw date/time and categorical fields into a clean format ready for machine learning models.

📁 **Dataset**
The dataset used is flight_price.xlsx, which includes features such as:

Date_of_Journey

Dep_Time

Arrival_Time

Duration

Total_Stops

Airline, Source, Destination, and Additional_Info

🧼 **Preprocessing Steps**
1. Basic Data Inspection
Used .info() and .describe() to explore dataset structure and summary statistics.

Loaded the dataset using pandas.read_excel().

2. Date Feature Engineering
Extracted Date, Month, and Year from the Date_of_Journey column.

Converted these to int types.

Dropped the original Date_of_Journey column.

3. Time Feature Engineering
Split Arrival_Time into Arrival_hour and Arrival_min.

Similarly split Dep_Time into Dep_hour and Dep_min.

Dropped the original time columns.

Converted all extracted time parts to int.

4. Duration Parsing
Extracted Duration_hour and Duration_min from the Duration column.

Filled missing values and cleaned non-numeric characters.

Converted both to int.

This helps standardize the time duration for modeling.

5. Handling Total_Stops
Mapped categories like 'non-stop', '1 stop', etc., to integers.

Filled missing values with the mode (1 stop → 1).

6. One-Hot Encoding for Categorical Variables
Columns encoded: Airline, Source, Destination, and Additional_Info.

Used sklearn.preprocessing.OneHotEncoder.

Converted the result into a pandas.DataFrame with meaningful column names using get_feature_names_out().

✅ **Output Columns**
After processing, the final dataset contains:

Numerical Features: Date, Month, Year, Dep_hour, Dep_min, Arrival_hour, Arrival_min, Duration_hour, Duration_min, Total_Stops

Encoded Features: One-hot encoded vectors for Airline, Source, Destination, Additional_Info

🛠️ **Tools & Libraries Used**
pandas

numpy

matplotlib, seaborn (for plotting)

sklearn.preprocessing.OneHotEncoder

📌 **Future Steps**
Impute missing values more robustly (if needed).

Normalize/scale numerical features for model compatibility.

Train machine learning models for price prediction or classification tasks.

Visualize feature importance.

📂 *File Structure**
bash
Copy
Edit
flight_price_preprocessing/
│
├── flight_price.xlsx             # Raw dataset
├── preprocessing_script.ipynb    # Jupyter notebook with all preprocessing
└── README.md                     # This file
🤝 **Contributing**
Feel free to fork the repo and suggest improvements in data cleaning or modeling. Always welcome to collaboration!

