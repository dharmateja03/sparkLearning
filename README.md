# sparkLearning
from pyspark.sql.functions import avg, sum, count

df.groupBy("Age").agg(
    avg("Salary").alias("avg_salary"),
    sum("Salary").alias("total_salary"),
    count("Salary").alias("count")
).show()

df.sort("column_name")  # Default: Ascending order
df.sort(df.column_name.desc())  # Sorting in descending order
df.sort("column1", "column2")  # Sort by multiple columns
df.sort(df["column1"].desc(), df["column2"].asc())  # Custom ordering


orderBY is fatster than sort
In PySpark, DataFrame transformations (like adding a new column) are not done in-place. Every transformation returns a new DataFrame, and the original DataFrame remains unchanged.

So, when you add a new column with .withColumn(), you need to assign it to a new variable (or reassign it to the same variable if you want to overwrite it).
