code: 
> num_var <-10.5 
> cat("1. Numeeric variable\n") 
1. Numeeric variable 
> cat("value:", num_var, "\n") 
value: 10.5  
> cat("type:", typeof(num_var), "\n\n") 
type: double  
>  
> int_var <-7L 
> cat("2.Integer variable\n") 
2.Integer variable 
> cat("value:", int_var, "\n") 
value: 7  
> cat("type:", typeof(int_var), "\n\n") 
type: integer  
>  
> char_var <-"Hello R!" 
> cat("3. Character variable") 
3. Character variable>  
> cat("3. Character variable\n") 
3. Character variable 
> cat("value:", char_var, "\n") 
value: Hello R!  
> cat("type:", typeof(char_var), "\n\n") 
type: character  
>  
> log_var<-TRUE 
> cat("3.Logical variable") 
3.Logical variable>  
> cat("3.Logical variable\n") 
3.Logical variable 
> cat("value:", log_var, "\n") 
value: TRUE  
> cat("type:", typeof(log_var), "\n\n") 
type: logical  
>  
> comp_var<-2+3i 
> cat("4.Complex variable\n") 
4.Complex variable 
> cat("value:", comp_var, "\n") 
value: 2+3i  
> cat("type:", typeof(comp_var), "\n\n") 
type: complex  
>  
> num_var<-10.99 
> int_converted<-as.integer(num_var2) 
Error: object 'num_var2' not found 
>  
> num_var2 <-10.99 
> int_converted <-as.integer(num_var2) 
> cat("7.convert numeric to integer\n") 
7.convert numeric to integer 
> cat("original numeric:", num_var2, "\n") 
original numeric: 10.99  
> cat("converted to integer:", int_converted, "\n\n") 
converted to integer: 10  
>  
>  
> list_example <-list(1, "hello", true, 3.14) 
Error: object 'true' not found 
> list_example <-list(1, "hello", TRUE, 3.14) 
> cat("11.data types in a list\n") 
11.data types in a list 
> cat("type:", typeof(list_example), "\n\n") 
type: list  
> cat("Each element can have a different types in a list!\n\n") 
Each element can have a different types in a list! 
interesting code facts: 
common ways used 
> int_var - integer variable 
>char_var - character variable etc. 
for inserting text 
>cat(“hello\n”) 
two types in general: 
1.) value 
2.) type 
Value  
>cat(“value:”, int_var, “\n”) 
Type 
>cat(“type:”, typeof(int_var),”\n\n”) 
Practical no.2 control structures and loops 
> #enter marks 
> marks<-as.numeric(readline(prompt="enter your marks:")) 
enter your marks:95 
> if (marks>=90) { 
+ grade<-"A" 
+ }else if(marks>=70){ 
+  
+  
+  
+  
+ grade<-"C" 
+ } else if(marks>=60) { 
+ grade<-"D" 
+ }else{ 
+ grade<-"F" 
+ } 
> #display grade 
> cat("Your grade is:",grade,"\n") 
Your grade is: A  
>  
>  
> #enter number 
> num<-as.numeric(readline(prompt="Enter your number:")) 
Enter your number:99 
> #check wheather odd or even 
> if(num%%2==0) { 
+ cat(num,"is even\n") 
+ }else{ 
+ cat(num,"is odd\n")} 
99 is odd 
> #enter number 
> num<-readline(prompt="enter a number:") 
enter a number:99 
> #check palindrome 
> is(num==paste(rev(strsplit(num,NULL) [[1]]), collapse="")) { 
Error: unexpected '{' in "is(num==paste(rev(strsplit(num,NULL) [[1]]), collapse="")) {" 
> if(num==paste(rev(strsplit(num,NULL) [[1]]), collapse="")) { 
+ cat(num,"is a palindrome\n") 
+ }else{ 
+ cat(num,"is not a palindrome\n") 
+ } 
99 is a palindrome 
>  
code facts: 
1.) palindrome (very imp) 
2.) word based 
#enter number 
number<-as.numeric(readline(prompt=”Enter your desired number:”))  
practical no.3 
working with data frames  
code: 
> name<-c("Jhon","Emma","Liam") 
> age<-c(25,30,22) 
> marks<-c(85,92,78) 
> #create a dataframe 
> students<-data.frame(Name=name,Age=age,Marks=marks) 
> #print the dataframe 
> print(students) 
Name Age Marks 
1 Jhon  25    85 
2 Emma  30    92 
3 Liam  22    78 
> #creating individual vectors 
> roll_no<_c(101,102,103,104) 
Error: unexpected symbol in "roll_no<_c" 
> roll_no<-c(101,102,103,104) 
> name<-c("Jhon","Emma","Liam","Chirag") 
> age<-c(21,20,22,19) 
> marks<-c(88,96,90,85) 
> #creating a dataframe 
> students<-data.frame(Rollno=roll_no,Name=name,Age=age,Marks=marks) 
> #print the dataframe 
> print("students dataframe:\n") 
[1] "students dataframe:\n" 
> print(students) 
Rollno   Name Age Marks 
1    101   Jhon  21    88 
2    102   Emma  20    96 
3    103   Liam  22    90 
4    104 Chirag  19    85 
>  
>  
> #accessing specific columns  
> print("Only names:") 
[1] "Only names:" 
> print(students$Name) 
[1] "Jhon"   "Emma"   "Liam"   "Chirag" 
>  
> #adding a new column  
> students$Grade<-c("A","B","C","D") 
>  
> #print updated dataframe 
> print(students) 
Rollno   Name Age Marks Grade 
1    101   Jhon  21    88     A 
2    102   Emma  20    96     B 
3    103   Liam  22    90     C 
4    104 Chirag  19    85     D 
> print("updated dataframe of students") 
[1] "updated dataframe of students" 
> print(students) 
Rollno   Name Age Marks Grade 
1    101   Jhon  21    88     A 
2    102   Emma  20    96     B 
3    103   Liam  22    90     C 
4    104 Chirag  19    85     D 
>  
code facts:  
>creating dataframes, using the “c” symbol at the end of an entry, after enter the 
details using a certain set of solidified commands like:- #print(dataframe name), 
#creating a dataframe so on and so forth, Naming the dataframe is also essential in 
adding the dataframe.  
practical no.4 
understanding data structures 
part of code: 
1.)creating list 
2.)creating matrices 
3.)creating factors 
code: 
> #a.creating list 
> my_list<-list(name="XYZ",age=20,score=c(85,90,88)) 
> print(my_list) 
$name 
[1] "XYZ" 
$age 
[1] 20 
$score 
[1] 85 90 88 
>  
> #b.creating matrices 
> my_matrix<-matrix(c(1,2,3,4,5,6),nrow=2,ncol=3) 
> print(my_matrix) 
[,1] [,2] [,3] 
[1,]    
1    3    5 
[2,]    2    4    6 
>  
> #ccreating factors(categorical data) 
> gender<-factor(c("Male","Female","Female","Male")) 
> print(gender) 
[1] Male   Female Female Male   
Levels: Female Male 
>  
practical no.7  
Transforming data  
library(tidyr) 
library(dplyr) 
data<-data.frame( 
Name=c("Alice","Bob"), 
Math=c(80,85), 
Science=c(85,88) 
) 
print("Original data:") 
print(data) 
long_data<-data%>% 
gather(key="Subject",value="Marks",Math,Science) 
print("Data after gather():") 
print(long_data) 
united_data<-data%>% 
unite(col = "Name_math",Name,Math,sep="-") 
print("Data after unite():") 
print(united_data) 
separated_data <- united_data%>% 
separate(col = "Name_math",into = c("Name","Math"), sep="-") 
print("Data after separated():") 
print(separated_data) 
practical no.6  
the tidyverse package 
#step1:install and load tidyverse package 
install.packages("tidyverse") 
library(tidyverse) 
#step2: Create a sample student data 
students<-tibble( 
Name=c("Anjali","Rahul","Priya","Aman","Sneha","Ravi"), 
Age=c(20,22,19,21,20,23), 
Gender=c("F","M","F","M","F","M") 
Marks=c(85,78,92,88,95,60) 
) 
#view original dataset 
print("original dataset:") 
print(students) 
#a.using select(): Select Name and Marks column 
selected_data<-students%>% 
select(Name,Marks) 
print("selected name and marks:") 
print(selected_data) 
#b.using filter(): filter students who scored above 85 
high_scores<-students%>% 
f
 ilter(marks>85) 
print("Students with marks above 85:") 
print(high_scores) 
#c.Using mutate():Add a columns 'result' as Pass\Fail 
students_with_results<-students%>% 
mutate(Results=ifelse(marks>=75,"Pass","Fail")) 
print("Data with result column:") 
print(students_with_results) 
#d.Using group_by() and summarise():Average marks by gender 
avg_marks_by_gender<-students%>% 
summarise(Average_Marks=mean(Marks)) 
print("Average marks by gender") 
print(avg_marks_by_gender) 
code facts: 
types used  
1.) tidyverse 
2.) tibble 
3.) select() 
4.) filter() 
5.) mutate() 
6.) group_by() and summarise() 
practical no.8  
ggplot in R language 
code: 
#create student dataset 
student_data<-data.frame( 
ID=1:5, 
name=c("aman","nikhil","lia","norman","mia"), 
age=c(20,25,22,21,24), 
gender=c("Male","Female","Male","Female","Male"), 
department=c(80,85,90,95,99)) 
#print dataset 
print(student_data) 
#load library 
library(ggplot2) 
#scatter plot with dark theme 
ggplot(student_data, aes(x=age, y=marks, color=gender)) + 
geom_point(size=3) + 
facet_wrap(~department) + 
labs( 
 
 
    title="students marks vs age", 
      x="age of students", 
      y="marks scored", 
      color="gender" 
       
  ) + 
   
  theme_dark() 
 
#load library 
library(ggplot2) 
#scatter plot with faces 
ggplot(data=iris, aes( x = Sepal.Length, y = Sepal.Width, color= Species)) + 
   
  #add scatter points 
  geom_point(size=3) + 
 
facet_wrap(~Species) + 
  labs( 
    title="Sepal length vs sepal width", 
    x="Sepal Length", 
    y="Sepal Width", 
    color="Flower Species" 
     
  ) + 
   
  theme_minimal()
