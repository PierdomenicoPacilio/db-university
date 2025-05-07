### 1. Contare quanti iscritti ci sono stati ogni anno

```
SELECT 
    YEAR(enrolment_date) AS 'year',
    COUNT(id) AS 'number_of_students'
FROM
    db_university.students
GROUP BY YEAR(enrolment_date);
```
---

### 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```
SELECT 
    office_address, COUNT(id) AS 'number_of_teachers'
FROM
    db_university.teachers
GROUP BY office_address;
```
---

### 3. Calcolare la media dei voti di ogni appello d'esame

```
SELECT 
    exam_id, AVG(vote) AS 'average_vote'
FROM
    db_university.exam_student
GROUP BY exam_id;
```
---

### 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```
SELECT 
    department_id, COUNT(id) AS 'number_of_degrees'
FROM
    db_university.degrees
GROUP BY department_id;
```