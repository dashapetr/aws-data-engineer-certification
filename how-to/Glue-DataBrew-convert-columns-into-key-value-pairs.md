# Convert user-selected columns into key-value pairs


A company receives .csv files that contain physical address data. The data is in columns that have the following names: Door_No, Street_Name, City, and Zip_Code. The company wants to create a single column to store these values in the following format:
```
{
   "Door_No": "24",
   "Street_Name": "AAA street",
   "City": "BBB",
   "Zip_Code": "111111"
}
```

**Which solution will meet this requirement with the LEAST coding effort?**

**Response:**

1. Use AWS Glue DataBrew to read the files.
2. Use the NEST_TO_MAP transformation to create the new column.

Documentation quote:
```
NEST_TO_MAP

Converts user-selected columns into key-value pairs,
each with a key representing the column name and a value representing the row value. 
```

Source: https://docs.aws.amazon.com/databrew/latest/dg/recipe-actions.NEST_TO_MAP.html
