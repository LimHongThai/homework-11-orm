## Answer
1.

```python
current_date = datetime.now()
employee = Employee(emp_num = 168, emp_fname = "John", emp_lname = "Doe", emp_initial = "JD", job_code = 500, emp_hiredate = current_date)
session.add(employee)
session.commit()
```
2.
``` python
employees = session.query(Employee, Job).filter(Employee.job_code == Job.job_code).filter(Employee.emp_num == 168).all()

for employee in employees:
    print(employee.EMPLOYEE.emp_num, employee.EMPLOYEE.emp_fname, employee.EMPLOYEE.emp_lname, employee.EMPLOYEE.emp_initial, employee.JOB.job_description, EMPLOYEE.JOB.job_chg_hour, employee.EMPLOYEE.emp_hiredate)
```
3.

```python
employee = session.query(Employee).filter(EMPLOYEE.emp_num == 168).first()
EMPLOYEE.job_code = 502
session.commit()
```

4.

```python
projects = session.query(Project, Employee).filter(Project.emp_num == Employee.emp_num).filter(Employee.job_code == 500).all()

for project in projects:
    print(project.Project.proj_num, project.Project.proj_name, project.Employee.emp_fname, project.Employee.emp_lname)
```
5.
```python
employee = session.query(Employee).filter(Employee.emp_num == 168).first()
session.delete(employee)
session.commit()
```