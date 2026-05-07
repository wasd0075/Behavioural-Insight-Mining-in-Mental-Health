In order the achieve an automated flow of the pipeline below are 3 simple steps to follow:

1. Open the Code in jupyter notebook in Google Colab.
2. Connect to the Kernel.
3. Under the 'Runtime' tab click on Run All.

This will run the entire code which will include getting the data from the Azure Blob using Spark, pre processing it and then storing in PostgreSQL using Spark's JDBC, retrieving it again from SQL storage (PostgreSQL) and visualizing it.