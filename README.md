I started with standardizing the date format. The dates in the data had time with it and I standardized it using CONVERT function first by selecting the date column from Nashville housing data. And then used the UPDATE function to add the new standardized column in the data. 

I filled in missing information for property addresses. At first, it was confusing because many rows had nothing in the property address column. But after checking the data, I noticed that the parcel ID and property address were the same, just with different unique IDs. So, I matched up the data with itself using the unique IDs in self-JOIN, and then I filled in the missing property addresses.


I split the address into separate parts: address, city, and state. In the data, these parts were separated by commas. Initially, I used a function to grab the characters from the beginning of the address up to the first comma. However, this left a comma at the end of each address, which looked odd. So, I adjusted the function to stop just before the comma by subtracting 1 from its result, making sure to capture all the letters before the comma.

I updated the "sold as vacant" field to have consistent answers. Initially, the field contained variations like "yes", "no", "Y", and "N". To standardize this, I used a CASE statement: if the value was "Y", it was changed to "yes", if it was "N", it was changed to "no", and for everything else, it remained unchanged. Finally, I applied this update to the data table.


I eliminated duplicate entries from the database. However, removing data isn't typically recommended for learning purposes, as it could have been useful. To accomplish this, I utilized the partition function with columns such as parcel ID, property address, sale price, sale date, and legal reference to identify and remove duplicate entries. I deleted some unnecessary columns from the data. These columns, like owner address, tax district, and property address, weren't useful for our analysis, so I removed them from the dataset.







