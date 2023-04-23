## Banco de dados: criação de tabelas (modelo físico)

### 💡 Visão Geral 
- O trabalho foi escrito com a utilização dos comandos DDL(Data Definition Language) - Create, Alter, Drop - para a implementação de quatro tabelas e inserir restrições de tipo e valores de dados, utilizando o SQL Server.  

- A atividade teve como objetivo exercitar os conceitos trabalhados na disciplina de Banco de Dados - Relacional, administrada pelo professor [Mateus Guilherme Fuini](https://br.linkedin.com/in/mateusfuini) na instituição [FATEC Itapira](https://fatecitapira.edu.br/).


Create table Cliente(
	CodCliente int primary key,
	Nome varchar(45) not null,
	CPF varchar(45) not null unique,
	Sexo varchar(20),
	Estado varchar(45),
	Cidade varchar(45) default 'Itapira',
	Bairro varchar(45),
	Numero varchar(45),
	Rua varchar(45),
	TelefoneFixo varchar(45),
	TelefoneCelular varchar(45) not null unique,
)
create table Carro(
	CodCarro int primary key,
	Placa varchar(45) not null,
	Marca varchar(45) not null,
	Modelo varchar(45) not null,
	Ano varchar(45) not null,
	Chassi varchar(45) not null,
	Cor varchar(45),
)
create table Apolice(
	CodApolice int primary key,
	ValorCobertura decimal not null,
	ValorFranquia decimal not null,
	DataInicioVigencia date check (DataInicioVigencia> getdate()),
	DataFimVigencia date not null,
	Cliente_CodCliente int references Cliente(CodCliente),
	Carro_CodCarro int references Carro(CodCarro),
)
create table Sinistro(
	CodSinistro int,
	HoraSinistro int,
	DataSinistro date,
	LocalSinistro varchar(45),
	Condutor varchar(45),
	Carro_CodCarro int,
	constraint pk_Sinistro primary key (CodSinistro, Carro_CodCarro),
	constraint fk_Sinistro foreign key (Carro_CodCarro) references Carro(CodCarro),
)
