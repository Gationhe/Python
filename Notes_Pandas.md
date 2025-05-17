# Data Cleaning
Data cleaning means fixing bad data in your data set. We may encounter the following situations:
- Empty cells
- Data in wrong format
- Wrong data
- Duplicates

## Solutions for each case:

### Empty Cells
- Remove Rows
- Replace Empty Values
- Replace Using Mean, Median, or Mode

### Data of Wrong Format
- Convert Into a Correct Format
- Removing Rows

### Wrong Data (i.e. unreasonable value(s) in data set)
- Replacing Values
- Removing Rows

### Duplicates
- Removing Duplicates

## Example

The data set contains some empty cells ("Date" in row 22, and "Calories" in row 18 and 28).
The data set contains wrong format ("Date" in row 26).
The data set contains wrong data ("Duration" in row 7).
The data set contains duplicates (row 11 and 12).

```
import pandas as pd
df = pd.read_csv("data_exercise.csv")

# new_df = df.dropna() # original data set is not revised
df.dropna(inplace = True) # original data set is revised

df["Date"] = pd.to_datetime(df['Date'], format='mixed')
df.dropna(subset=['Date'], inplace = True)

df.loc[7, 'Duration'] = 45 # observe & guess

print(df.duplicated()) # return boolean (T/F) for every row that is a duplicate
df.drop_duplicates(inplace = True) # remove all duplicates
```
