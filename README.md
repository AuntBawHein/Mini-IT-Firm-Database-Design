Mini-IT-Firm-Database-Design
The scope of this project is to design A startup IT firm in Myanmar”. The tools used are white online sketch board => PROBLEM STATEMENT/IDEA:

1. To design and create ER diagram
2. Automate the query and store procedures.
3. Pencil and white paper to sketch my idea before implementation.
4. Finally, test run each table to make that ER diagrams are in place.
Below are the processes and questions that I’m going to create step by step. 
Step 1: I’m going to create and define lots of objects here. These are all my objects employee, canteen, computer, gym, security, bicycle, projector, bus and company. 
Step 2: I’m going to create lots of tables called employee_table, canteen_table, computer_table, gym_table, security_table, bicycle_table, projector_table, bus_table and company_table. 
These are all tables that I have created here. 
-- Creating employee_table 
CREATE TABLE employee_table ( it_employee_id INT PRIMARY KEY), 
it_employee_firstname VARCHAR(100), 
it_employee_lastname VARCHAR(100), 
it_employee_age INT, 
it_employee_gender VARCHAR(100), 
it_employee_nationality VARCHAR(100), 
it_employee_mobile_ph VARCHAR(100), 
it_employee_email VARCHAR(100), 
it_employee_address VARCHAR(100), 
it_employee_position_jobs VARCHAR(100), 
it_employee_working_experience INT, 
it_employee_salaries DECIMAL(10, 2) );

-- Creating canteen_table 
CREATE TABLE canteen_table (
	canteen_id INT PRIMARY KEY,
	canteen_name VARCHAR(100),
	canteen_food INT,
	canteen_drinks INT,
	canteen_seats INT,
	canteen_tables INT,
	canteen_elevator INT,
	canteen_stairs INT,
	canteen_doors INT,
	canteen_windows INT,
	canteen_staff INT,
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating computer_table
CREATE TABLE computer_table (
	it_computer_id INT PRIMARY KEY,
	it_computer_devices_brand VARCHAR(100),
	it_computer_devices_color VARCHAR(100),
	it_computer_devices_og_country VARCHAR(100),
	it_computer_devices_edition VARCHAR(100),
	it_computer_devices_ram VARCHAR(100),
	it_computer_devices_size VARCHAR(100),
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);



-- Creating gym_table 
CREATE TABLE gym_table (
	gym_id INT PRIMARY KEY,
	gym_name VARCHAR(100),
	gym_color VARCHAR(100),
	gym_equipment VARCHAR(100),
	gym_fan INT,
	gym_ac INT,
	gym_window INT,
	gym_fees_price DECIMAL(10, 2),
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating security_table 
CREATE TABLE security_table (
	it_security_id INT PRIMARY KEY,
	it_security_firstname VARCHAR(100),
	it_security_lastname VARCHAR(100),
	it_security_age INT,
	it_security_gender VARCHAR(100),
	it_security_mobile_ph VARCHAR(100),
	it_security_email VARCHAR(100),
	it_security_nationality VARCHAR(100),
	it_security_position_jobs VARCHAR(100),
	it_security_working_experience INT,
	it_security_salaries DECIMAL(10, 2),
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating bicycle_table 
CREATE TABLE bicycle_table (
	it_bicycle_id INT PRIMARY KEY,
	it_bicycle_brand VARCHAR(100),
	it_bicycle_color VARCHAR(100),
	it_bicycle_og_country VARCHAR(100),
	it_bicycle_owner_name VARCHAR(100),
	it_bicycle_speed_mph INT,
	it_bicycle_seats INT,
	it_bicycle_wheels INT,
	it_bicycle_price DECIMAL(10, 2),
	it_bicycle_manufactured_year INT,
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating projector_table 
CREATE TABLE projector_table (
	projector_id INT PRIMARY KEY,
	projector_brand VARCHAR(100),
	projector_color VARCHAR(100),
	projector_price DECIMAL(10, 2),
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating bus_table 
CREATE TABLE bus_table (
	bus_id INT PRIMARY KEY,
	bus_brand VARCHAR(100),
	bus_color VARCHAR(100),
	bus_seats INT,
	bus_ticket_price DECIMAL(10, 2),
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);

-- Creating company_table 
CREATE TABLE company_table (
	company_id INT PRIMARY KEY,
	company_name VARCHAR(100),
	company_director_name VARCHAR(100),
	company_type VARCHAR(100),
	company_cctv INT,
	company_car_parking_space INT,
	company_bicycle_parking_space INT,
	it_employee_id INT,
	FOREIGN KEY (it_employee_id) REFERENCES employee_table (it_employee_id)
);
Step 3: I’m going to insert data into employee_table, computer_table, gym_table, security_table, bicycle_table, projector_table, bus_table and company_table.

These are all data that I have insert here.

-- Inserting data into employee_table first INSERT INTO employee_table VALUES (11, 'John', 'Doe', 30, 'Male', 'Myanmar', '098-112-4567', 'john.doe@example.com', 'Maeku', 'Cloud Architect', 5, 50000.00), 
(15, 'Ma', 'Mu', 28, 'Female', 'Ethnic', '087-890-1134', 'ma_mu_@gmail.com', 'Maepa', 'Database Administrator', 3, 45000.00), (18, 'Yar', 'Koob', 35, 'Male', 'Myanmar', '089-123-5567', 'yar_koob_@gmail.com', 'Maesot', 
'Software Engineering', 8, 70000.00), (14, 'Ma', 'Than', 32, 'Female', 'Myanmar', '085-412-6789', 'ma_than_@gmail.com', 'Maeramat', 'Data Analyst', 4, 55000.00), (19, 'Yell', 'Soe', 40, 'Male', 'Myanmar', 
'092-137-5541', 'yell_soe_@gmail.com', 'Phop-phra', 'Cloud Engineering', 6, 60000.00);

-- Inserting data into computer_table INSERT INTO computer_table VALUES (23, 'Panasonic', 'Black', 'Japan', '2021 Edition', '32GB', '41 inches', 11), (21, 'HP', 'Gray', 'USA', '2022 Edition', '16GB', '17 inches', 15), 
(29, 'Lenovo', 'Gray', 'China', '2022 Edition', '12GB', '14 inches', 18), (27, 'Apple', 'Silver', 'USA', '2021 Edition', '16GB', '13 inches', 14), (22, 'Acer', 'Blue', 'Taiwan', '2023 Edition', '20GB', '15 inches', 19);

-- Inserting data into canteen_table INSERT INTO canteen_table VALUES (32, 'Mani canteen', 50, 30, 100, 20, 1, 2, 5, 10, 3, 11), (35, 'Two-in-one canteen', 40, 25, 80, 15, 1, 1, 4, 8, 2, 15), 
(39, 'Tee-Nee Maesot canteen', 60, 35, 120, 25, 2, 3, 7, 12, 4, 18), (36, 'U Gyi Soe canteen', 45, 28, 90, 18, 1, 2, 6, 11, 3, 14), (31, 'Boss canteen', 55, 32, 110, 22, 2, 2, 8, 15, 5, 19);

-- Inserting data into gym_table INSERT INTO gym_table VALUES (45, 'Fitness Center', 'White', 'Treadmill', 2, 5, 4, 30.00, 11), (47, 'Power Gym', 'Black', 'Rope Climbing', 3, 4, 3, 25.00, 15),
(44, 'Cardio Zone', 'Red', 'Cycling Machine', 2, 3, 2, 20.00, 18), (41, 'Tiger Fitness', 'Blue', 'Dumbbell', 4, 6, 5, 35.00, 14), (48, 'Wellness Club', 'Green', 'Yoga Mats', 1, 3, 2, 40.00, 19);

-- Inserting data into security_table INSERT INTO security_table VALUES (53, 'Saw', 'Christ', 35, 'Male', '091-519-0012', 'saw_christ_@gmail.com', 'Myanmar', 'Information Security Analyst', 8, 60000.00, 11),
(57, 'Kaw', 'Lay', 28, 'Female', '086-678-3345', 'kaw_lay_@gmail.com', 'Myanmar', 'Cloud Security Architect', 5, 55000.00, 15), (51, 'Htee', 'Moo', 40, 'Male', '085-613-2215', 'htee_moo_@gmail.com', 'Myanmar', 'IT Security Architect', 10, 70000.00, 18), (59, 'Oh', 'Zite', 32, 'Male', '082-456-1279', 'oh_zite_@gmail.com', 'Myanmar', 'Network Security Administrator', 6, 50000.00, 14), (55, 'Ma', 'Own', 30, 'Female', '08-615-3310', 'ma_own_@gmail.com', 'Myanmar', 'Cybercrime Investigator', 4, 45000.00, 19);

-- Inserting data into bicycle_table INSERT INTO bicycle_table VALUES (68, 'Giant', 'Black', 'Taiwan', 'Mya Shwe', 20, 1, 2, 800.00, 2020, 11), (66, 'Trek', 'Blue', 'USA', 'Ler Pwe', 18, 1, 2, 750.00, 2021, 15), 
(61, 'Cannondale', 'Red', 'USA', 'Daw Mu Yee', 22, 1, 2, 900.00, 2019, 18), (69, 'Specialized', 'White', 'USA', 'Zar Nar Bee', 16, 1, 2, 700.00, 2022, 14), (64, 'Scott', 'Yellow', 'Switzerland', 'San San Win', 
24, 1, 2, 950.00, 2023, 19);

-- Inserting data into projector_table INSERT INTO projector_table VALUES (77, 'Epson', 'White', 500.00, 11), (72, 'Sony', 'Black', 700.00, 15), (79, 'LG', 'Silver', 600.00, 18), (73, 'Panasonic', 'Gray', 550.00, 14), 
(71, 'Canon', 'Blue', 800.00, 19);

-- Inserting data into bus_table INSERT INTO bus_table VALUES (88, 'Mercedes', 'Blue', 30, 10.00, 11), (81, 'Volvo', 'Red', 40, 12.00, 15), (84, 'Toyota', 'Green', 35, 11.00, 18), (86, 'Ford', 'Yellow', 45, 14.00, 14), 
(85, 'Nissan', 'Black', 50, 15.00, 19);

-- Inserting data into company_table INSERT INTO company_table VALUES (1, 'Microsoft Company', 'Ma Own Kyi', 'Public Company', 1, 50, 20, 11), (2, 'IBM Company', 'Saw Bi Koh', 'Public', 1, 40, 15, 15), 
(3, 'Master Tech Company', 'Naw Mg Lay', 'Private Company', 1, 30, 10, 18), (4, 'Google Company', 'Naing Oo', 'Public Company ', 1, 20, 5, 14), (5, 'Facebook Company', 'Nu Nu Thin', 'Public Company ', 1, 60, 25, 19);

Questions

Why do we use LEFT JOIN statement here? = Because we want to make sure we see information from the left table (like the canteen_table) and also we can see the right table too.
Step 4: I want to find and join 2 information’s.

-- Joining information table using JOIN

-- 1. We want to find information from both the canteen and security tables. These are all codes.

SELECT canteen_table.canteen_id, canteen_table.canteen_name, canteen_table.canteen_food, canteen_table.canteen_seats,

security_table.it_security_id,
security_table.it_security_firstname,
security_table.it_security_age
-- We're looking in the canteen table FROM canteen_table 
-- We're matching it with information from the security table using an INNER LEFT JOIN. LEFT JOIN security_table ON canteen_table.it_employee_id = security_table.it_employee_id;

Questions 2. Why do we use RIGHT JOIN statement here? = Because We want to see information all computers, whether or not they are assigned to an employee. So, we use RIGHT JOIN to include all computers and match them 
with employee information if they are assigned.

-- 2. I want to find information from both the employee and computer tables here. These are all codes that I used.

SELECT employee_table.it_employee_id, employee_table.it_employee_firstname, employee_table.it_employee_lastname, employee_table.it_employee_age, employee_table.it_employee_gender, 
employee_table.it_employee_nationality, employee_table.it_employee_address, employee_table.it_employee_email, employee_table.it_employee_mobile_ph, employee_table.it_employee_position_jobs, 
employee_table.it_employee_working_experience, employee_table.it_employee_salaries,
computer_table.it_computer_id,
computer_table.it_computer_devices_brand,
computer_table.it_computer_devices_edition,
computer_table.it_computer_devices_color,
computer_table.it_computer_devices_og_country,
computer_table.it_computer_devices_ram,
computer_table.it_computer_devices_size
FROM employee_table -- We're matching it with information from the computer table using a RIGHT OUTER JOIN. RIGHT OUTER JOIN computer_table ON employee_table.it_employee_id = computer_table.it_employee_id;

Questions 3. Why do we have to create a table diagram? 
= Because it helps us see how different information is organized, making it easier to understand and work on our project. 

4. Why do we have to link the table?
= Because it helps us combine information from different parts of our project. When tables are linked, it's easier to find and use the data we need.

Step 5: I want to show the table diagram of all objects and entities here. it_myanmar_database_projects_digram drawio drawio
![it_myanmar_database_projects_digram drawio drawio](https://github.com/AuntBawHein/Mini-IT-Firm-Database-Design/assets/150255399/bca522c3-a00a-48fa-8c6e-2b4e21c9d049)

Step 6: I’m going to show you SQL It_myanmar_company_projects_database.
[IT_projects_database_company_projects_word.docx](https://github.com/AuntBawHein/Mini-IT-Firm-Database-Design/files/13694895/IT_projects_database_company_projects_word.docx)

