## Modelo de Domínio (MD) do E-commerce

### 1. Contexto de Vendas
Responsável por tudo relacionado ao processo de compra: produtos, pedidos, carrinho, descontos, e status do pedido.

#### Entidades:
- **Pedido**: Representa um pedido feito por um cliente.
  - Atributos: ID, Data, Status, Valor Total, Cliente (associado), Itens de Pedido (associados).
  - Relacionamentos: Vinculado a um cliente, contém múltiplos itens de pedido, pode ter um pagamento vinculado.
  
- **Produto**: Representa um item disponível para compra.
  - Atributos: ID, Nome, Descrição, Preço, Estoque.
  - Relacionamentos: Pode estar presente em vários itens de pedido.
  
- **Item de Pedido**: Representa um produto dentro de um pedido.
  - Atributos: ID, Quantidade, Preço Unitário.
  - Relacionamentos: Pertence a um pedido, associado a um produto.
  
- **Carrinho de Compras**: Representa o carrinho de compras do cliente, onde ele armazena os itens antes de realizar o pedido.
  - Atributos: ID, Produtos (com quantidade), Cliente (associado).
  - Relacionamentos: Associado a um cliente, contém múltiplos produtos.
  
- **Desconto/Cupom**: Representa um cupom de desconto que pode ser aplicado ao pedido.
  - Atributos: ID, Código, Desconto Percentual, Data de Validade.
  - Relacionamentos: Pode ser aplicado em um pedido.

### 2. Contexto de Estoque
esponsável por controlar o estoque de produtos, incluindo a atualização de quantidade e a reserva de produtos para pedidos.

#### Entidades:
- **Produto**: Representa os produtos vendidos, incluindo o controle de estoque.
  - Atributos: ID, Nome, Descrição, Preço, Quantidade em Estoque.
  - Relacionamentos: Cada produto pode ser parte de múltiplos itens de pedido.
  
- **Estoque**: Representa a quantidade disponível do produto.
  - Atributos: ID, Quantidade Disponível.
  - Relacionamentos: Cada produto pode ter um estoque vinculado.

### 3. Contexto de Clientes
Responsável pela gestão de informações dos clientes, como dados pessoais, histórico de compras, preferências, e endereço.

#### Entidades:
- **Cliente**: Representa o cliente do e-commerce.
  - Atributos: ID, Nome, Email, Telefone, Endereço.
  - Relacionamentos: Um cliente pode fazer múltiplos pedidos.

- **Endereço**: Representa o endereço de entrega ou cobrança do cliente.
  - Atributos: ID, Rua, Número, Complemento, Bairro, Cidade, Estado, CEP.
  - Relacionamentos: Cada cliente pode ter múltiplos endereços.

- **Histórico de Compras**: Representa o histórico de compras feitas pelo cliente.
  - Atributos: ID, Lista de Pedidos, Data de Compra.
  - Relacionamentos: Relacionado a múltiplos pedidos feitos pelo cliente.

### 4. Contexto de Pagamento
Responsável por todo o processo de pagamento: métodos, status de pagamento, e transações associadas a um pedido.

#### Entidades:
- **Pagamento**: Representa o pagamento de um pedido.
  - Atributos: ID, Valor, Status (Pendente, Concluído, Cancelado), Método de Pagamento (Cartão, Boleto, Pix).
  - Relacionamentos: Vinculado a um pedido.
  
- **Transação de Pagamento**: Representa os detalhes de uma transação de pagamento.
  - Atributos: ID, Código de Transação, Status da Transação, Data.
  - Relacionamentos: Cada pagamento pode ter uma ou mais transações.

### 5. Contexto de Logística
Responsável por gerenciar o processo de entrega dos pedidos, incluindo rastreamento e informações sobre transportadoras.

#### Entidades:
- **Envio**: Representa o envio de um pedido para o cliente.
  - Atributos: ID, Data de Envio, Transportadora, Código de Rastreio, Status de Envio.
  - Relacionamentos: Associado a um pedido, possui um transportador.
  
- **Transportadora**: Representa a transportadora responsável pela entrega.
  - Atributos: ID, Nome, Detalhes de Contato.
  - Relacionamentos: Cada envio pode ter uma transportadora.

### Resumo das Entidades por Contexto Delimitado

| **Contexto Delimitado**    | **Entidades**                                                                 |
|----------------------------|-------------------------------------------------------------------------------|
| **Vendas**                 | Pedido, Produto, Item de Pedido, Carrinho de Compras, Desconto/Cupom         |
| **Estoque**                | Produto, Estoque                                                              |
| **Clientes**               | Cliente, Endereço, Histórico de Compras                                       |
| **Pagamento**              | Pagamento, Transação de Pagamento                                             |
| **Logística**              | Envio, Transportadora                                                         |
