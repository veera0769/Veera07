CREATE TABLE student_rowtri ( previous_age NUMBER(5), current_age 
NUMBER(5), agediff NUMBER(10) ); 
TRIGGER Creation:
BEFORE DELETE OR INSERT OR UPDATE ON student_rowtri 
FOR EACH ROW 
WHEN (NEW.CODE > 0) 
DECLARE 
age_diff number; 
BEGIN 
age_diff := :NEW.age - :OLD.age; 
dbms_output.put_line ('Prevoius age: ' || : OLD.age); 
dbms_output.put_line ('Current age: ' || : NEW.age); 
dbms_output.put_line ('Age difference: ' || age_diff); 
END; 
DML Operations
INSERT INTO student_rowtri VALUES (10, 30, 20); 
UPDATE student_rowtri SET current_age = 35 WHERE previous_age = 10; 
DELETE FROM student_rowtri WHERE previous_age = 10;
