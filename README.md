# VBA

- The whole process has three stages: defining variables, copying and pasting the 2 columns dataset into a new workbook and filling in the middle column of the new workbook. For every step in the way, I am just mimicking how one can do the same thing manually.
- Usually the user will start with the selection of a cell by clicking one of the columns in the first row. The first row consist of a company name with the stock ticker on the right. Each pair of 2 columns is separated by a blank column. I will use that as a reference point and store the cell reference using thisworkbook dot activesheet dot range, bracket, activecell.address. I will assign this syntax to a variable called company name which is also our reference point as well.
- Then, I will create a new workbook and fill in the column headers for the 1st three columns, namely the date, stock ticker and the price
- Moving on, I will copy paste the data set column by column. The tricky part here is to identify the first cell and the last cell of the dataset. Taking the date entry as an example, it is located at eight cells below the reference point. So, I will just write a syntax like co_name.offset(8,0).address to identify the starting point. I repeat the same syntax for locating the end point, which will be something like co_name.offset(8,0).End(xlDown).Address.
- I will repeat the same procedure for the stock data.
- Once we have filled in the first and third columns of the data set, I will need to fill in the middle column, which is our stock ticker. It is stored at the 1 cell on the right of the company name. The difficult part now becomes knowing exactly the no. of rows to be filled.
- I will use syntax like currentregion.rows.count to return the no. of rows that exist in the three columns and assign the same stock ticker using syntax like Range bracket B2 and the last column of the row
- Finally, we have everything ready and save the workbook as a csv file.
