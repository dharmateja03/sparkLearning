# sparkLearning
from pyspark.sql.functions import avg, sum, count

df.groupBy("Age").agg(
    avg("Salary").alias("avg_salary"),
    sum("Salary").alias("total_salary"),
    count("Salary").alias("count")
).show()
