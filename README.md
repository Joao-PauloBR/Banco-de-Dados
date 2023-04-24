# Banco de dados: criação de tabelas (modelo físico)

### 💡 Visão Geral 
- O trabalho foi escrito com a utilização dos comandos DDL(Data Definition Language) - Create, Alter, Drop - para a implementação de quatro tabelas e inserir restrições de tipo e valores de dados, utilizando o SQL Server.  

- A atividade teve como objetivo exercitar os conceitos trabalhados na disciplina de Banco de Dados - Relacional, administrada pelo professor [Mateus Guilherme Fuini](https://br.linkedin.com/in/mateusfuini) na instituição [FATEC Itapira](https://fatecitapira.edu.br/).

![Modelo Entidade Relacionamento(MER)](./img/mer.png)

## Contexto do exercício

### Tabela Cliente

Contém informações sobre os clientes da seguradora. Identificador exclusivo para CodCliente, tornando-o uma chave primária(PK) e, consequentemente, diferenciando cada cliente cadastrado. A tabela deve ter as colunas Nome, CPF, Sexo, Estado, Cidade, Bairro, Numero, Rua, TelefoneFixo e TelefoneCelular para armazenar informações pessoais e de contato dos clientes. As colunas possuem restrições[^1], como a coluna Nome que não pode ser nula (NOT NULL), e as colunas CPF e TelefoneCelular que devem ser únicas (UNIQUE). A coluna Cidade possui um valor padrão definido como 'Itapira', ou seja, caso a informação não seja fornecida, esse será o valor padrão atribuído.

```sql
-- Cliente:
CREATE TABLE Cliente
CodCliente INT
Nome VARCHAR(45)
CPF VARCHAR(45)
Sexo VARCHAR(20)
Estado VARCHAR(45)
Cidade VARCHAR(45)
Bairro VARCHAR(45)
Numero VARCHAR(45)
Rua VARCHAR(45)
TelefoneFixo VARCHAR(45)
TelefoneCelular VARCHAR(45)
```

```sql
-- Carro:
CREATE TABLE Carro
CodCarro INT
Placa VARCHAR(45) 
Marca VARCHAR(45) 
Modelo VARCHAR(45) 
Ano VARCHAR(45) 
Chassi VARCHAR(45) 
Cor VARCHAR(45)
```

```sql
-- Apolice
CREATE TABLE Apolice
CodApolice INT
ValorCobertura DECIMAL 
ValorFranquia DECIMAL
DataInicioVigencia DATE
DataFimVigencia DATE
Cliente_CodCliente INT
Carro_CodCarro INT
```

```sql
-- Sinistro:
CREATE TABLE Sinistro
CodSinistro INT
HoraSinistro INT
DataSinistro DATE
LocalSinistro VARCHAR(45)
Condutor VARCHAR(45)
Carro_CodCarro INT
```
