# Video Game Sales Analysis
This analysis investigates a dataset about video game sales. Each observation is a unique title and contains data about that title's platform, publisher, and most importantly, sales.

## Cleaning the data
I conducted some preliminary data cleaning and exploration in python to make creating visualizations in Tableau smoother. For example:

#### Handling nulls

```python
plt.figure(figsize=(10,6))
sns.heatmap(raw_data.isnull(), cbar=False)
plt.title('Null Value Heatmap')
plt.show()
```
![Screenshot of null heatmap](https://github.com/digitoby/Video-Game-Sales-Analysis/blob/main/images/nullvalues.png)

I made a visualization with matplotlib and seaborn to identify null values with a heatmap. I then proceeded to delete the null values for a cleaner analysis in tableau.

#### Preliminary exploration

I often explore the data during preprocessing to get a better idea of its nature and come up with visualization ideas for tableau.

```python
sns.histplot(clean_data['Year'].dropna(), bins=30, kde=False)
plt.title("Distribution of Games by Release Year")
plt.show()
```
![Screenshot of games by year dist](https://github.com/digitoby/Video-Game-Sales-Analysis/blob/main/images/games_by_year.png)

Perfect for understanding the dataset better. Obviously the industry did not slow down after 2010 in terms of releasing games. This distribution tells us that we are working with games released mostly during the 2000s and 2010s.

```python
plt.figure(figsize=(12,6))
sns.countplot(y='Genre', data=clean_data, order=clean_data['Genre'].value_counts().index[:10])
plt.title('Top 10 Genres by Number of Games')
plt.show()
```
![Screenshot of sales by genre](https://github.com/digitoby/Video-Game-Sales-Analysis/blob/main/images/sales_by_genre.png)

Perfect for drafting ideas for Tableau visualizations. Illustrating genre distributions can help us understand what games perform the best but also which genres are the most competitive.

## Dashboarding in Tableau
This is the final dashboard:

![Screenshot of sales by genre](https://github.com/digitoby/Video-Game-Sales-Analysis/blob/main/images/vgsales_dash.png)

Final report:

Genre Performance:
The top-selling genres during the period analyzed were action, sports, and shooter titles. These categories consistently outperformed others in terms of global sales, highlighting player preference for fast-paced, competitive, and immersive gameplay experiences.

Regional Market Insights:
North America (NA) emerged as the largest market for video games, contributing the highest share of global sales compared to Europe, Japan, and other regions. This emphasizes the importance of the North American market for developers and publishers seeking strong commercial performance.

Platform Dominance:
The Wii platform dominated sales across this time frame. Nintendo’s success with the Wii underscores the impact of innovative hardware and broad market appeal, particularly in attracting casual gamers and family audiences.
