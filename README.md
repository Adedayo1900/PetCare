# PetCare
PetCare is an organization that deals in pet related supplies. However, they are interested in prioritizing their marketing and distribution strategies to maximize sales. This project gives insight to how best they should channel their marketing strategy and maximize sales.

# Overview
PetCare deals in marketing and selling different categories of pet needs and they have got them in different sizes. Some of these products enjoy repeat purchase (A repeat purchase is the purchase of same product as bought on a previous occasion by a consumer). This indicates a degree of customer loyalty to a product. The marketing team at PetCare has a constrained budget and is looking at channelling all their resources to advertising and marketing of products that enjoy repeat purchases alone as they believe this will help boost sales rather than sharing their constrained budget on marketing all products. They have done this (focus on products that enjoy repeat_purchase) for six months and would like to know if their strategy is working and if they should continue this marketing strategy or go back to focusing on all products with inclusion of those that do not enjoy repeat purchase.

# Business Question
Should PetCare continue to focus their marketing and advertising budget on only product that enjoy repeat_purchase?

# Available Data
The marketing team of PetCare has provided us with the dataset containing their sale for the past month (Septemer, 2023). 

DATASET: [pet_supplies_2212.csv](https://github.com/Adedayo1900/PetCare/files/13046716/pet_supplies_2212.csv)

It contains 1500 rows and 8 columns (product_id,category,animal,size,price,sales,rating,repeat_purchase)

DATA SOURCE: This data was featured on DataCamp associate data analyst exam.

# Analysis
  # Importing of Data and viewing its data type.
To begin analysis, This data was imported and a subset of the data was viewed to give an insight into its records. This was done using the python code below.

##To import the data and also view a subset of the data

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/4e736727-8288-407b-84e4-80b7a9e57aad)

Next, i had to view the data type of the different columns, to ensure they match with their contents. Hence, i did this with the code below.

##Check Datatype

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/88c4b44d-132c-4f0c-a967-a2f64c459955)

I realized that the column 'price' was of the datatype string when it should actually be numerical. Also, although the column 'repeat_purchase' had two unique values ('1' and '0'), they represented (repeated_purchases and non_repeated_purchases) respectively, hence it should be a categorical data with the datatype 'string'. I had to go ahead to do some data wrangling and cleaning before proper analysis.
  # Data Cleaning
First, the data type of the columns 'price' and 'repeat_purchase' were changed into 'float' and 'string' respectively.

##Changed the datatype of the column 'price' and 'repeat_purchase'.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/9b07c0a9-2e9c-47f3-90fb-d129932b7039)

Second, i checked for missing data, this is to ensure proper data exploration.

##Checked for missing data.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/3eb8d58d-204b-4bb2-b7cb-caa25adcc9a7)

Here, i noticed that the 'price' column had 150 missing data. This was filled with the overall average price. Also, the column 'rating' had a total of 150 missing columns. Since they werent rated by consumers, the missing rows were filled with a rating of zero (0). When this was done, a second check gave no missing data.

##Fill missing data.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/b0698c2d-75ca-4629-ae9d-8f503de35613)

Lastly, to finish up my data cleaning process, records for the 'size' column was cleaned as it had 9 unique values (large, LARGE, Large, Small, small, SMALL, MEDIUM, medium and Medium) due to case sensitivity. This was cleaned and replaced with title case values (Large, Small and Medium).

Also, the column 'repeat_purchase' had two unique values ('1' and '0'), they were replaced with (repeated_purchases and non_repeated_purchases) respectively.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/ac9bd7d1-3184-4282-bb81-e42b8a1c81f9)

Now, the data is clean and it was ready for analysis to derive insight.
  # Data Analysis
To answer the business question of whether PetCare should shift from advertising and marketing products that do not enjoy repeat purchases and focus on product that enjoy repeat purchase, i had to do some analysis. 

The first was to check for the number of products that enjoy repeat_purchase and compare with those that do not. Also, i plot a graph of repeat purchase against sales to see their contribution to total sales.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/faedfe0d-bc20-4063-a316-b7038c0ff384)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/4192757b-91d6-4d26-a3df-d6a8bc5eb872)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/742bf359-f82a-4b9f-bde6-c40201a4dd6c)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/63aa1203-5853-4e2f-8e31-b78e71f061a4)

From the plots above, one could tell that products with repeat_purchase were more and they contributed a lot to total sales. We might want to conclude that continued focus on products that enjoy repeat purchase is more beneficial as they truly contribute more to total sales.

However, when i looked deeply, i realised that products that do no not enjoy repeat_purchase had a higher average sales compared to those that enjoy repeat purchase. This is show in the plot below.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/3815365a-ab99-4d33-afb6-78053f057717)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/123dd4b1-6396-47a7-af4a-3b1c06426e87)

This might suggest that although they aren't contributing as high as those that enjoy repeat purchases to total sales, they however generate high quality sales, i.e, their sale values are more concentrated above the 50th percentile of sales distribution compared to those that enjoy repeat purchase. This made me go ahead to view 'sales' distribution with respect to 'repeat_purchase'.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/3660b47d-e073-4cfd-a925-5e46a2601073)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/1b0fc81c-78f6-4c24-a661-1ce12ee19006)

The box plot confirms the suggestion above as we can see that sales of products that do not enjoy repeat_purchase are more distributed above the 50th percentile compared to those that enjoy repeat_purchase.

Could this be by chance? To confirm this statistically, i went ahead to do a t-test to see if it is statistically significant.

The null hypothesis was an assumption that product that enjoy repeat purchase and those that do not contribute equally to average sales.

The t-test which is represented in the analysis as t-stat was done using the code below.

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/5fffdcd9-31a0-4bcf-8c24-eddbf98f9ff6)

![image](https://github.com/Adedayo1900/PetCare/assets/130705411/b4e1407f-ea22-4686-b5f8-d11256c30973)

Where
mean sales of repeat purchase= x_reap= 975.768400

mean sales of non-repeat purchase= x_non_reap= 1028.368013

standard deviation of repeat purchase= s_reap = 326.985415

standard deviation of non-repeat purchase= s_non_reap= 316.915770

frequency of repeat purchase= n_reap = 906

frequency of non-repeat purchase= n_non_reap= 594

degree of freedom= dfe= n_non_reap + n_reap - 2

The calculation gave a t-test (t-stat) value of 3.1043 and a p-value of 0.00097. This p-value is below 0.05 and it indicates that there is a significant difference and they do not contribute equally to average sales.

# Recommedation
The analysis has shown that although products that enjoy repeat purchase boost sales by contributing more to total sales, however, products that do not enjoy repeat purchase also boost sales as they have higher average sale thereby generating more quality sales (sales above the 50th percentile of sales distribution), hence choosing to ignore them to focus on products with repeat_purchase might affect overall sales and cause a reduction in sale value or revenue.
