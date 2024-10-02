There is a logic of limited rows per page in stock Adjustment file so the flow of that logic is as follows

Detailed Flow of the Logic:

1.

When doc.items Has Fewer Than 10 Items:
Let's start with an example where doc.items has 6 items.

First Loop (for item in doc.items):

For each item in doc.items, a row is printed in the table.
The value of row_count starts at 0, and each time a row is printed, it increments by 1.
After printing 6 items, row_count becomes 6.
At this point, there are only 6 rows printed, and row_count = 6.

Second Loop (for i in range(row_count, 10)):

This loop generates the remaining rows to fill up to 10 rows in the table.
In this case, since row_count is 6, the range will be range(6, 10), meaning it will run 4 times (for i = 6, 7, 8, 9).
As a result, 4 blank rows are added to make a total of 10 rows.

2. 

When doc.items Has Exactly 10 Items:
First Loop (for item in doc.items):

The loop runs through each item in doc.items and prints a row for each one.
After printing all 10 items, row_count becomes 10.
Second Loop (for i in range(row_count, 10)):

Here’s the key part: Since row_count = 10, the second loop will use the range range(10, 10).
In Python (and Jinja), range(10, 10) means the loop does not run at all because the start and end of the range are the same (10), and there are no values in between.
As a result, no blank rows are added because the range doesn't provide any iterations.

3 .

When doc.items Has More Than 10 Items:
First Loop (for item in doc.items):
The loop will run for each item, but it’s controlled by the condition if row_count < 10.
As soon as row_count reaches 10, the loop stops, meaning only the first 10 items are printed.
Second Loop (for i in range(row_count, 10)):
Similar to the previous case, since row_count = 10, the range becomes range(10, 10), which doesn't run.
No blank rows are added because the table already has 10 rows of data.
