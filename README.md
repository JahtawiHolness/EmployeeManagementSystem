# EmployeeManagementSystem

Vulnerabilities
1. Broken Access Control:
•	Threat:
•	Unauthorized users gaining access to sensitive employee information or performing actions meant for privileged users.
•	Potential Scenarios:
•	Accessing employee records without proper authentication.
•	Modifying or deleting employee records without proper authorization.
•	Risk Mitigation:
•	Implement proper authentication and authorization mechanisms.
•	Use role-based access control (RBAC) to restrict access based on user roles.
•	Regularly review and test access controls to ensure their effectiveness.
2. Password Hashing:
•	Threat:
•	Storing passwords in plain text or using weak hashing algorithms, making it easier for attackers to compromise user accounts.
•	Potential Scenarios:
•	Obtaining plaintext passwords from the database and using rainbow table attacks.
•	Exploiting weaknesses in password recovery mechanisms.
•	Risk Mitigation:
•	Use a strong and adaptive hashing algorithm (e.g., bcrypt or Argon2).
•	Implement salting to protect against rainbow table attacks.
•	Regularly update password hashing mechanisms as security best practices evolve.
3. SQL Injection:
•	Threat:
•	Malicious users injecting SQL queries, leading to unauthorized access or manipulation of the database.
•	Potential Scenarios:
•	Submitting malicious input to user input fields that are not properly validated.
•	Crafting SQL queries to manipulate or extract data.
•	Risk Mitigation:
•	Use parameterized queries or prepared statements to handle user input.
•	Implement input validation to ensure that only expected data is accepted.
•	Regularly conduct security audits and code reviews to identify and fix potential injection points.
Steps to Exploit Each Vulnerability
1. Exploiting Broken Access Control vulnerability:
•	Steps:
1.	Log in with user level access.
2.	Gain unrestricted access to access admin level content and privileges.
2. Exploiting Password Hashing vulnerability:
•	Steps:
1.	Gain access to database file
2.	View un-hashed user account passwords
3. Exploiting SQL Injection vulnerability:
•	Steps:
1.	Attempt to obtain login access as an unidentified/ unrecognized account with “user field” as: admin'; select username from employees where username = 'admin OR '1'='1 
2.	Attempt to obtain login access as an unidentified/ unrecognized account with “user” field and “password” field as: unknown' OR '1'='1
3.	Gain access



Steps to Fix Each Vulnerability
1. Fixing Broken Access Control Fix:
•	Steps:
1.	Implement Role Authentication principles
2.	Apply the rule of least privilege, and authorize user only to what’s required (ie. Only their record/ information), much less than what admin would require (Add, Update, View all, delete etc.)
2. Fixing Password Hashing:
•	Steps:
1.	Introduce new method which uses SHA256 hashing algorithm.
2.	Save hashed password into database replacing plaintext password
3. Fixing SQL Injection:
•	Steps:
1.	Use parameterized queries or prepared statements to handle user input securely.
2.	Set search parameter fields for Id as an “int” over “string”
Challenges Faced During the Project
Technical Challenges:
1.	Adapting Existing Code:
•	Challenge: Balancing the implementation of security enhancements without disrupting existing functionality.
•	Resolution: Carefully review and modify code, ensuring that security improvements are seamlessly integrated.
