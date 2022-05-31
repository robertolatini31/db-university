# University

## department:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- name: VARCHAR(255) NOTNULL
- ?courses? 1

## degree_course:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- name: VARCHAR(255) NOTNULL
- hours: SMALLINT   NULL
- ?department? *
- ?university_subjects? 1
- ?student? 1

## university_subject:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- name: VARCHAR(255) NOTNULL
- hours: SMALLINT   NULL
- ?degree_course? *
- ?teacher? *
- ?exam_session? 1

## teacher:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- name: VARCHAR(255) NOTNULL
- lastname: VARCHAR(255) NOTNULL
- ?university_subject? *

## exam_session:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- date: DATETIME NOTNULL
- ?university_subject? *
- ?student? *

## student:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- name: VARCHAR(255) NOTNULL
- lastname: VARCHAR(255) NOTNULL
- average_grades: TINYINT NULL
- ?votes? 1
- ?degree_course? *
- ?exam_session? 1


## votes:
- id: BIGINT PRIMARYKEY (NOTNULL, AUTOINCREMENTS, UNIQUE)
- vote: TINYINT NOTNULL
- ?student? 1









<!-- - ------ sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ------ ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ------ ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.;
- -------- ogni Corso può essere tenuto da diversi Insegnanti;
- ----------- ogni Corso prevede più appelli d'Esame;


- ------------ ogni Studente è iscritto ad un solo Corso di Laurea;
- ------------- ogni Studente può iscriversi a più appelli di Esame;
- ------------- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. -->