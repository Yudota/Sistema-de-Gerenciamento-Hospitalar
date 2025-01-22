# Bounded Contexts de E-commerce

## 1. Bounded Context: Gerenciamento de Produtos
- **Responsabilidade**: Gerenciar informações sobre os produtos, como cadastro, alteração, inativação e consulta.
- **Entidades**:
  - Produto
  - Categoria
  - Imagem de Produto
- **Ações principais**:
  - Cadastro de produto
  - Edição de produto
  - Inativação
  - Consulta e pesquisa de produtos
- **Exemplo de Regras**:
  - Validação de preço
  - Requisitos de dados obrigatórios para cadastro de produtos


## 2. Bounded Context: Gerenciamento de Estoque
- **Responsabilidade**: Controlar o inventário de produtos, incluindo a entrada, saída e controle de estoque.
- **Entidades**:
  - Estoque
  - Entrada de Estoque
  - Saída de Estoque
- **Ações principais**:
  - Registrar entradas e saídas
  - Controle de reposição de estoque
- **Exemplo de Regras**:
  - Bloqueio de itens para o carrinho de compras
  - Controle de estoque baixo
  - Reabastecimento automático


## 3. Bounded Context: Gerenciamento de Clientes
- **Responsabilidade**: Gerenciar o cadastro de clientes, dados pessoais, endereços e histórico de compras.
- **Entidades**:
  - Cliente
  - Endereço
  - Histórico de Compras
  - Lista de Desejos
- **Ações principais**:
  - Cadastro de cliente
  - Alteração de dados
  - Login
  - Consulta de histórico de compras
- **Exemplo de Regras**:
  - Validação de CPF
  - Restrição de número de endereços


## 4. Bounded Context: Carrinho de Compras
- **Responsabilidade**: Gerenciar o carrinho de compras, incluindo adição, remoção, alteração de quantidades e cálculo do total.
- **Entidades**:
  - Carrinho
  - Item de Carrinho
- **Ações principais**:
  - Adicionar, remover e alterar a quantidade de itens no carrinho
  - Aplicar cupom de desconto
  - Calcular frete
- **Exemplo de Regras**:
  - Preço total do carrinho
  - Validade do cupom
  - Bloqueio de produtos no estoque


## 5. Bounded Context: Processamento de Pedidos
- **Responsabilidade**: Gerenciar o processo de finalização de compras, incluindo escolha de pagamento, confirmação de pedido e emissão de nota fiscal.
- **Entidades**:
  - Pedido
  - Pagamento
  - Nota Fiscal
- **Ações principais**:
  - Finalizar compra
  - Registrar pagamento
  - Gerar nota fiscal
  - Alterar status do pedido
- **Exemplo de Regras**:
  - Validação do pagamento
  - Status do pedido
  - Cancelamento


## 6. Bounded Context: Pagamento e Cobrança
- **Responsabilidade**: Gerenciar transações financeiras, processamento de pagamentos e controle de estornos.
- **Entidades**:
  - Transação
  - Cartão de Crédito
  - Boleto Bancário
  - Estorno
- **Ações principais**:
  - Processar pagamento
  - Estorno de pagamento
  - Validar dados de pagamento
- **Exemplo de Regras**:
  - Validação do cartão de crédito
  - Aprovação de pagamento


## 7. Bounded Context: Promoções e Cupons
- **Responsabilidade**: Gerenciar promoções, cupons de desconto e validações de promoções aplicáveis aos pedidos.
- **Entidades**:
  - Cupom de Desconto
  - Promoção
- **Ações principais**:
  - Criar e aplicar cupons de desconto
  - Definir promoções por produto
- **Exemplo de Regras**:
  - Validade de cupons
  - Quantidade máxima de descontos por pedido


## 8. Bounded Context: Relatórios e Análises
- **Responsabilidade**: Gerar relatórios sobre vendas, clientes e estoque, proporcionando informações analíticas para os administradores.
- **Entidades**:
  - Relatório de Vendas
  - Relatório de Estoque
  - Relatório de Clientes
- **Ações principais**:
  - Gerar relatórios de vendas
  - Gerar relatórios de estoques
  - Gerar relatórios de clientes
- **Exemplo de Regras**:
  - Periodicidade de geração dos relatórios
  - Formato dos relatórios


## 9. Bounded Context: Segurança e Autenticação
- **Responsabilidade**: Gerenciar a autenticação de usuários, segurança dos dados e compliance com regulamentações como a LGPD.
- **Entidades**:
  - Usuário
  - Sessão
  - Log de Ações
- **Ações principais**:
  - Login
  - Autenticação de dois fatores
  - Criptografia de dados
  - Auditoria
- **Exemplo de Regras**:
  - Regras de autenticação
  - Auditoria de ações de administradores
  - Compliance com LGPD
