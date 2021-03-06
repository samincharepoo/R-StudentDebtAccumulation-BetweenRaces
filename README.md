# R-StudentDebtAccumulation-BetweenRaces

**Student Debt Accumulation Between Different Races and the Long Term Effects**


Student debt affects more than 40 million Americans in 2021. The burden of that debt varies across gender, location, demographic, and very strongly, race. There is a growing library of research which points to the apparent inequality in student debts held by students of color. This statistical analysis will look deeper into the difference in dept accumulation between Black, Hispanic and White Students as well as dive into how this debt could possibly effect other long term financial factors such as home ownership and average income.

The data set used here is the student_debt data set from TidyTuesday on GitHub showing average student debt amount in US dollars between White, Black and Hispanic students from the years 1989-2016. 

**Read in the data:**

student_debt <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-09/student_debt.csv')
home_owner <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-09/home_owner.csv')
race_wealth <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-02-09/race_wealth.csv')


**Clean Data:**

race_wealth_c<-na.omit(race_wealth)
race_wealth_clea<-race_wealth_c[!(race_wealth_c$race=="Non-White"),]
race_wealth_clea1<-race_wealth_clea[!(race_wealth_clea$year=="1963"),]
race_wealth_clean<-race_wealth_clea1[!(race_wealth_clea1$type=="Median"),]

HighestLowest<-race_wealth_clean[!(race_wealth_clean$race=="Hispanic"),]
highLow<-student_debt[!(student_debt$race=="White"),]
