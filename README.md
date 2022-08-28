
# Netflix Data Cleaning

I used a dataset on Netflix from Kaggle.com for this and cleaned the data to make it more beneficial and user-friendly.


## Acknowledgements

 - [Netflix DataSet](https://www.kaggle.com/datasets/shivamb/netflix-shows)


## Usage/Examples

```python
import numpy as np #linear algebra
import pandas as pd # data processing and file reading
```
```python
#reading the file and seeing it's values

netflix_data = pd.read_csv('/Users/aniketsharma/Documents/Data Science Project/Data/netflix/netflix_titles.csv')
netflix_data.head()
```
<img width="984" alt="Screenshot 2022-08-28 at 7 55 12 PM" src="https://user-images.githubusercontent.com/69108762/187079131-5bb6834e-b267-4cc3-83b4-18d4879bb3c8.png">

```python
#date formatting

netflix_data['date_added'] = pd.to_datetime(netflix_data['date_added'])
netflix_data.head()
```
<img width="980" alt="Screenshot 2022-08-28 at 8 58 24 PM" src="https://user-images.githubusercontent.com/69108762/187081925-2bbb7b48-6967-4ab6-978b-3f01a9755730.png">

```python
#Adding month added field in month name format to the dataset

netflix_data['month_added'] = netflix_data['date_added'].dt.strftime('%B')
netflix_data.head()
```
<img width="975" alt="Screenshot 2022-08-28 at 9 00 06 PM" src="https://user-images.githubusercontent.com/69108762/187081975-00901a55-f129-4b5e-b8c1-b96127d5eeb7.png">

```python
#Changing duration field to numeric format if it is a Movie

netflix_data['duration'] = netflix_data['duration'].str.replace(' min', '')
```
```python
#Spliting duration to two columns for tv shows and movies

netflix_data['duration_movies'] = netflix_data['duration'].str.split('').str[0]
netflix_data['duration_tv'] = netflix_data['duration']

#Now Removing the duration Column

netflix_data.drop('duration', axis = 1, inplace = True)
netflix_data.head()
```
```python
netflix_data['listed_in'] = netflix_data['listed_in'].str.replace(' ','')
```
```python
#Replacing the empty cells with NULL

netflix_data.fillna('NULL', inplace = True)
```
```python
netflix_data.to_csv('netflix_data_updated.csv', index = False)
```
## 🚀 About Me
I'm currently a student and a learning data analyst.


## 🛠 Skills
Python | SQL | Data Visualization | MATLAB | Linear Algebra | Excel


## 🔗 Links

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aniket06/)


