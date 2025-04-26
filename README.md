# 🎓 Banco de Dados para Gestão Universitária

📚 **Foco:** Este projeto consiste em um banco de dados relacional para a gestão acadêmica de uma universidade. 
Ele está voltado para fins educativos e serve como exemplo para estudantes de áreas relacionadas como: computação, administração e gestão de dados.
Este documento apresenta explicações de forma simples e fácil de entender, até para quem não tem experiência na área.

## 📌 Modelagem do Banco de Dados

A estrutura do banco de dados é composta pelas seguintes tabelas:

### Entidades Principais

#### 1. **ALUNO**
Armazena informações sobre os alunos matriculados na instituição.
- **cd_aluno** (PK) - Código único do aluno
- **nome** - Nome do aluno
- **matrícula** - Número da matrícula
- **endereço** - Endereço do aluno
- **data_nascimento** - Data de nascimento
- **fk_curso** (FK) - Referência ao curso do aluno

#### 2. **CURSO**
Registra os cursos oferecidos pela universidade.
- **cd_curso** (PK) - Código único do curso
- **nome** - Nome do curso
- **turno** - Período do curso (manhã/tarde/noite)
- **numero_alunos** - Número de alunos matriculados

#### 3. **DEPARTAMENTO**
Guarda os departamentos acadêmicos da instituição.
- **cd_departamento** (PK) - Código único do departamento
- **nome** - Nome do departamento
- **campus** - Campus onde o departamento está localizado

#### 4. **PROFESSOR**
Armazena os dados dos professores da universidade.
- **cd_professor** (PK) - Código único do professor
- **nome** - Nome do professor
- **cpf** - CPF do professor
- **salário** - Salário do professor
- **data_nascimento** - Data de nascimento
- **fk_departamento** (FK) - Referência ao departamento do professor

#### 5. **DISCIPLINA**
Registra as disciplinas oferecidas nos cursos.
- **cd_disciplina** (PK) - Código único da disciplina
- **nome** - Nome da disciplina
- **horas** - Carga horária da disciplina

#### 6. **OFERTA**
Relaciona as disciplinas oferecidas aos alunos em determinados períodos.
- **cd_oferta** (PK) - Código único da oferta
- **frequencia** - Frequência do aluno na disciplina
- **ano** - Ano letivo
- **nota** - Nota do aluno
- **semestre** - Semestre da oferta
- **fk_professor** (FK) - Professor responsável pela disciplina
- **fk_aluno** (FK) - Aluno matriculado na disciplina
- **fk_disciplina** (FK) - Disciplina oferecida

### 📂 Entidades de Relacionamento

#### 7. **DEPARTAMENTO_CURSO**
Relaciona departamentos e cursos.
- **cd_departamento_curso** (PK) - Código único da relação
- **fk_departamento** (FK) - Referência ao departamento
- **fk_curso** (FK) - Referência ao curso

#### 8. **DISCIPLINA_CURSO**
Relaciona disciplinas e cursos.
- **cd_disciplina_curso** (PK) - Código único da relação
- **fk_curso** (FK) - Referência ao curso
- **fk_disciplina** (FK) - Referência à disciplina

#### 9. **TITULACAO**
Armazena os títulos acadêmicos dos professores.
- **cd_titulacao** (PK) - Código único da titulação
- **instituição** - Instituição de ensino
- **curso** - Curso da titulação
- **grau** - Grau obtido (Mestre, Doutor, etc.)
- **fk_professor** (FK) - Professor que possui a titulação

#### 10. **DEPENDENTE**
Armazena informações sobre os dependentes dos professores.
- **cd_dependente** (PK) - Código único do dependente
- **nome** - Nome do dependente
- **relacionamento** - Relação com o professor
- **data_nascimento** - Data de nascimento
- **fk_professor** (FK) - Professor responsável pelo dependente

## 🔗 Relacionamentos
- Um **Aluno** pertence a um **Curso**.
- Um **Curso** pode pertencer a um ou mais **Departamentos**.
- Uma **Disciplina** pode pertencer a vários **Cursos**.
- Um **Professor** pertence a um **Departamento** e pode ministrar várias **Ofertas** de disciplinas.
- Um **Professor** pode ter vários **Dependentes** e várias **Titulações**.
- Uma **Oferta** registra a relação entre **Alunos**, **Disciplinas** e **Professores**.

## 📌 Uso do Banco de Dados
Este banco de dados pode ser utilizado para:
- Gerenciar alunos, professores, cursos e departamentos.
- Controlar ofertas de disciplinas e notas dos alunos.
- Registrar as titulações dos professores.
- Monitorar dependentes dos professores.

## 🚀 Tecnologias Utilizadas
Utilizando apenas Microsoft SQL Server Management Studio:
- **Banco de Dados Relacional (SQL)**
- **Ferramentas de Modelagem**

## IMAGENS
![Modelo Relacional](https://github.com/user-attachments/assets/4cb03af1-9351-4ac1-a23f-ed4b78987213)


# Licença
Este projeto está licenciado sob a MIT License - veja o arquivo LICENSE para mais detalhes.

