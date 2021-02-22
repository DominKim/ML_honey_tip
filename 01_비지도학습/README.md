# ML_honey_tip


- sns.FacetGrid(....) : Initialize the matplotlib figure and FacetGrid object
- .map(func, ....) : func는 plt, sns의 그리고자 하는 그래프 지정
    - Apply a plotting function to each facet’s subset of the data.
``` python3
grid = sns.FacetGrid(tsne_df, hue = "targets", size = 8)
grid.map(plt.scatter, "x", "y").add_legend()
```