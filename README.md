# This is an Online Store Analysis
   ## Data Analysis Project With Python Pandas
 
Analysing dataset from an online store to answer bussiness questions:
1. What was the best month for sales. How much was earned?
2. What Us City has the highest number of sales.
3. What time should we place advertisement to increase the  likelihood of buying?
4. What are some product that are always sold together?
5. What product is sold the most and why do you think is sold?

This business questions is answered analysing the store dataset with pandas and matplotlib for the data visualization

# Step 1 :

   Loading the data using the panda method ***pd.read_csv()***
   
# Step 2 :
   Cleaning the dataset which include finding missing value in the dataset this was achieved using the ***is_null()*** panda method
   I deleted the missing value with the following lines of code
   
   `all_data = all_data[all_data['Order Date'].str[0:2]!="Or"]`
   Then i converted the column to the right data type using ***to_numerical()*** function
   
   I augment my data column with the table,i converted it to a the right data type using the ***.astype()***  function
   
   I added the city column with the following line of code
   
`def get_city(address):
    return address.split(",")[1]
def get_state(address):
    return address.split(',')[2].split(" ")[1]
all_data["City"] = all_data["Purchase Address"].apply(lambda x : f"{get_city(x)}({get_state(x)})" )`
 
 After i made sure my data is well cleaned ,then i proceed to step 4
 # Step 4:
   Answering the first question.
   # What was the best month for sales .How much was earned?
       # add sales column by multiplying Quanttity ordered by price
   
   Then i visualized my results with matplotlib 
   `import matplotlib.pyplot as plt
months=range(1,13)
plt.bar(months,results['Sales'])
plt.ylabel("Price in USD ($)")
plt.xlabel("Month Number")
plt.show()
`

According to my analysis i found out that month of december has the highest number of sales

 # Step 5. What Us City has the highest number of sales.How much was earned?
Using  data visualization library *matplotlib* i  found out that San francisco as the highest number of sales
Using the sum function i found out how much was earned
 
