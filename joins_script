CREATE TABLE departments (
    dept_id SERIAL PRIMARY KEY,
    dept_name VARCHAR(50) NOT NULL,
    location VARCHAR(50)
);
INSERT INTO departments (dept_name, location) VALUES
('IT', 'Bangalore'),
('HR', 'Delhi'),
('Finance', 'Mumbai'),
('Sales', 'Pune');
CREATE TABLE employees (
    emp_id SERIAL PRIMARY KEY,
    emp_name VARCHAR(50) NOT NULL,
    email VARCHAR(100),
    salary INT,
    dept_id INT,
    manager_id INT,
    CONSTRAINT fk_dept FOREIGN KEY (dept_id) REFERENCES departments(dept_id),
    CONSTRAINT fk_manager FOREIGN KEY (manager_id) REFERENCES employees(emp_id)
);
INSERT INTO employees (emp_name, email, salary, dept_id, manager_id) VALUES
('Rahul', 'rahul@company.com', 90000, 1, NULL),
('Ankit', 'ankit@company.com', 60000, 1, 1),
('Neha', 'neha@company.com', 55000, 2, 1),
('Pooja', 'pooja@company.com', 50000, 3, 3),
('Amit', 'amit@company.com', 45000, NULL, 1);
CREATE TABLE projects (
    project_id SERIAL PRIMARY KEY,
    project_name VARCHAR(50),
    dept_id INT,
    start_date DATE,
    end_date DATE,
    CONSTRAINT fk_project_dept FOREIGN KEY (dept_id)
        REFERENCES departments(dept_id)
);
INSERT INTO projects (project_name, dept_id, start_date, end_date) VALUES
('Website Revamp', 1, '2024-01-01', '2024-06-30'),
('Recruitment Drive', 2, '2024-02-01', '2024-05-31'),
('Budget Planning', 3, '2024-03-01', '2024-09-30'),
('Sales Expansion', 4, '2024-04-01', '2024-12-31');
CREATE TABLE employee_projects (
    emp_id INT,
    project_id INT,
    role VARCHAR(50),
    PRIMARY KEY (emp_id, project_id),
    FOREIGN KEY (emp_id) REFERENCES employees(emp_id),
    FOREIGN KEY (project_id) REFERENCES projects(project_id)
);
INSERT INTO employee_projects VALUES
(1, 1, 'Architect'),
(2, 1, 'Developer'),
(3, 2, 'Recruiter'),
(4, 3, 'Analyst'),
(2, 4, 'Support');
CREATE TABLE salaries (
    salary_id SERIAL PRIMARY KEY,
    emp_id INT,
    amount INT,
    effective_from DATE,
    FOREIGN KEY (emp_id) REFERENCES employees(emp_id)
);
INSERT INTO salaries (emp_id, amount, effective_from) VALUES
(1, 80000, '2023-01-01'),
(1, 90000, '2024-01-01'),
(2, 50000, '2023-01-01'),
(2, 60000, '2024-01-01'),
(3, 55000, '2024-01-01'),
(4, 45000, '2023-01-01'),
(4, 50000, '2024-01-01');
