## C. Modelagem Física
Usando o phpMyAdmin e comandos SQL, você deve fazer a modelagem física de um banco de dados chamado tecinternet_escola_seunome e nele criar as tabelas, colunas e relacionamentos.

💡Não se esqueça de guardar todos os comandos SQL que utilizou na modelagem física em um arquivo Markdown (exemplo: modelo-fisico.md). Este arquivo deve ser colocado no seu repositório.

Ao final, exporte um backup do seu banco de dados com as tabelas vazias e coloque também em seu repositório.

### Criar banco de dados

```sql
CREATE DATABASE tecinternet_escola_vanessa CHARACTER SET utf8mb4;
```

### Criar tabela de Fabricante

```sql
CREATE TABLE fabricantes(
  id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
  nome VARCHAR(50) NOT NULL
);
```