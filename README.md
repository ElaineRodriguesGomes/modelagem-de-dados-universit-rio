# 🗄️ Modelagem de Dados: Sistema Universitário

Este repositório contém o estudo de caso e a construção do **Diagrama Entidade-Relacionamento (DER)** para um sistema de gestão universitária, abrangendo desde a modelagem conceitual inicial até a expansão com novos requisitos de negócio.

---

## 📌 1. Estrutura Inicial do Sistema

### 🏢 Entidades e Atributos Principais
- **Aluno:** `matrícula` *(PK)*, `nome`, `CPF`, `data_nascimento`
- **Curso:** `código` *(PK)*, `nome_curso`
- **Disciplina:** `código_disc` *(PK)*, `nome_disciplina`, `carga_horária`, `período`
- **Professor:** `siape` *(PK)*, `nome`, `especialidade`

### 🔗 Relacionamentos e Cardinalidades
- **Aluno** *(N:1)* **está matriculado em** **Curso**
- **Curso** *(1:N)* **possui** **Disciplina**
- **Aluno** *(N:M)* **cursa** **Disciplina** *(Resolvido via Entidade Associativa `MATRÍCULA` com atributos `matrícula_aluno` (FK), `código_disciplina` (FK) e `nota`)*
- **Professor** *(1:N)* **leciona** **Disciplina**

---

## 🛠️ 2. Regras de Negócio e Restrições

### 💡 Suposições
- Um aluno está vinculado a apenas um curso por matrícula.
- Cada disciplina pertence obrigatoriamente a um curso.
- Um professor pode ministrar múltiplas disciplinas.

### 🛑 Restrições de Integridade
- Não pode existir uma matrícula sem um aluno vinculado.
- Um curso não existe sem ao menos uma disciplina cadastrada.
- A nota deve obrigatoriamente estar associada ao par (Aluno, Disciplina).

---

## 🚀 3. Expansão dos Requisitos do Modelo

Com a evolução do sistema, foram incorporadas as seguintes regras avançadas:

1. **Pré-requisitos de Disciplinas:** Implementado via **Auto-relacionamento** na entidade `DISCIPLINA`.
2. **Departamentos:** Criada a entidade `DEPARTAMENTO` (`código_dep`, `nome`), onde um **Professor** pertence a um departamento *(N:1)*.
3. **Gestão de Bolsas:** Criada a entidade `BOLSA` (`tipo_bolsa`, `valor`), permitindo que um **Aluno** receba bolsa *(N:1)*.

---

## 📊 4. Ferramenta Utilizada

- Os diagramas conceituais e lógicos foram construídos utilizando a ferramenta visual **[draw.io (Diagrams.net)](https://app.diagrams.net/)**.
