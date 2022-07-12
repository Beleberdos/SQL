
DROP TABLE SUBJECT;
create table SUBJECT
(
  SUBJ_ID   NUMERIC not null,
  SUBJ_NAME VARCHAR(60),
  HOUR      NUMERIC,
  SEMESTER   NUMERIC
);
insert into subject VALUES (1,'PROGRAMM',104,1);
insert into subject VALUES (2,'MATH',104,1);
alter table SUBJECT
add primary key (SUBJ_ID);


  
  
  
DROP TABLE STUDENT;
create table STUDENT
(
  STUDENT_ID NUMERIC not null,
  SURNAME    VARCHAR(60),
  NAME       VARCHAR(60),
  STIPEND    NUMERIC(16,2),
  KURS       NUMERIC,
  CITY       VARCHAR(60),
  BIRTHDAY   DATE
);
INSERT INTO STUDENT VALUES (1,'ABZALOV','ALEX',4350,1,'MAGNITOGORSK', 
                            TO_DATE('01.08.2003', 'DD.MM.YYYY'));
INSERT INTO STUDENT VALUES (2,'KILIEVICH','DMITRY',4350,1,'MAGNITOGORSK', 
                            TO_DATE('11.11.2003', 'DD.MM.YYYY'));
INSERT INTO STUDENT VALUES (3,'TERESHCHENKO','NIKITA',8350,1,'MAGNITOGORSK', 
                            TO_DATE('05.12.2003', 'DD.MM.YYYY'));
INSERT INTO STUDENT VALUES (4,'ROMANOVSKY','GRIGORY',4350,1,'MAGNITOGORSK', 
                            TO_DATE('21.05.2003', 'DD.MM.YYYY'));

alter table STUDENT
  add primary key (STUDENT_ID);
alter table STUDENT;
DROP TABLE EXAM_MARKS;






DROP TABLE EXAM_MARKS;
create table EXAM_MARKS
(
  EXAM_ID    NUMERIC not null,
  STUDENT_ID NUMERIC not null,
  SUBJ_ID    NUMERIC not null,
  MARK       NUMERIC,
  EXAM_DATE  DATE
);
INSERT INTO exam_marks VALUES (1,1,1,5,TO_DATE('27.07.2022', 'DD.MM.YYYY'));
alter table EXAM_MARKS
  add primary key (EXAM_ID,STUDENT_ID,SUBJ_ID);
alter table EXAM_MARKS
  add constraint STUDENT_FOR_KEY foreign key (STUDENT_ID)
  references STUDENT (STUDENT_ID);
alter table EXAM_MARKS
  add constraint SUBJECT_FOR_KEY foreign key (SUBJ_ID)
  references SUBJECT (SUBJ_ID);
create index STUDENT_ID_1 on EXAM_MARKS (STUDENT_ID);

select * from STUDENT;

UPDATE 
STUDENT
SET
KURS = 2;


select * from STUDENT;
        
DELETE FROM STUDENT
WHERE NAME = 'NIKITA';

select * from STUDENT;
        
        
        
