CREATE TABLE employees (emp_id NUMBER PRIMARY KEY, emp_name VARCHAR2(50), deptno NUMBER, sal NUMBER, comm NUMBER);

Insert Employee Table:- INSERT INTO employees VALUES (1, 'Ramesh', 10, 50000, 5000); INSERT INTO employees VALUES (2, 'Suresh', 20, 60000, 6000); Create the salary_audit Table:- CREATE TABLE salary_audit (audit_id NUMBER PRIMARY KEY, emp_id NUMBER, old_salary NUMBER, new_salary NUMBER, change_date

TIMESTAMP);

Create Sequence for Audit Table:- CREATE SEQUENCE salary_audit_seq START WITH 1 INCREMENT BY 1;

CREATE OR REPLACE TRIGGER trg_salary_audit

1/2

AFTER UPDATE OF sal ON employees FOR EACH ROW

WHEN (NEW.sal <> OLD.sal)

DECLARE v_audit_id NUMBER;

BEGIN SELECT salary_audit_seq.NEXTVAL

INTO v_audit_id FROM DUAL;

INSERT INTO salary_audit (audit_id,

emp_id, old_salary, new_salary,

change_date) VALUES (v_audit_id,

:OLD.emp_id, :OLD.sal, :NEW.sal,

SYSTIMESTAMP);

END;

/

Check The Trigger:-

UPDATE employees SET sal = 70000

WHERE emp_id = 1;

SELECT * FROM salary_audit;
