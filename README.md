# GradeDashboard
Dashboard that I use in my day-to-day to track classroom performance

This dashboard was built in PowerBI to track classroom performance, and is meant to give a snapshot of the progress towards certain goals. It contains 3 components- slicers, visuals, and cards. 

The slicers are meant to enable scrutinizng specific parts of the student population. You can filter based on class period, grade level, and performance in the class. For example, you can filter based on students that are performing low in the formative category. 

There are two visuals- a stacked column chart and a gauge. The stacked column chart shiows the breakdown of columns based on each letter grade. This enables an overview of the general performance of the class-not just whether students are passing, but if they're excelling. And, going further, how much of them are excelling. The gauge shows the amount of students passing the class(getting at least a 60% grade). The target value is calculated using a measure with the formula 'Pass Target = CALCULATE((COUNTA(Grades[Student])*.8))' which means the target dynamically changes as the slicers are adjusted. This is to give quick reference for how many students in a given population group are passing the class. 

Tbe cards show the average grade, average formative grade(homework assignments), and average summative grade(projects, tests, essays, etc). This enables viewing how students are doing in general, while also viewing their performance in formatives and summatives sepparately. For example, a high formative average but low summative average indicates students are doing well on homework but doing poorly on tests. This likely means the skills being built by formative assignments are not relevant to summative assignments, indicating misalignment. 

The KPIs track the fail rate(how many students in the class have a grade below 60), and show the current fail rate as compared to Quarter 1, Quarter 2 Year over Year, and Quarter 1 Year over Year. 

The excel sheet stores the data, and most columns are calculated here for simplicity. For instance, the grade for formative scores is calculated using '=(B2:B181+C2:C181+D2:D181+E2:E181+F2:F181+G2:G181+H2:H181+I2:I181+J2:J181+K2:K181)/DSUM(Assignments!A1:D14,"Points",U1:U2)'. Then, the final grade is calculated using the formula '=(O2:O181*0.2)+(P2:P181*0.8)' in order to weight the two categories to match their weight in the gradebook. 
