## Banco de dados: criação de tabelas (modelo físico)

### 💡 Visão Geral 
- O trabalho foi escrito com a utilização dos comandos DDL(Data Definition Language) - Create, Alter, Drop - para a implementação de quatro tabelas e inserir restrições de tipo e valores de dados, utilizando o SQL Server.  

- A atividade teve como objetivo exercitar os conceitos trabalhados na disciplina de Banco de Dados - Relacional, administrada pelo professor [Mateus Guilherme Fuini](https://br.linkedin.com/in/mateusfuini) na instituição [FATEC Itapira](https://fatecitapira.edu.br/).

![Modelo Entidade Relacionamento(MER)](./img/Ativadade DDL.png)

## Cliente

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
