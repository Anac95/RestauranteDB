# RestauranteDB
DB restaurante fictício no MySQL 
# Restaurante - Sistema de Gestão de Funcionários, Clientes e Pedidos

Este é um sistema simples de gerenciamento de um restaurante, desenvolvido para gerenciar funcionários, clientes, produtos e pedidos. O banco de dados contém tabelas para armazenar informações sobre os funcionários do restaurante, os clientes que realizam pedidos, os produtos oferecidos no cardápio, e os pedidos realizados pelos clientes.

## Estrutura do Banco de Dados

O banco de dados foi projetado com as seguintes tabelas:

### 1. Funcionários
Armazena informações sobre os funcionários do restaurante, incluindo dados pessoais e informações sobre o cargo, salário e data de admissão.

**Campos**:
- `id_funcionarios` (PK): Identificador único do funcionário.
- `nome`: Nome completo do funcionário.
- `cpf`: CPF do funcionário.
- `data_nascimento`: Data de nascimento do funcionário.
- `endereço`: Endereço residencial.
- `telefone`: Número de telefone de contato.
- `email`: Endereço de e-mail.
- `cargo`: Cargo ou posição do funcionário no restaurante.
- `salario`: Salário do funcionário.
- `data_admissao`: Data de admissão no restaurante.

### 2. Clientes
Armazena informações sobre os clientes do restaurante, com dados pessoais e histórico de cadastro.

**Campos**:
- `id_cliente` (PK): Identificador único do cliente.
- `nome`: Nome completo do cliente.
- `cpf`: CPF do cliente.
- `data_nascimento`: Data de nascimento do cliente.
- `endereco`: Endereço de residência do cliente.
- `telefone`: Número de telefone de contato.
- `email`: Endereço de e-mail.
- `data_cadastro`: Data de cadastro do cliente no sistema.

### 3. Produtos
Armazena informações sobre os produtos disponíveis no cardápio, incluindo descrição, preço e categoria.

**Campos**:
- `id_produto` (PK): Identificador único do produto.
- `nome`: Nome do produto.
- `descricao`: Descrição detalhada do produto.
- `preco`: Preço do produto.
- `categoria`: Categoria do produto (ex: Prato Principal, Bebida, Sobremesa, etc.).

### 4. Pedidos
Armazena informações sobre os pedidos realizados pelos clientes, incluindo dados sobre o cliente, o funcionário responsável, os produtos adquiridos, quantidade, preço e status do pedido.

**Campos**:
- `id_pedido` (PK): Identificador único do pedido.
- `id_cliente` (FK): Identificador do cliente que fez o pedido.
- `id_funcionarios` (FK): Identificador do funcionário responsável pelo pedido.
- `id_produto` (FK): Identificador do produto solicitado.
- `quantidade`: Quantidade do produto solicitado.
- `preco`: Preço total do pedido.
- `data_pedido`: Data de realização do pedido.
- `status_pedido`: Status do pedido (ex: Concluído, Pendente, etc.).

## Comandos SQL Utilizados

O projeto inclui várias operações SQL para manipulação e consulta dos dados no banco. Alguns dos principais comandos SQL são:

### Criação das Tabelas
```sql
CREATE TABLE Funcionarios (
    id_funcionarios INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    cpf VARCHAR(14),
    data_nascimento DATE,
    endereco VARCHAR(255),
    telefone VARCHAR(15),
    email VARCHAR(100),
    cargo VARCHAR(100),
    salario DECIMAL(10, 2),
    data_admissao DATE,
    UNIQUE(email)
);
### Inserção de Dados
INSERT INTO Funcionarios (nome, cpf, data_nascimento, endereco, telefone, email, cargo, salario, data_admissao)
VALUES
('Ricardo Sousa', '111.222.333-44', '1992-05-12', 'Rua Harmonia 157. São Paulo', '11987651234', 'ricardo.sousa@email.com', 'Chefe de Cozinha', 6000.00, '2019-03-15');

### Atualização de Dados
sql
Copiar
UPDATE Funcionarios
SET cargo = 'Garçonete', salario = 2700.00
WHERE id_funcionarios = 4;

### Seleção de Dados
sql
Copiar
SELECT nome, cargo, salario
FROM Funcionarios
WHERE salario > 3000;

### Instruções para Execução
Configuração do Banco de Dados:

1. Crie um banco de dados chamado Restaurante.

2. Importe as tabelas fornecidas para o banco de dados.

Inserção de Dados:

Insira os dados nas tabelas utilizando os comandos de INSERT INTO.

3. Consultas e Atualizações:

Execute as consultas e atualizações para manipular os dados conforme necessário.

Contribuições
Se você deseja contribuir para o projeto, faça um fork deste repositório, faça as alterações desejadas e envie um pull request.

Licença
Este projeto é de uso livre, sem garantia de qualquer tipo.
