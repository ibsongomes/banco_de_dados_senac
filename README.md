# Banco de Dados — Projeto Senac

Este repositório contém o projeto desenvolvido para a atividade de Banco de Dados do Senac.  
O objetivo foi criar um banco de dados completo utilizando comandos DDL e DML, aplicados a um comércio fictício.

---

## Sobre o Banco de Dados

O banco foi criado para representar uma **cafeteria**, contendo tabelas como:

- Produtos  
- Clientes  
- Pedidos

Cada tabela foi definida utilizando comandos **DDL**, e posteriormente preenchida com exemplos de **DML**.

---
## DDL

**DDL (Data Definition Language)** é o conjunto de comandos responsáveis por definir a estrutura do banco de dados.  
É com DDL que criamos, alteramos ou excluímos tabelas e bancos.

### **Principais comandos DDL**
- `CREATE` → cria bancos e tabelas  
- `ALTER` → altera uma tabela existente  
- `DROP` → exclui uma tabela ou banco

#### Exemplos de DDL usados no projeto:

 1- Criando a tabela **Produtos**

```sql
CREATE TABLE Produtos (
    ProdutoID INT PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Categoria VARCHAR(50),
    Preco DECIMAL(10,2) NOT NULL,
    Estoque INT NOT NULL
);
```
2- Criando a tabela **Cliente**
```sql
CREATE TABLE Clientes (
    ClienteID INT AUTO_INCREMENT PRIMARY KEY,
    Nome VARCHAR(100) NOT NULL,
    Telefone VARCHAR(20),
    Email VARCHAR(100)
);
```
3- Criando a tabela **Pedidos**
```sql
CREATE TABLE Pedidos (
    PedidoID INT AUTO_INCREMENT PRIMARY KEY,
    ClienteID INT,
    DataPedido DATETIME DEFAULT CURRENT_TIMESTAMP,
    ValorTotal DECIMAL(10,2),

    FOREIGN KEY (ClienteID) REFERENCES Clientes(ClienteID)
);
```
---
## DML

Os comandos **DML (Data Manipulation Language)** são responsáveis por **manipular os dados** dentro das tabelas do banco.  
Eles permitem inserir, consultar, atualizar e apagar registros.

### Principais Comandos DML

- **INSERT** → Insere novos dados  
- **SELECT** → Consulta dados já existentes  
- **UPDATE** → Atualiza registros  
- **DELETE** → Remove registros  

Todos esses comandos foram utilizados nas tabelas criadas no projeto:  
**Produtos**, **Clientes** e **Pedidos**.

#### Exemplos de Insert na tabela **Produtos**:


```sql
INSERT INTO Produtos (Nome, Categoria, Preco, Estoque)
VALUES ('Café Expresso', 'Bebida', 5.00, 30);

INSERT INTO Produtos (Nome, Categoria, Preco, Estoque)
VALUES ('Cappuccino', 'Bebida', 8.50, 20);

INSERT INTO Produtos (Nome, Categoria, Preco, Estoque)
VALUES ('Pão de Queijo', 'Salgado', 4.00, 50);
```
