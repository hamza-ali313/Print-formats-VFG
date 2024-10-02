There is a logic of limited rows per page in stock Adjustment file so the flow of that logic is as follows

When there are 0 items:
If doc.items is empty, the first loop (for item in doc.items) will not run at all. As a result, row_count will remain 0, and the next loop (for i in range(row_count, 10)) will generate 10 blank rows to fill the table.

When there are fewer than 10 items:
If doc.items has fewer than 10 items (e.g., 6 items), the first loop will run 6 times, incrementing row_count to 6. Then the second loop will add the remaining 4 empty rows to make the total number of rows equal to 10.

When there are 10 or more items:
If there are exactly 10 or more items, the first loop will run until row_count reaches 10, and no blank rows will be added. If there are more than 10 items, only the first 10 items will be displayed because of the condition if row_count < 10.
