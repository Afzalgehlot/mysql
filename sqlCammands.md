### student table
```
create table students (
    studentid int not null auto_increment,
    Name varchar(255) not null,
    FatherName varchar(255) not null,
    Mobile bigint not null,
    Email varchar(255) not null,
    Address varchar(155) not null,
    AdmissionDate date not null,
    primary key (studentid)
);
```

### Employee table
```
create table Employee (
   Employeeid int,
    name varchar(255),
    Employeetype varchar(255)
);
```

###  EmployeeType
```
create table `EmployeeType` (
`EmployeeTypeid` integer unsigned primary key not null auto_increment ,
`EmployeeType` varchar(155) not null
);
```

### course table
```
create table Course (
     Courseid int not null auto_increment,
    Name varchar(255) not null,
    Fees bigint not null,
    StartDate date not null,
    EndDate date not null ,
    Timing time not null,
    primary key (Courseid )
);
```

### test table
```
create table test (
       testid int not null auto_increment, 
    testname varchar(100) not null,
    passingmarks bigint not null,
    totalmarks bigint not null,
    testdate date,
    primary key (testid)
);
```

### result table
```
create table `Result`(
`Resultid` integer  not null auto_increment ,
`TotalMarks` integer not null,
`ObtainedMarks` integer not null,
`ResultPassAndFail` varchar(155) not null,
primary key (Resultid)
);
```

### studentCourse table

```
      create table `StudentCourse` (
`StudentCourseid`integer unsigned not null  ,
`Studentid` integer not null,
`Courseid` integer not null ,
primary key (Studentid,Courseid)
);
```

### Expense
```
create table `Expenses` (
`Expensesid`  integer unsigned primary key not null auto_increment ,
`Expense Details` varchar (155) not null,
`Amount` bigint not null,
`Date` date
);

```

### fees table

```
create table Fees (
	`FeesId` integer primary key auto_increment not null,
    `Amount` bigint not null,
    `Month` date not null,
    `studentid` integer,
    CONSTRAINT  f_k_studentid FOREIGN KEY (studentid)
	REFERENCES students(studentid)
	);
    
    ```
