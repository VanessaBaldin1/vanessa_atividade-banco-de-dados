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
SELECT nome, data_de_nascimento 
FROM alunos 
WHERE data_de_nascimento < '2009-01-01';
```
## 2- Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

```sql
SELECT nome, 
       (primeira_nota + segunda_nota) AS soma_notas,
       ROUND((primeira_nota + segunda_nota) / 2, 2) AS media_notas
FROM alunos;

```
## 3 Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

```sql
SELECT 
    titulo AS Titulo_Curso, 
    carga_horaria, 
    (carga_horaria * 0.25) AS Limite_Faltas
FROM cursos 
ORDER BY titulo ASC;
```
## 4 - Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".

```sql
SELECT nome 
FROM professores 
WHERE area_atuacao;
```
## 5-Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.

```sql
SELECT area_atuacao, COUNT(*) As 'quantidade de professores' 
FROM professores 
WHERE area_atuacao IN ('Design', 'desenvolvimento', 'infra')
GROUP BY area_atuacao;
```

## 6-Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.

```sql
SELECT 
    alunos.nome AS nome_aluno,
    cursos.titulo AS titulo_curso,
    cursos.carga_horaria
FROM alunos
JOIN cursos ON alunos.cursos_id = cursos.id;
```

## 7- Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.

```sql
SELECT 
    professores.nome AS nome_professor,
    cursos.titulo AS titulo_curso
FROM professores
JOIN cursos ON professores.cursos_id = cursos.id
ORDER BY professores.nome;
```
## 8- Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.

```sql
SELECT 
    alunos.nome AS nome_aluno,
    cursos.titulo AS titulo_curso,
    professores.nome AS nome_professor
FROM alunos
JOIN cursos ON alunos.cursos_id = cursos.id
JOIN professores ON cursos.id = professores.cursos_id;
```
## 9- Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.

```sql 
   SELECT 
    cursos.titulo AS titulo_curso,
    COUNT(alunos.id) AS quantidade_alunos
FROM cursos
LEFT JOIN alunos ON cursos.id = alunos.cursos_id
GROUP BY cursos.titulo
ORDER BY quantidade_alunos DESC;
```
## 10- Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.

```sql 
SELECT 
    alunos.nome AS nomes,
    alunos.primeira_nota,
    alunos.segunda_nota,
    ROUND((alunos.primeira_nota + alunos.segunda_nota) / 2, 2) AS media,
    cursos.titulo AS titulo_curso
FROM alunos
JOIN cursos ON alunos.cursos_id = cursos.id
WHERE cursos.titulo IN ('Front-End', 'Back-End')
ORDER BY alunos.nome;
```
## 11- Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.

```sql 
UPDATE cursos
SET titulo = 'Adobe XD', carga_horaria = 15
WHERE titulo = 'Figma';
```

## 12 - Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.

```sql
DELETE FROM alunos
WHERE cursos_id = (SELECT id FROM cursos WHERE titulo = 'Redes de Computadores')
LIMIT 1; 

DELETE FROM alunos
WHERE cursos_id = (SELECT id FROM cursos WHERE titulo = 'UX/UI Design')
LIMIT 1;
```
## 13 - Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.

```sql
SELECT 
    alunos.nome AS nome_aluno,
    cursos.titulo AS titulo_curso
FROM alunos
JOIN cursos ON alunos.cursos_id = cursos.id
ORDER BY alunos.nome ASC;
```

### 🔥 DESAFIOS 🔥

# 1- Criar uma consulta que calcule a idade do aluno

```sql
SELECT nome,
       data_de_nascimento,
       TIMESTAMPDIFF(YEAR, data_de_nascimento, CURDATE()) AS idade
FROM alunos;
```

# 2 - Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média maior ou igual a 7.

```sql
SELECT nome,
       ROUND((primeira_nota + segunda_nota) / 2, 2) AS media
FROM alunos
HAVING media >= 7;
```

# 3- Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média menor que 7.

```sql
SELECT nome,
       ROUND((primeira_nota + segunda_nota) / 2, 2) AS media
FROM alunos
HAVING media < 7;
```
# 4- Criar uma consulta que mostre a quantidade de alunos com média maior ou igual a 7.

```sql
SELECT COUNT(*) AS quantidade_alunos
FROM alunos
HAVING (ROUND((primeira_nota + segunda_nota) / 2, 2)) >= 7;
```