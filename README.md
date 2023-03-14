# FIFA21DataAnalysisProject
The following shows the steps taken in cleaning the data in the Excel file.

Opened a blank workbook.
Went to Data tab and in the Get and Transform Data panel selected From Text/CSV. Selected the csv file and under the encoding/File Origin selected 65001: Unicode (UTF-8) and finish the process.
Made a copy of the original data and named it FIFA21_cleaned_data.xlsx.
Resized columns for better visibility.
Format as table; aids in looking for blanks, misspellings.
Froze top row for better reference.
Replaced blanks in the loan date end with “N/A” and hits with 0.
Aligned the data in hits to the right.
Found and replaced all the “K” with “000” to change the number format to number.
Created a new column to the right of each of the three columns.
Sorted value from smallest to largest. Found cells that contain “M” and insert the formula =D2*1000000 on the adjacent empty cell to the right with the relative cell reference based on the corresponding cell to the left. Autofilled the formula cell to the bottom where the last cell with “M”. Selected all the cells in that column that contain “M” and open Find and Replace. In the find box, entered “M” without the quotes and in the replace with box left it blank. In the search option, selected “By Column” and replaced all. Then copied the results of the formula to the original cells immediately adjacent to their left by pasting values. The empty column was then deleted.
The above procedure was repeated for the wage and release clause columns.
Changed the number format of the three columns in step 6 to Euro currency.
No duplicate records found.
Split the weight and height columns into two to represent the former in kg and lbs and the latter in m and ft as they are inconsistent. Used the CONVERT function to CONVERT lbs to kg and vice versa. 
Created a temp column to the right of Contract and used the SUBSTITUTE function to SUBSTITUTE “~” with “-“. Copied the results and pasted values onto the Contract column. Then deleted the temp column.
Used the SUM function to check IF the attribute categories were adding up correctly i.e.
    a.	Attacking: crossing, finishing, heading accuracy, short passing, volleys
    b.	Skill: dribbling, curve, FK accuracy, long passing, ball control
    c.	Movement: acceleration, sprint speed, agility, reactions, balance
    d.	Power: shot power, jumping, stamina, strength, long shots
    e.	Mentality: aggression, interceptions, positioning, vision, penalties, composure
    f.	Defending: marking, standing tackle, sliding tackle
    g.	Goalkeeping: GK diving, GK handling, GK kicking, GK positioning, GK reflexes
    h.	Total stats: SUM of all of the above
All but mentality was adding up. It did not include composure stats which were also missing in the total stats. This was corrected.
Used the SUM function to add up the base stats (PAC, SHO, PAS, DRI, DEF, PHY, HITS) and compare with the base stats column using the IF function. All apart from Michael Gurski ID 104900 were correct. This one was missing hits which was corrected.
Removed the whitespace in the club column entries using the TRIM and CLEAN functions.
Cleared the “1.” In the club names in the Club column using Find and Replace.
