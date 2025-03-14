## Atividades de Banco de Dados - Etapa 1

Antes de começar, crie um novo repositório chamado seunome_atividade-banco-de-dados para colocar sua produção.

### Modelagem Conceitual
A. Modelagem Conceitual
Usando o BrModelo, faça a modelagem conceitual de três entidades: CURSO, PROFESSOR e ALUNO.

A entidade **CURSO** deve conter os seguintes atributos:

Identificador, obrigatório
Título, obrigatório
Carga horária, obrigatório
Identificador do Professor, opcional
A entidade PROFESSOR deve conter os seguintes atributos:

Identificador, obrigatório
Nome, obrigatório
Área de atuação (coloque entre parênteses: design, desenvolvimento, infra), obrigatório
Identificador do Curso, obrigatório
A entidade ALUNO deve conter os seguintes atributos:

Identificador, obrigatório
Nome, obrigatório
Data de nascimento, obrigatório
Primeira nota, obrigatório
Segunda nota, obrigatório
Identificador do Curso, obrigatório

Crie os relacionamentos de acordo com a cardinalidade indicada a seguir:
1 curso tem vários alunos, portanto será usada a cardinalidade 1:N.

1 professor leciona somente 1 curso, portanto será usada a cardinalidade 1:1.

1 curso é lecionado somente por 1 professor, portanto será usada a cardinalidade 1:1.
 
## Exemplo de Modelagem Conceitual
 
![Entidades, atributos e relacionamento](/exercicio-modelagem-conceitual/conceitual_atividade-banco-de-dados.png)

## Atividades de Banco de Dados - Etapa 2
### B. Modelagem Lógica
Usando o MySQL Workbench, faça a modelagem lógica a partir do que fez na modelagem conceitual, transformando as entidades em tabelas e seus atributos em colunas, além de definir os tipos de dados e relacionamentos.

🚨Fique atento(a) quanto ao nome das tabelas e das colunas. A sugestão segue sendo usar plural para tabelas e singular para colunas.

💡Sobre a entidade/tabela para Professores
Na modelagem conceitual da entidade PROFESSOR foi criado um atributo para a Área de atuação e indicado entre parênteses os valores design, desenvolvimento, infra.

Agora, na modelagem lógica, você deverá pesquisar qual tipo de dados permite indicar uma lista fixa de valores, aplicando ele na coluna da área de atuação.

Ao final, coloque o arquivo de modelagem lógica em seu repositório do exercício em versão original e também exportado em formato de imagem.

## Exemplo de Modelagem Lógico
![Entidades, atributos e relacionamento](/modelagem-logica/logico_atividade-banco-de-dados.png)

## Atividades de Banco de Dados - Etapa 3
### C. Modelagem Física
Usando o phpMyAdmin e comandos SQL, você deve fazer a modelagem física de um banco de dados chamado tecinternet_escola_seunome e nele criar as tabelas, colunas e relacionamentos.

💡Não se esqueça de guardar todos os comandos SQL que utilizou na modelagem física em um arquivo Markdown (exemplo: modelo-fisico.md). Este arquivo deve ser colocado no seu repositório.

Ao final, exporte um backup do seu banco de dados com as tabelas vazias e coloque também em seu repositório.

CRUD
💡Não se esqueça de guardar todos os comandos SQL que utilizou na nesta manipulação de dados em um arquivo Markdown (exemplo: comandos-crud.md). Este arquivo deve ser colocado no seu repositório.

Cadastre pelo menos 5 cursos:
Front-End, carga horária 40h
Back-End, carga horária 80h
UX/UI Design, carga horária 30h
Figma, carga horária 10h
Redes de Computadores, carga horária 100h
🚨 Atenção: por enquanto, deixe o campo professor_id como nulo.

Cadastre pelo menos 5 professores:
Jon Oliva, área infra
Lemmy Kilmister, área design
Neil Peart, área design
Ozzy Osbourne, área desenvolvimento
David Gilmour, área desenvolvimento
🚨 Atenção: durante o cadastro dos professores, associe cada professor a um curso na ordem contrária dos registros.

Exemplos:

O primeiro professor (Jon Oliva, infra) será atribuido ao último curso (Redes de Computadores)
O segundo professor (Lemmy, design) será atribuido ao penúltimo curso (Figma)
Atualize os dados do campo professor_id da tabela cursos, associando cada curso ao seu professor correspondente.
Cadastre pelo menos 10 alunos distribuidos aleatoriamente dentre os cursos, com datas de nascimento variadas, notas baixas e altas (sempre entre 0.00 e 10.00).
💡Não se esqueça de guardar todos os comandos SQL que utilizou nesta manipulação de dados em um arquivo Markdown (exemplo: comandos-crud.md). Este arquivo deve ser colocado no seu repositório.


## Atividades de Banco de Dados - Etapa 4 (FINAL)
### CRUD - Consultas
💡Não se esqueça de continuar guardando todos os comandos SQL bem-sucedidos que utilizou em um arquivo Markdown (exemplo: comandos-crud.md). Este arquivo deve ser colocado no seu repositório.

1) Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

2) Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

3) Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

4) Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".

5) Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.

6) Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.

7) Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.

8) Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.

9) Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.

10) Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.

11) Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.

12) Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.

13) Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.

Ao final, exporte um backup completo do seu banco de dados e coloque também em seu repositório.

🔥 DESAFIOS 🔥

1- Criar uma consulta que calcule a idade do aluno

2- Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média maior ou igual a 7.

3- Criar uma consulta que calcule a média das notas de cada aluno e mostre somente os alunos que tiveram a média menor que 7.
4- Criar uma consulta que mostre a quantidade de alunos com média maior ou igual a 7.


## Os comandos foram feitos nos arquivos abaixo:
**Comandos-fisico**
[Veja o modelo físico aqui](modelo-fisico.md)

**Comandos-crud**
[Veja o modelo físico aqui](comandos-crud.md)
