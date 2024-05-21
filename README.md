use Master
create database School
	Use School

	SP_helpdb School

	Create Table CourseMaster
		(
			CID			int 			Not Null Primary Key,
			CourseName	Varchar(40)		NOT NULL, 
			Category	Char(1)			NULL,	check(Category in('B', 'M', 'A')),
			Fee			Smallmoney		NOT NULL check (Fee > 0)
	)
	go
	
	Select * from CourseMaster

	Insert into CourseMaster values ( 1, 'Java', 'A', 10000)
	Insert into CourseMaster values ( 2, 'Python','B',20000)
	Insert into CourseMaster values ( 3, 'Java', 'M', 30000)
	Insert into CourseMaster values ( 4, 'Java', 'A', 40000)
	Insert into CourseMaster values ( 5, 'Java', 'B', 90000)
	Insert into CourseMaster values ( 6, 'Java', 'M', 50000)
	Insert into CourseMaster values ( 7, 'Java', 'A', 60000)
	Insert into CourseMaster values ( 8, 'Java', 'M', 70000)
	Insert into CourseMaster values ( 9, 'Java', 'B', 80000)
	Insert into CourseMaster values ( 10, 'Java', 'M', 8000)
	Insert into CourseMaster values ( 11, 'C++', 'B', 15000)
	Insert into CourseMaster values ( 12, 'Data Science', 'A', 45000)
	Insert into CourseMaster values ( 13, 'Web Development', 'M', 25000)
	Insert into CourseMaster values ( 14, 'Machine Learning', 'B', 35000)
	Insert into CourseMaster values ( 15, 'Cyber Security', 'A', 55000)
	Insert into CourseMaster values ( 16, 'Database Management', 'M', 20000)
	Insert into CourseMaster values ( 17, 'Cloud Computing', 'A', 30000)
	Insert into CourseMaster values ( 18, 'AI Fundamentals', 'M', 60000)
	Insert into CourseMaster values ( 19, 'Big Data', 'B', 40000)
	Insert into CourseMaster values ( 20, 'Mobile App Development', 'A', 50000)
	Insert into CourseMaster values ( 21, 'Software Testing', 'M', 10000)
	Insert into CourseMaster values ( 22, 'Networking', 'B', 25000)
	Insert into CourseMaster values ( 23, 'Blockchain Technology', 'A', 70000)
	Insert into CourseMaster values ( 24, 'Game Development', 'M', 45000)
	Insert into CourseMaster values ( 25, 'IoT', 'B', 35000)
	Insert into CourseMaster values ( 26, 'DevOps', 'A', 40000)
	Insert into CourseMaster values ( 27, 'Agile Project Management', 'M', 30000)
	Insert into CourseMaster values ( 28, 'Full Stack Development', 'B', 55000)
	Insert into CourseMaster values ( 29, 'UX/UI Design', 'A', 15000)
	Insert into CourseMaster values ( 30, 'Robotics', 'M', 50000)


	Use School

	Create table StudentMaster
	(
		SID				Tinyint		Primary Key,
		StudentName		Varchar(40)	NOT NULL,
		Origin			Char(1)		NOT NULL	 check(Origin in ('L','F')),
		Type			Char(1)		NOT NULL,	 check(Type in ('U','G')),
	)
	go

	Select * from StudentMaster


	Insert into StudentMaster values (1,'Geetha','L', 'G')
	Insert into StudentMaster values (2,'Ram','F', 'U')
	Insert into StudentMaster values (3,'Sreyanth','L', 'G')
	Insert into StudentMaster values (4,'Mini','F', 'U')
	Insert into StudentMaster values (5,'Siri','L', 'G')
	Insert into StudentMaster values (6,'Pihu','F', 'U')
	Insert into StudentMaster values (7,'Nish','L', 'G')
	Insert into StudentMaster values (8,'kiwi','F', 'U')
	Insert into StudentMaster values (9, 'Ravi', 'L', 'G')
	Insert into StudentMaster values (10, 'Anita', 'F', 'U')
	Insert into StudentMaster values (11, 'Kiran', 'L', 'G')
	Insert into StudentMaster values (12, 'Priya', 'F', 'U')
	Insert into StudentMaster values (13, 'Arjun', 'L', 'G')
	Insert into StudentMaster values (14, 'Rhea', 'F', 'U')
	Insert into StudentMaster values (15, 'Vikram', 'L', 'G')
	Insert into StudentMaster values (16, 'Anushka', 'F', 'U')
	Insert into StudentMaster values (17, 'Raj', 'L', 'G')
	Insert into StudentMaster values (18, 'Sneha', 'F', 'U')
	Insert into StudentMaster values (19, 'Rohit', 'L', 'G')
	Insert into StudentMaster values (20, 'Aisha', 'F', 'U')
	Insert into StudentMaster values (21, 'Dhruv', 'L', 'G')
	Insert into StudentMaster values (22, 'Kavya', 'F', 'U')
	Insert into StudentMaster values (23, 'Sam', 'L', 'G')
	Insert into StudentMaster values (24, 'Nina', 'F', 'U')
	Insert into StudentMaster values (25, 'Aryan', 'L', 'G')
	Insert into StudentMaster values (26, 'Zara', 'F', 'U')
	Insert into StudentMaster values (27, 'Neel', 'L', 'G')
	Insert into StudentMaster values (28, 'Tara', 'F', 'U')
	Insert into StudentMaster values (29, 'Dev', 'L', 'G')
	Insert into StudentMaster values (30, 'Maya', 'F', 'U')

	Select * from StudentMaster


	Create table EnrollmentMaster
	(
		CID		Int			NOT NULL	Foreign Key References CourseMaster(CID),
		SID		Tinyint		NOT NULL	Foreign Key References StudentMaster(SID),
		DOE		DateTime	NOT NULL,
		FWF 	Bit			NOT NULL,
		Grade	Char(1)		Null, check (Grade in ('o','A','B','C')),
)
	go

	Select * from EnrollmentMaster

	Insert into EnrollmentMaster values (1, 1,'2022/06/05', 0, 'o')
	Insert into EnrollmentMaster values (2, 2,'2021/06/06', 1, 'A')
	Insert into EnrollmentMaster values (3, 3,'2020/07/06', 0, 'B')
	Insert into EnrollmentMaster values (4, 4,'2022/05/07', 0, 'C')
	Insert into EnrollmentMaster values (5, 5,'2023/03/07', 1, 'o')
	Insert into EnrollmentMaster values (6, 6,'2024/02/07', 0, 'A')
	Insert into EnrollmentMaster values (7, 7,'2024/01/08', 1, 'B')
	Insert into EnrollmentMaster values (8, 8,'2023/09/05', 0, 'C')
	Insert into EnrollmentMaster values (1, 9, '2022/08/15', 0, 'o')
	Insert into EnrollmentMaster values (2, 10, '2021/07/20', 1, 'A')
	Insert into EnrollmentMaster values (3, 11, '2020/11/25', 0, 'B')
	Insert into EnrollmentMaster values (4, 12, '2023/04/10', 1, 'C')
	Insert into EnrollmentMaster values (5, 13, '2023/05/18', 0, 'o')
	Insert into EnrollmentMaster values (6, 14, '2024/06/12', 1, 'A')
	Insert into EnrollmentMaster values (7, 15, '2023/07/19', 0, 'B')
	Insert into EnrollmentMaster values (8, 16, '2022/10/22', 1, 'C')
	Insert into EnrollmentMaster values (9, 17, '2021/09/14', 0, 'o')
	Insert into EnrollmentMaster values (10, 18, '2024/08/11', 1, 'A')
	Insert into EnrollmentMaster values (11, 19, '2023/11/05', 0, 'B')
	Insert into EnrollmentMaster values (12, 20, '2022/12/20', 1, 'C')
	Insert into EnrollmentMaster values (13, 21, '2021/03/10', 0, 'o')
	Insert into EnrollmentMaster values (14, 22, '2024/05/25', 1, 'A')
	Insert into EnrollmentMaster values (15, 23, '2023/06/15', 0, 'B')
	Insert into EnrollmentMaster values (16, 24, '2022/07/09', 1, 'C')
	Insert into EnrollmentMaster values (17, 25, '2021/02/20', 0, 'o')
	Insert into EnrollmentMaster values (18, 26, '2024/01/05', 1, 'A')
	Insert into EnrollmentMaster values (19, 27, '2023/09/11', 0, 'B')
	Insert into EnrollmentMaster values (20, 28, '2022/11/18', 1, 'C')
	Insert into EnrollmentMaster values (21, 29, '2021/08/22', 0, 'o')
	Insert into EnrollmentMaster values (22, 30, '2024/02/14', 1, 'A')


	Select * from EnrollmentMaster



Select * from StudentMaster
Select * from EnrollmentMaster
Select * from CourseMaster
-- 2.	List the names of the students who have not enrolled for Java course.
	Select StudentName, CourseName
	from 
	StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
	join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
	where  CourseName not in ('Java')

	Select * from StudentMaster
	Select * from EnrollmentMaster
	Select * from CourseMaster
--1.	List the course wise total no. of Students enrolled. Provide the information 
--only for students of foreign origin and only if the total exceeds 1.
	select CourseName, count(*) as [Number of Students] from 
	CourseMaster join EnrollmentMaster on EnrollmentMaster.CID = CourseMaster.CID
	join StudentMaster on StudentMaster.SID = EnrollmentMaster.SID
	where origin = 'F'	 
	group by CourseName
	having count(*)>1

--List the name of the advanced course where the enrollment by foreign students is the highest
 	

	select top 1 CourseName, count(*) as [Number of Students] from 
	CourseMaster join EnrollmentMaster on EnrollmentMaster.CID = CourseMaster.CID
	join StudentMaster on StudentMaster.SID = EnrollmentMaster.SID
	where origin = 'F'	AND Category = 'A'
	group by CourseName
	order by count(*) Desc

		
--4.	List the names of the students who have enrolled for at least one basic course 
--in the current month.

		Select StudentName, DOE, datediff(MM, DOE, GETDATE()) as CurrentMonth
		from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
		join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
		where category in ('B') AND datediff(MM, DOE, GETDATE()) = 0
		group by StudentName, DOE


--5.	List the names of the Undergraduate, local students 
--who have got a “C” grade in any basic course.
		Select StudentName, Type, category, Grade, Origin
		from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
		join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
		where category in ('B') and Type = 'U' and Grade ='C' and origin = 'L'
		group by StudentName, Type, category, Grade, Origin






--6. List the names of the courses for which no student has 
--enrolled in the month of May 1989.
	Select CourseMaster.CourseName, DOE
	from CourseMaster left join  EnrollmentMaster on EnrollmentMaster.CID= CourseMaster.CID   
	and  Month(DOE) = '06' and YEAR(DOE) = 2023 
	where DOE is null
	
--13.	List the course name, total no. of enrollments in the current month.

	select CourseName, count(*) as [Total number of enrollment]
	from CourseMaster join EnrollmentMaster on CourseMaster.CID = EnrollmentMaster.CID
	where DATEDIFF(MM,DOE,getdate()) = 0
	group  by CourseName


--12.List the names of the foreign, undergraduate students who have got 
--grade ‘C’ in any basic course.
		Select StudentName, Type,  Grade, Origin
		from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
		where origin = 'F' AND Type = 'U' and Grade ='C'
		group by StudentName, Type, Grade, Origin

--11.	For those enrollments for which fee have been waived, provide the names of students 
--who have got ‘O’ grade.
		Select StudentName,  FWF, Grade
		from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
		join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
		where FWF = 1 and Grade = 'O'
--10.	List the names of the Courses enrolled by all (every) students.
	SELECT CourseName
	FROM CourseMaster
	JOIN EnrollmentMaster ON CourseMaster.CID = EnrollmentMaster.CID
	GROUP BY CourseName, CourseMaster.CID
	HAVING COUNT(DISTINCT EnrollmentMaster.SID) = (SELECT COUNT(*) FROM StudentMaster)
--9.	List the names of the Local students who have enrolled for exactly 2 basic courses. 	
		Select StudentName, origin,category, count (*) as [Number of Courses]
		from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
		join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
		where origin = 'L' and Category = 'B' 
		group by StudentName, origin,category
		having  count(*) =2


--8.List the most recent enrollment details with information on Student Name, 
--Course name and age of enrollment in days.
	
	Select  top 1 StudentName,  coursename, datediff(DAY,DOE, getdate() ) as EnrollAgeinDays
	from StudentMaster join EnrollmentMaster on StudentMaster.SID = EnrollmentMaster.SID
	join CourseMaster on EnrollmentMaster.CID = CourseMaster.CID
	order by datediff(DD, DOE, getdate()) ASC

--7.List name, Number of Enrollments and Popularity for all Courses. Popularity has to be 
--displayed as “High” if number of enrollments is higher than 50,  “Medium” if greater than 
--or equal to 20 and less than 50, and “Low” if the no.  Is less than 20.

	SELECT 
    CourseMaster.CourseName, 
    COUNT(EnrollmentMaster.SID) AS NumberOfEnrollments,
    CASE 
        WHEN COUNT(EnrollmentMaster.SID) > 50 THEN 'High'
        WHEN COUNT(EnrollmentMaster.SID) >= 20 THEN 'Medium'
        ELSE 'Low'
    END AS Popularity
FROM 
    CourseMaster
LEFT JOIN 
    EnrollmentMaster ON CourseMaster.CID = EnrollmentMaster.CID
GROUP BY 
    CourseMaster.CourseName;




		



	 
