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
UPDATE cursos SET professores_id = 1 WHERE titulo = 'Redes de Computadores';  -- Jon Oliva (Infra)
UPDATE cursos SET professores_id = 2 WHERE titulo = 'Figma';  -- Lemmy Kilmister (Design)
UPDATE cursos SET professores_id = 3 WHERE titulo = 'UX/UI Design';  -- Neil Peart (Design)
UPDATE cursos SET professores_id = 4 WHERE titulo = 'Back-End';  -- Ozzy Osbourne (Desenvolvimento)
UPDATE cursos SET professores_id = 5 WHERE titulo = 'Front-End';  -- David Gilmour (Desenvolvimento)
```

## INSERT Cadastre pelo menos 10 alunos distribuidos aleatoriamente dentre os cursos, com datas de nascimento variadas, notas baixas e altas (sempre entre 0.00 e 10.00).

```sql
INSERT INTO alunos (nome, data_de_nascimento, primeira_nota, segunda_nota, cursos_id) VALUES
('Alice Silva', '2000-05-12', 9.5, 8.7, 1),  -- Front-End
('Bob Souza', '1998-10-21', 7.3, 6.0, 2),    -- Back-End
('Carlos Lima', '2001-02-18', 6.2, 7.4, 3),  -- UX/UI Design
('Daniela Costa', '1999-06-29', 8.0, 9.2, 4), -- Figma
('Eva Martins', '2002-07-07', 10.0, 9.5, 5),  -- Redes de Computadores
('Felipe Pereira', '2000-11-30', 5.3, 6.5, 1), -- Front-End
('Gabriela Rocha', '1997-03-22', 8.5, 7.9, 2), -- Back-End
('Hugo Oliveira', '2001-09-03', 4.0, 5.5, 3),  -- UX/UI Design
('Igor Alves', '2002-04-15', 9.0, 8.2, 4),    -- Figma
('Júlia Santana', '2000-12-25', 6.5, 7.0, 5);  -- Redes de Computadores
```

## Atividades de Banco de Dados - Etapa 4 (FINAL)

**CRUD - Consultas**
💡Não se esqueça de continuar guardando todos os comandos SQL bem-sucedidos que utilizou em um arquivo Markdown (exemplo: comandos-crud.md). Este arquivo deve ser colocado no seu repositório.

## 1- Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

```sql
SELECT nome, data_de_nascimento FROM alunos
WHERE data_de_nascimento < 2009;
```
## 2- Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

```sql
SELECT alunos.cursos_id, SUM(primeira_nota + segunda_nota) AS Total FROM alunos
JOIN cursos ON alunos.cursos_id = cursos.professores.id
GROUP BY cursos_id;

```