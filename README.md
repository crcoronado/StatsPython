# StatsPython
Statistics Training for Python

*axis*
Vertical Axis = 0
Horizontal Axis = 1

*Read a file*
df = pandas.read_csv('filename')
d1 = np.loadtxt(filename, skiprows=1, delimiter=",")
d2 = np.genfromtxt(filename, delimiter=",", names=True, dtype=None)
with open("load_pickle.pickle", "rb") as f:
    d3 = pickle.load(f)
    
*Get info of Dataset, columns, types, nulls and entries*
df.info()

*Get the first n values of a Dataset, default is 5*
df.head(n)

*Fill empty values with "data"*
df = df.fillna('data')

*Save Specific columns from Dataset*
df2 = df[['column_1', 'column_2', ..., 'column_n']]

*#See statistics information for numerical information*
d2.describe()

#Group the table by the column_1 Vs. all the other columns, and calculate the mean statistic
df3.groupby("column_1").mean()

#Group in a table but with different statistic calculations per column
df3.groupby("column_1").agg({"column_2":"stat_1", "column_3":"stat_2", ..., "column_n":"stat_m"})

#Group in a table but with different statistic calculations for all columns
df3.groupby("column_1").agg(["stat_1", "stat_2", ..., "stat_m"])

#Get the information of a column with specific values
value_one = df3.loc[df3["column_1"]==1]
print(value_one.shape) -> This will print the rows and "columns" with that value

#Save a file into CSV (usually a processed file), and removing the index
df3.to_csv("clean_dataset.csv", index=False)