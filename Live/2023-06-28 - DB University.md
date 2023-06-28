## DB
[[DBs/DB University/2023-06-28 - DB University|2023-06-28 - DB University]]

## Query
### SELECT
1. Selezionare tutti gli insegnanti
```sql
SELECT *
FROM teachers;
```

2. Selezionare tutti i referenti per ogni dipartimento
```sql
SELECT head_of_department
FROM departments;
```

3. Selezionare tutti gli studenti il cui nome inizia per "E" (373)
```sql
SELECT *
FROM students
WHERE name LIKE 'e%';
```

4. Selezionare tutti gli studenti che si sono iscritti nel 2021 (734)
```sql
-- VERSION 1
SELECT *
FROM students
WHERE enrolment_date >= '2021-01-01'
    AND enrolme _date < '2022-01-01';

-- VERSION 2
SELECT *
FROM students
WHERE enrolment_date 
	BETWEEN '2021-01-01' AND '2021-12-31';

-- VERSION 3
SELECT *
FROM students
WHERE YEAR(enrolment_date) = 2021;
```

5. Selezionare tutti i corsi che non hanno un sito web (676)
```sql
SELECT *
FROM courses
WHERE website IS NULL;
```

6. Selezionare tutti gli insegnanti che hanno un numero di telefono (50)
```sql
SELECT *
FROM teachers
WHERE phone IS NOT NULL;
```

7. Selezionare tutti gli appelli d'esame dei mesi di giugno e luglio 2020 (2634)
```sql
-- VERSION 1
SELECT *
FROM exams
WHERE (MONTH(date) = 6 
       	OR MONTH(date) = 7)
       AND YEAR(date) = 2020;

-- VERSION 2
SELECT *
FROM exams
WHERE date 
	BETWEEN '2020-06-01' AND '2020-07-31';

-- VERSION 3
SELECT *
FROM exams
WHERE date >= '2020-06-01' 
	AND date < '2020-08-01';
```

8. Qual è il numero totale degli studenti iscritti? (5000)
```sql
SELECT COUNT(*)
FROM students;
```


### GROUP BY
1. Contare i corsi raggruppati per cfu
```sql
SELECT cfu, COUNT(*) AS 'course_count'
FROM courses
GROUP BY cfu;
```

2. Contare gli studenti raggruppati per anno di nascita
```sql
SELECT YEAR(date_of_birth), COUNT(*)
FROM students
GROUP BY YEAR(date_of_birth);
```

3. Selezionare il voto più basso dato ad ogni appello d'esame
```sql
SELECT exam_id, MIN(vote)
FROM exam_student
GROUP BY exam_id;
```

4. Contare gli appelli d'esame del mese di luglio raggruppati per giorno
```sql
SELECT DAY(date), COUNT(*)
FROM exams
WHERE MONTH(date) = 7
GROUP BY DAY(date);
```


### JOIN
TODO TOMORROW