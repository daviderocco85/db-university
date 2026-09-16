
# Db university

Modellazione della struttura di un database per memorizzare tutti i dati riguardanti una università.

# Obiettivi

Il database deve gestire:

- Diversi dipartimenti.
- Ogni dipartimento offre più corsi di laurea.
- Ogni corso di laurea prevede diversi corsi.
- Ogni corso può essere tenuto da diversi insegnanti.
- Ogni corso prevede più appelli d'esame.
- Ogni studente è iscritto ad un solo corso di laurea.
- Ogni studente può iscriversi a più appelli d'esame.
- Per ogni appello d'esame a cui lo studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.

## Struttura del database

Il database è composto dalle seguenti tabelle:

- `department` – contiene i dipartimenti.
- `degree_program` – contiene i corsi di laurea.
- `course` – contiene i corsi previsti dai corsi di laurea.
- `teacher` – contiene gli insegnanti.
- `course_teacher` – tabella ponte per la relazione tra corsi e insegnanti.
- `student` – contiene gli studenti.
- `exam` – contiene gli appelli d'esame.
- `exam_registration` – tabella ponte che registra la partecipazione degli studenti agli appelli e il voto ottenuto.

## Relazioni principali 

- `department` -> `degree_program` **1:N** 
- `degree_program` -> `course` **1:N**
- `degree_program` -> `student` **1:N**
- `course` -> `exam` **1:N**
- `course` <-> `teacher` **N:M**
- `student` <-> `exam` **N:M**

Le relazioni **N:M** sono gestite tramite le tabelle ponte `course_teacher` ed `exam_registration`.

## drawSQL screenshot

![Struttura del database](img/drawSQL_schema.jpg)