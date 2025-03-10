# Comandos para operações CRUD no Banco de Dados

## INSERT (Cadastre pelo menos 5 cursos:)

```sql
INSERT INTO cursos(titulo, carga_horaria)
VALUES(
  'Front-End',
   40
);
```
```sql
INSERT INTO cursos(titulo, carga_horaria)
VALUES(
  'Back-End',
   80
);
```
```sql
INSERT INTO cursos(titulo, carga_horaria)
VALUES(
  'UX/UI Design',
   30
);
```
```sql
INSERT INTO cursos(titulo, carga_horaria)
VALUES(
  'Figma',
   10
);
```
```sql
INSERT INTO cursos(titulo, carga_horaria)
VALUES(
  'Redes de Computadores',
   100
);
```
## INSERT (Cadastre pelo menos 5 professores:)

```sql
INSERT INTO professores(nome, area_atuacao, cursos_id)
VALUES(
  'Jon Oliva',
   'infra',
   5
);
```
```sql
INSERT INTO professores(nome, area_atuacao, cursos_id)
VALUES(
  'Lemmy Kilmister',
   'design',
   4
);
```
```sql
INSERT INTO professores(nome, area_atuacao, cursos_id)
VALUES(
  'Neil Peart',
   'design',
   3
);
```
```sql
INSERT INTO professores(nome, area_atuacao, cursos_id)
VALUES(
  'Ozzy Osbourne',
   'desenvolvimento',
   2
);
```

```sql
INSERT INTO professores(nome, area_atuacao, cursos_id)
VALUES(
  'David Gilmour',
   'desenvolvimento',
   1
);
```

## INSERT (Atualize os dados do campo professor_id da tabela cursos, associando cada curso ao seu professor correspondente.)



```sql
INSERT INTO cursos(professores_id)
VALUES(
  'David Gilmour',
   'desenvolvimento',
   1
);
```