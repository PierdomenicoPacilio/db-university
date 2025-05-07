### 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```
SELECT 
    degrees.name AS 'degree_name', students.*
FROM
    db_university.students
        INNER JOIN
    degrees ON degree_id = degrees.id
WHERE
    degrees.name = 'Corso di Laurea in Economia';
```
---

### 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```
SELECT 
    departments.name AS department_name, degrees.*
FROM
    db_university.degrees
        INNER JOIN
    departments ON department_id = departments.id
WHERE
    departments.name = 'Dipartimento di Neuroscienze'
        AND degrees.level = 'magistrale';
```
---

### 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```
SELECT 
    teachers.*, courses.*
FROM
    db_university.courses
        INNER JOIN
    course_teacher ON courses.id = course_teacher.course_id
        INNER JOIN
    teachers ON course_teacher.teacher_id = teachers.id
WHERE
    teachers.name = 'Fulvio'
        AND teachers.surname = 'Amato';
```
---

### 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```
SELECT 
    *
FROM
    db_university.students
        INNER JOIN
    degrees ON degree_id = degrees.id
        INNER JOIN
    departments ON degrees.department_id = departments.id
ORDER BY students.name , students.surname;
```
---

### 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```
SELECT 
    *
FROM
    db_university.degrees
        INNER JOIN
    courses ON degrees.id = courses.degree_id
        INNER JOIN
    course_teacher ON courses.id = course_teacher.course_id
        INNER JOIN
    teachers ON course_teacher.teacher_id = teachers.id;
```
---

### 6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

```
SELECT 
    departments.name, teachers.*
FROM
    db_university.teachers
        INNER JOIN
    course_teacher ON teachers.id = course_teacher.teacher_id
        INNER JOIN
    courses ON course_teacher.course_id = courses.id
        INNER JOIN
    degrees ON courses.degree_id = degrees.id
        INNER JOIN
    departments ON degrees.department_id = departments.id
WHERE
    departments.name = 'Dipartimento di Matematica'
GROUP BY teachers.id;
```
---

### 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

```

```