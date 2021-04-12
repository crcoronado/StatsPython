# StatsPython
Statistics Training for Python

*axis*
Vertical Axis = 0
Horizontal Axis = 1

*print with value*
print(f"Any Text {variables or calculations} other text")

*Read a file*
df = pandas.read_csv('filename')
d1 = np.loadtxt(filename, skiprows=1, delimiter=",")
d2 = np.genfromtxt(filename, delimiter=",", names=True, dtype=None)
with open("load_pickle.pickle", "rb") as f:
    d3 = pickle.load(f)

*Get number of rows and columns of a dataset*
df.shape

*Get info of Dataset, columns, types, nulls and entries*
df.info()

*Get the first n values of a Dataset, default is 5*
df.head(n)

*Fill empty values with "data"*
df = df.fillna('data')

*Save Specific columns from Dataset*
df2 = df[['column_1', 'column_2', ..., 'column_n']]

*See statistics information for numerical information*
d2.describe()

*Group the table by the column_1 Vs. all the other columns, and calculate the mean statistic*
df3.groupby("column_1").mean()

*Group in a table but with different statistic calculations per column*
df3.groupby("column_1").agg({"column_2":"stat_1", "column_3":"stat_2", ..., "column_n":"stat_m"})

*Group in a table but with different statistic calculations for all columns*
df3.groupby("column_1").agg(["stat_1", "stat_2", ..., "stat_m"])

*Get the information of a column with specific values*
value_one = df3.loc[df3["column_1"]==1]
print(value_one.shape) -> This will print the rows and "columns" with that value

*Save a file into CSV (usually a processed file), and removing the index*
df3.to_csv("clean_dataset.csv", index=False)

*Create an array of data with linspace*
variable = np.linspace(first_value, last_value, number_of_items)

*Plot line graphic, X (column 0) vs Y (column 1) or plot with points*
plt.plot(dataframe[:, 0], dataframe[:, 1])
plt.plot(X_Values, Y_Values, ".", label="Data_Label")
plt.legend()

*Plot scatter graphic, X (column 0) vs Y (column 1)*
plt.scatter(dataframe[:, 0], dataframe[:, 1])
plt.legend()
plt.show()

*Plot scatter graphic with colors and Data
plt.scatter(X_value, Y_value, s=2, label="Data_Label", color="#FFFFFF")*

*Plot histogram with n bins (section bars), adding density=True will show the Y axis as probability of the data, histtype="type_of_fill_type" {step, barstacked}, ln-> lineweigth, ls-> linestyle, alpha-> transparency*
plt.hist(data or [df1, df2, ...], bins=n, label="Data_Label", density=True, lw=m, ls=":", alpha)
plt.legend()
plt.ylabel("Y_label");

*Statistical Polynomial Values Calculation, and function based on X and Polynomial Formula*
p = np.polyfit(X_Values, Y_Values, degree=n)
ps = np.polyval(p, X_values)


