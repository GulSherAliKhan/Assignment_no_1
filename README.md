# Assignment_no_1

## Q NO1: Write a function called proportion_of_education which returns the proportion of children in the dataset who had a mother with the education levels equal to less than high school (<12), high school (12), more than high school but not a college graduate (>12) and college degree.


1. ### Importing Libraries:
    The code starts by importing the required libraries. `pandas` is imported as `pd`, which is a popular library for data manipulation and analysis.

3. ### Defining the Function:
   The function `proportion_of_education` is defined with a single parameter `file_path`, representing the path to the CSV file containing the dataset.

5. ### Reading the CSV File:
   Inside the function, the CSV file is read using the `pd.read_csv()` function, which loads the data into a pandas DataFrame named `df`.

7. ### Calculating Proportions: \
   The function proceeds to calculate the proportion of children with mothers having different education levels. It does this by using the `value_counts()` function on the 'EDUC1' column of the DataFrame `df`. This function counts the occurrences of each unique value in the 'EDUC1' column and returns a pandas Series object with the counts. By setting `normalize=True`, the counts are converted into proportions, ensuring that the sum of all proportions is 1.

9. ### Creating the Proportions Dictionary:
 The function then creates a dictionary named `education_proportions` to store the education levels as keys and their corresponding proportions as values. The education levels are defined as strings, such as 'Less than high school (<12)', 'High school (12)', 'More than high school but not a college graduate (>12)', and 'College degree'. The proportions obtained from the previous step are assigned as the values to the respective keys.

11. ### Returning the Result:
12.  Finally, the function returns the `education_proportions` dictionary containing the education levels and their proportions.

The purpose of this function is to allow users to quickly compute and obtain the proportion of children in the dataset with mothers having different education levels. By calling this function with the path to their CSV file, users can get a clear overview of the distribution of education levels among the mothers in the dataset. This can be particularly useful for understanding the educational background of the mothers and gaining insights into the data.

## Question 2: Let's explore the relationship between being fed breastmilk as a child and getting a seasonal influenza vaccine from a healthcare provider. Return a tuple of the average number of influenza vaccines for those children we know received breastmilk as a child and those who know did not.
The provided code utilizes the pandas library to read data from a CSV file named "NISPUF17.csv" and performs calculations to determine the average number of influenza doses for two distinct groups based on whether they received a flu shot during the survey period.

The code defines a function called `average_influenza_doses`, which is capable of computing the mean number of influenza doses for the following groups:

1. Group df1: This DataFrame includes only the records where the value of the "CBF_01" column is equal to 1. "CBF_01" is a binary variable indicating whether a person received a flu shot (1 for yes, 2 for no).

2. Group df2: This DataFrame includes only the records where the value of the "CBF_01" column is equal to 2. This group represents people who did not receive a flu shot during the survey period.

The function calculates the mean of the "P_NUMFLU" column for both df1 and df2 using the pandas `mean` method. The "P_NUMFLU" column represents the number of influenza doses a person received.

Subsequently, the function returns a tuple containing the mean of the "P_NUMFLU" column for df1 and df2. This tuple consists of two values: the average number of influenza doses for people who received a flu shot (group df1) and the average number for those who did not receive a flu shot (group df2).

In essence, the `average_influenza_doses` function serves to compute and provide valuable insights into the average number of influenza doses for individuals belonging to the two specified groups, distinguished by their flu shot status during the survey period.

## Question 3 :It would be interesting to see if there is any evidence of a link between vaccine effectiveness and sex of the child. Calculate the ratio of the number of children who contracted chickenpox but were vaccinated against it (at least one varicella dose) versus those who were vaccinated but did not contract chicken pox. Return results by sex.This function should return a dictionary in the form of (use the correct numbers):
## {"male":0.2,
## "female":0.4}
## ANS
The function provided performs several data manipulation and analysis tasks using the pandas library. Here is a summary of its functionality:

1. ### Importing Libraries:
    The function imports the pandas library, a powerful tool for data handling and analysis.

3. ### Reading the CSV File:
    The function reads data from a CSV file named "NISPUF17.csv" and stores it in a pandas DataFrame called 'df'.
   
4. ### Selecting Columns:
   The function selects specific columns of interest from the DataFrame, which are "SEX" (gender), "HAD_CPOX" (indicates whether a person had chickenpox), and "P_NUMVRC" (number of doses of the chickenpox vaccine received).

5. ### Removing Missing Values:
   The function drops any rows that contain missing values using the `dropna` method. This step ensures that the subsequent calculations are based on complete and valid data.

6. ### Filtering Rows:
    The function filters out rows where the number of chickenpox vaccine doses ("P_NUMVRC") is equal to 0, indicating that the person did not receive any doses of the vaccine.

7. ### Creating Gender-Specific DataFrames:
    The function creates two new DataFrames, one for males and one for females, by using boolean indexing based on the "SEX" column.

8. ### Calculating Ratios:
     For each gender group, the function calculates the ratio of the number of people who had chickenpox (indicated by the value 1 in the "HAD_CPOX" column) to the number who did not (indicated by the value 2 in the "HAD_CPOX" column). These calculations are limited to individuals who received at least one dose of the chickenpox vaccine (indicated by "P_NUMVRC >= 1").

9. ### Returning Results:
    The function returns a dictionary with two keys, "male" and "female", where the values are the respective ratios calculated for each gender group.

10. ### Assertion Check:
The final assertion statement ensures that the returned dictionary contains exactly two items, one for males and one for females, confirming the correctness of the function's output.

In summary, the function processes data related to gender, chickenpox vaccination status, and the number of vaccine doses received. It then computes and provides the ratio of individuals who had chickenpox to those who did not, but only for those who received at least one dose of the vaccine, separately for males and females.
## Question 4:A correlation is a statistical relationship between two variables. If we wanted to know if vaccines work, we might look at the correlation between the use of the vaccine and whether it results in prevention of the infection or disease [1]. In this question, you are to see if there is a correlation between having had the chicken pox and the number of chickenpox vaccine doses given (varicella).
ANS: The function average_influenza_doses() reads in the data from a CSV file using pandas and then filters the data based on the value of the "CBF_01" column. The values of 1 and 2 in the "CBF_01" column indicate whether the child was born in the US or not, respectively. Two new dataframes are created: one for children born in the US (CBF_01 = 1) and one for children born outside the US (CBF_01 = 2). The function then calculates the mean number of influenza vaccine doses administered to children in each group using the "P_NUMFLU" column, which contains the number of flu vaccine doses administered to each child. Finally, the function returns a tuple with two values: the mean number of flu vaccine doses for children born in the US and the mean number of flu vaccine doses for children born outside the US.
