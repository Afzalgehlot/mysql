### create databasse
```
create database institute_management
```

### use database

```
use institute_management
```

### STUDENT TABLE

```
create table student (
student_id INTEGER AUTO_INCREMENT PRIMARY KEY,
student_name varchar(60) NOT NULL , 
father_name varchar(60) NOT NULL,
mobile bigint DEFAULT '8619426228', 
email varchar(60) UNIQUE NOT NULL,
admissionDate DATE
);

```

### ADDRESS TABLE

```

create table address(		
address_id INTEGER AUTO_INCREMENT PRIMARY KEY,
sId INTEGER NOT NULL,
city VARCHAR(30) NOT NULL,
state VARCHAR(30)  DEFAULT 'rajasthan',
pincode INTEGER NOT NULL,
FOREIGN KEY address(sId) references student(student_id)	
); 

```


### EMPLOYEE TABLE

```

create table employee(	
employee_id INTEGER AUTO_INCREMENT PRIMARY KEY,
employee_name VARCHAR(50) NOT NULL,
employee_type INTEGER NOT NULL ,
email varchar(40) UNIQUE NOT NULL,
mobile BIGINT ,
FOREIGN KEY (employee_type) REFERENCES employee_type(employee_type_id)
);

```


### EMPLOYEE_TYPE TABLE

```

create table employee_type(
employee_type_id INTEGER AUTO_INCREMENT PRIMARY KEY,
employee_type VARCHAR(40) NOT NULL,
employee_add VARCHAR(40) NOT NULL
);

```

### COURSE TABLE

```

create table course(
course_id INTEGER AUTO_INCREMENT PRIMARY KEY,
course_name VARCHAR(40) NOT NULL,
course_fees INTEGER DEFAULT '3000' ,
startDate DATE NOT NULL,
endDate DATE NOT NULL,
timing TIME NOT NULL
);

```

### TEST TABLE

```

create table test (
test_id INTEGER AUTO_INCREMENT PRIMARY KEY,
test_name VARCHAR(40) NOT NULL ,
passing_marks INTEGER NOT NULL ,
total_marks INTEGER NOT NULL ,
test_date DATE NOT NULL 
);

```

### RESULT TABLE

```

create table result (
result_id INTEGER AUTO_INCREMENT PRIMARY KEY,
test_Id INTEGER NOT NULL,
stu_Id INTEGER NOT NULL ,
obtainedmarks INTEGER NOT NULL,
result ENUM('pass' , 'fail'),
FOREIGN KEY (stu_Id) references student(student_id),
FOREIGN KEY (test_Id) references test(test_id)
);

```

### FEES TABLE

```

 create table fees(
 fees_id INTEGER AUTO_INCREMENT PRIMARY KEY,
 student_id INTEGER NOT NULL,
 amount INTEGER NOT NULL ,
 FOREIGN KEY (student_Id) REFERENCES student(student_id)
 );

 ```

 ### student_course table

 ```

 create table  studentCourse(
 student_course_id INTEGER AUTO_INCREMENT PRIMARY KEY,
 student_id INTEGER NOT NULL ,
 course_id INTEGER NOT NULL,
 FOREIGN KEY (student_id) REFERENCES student(student_id),
 FOREIGN KEY (course_id) REFERENCES course(course_id)
 );

 ```


 ### salary table

 ```
 create table salary (
 salary_id INTEGER AUTO_INCREMENT PRIMARY KEY,
 employee_id INTEGER NOT NULL ,
 amount INTEGER NOT NULL,
 FOREIGN KEY (employee_id) REFERENCES employee(employee_id) 
 );

 ```
