types of login - candidate < teachers < admin

online exam system 
tag line -> "Get exam-ready with concepts, questions and study notes as per the latest pattern"

1--Admin Module--------------------
Teachers -crud

----------------------------------------------------------
2--Teacher module-------------------
	1. Create Exam - delete, modify, delete -crud
		fix subjects for exams
	candidate - crud
	questions - crud large database -> link exams to questions/subjects
	subjects  - crud 
	marks - crud (autocalculated/optional)

----------------------------------------------------------
3--candidate module-----------------

1. page - exam start page
	question display and answer submision
	time left
	mark for review & clear response 
	save and next 
	question pallete - colours - green(attempted), purple(review), red(not attempted)
	SUBMISION 

2. Exam result page
	rank, score, question wise details

3. List of exams

4. all previous exams results

5. Leaderboard 

redux/apicall

USERS		USER_DETAILS		QUESTIONS		SUBJECTS		TEACHERS		EXAMS	EXAM_QUESTIONS
userid		userid				qs_id							userid			
username	gender				subject							subject			
name		address				question							
email		profilepic			answer1							
password	pincode				ans2							
status		contact				ans3							
mobile		city				ans4							
usertype	country				ans5							
			college				correctanswer							
			company				maxmarks							
			age					negativemarks							
			course				difficultylevel							
			gradyear									
			accountdate									
			lastdate									


--------------------MySQL----------------------------------------------
-- CREATE SCHEMA nstest; -- -- -> db creation

-- --  CREATE TABLE users(name varchar(20), email varchar(50), mobile bigint); -- -> table creation

-- -- INSERT INTO users (name, email, mobile) VALUES ('ruchi', 'test@test.com', 1445);
-- -- SELECT name, email, mobile FROM users

-- CREATE TABLE products (productid varchar(20), name varchar(50), price int, description VARCHAR(100), category VARCHAR(20));
-- INSERT INTO products (productid, name, price, description, category) VALUES ('id002', 'shirt', 300, 'formalwear', 'man');
-- SELECT * FROM nstest.products;

-- SELECT * FROM products; 
-- SELECT name FROM products;
-- SELECT price FROM products;

-- INSERT INTO products () VALUES ();
-- SELECT * FROM products WHERE name = 'ruchi';


-- SELECT * FROM products ORDER BY name;
-------------------------------------------------
28-07-2022

CREATE TABLE users(userid varchar(), username varchar(),  name varchar(), email varchar(), password varchar(), status boolean (##--DEFAULT) false, mobile bigint, usertype varchar());
## ALTER TABLE users MODIFY COLUMN status boolean DEFAULT false;
-- change default values

INSERT INTO users (userid, username, name, email, mobile, password, status, usertype) VALUES ('id0622', 'testusername', 'fullname', 'testtest@test.com', 12323424  'pass123pass',  false,  123);  
INSERT INTO users (userid, username, name1, email, userpassword, userstatus, mobile_number, user_type) VALUES ('id0622', 'testusername', 'fullname', 'testtest@test.com', 'pass123pass', false,7889552252,'1'); 
INSERT INTO USERS ( userid , username , name_of_user , email , user_password , user_status , mobile_number , user_type ) VALUES ( '01', 'rohitbahuguna', 'Rohit Bahuguna', 'rohitbahuguna@gmail.com', 'df33fd3fd2f1d', 'false', '1025214524', 'student' ) 
INSERT INTO users (userid, username, name, email, mobile, password, status, usertype) VALUES ('id099', 'anurag1', 'Anurag', 'testtest@test.com', 'pass123', false, 1); 
INSERT INTO users (userid, username, name1, email, userpassword, userstatus, mobile_number, user_type) VALUES ('id045', 'usernamerahul', 'fullname', 'test@test.com', 'pass045pass', false,7823242567,'1'); 
INSERT INTO users (userid, username, name, email, password, status, mobile, usertype) VALUES ('id051', 'mumtaj21', 'mumtaj', 'mumtaj@test.com', 'Mumtaj@pass', 'true', '8877564275', '1'); 

ALTER TABLE users MODIFY COLUMN STATUS boolean;

required
index
unique
default

add (--new entry)
	ALTER TABLE users ADD test varchar(50);
drop(delete) 
	ALTER TABLE users DROP COLUMN test;
-----------------------------------------------------------
29-07-2022

-- CREATE TABLE online_exam.user_details (userid varchar (20), gender varchar (20), address varchar (80), profilepic BLOB, pincode bigint, contact bigint, city varchar (50), country varchar(50), college varchar (50), company varchar (80), age int, course varchar (50), graduation_year int, account_creation_date int, last_active_date int );
-- SELECT * FROM online_exam.user_details;
INSERT INTO online_exam.user_details (userid, gender,  address, profilepic, pincode, contact, city, country, college, company, age, course,  graduation_year,  account_creation_date, last_active_date)VALUES ('ID0622', 'female', 'city Itarsi, District Narmadapuram, State M.P.', '/home/ruchi/Desktop/student.png', 461111, '32446454', 'Itarsi', 'India', 'M.G.M. college', 'xyz', 20, 'BA', 2023, 2907, 2907);
-- https://freesvg.org/img/1555073263.png;


INSERT INTO user_details (userid, gender,  address, profilepic, pincode, contact, city, country, college, company, age, course,  gradyear,  accountdate, lastlogin) VALUES ('id0622', 'female', 'city abcd, District zxy, State M.P.', 'https://freesvg.org/img/1555073263.png',  461111,  32446454,  'Bhopal',  'India', 'M.G.M. college', 'Newton School', 20, 'BA', 2023, 2022/07/29, 10:40);
-- https://freesvg.org/img/1555073263.png



#####imp
difference between truncate and delete and drop in sql
what is differnece between primary and unique key in sql

______________01-08-2022________________________

how to deploye project on heroku 

safe mode err in which delete and update not allowed
	--  to resolve that err use -> SET SQL_SAFE_UPDATES = 0;


UPDATE user_details SET address = 'MP' WHERE userid = 'id0622';

DELETE FROM user_details WHERE userid = 'id001';

TRUNCATE TABLE users; --> only entries will be deleted

ALTER TABLE users ADD PRIMARY KEY userid; --> not accept duplicate entries


--joins 
	select all those userids where gender is female
	and than select all those names where gender is female

	tbl1 = users			name(fields)
	tbl2 = user_details		gender(fields)

	users.userid ===== user_details.userid


	SELECT users.name, user_details.gender FROM users INNER JOIN 
	user_details.userid = user_details.userid WHERE user_details.gender;
	

---------------------02-08-2022----------------

Adding typeScript
	npx create-react-app Goodluck --template typeScript

what is typescript and why we use it ??

file.ts

flow library --> to check errors
static typecheking (main advantages of ts )
es linting library( used to make you follow best coding practices) 







































# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).
