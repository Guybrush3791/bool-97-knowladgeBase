## Repo
`db-university`

## Todo
Dopo aver creato un nuovo database nel vostro `phpMyAdmin` e aver importato lo schema allegato, *eseguite le query del file allegato*.

### Cosa consegnare?
Dopo aver testato le vostre query con `phpMyAdmin`, riportatele in un file `txt` e caricatelo *nella vostra repo*.

### Query
#### Join
1. Selezionare tutti gli studenti iscritti al `Corso di Laurea in Economia`
```sql
SELECT students.*
FROM degrees
    JOIN students
        ON degrees.id = students.degree_id
WHERE degrees.name LIKE "Corso di Laurea in Economia";
```

2. Selezionare tutti i `Corsi di Laurea Magistrale` del `Dipartimento di Neuroscienze`
```sql
SELECT degrees.*
FROM departments
    JOIN degrees
        ON departments.id = degrees.department_id
WHERE departments.name LIKE "Dipartimento di Neuroscienze"
    AND degrees.level LIKE "magistrale";
```

3. Selezionare tutti i corsi in cui insegna `Fulvio Amato` (id=`44`)
```sql
-- VERSION 1
SELECT *
FROM courses
    JOIN course_teacher
        ON courses.id = course_teacher.course_id
WHERE course_teacher.teacher_id = 44;

-- VERSION 2
SELECT *
FROM courses
    JOIN course_teacher
        ON courses.id = course_teacher.course_id
    JOIN teachers
        ON course_teacher.teacher_id = teachers.id
WHERE teachers.name LIKE 'fulvio' 
	AND teachers.surname LIKE 'amato';
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql
SELECT *
FROM students
    JOIN degrees
        ON students.degree_id = degrees.id
    JOIN departments
        ON degrees.department_id = departments.id
ORDER BY students.name, students.surname;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
```sql
SELECT degrees.*, courses.*, teachers.*
FROM degrees
    JOIN courses
        ON degrees.id = courses.degree_id
    JOIN course_teacher
        ON courses.id = course_teacher.course_id
    JOIN teachers
        ON course_teacher.teacher_id = teachers.id;
```

6. Selezionare tutti i docenti che insegnano nel `Dipartimento di Matematica` (54)
```sql
SELECT DISTINCT teachers.*
FROM departments
    JOIN degrees
        ON departments.id = degrees.department_id
    JOIN courses
        ON degrees.id = courses.degree_id
    JOIN course_teacher
        ON courses.id = course_teacher.course_id
    JOIN teachers
        ON course_teacher.teacher_id = teachers.id
WHERE departments.name LIKE "Dipartimento di Matematica";
```

##### Bonus
7. Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo; successivamente,
filtrare i tentativi con voto minimo 18
```sql
-- VERSION 1
SELECT students.name, students.surname, courses.name, COUNT(*) AS 'exam_count', MAX(exam_student.vote) AS 'voto_max'
FROM students
    JOIN exam_student
        ON students.id = exam_student.student_id
    JOIN exams
        ON exam_student.exam_id = exams.id
    JOIN courses
        ON exams.course_id = courses.id
GROUP BY students.id, courses.id;

-- VERSION 2
SELECT students.name, students.surname, courses.name, COUNT(*) AS 'exam_count', MAX(exam_student.vote) AS 'voto_max'
FROM students
    JOIN exam_student
        ON students.id = exam_student.student_id
    JOIN exams
        ON exam_student.exam_id = exams.id
    JOIN courses
        ON exams.course_id = courses.id
WHERE exam_student.vote >= 18
GROUP BY students.id, courses.id;
```
