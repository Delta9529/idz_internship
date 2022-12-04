# idz_internship
Internship task

Case table : 

id	case no	subject	created date	owner name
500DMS	12	xyz	datetime	zima
500TMS	13	abc	datetime	elka
Case Log: 

Case_c	proxy	case no	created by	Start_Date__c	Office__c	Queue_Name	Status	Come Back2[calculated]
asvsaj	500DMS	12	 	10/28/2022 9:06	Monterrey	Client Service 	In Progress	 
asbsat	500DMS	12	 	10/26/2022 1:33	Monterrey	Client Service 	In Progress	 
sacbsn	500DMS	12	 	10/25/2022 6:23	Monterrey	Client Service 	In Progress	 
safghj	500DMS	12	 	10/23/2022 22:54	Monterrey	Client Service 	In Progress	 
sdacasa	500DMS	12	 	10/26/2022 22:58	New York	Client Service 	In Progress	 
ssasaccsa	500DMS	12	 	10/26/2022 20:09	New York	Client Service 	In Progress	 
scsZXxz	500DMS	12	 	10/22/2022 0:13	Manila	Client Service 	New	 
xzccac	500DMS	12	 	10/26/2022 20:20	Monterrey	DCS - Data and series team	Escalated	Yes
czxxzcxz	500DMS	12	 	10/26/2022 18:27	Monterrey	DCS - Data and series team	Escalated	Yes
zxxz hgg	500DMS	12	 	10/25/2022 21:12	Manila	DCS - Data and series team	Escalated	Yes
xzxczxcsd	500DMS	12	 	10/26/2022 19:33	Monterrey	DCS - Data and series team	Escalated	Yes
xzxzxc	500DMS	12	 	10/26/2022 3:17	New York	Client Service	Escalated	 
zxxzxzxz	500DMS	12	 	10/27/2022 3:00	Budapest	DCS - Data and mani team	Escalated	Yes
zxxzcxzc	500DMS	12	 	10/26/2022 20:23	Monterrey	DCS - Data and mani team	Escalated	Yes
xzxzcxz	500DMS	12	 	10/24/2022 21:12	Manila	DCS - Data and mani team	Escalated	Yes
xzxzczx	500DMS	12	 	10/27/2022 8:22	Budapest	DCS - Data and mani team	Escalated	Yes
zxcxzc	500DMS	12	 	11/11/2022 23:17	Monterrey	DCS - Data and mani team	Escalated	Yes
So the case and case log are connect by 'Case'[ID] and 'Case Log'[Proxy] column by one to many. I want to get the case comeback for each case when it came to the department DCS and status not 'escalated' or 'assigned' or few more values . so i created the calculated column. now when i use the matrix or table filter 

Case owner	no of cases	count of comeback
zima	1	9
It doesn't skips the first 'yes'. i don't know why. for count of comeback i use

Count of Come_Back_2 = if((COUNTA('Case Log'[Come Back])-1)<=0,BLANK(),(COUNTA('Case Log'[Come Back])-1))
 So all in all i get the count of comeback value but when i put it in table w.r.t the case owner it just substracts (1) from the whole count of comebacks. so if i have 2 cases for one owner and 7 comebacks for case1 and 6 for case 2 it gives me total count as 12 i.e 13 - 1. but i need is (7-1) + (6-1) i.e 11

Hope it is clear. Thanks for your time again.
