1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql

SELECT *
FROM `students`
JOIN `degrees`
ON `degree_id` = `degrees`.`id`
WHERE `degree_id` = 53 ;

```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

```sql

SELECT * 
FROM `degrees`
JOIN `departments`
ON `department_id` = `departments`.`id`
WHERE `department_id` = 7 AND `degrees`.`level` = 'magistrale' ;

```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql



```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome

```sql



```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql



```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)

```sql



```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.

```sql



```