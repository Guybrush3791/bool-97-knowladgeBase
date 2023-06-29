## Repo
`db-university`

## Todo
Dopo aver creato un nuovo database nel vostro `phpMyAdmin` e aver importato lo schema allegato, *eseguite le query del file allegato*.

### Cosa consegnare?
Dopo aver testato le vostre query con `phpMyAdmin`, riportatele in un file `txt` e caricatelo *nella vostra repo*.

### Query
#### SELECT
1. Selezionare tutti gli studenti nati nel 1990 `(160)`
```sql
SELECT *
FROM students
WHERE YEAR(date_of_birth) = 1990;
```
2. Selezionare tutti i corsi che valgono più di 10 crediti `(479)`
```sql
SELECT *
FROM courses
WHERE cfu > 10;
```
3. Selezionare tutti gli studenti che hanno più di 30 anni
```sql
SELECT *
FROM students
WHERE YEAR(NOW()) - YEAR(date_of_birth) > 30;
```
4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea `(286)`
```sql
SELECT *
FROM courses
WHERE period LIKE "I semestre" 
    AND year = 1;
```
5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 `(21)`
```sql
SELECT *
FROM exams
WHERE hour > "14:00:00"
    AND date = "2020-06-20";
```
6. Selezionare tutti i corsi di laurea magistrale `(38)`
```sql
SELECT *
FROM degrees
WHERE level LIKE "magistrale";
```
7. Contare il numero di dipartimenti di cui e' composta l'università `(12)`
```sql
SELECT COUNT(*)
FROM departments;
```
8. Contare gli insegnanti che non hanno un numero di telefono `(50)`
```sql
SELECT COUNT(*)
FROM teachers
WHERE phone IS NULL;
```

#### GROUP BY
1. Contare quanti iscritti ci sono stati ogni anno
```sql
SELECT YEAR(enrolment_date), COUNT(*)
FROM students
GROUP BY YEAR(enrolment_date);
```
2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT office_address, COUNT(*)
FROM teachers
GROUP BY office_address;
```
3. Calcolare la media dei voti di ogni appello d'esame
```sql
SELECT exam_id, AVG(vote)
FROM exam_student
GROUP BY exam_id;
```
4. Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT department_id, COUNT(*)
FROM degrees
GROUP BY department_id;
```