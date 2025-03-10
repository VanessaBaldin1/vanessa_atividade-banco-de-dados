## C. Modelagem Física
Usando o phpMyAdmin e comandos SQL, você deve fazer a modelagem física de um banco de dados chamado tecinternet_escola_seunome e nele criar as tabelas, colunas e relacionamentos.

💡Não se esqueça de guardar todos os comandos SQL que utilizou na modelagem física em um arquivo Markdown (exemplo: modelo-fisico.md). Este arquivo deve ser colocado no seu repositório.

Ao final, exporte um backup do seu banco de dados com as tabelas vazias e coloque também em seu repositório.

### Criar banco de dados

```sql
CREATE DATABASE tecinternet_escola_vanessa CHARACTER SET utf8mb4;
```

### Criar tabelas cursos

```sql
CREATE TABLE cursos(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  titulo VARCHAR(80) NOT NULL,
  carga_horaria INT NOT NULL,
  professor_id INT NULL --Será chave estrangeira
);
```

```sql
CREATE TABLE professores(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  id_curso INT NOT NULL,
  area_atuacao ENUM('design, desenvolvimento, infra') NOT NULL,
  nome VARCHAR(100) NOT NULL,
  cursos_id  INT NOT NULL --Será chave estrangeira
);
```

```sql
CREATE TABLE alunos(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  data_de_nascimento DATE NOT NULL,
  primeira_nota DECIMAL(4,2),
  segunda_nota DECIMAL (4,2),
  nome VARCHAR(60),
  cursos_id INT NOT NULL --Será chave estrangeira
);
```

### Criar relacionamento entre as tabelas e configurar a chave estrangeira

```sql
ALTER TABLE produtos
-- Adicionando uma restrição indicando o nome do relacionamento
  ADD CONSTRAINT fk_produtos_fabricantes

-- Criando a chave-estrangeira (fabricante_id) que
-- aponta para a chave-primária (id) de OUTRA TABELA (fabricantes)
  FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id);
```