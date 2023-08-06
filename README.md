# 30 days of pandas
This repository contains solutions to the [30 Days of Pandas](https://leetcode.com/studyplan/30-days-of-pandas/) study plan on Leetcode.

[1. Big Countries](https://leetcode.com/problems/big-countries)
```py
def big_countries(world: pd.DataFrame) -> pd.DataFrame:
    df = world[(world['area'] >= 3000000) | (world['population'] >= 25000000)]
    return df[['name', 'population', 'area']]
```
[2. Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/)
```py
def find_products(products: pd.DataFrame) -> pd.DataFrame:
    df = products[(products['low_fats'] == 'Y') & (products['recyclable'] == 'Y')]
    return df[['product_id']]
```
[3. Customers Who Never Order](https://leetcode.com/problems/customers-who-never-order/)
```py
def find_customers(customers: pd.DataFrame, orders: pd.DataFrame) -> pd.DataFrame:
    df = customers.merge(orders, how='left', left_on='id', right_on='customerId')
    df = df[df['customerId'].isna()]
    df = df[['name']].rename(columns={'name': 'Customers'})
    return df
```

[4. Article Views I](https://leetcode.com/problems/article-views-i/)
```py
def article_views(views: pd.DataFrame) -> pd.DataFrame:
    df = views[views['author_id'] == views['viewer_id']]
    df = df['author_id'].unique()
    df = sorted(df)
    result_df = pd.DataFrame({'id': df})
    return result_df
```

5. 