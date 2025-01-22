# Documento de Requisitos para E-commerce

## Introdução
Este documento detalha os requisitos funcionais, não funcionais e regras de negócio para o desenvolvimento de um sistema de e-commerce focado em produtos não perecíveis. O objetivo é priorizar os modelos críticos, considerando os domínios definidos e as melhores práticas para sistemas escaláveis e seguros.

---

## Requisitos Funcionais

### Grupo: Gerenciamento de Produtos
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RF001    | Cadastrar produto                | O sistema deve permitir o cadastro único de produtos com informações como nome, descrição, código, categoria, e preço. |
| RF002    | Alterar cadastro de produto      | Deve ser possível editar informações de produtos já cadastrados.                                                     |
| RF003    | Inativar produto                 | O sistema deve possibilitar a inativação de produtos para impedir sua venda, justificando o motivo.               |
| RF004    | Consultar produtos               | Deve ser possível buscar produtos com filtros combinados ou isolados por código, nome, categoria ou preço.        |

### Grupo: Gerenciamento de Estoque
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RF010    | Controle de entrada e saída     | Registrar entradas e saídas de estoque, identificando o responsável pela operação.                                      |
| RF011    | Atualização automática          | Atualizar automaticamente o estoque após compras, devoluções ou cancelamentos.                               |
| RF012    | Notificação de estoque baixo    | Alertar quando a quantidade de produtos estiver abaixo de um limite predefinido.                              |

### Grupo: Gerenciamento de Clientes
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RF020    | Cadastro de cliente               | O sistema deve permitir o registro de clientes com dados como nome, e-mail, CPF, telefone e endereço.             |
| RF021    | Alterar dados cadastrais          | Deve ser possível que os clientes atualizem seus dados pessoais e senhas.                                          |
| RF022    | Cadastro de endereços            | Associar múltiplos endereços aos clientes, identificados por um nome descritivo.                                   |
| RF023    | Histórico de compras              | Consultar histórico de compras realizadas pelo cliente com opção de reordenar produtos.                            |

### Grupo: Gerenciamento de Vendas
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RF030    | Gerenciar carrinho de compras     | Permitir adicionar, remover e alterar a quantidade de itens no carrinho.                                     |
| RF031    | Calcular frete                    | Calcular o frete com base no endereço de entrega e peso total dos produtos no carrinho.                       |
| RF032    | Finalizar compra                  | Realizar a finalização da compra após seleção do método de pagamento e endereço de entrega.                  |
| RF033    | Cancelar pedido                   | Permitir o cancelamento de pedidos antes de sua aprovação ou envio.                                           |

---

## Requisitos Não Funcionais

### Desempenho
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RNF001   | Tempo de resposta                 | Toda consulta deve ser realizada em até 1 segundo para buscas simples e 2 segundos para buscas complexas.           |
| RNF002   | Alta disponibilidade              | O sistema deve garantir 99,9% de uptime mensal.                                                        |

### Segurança
| Código   | Nome do Requisito                 | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RNF010   | Criptografia de dados sensíveis  | Dados como senhas e informações de pagamento devem ser armazenados de forma criptografada.                       |
| RNF011   | Logs de auditoria                 | Registrar ações de usuários e administradores com data, horário e detalhes das operações.                     |

---

## Regras de Negócio

### Produtos
| Código   | Nome da Regra                   | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RN001    | Cadastro obrigatório             | Nome, código, categoria e preço são obrigatórios para o cadastro de qualquer produto.                           |
| RN002    | Validação de preços              | Preços não podem ser inferiores ao custo do produto mais a margem de lucro definida pelo sistema.              |

### Estoque
| Código   | Nome da Regra                   | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RN010    | Bloqueio de itens                | Produtos adicionados ao carrinho devem ser temporariamente bloqueados no estoque.                             |
| RN011    | Reabastecimento automático       | Sugestão de reabastecimento gerada automaticamente quando o estoque estiver abaixo do limite.                |

### Clientes
| Código   | Nome da Regra                   | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RN020    | Validação de CPF                | O CPF fornecido no cadastro deve ser válido e único no sistema.                                                |
| RN021    | Limitação de endereços         | Cada cliente pode cadastrar até 5 endereços de entrega.                                                       |

### Vendas
| Código   | Nome da Regra                   | Descrição                                                                                                     |
|----------|-----------------------------------|-------------------------------------------------------------------------------------------------------|
| RN030    | Validação de pagamento          | Uma compra só é finalizada após a aprovação do pagamento pela operadora.                                    |
| RN031    | Cupom promocional                | Apenas um cupom promocional pode ser utilizado por pedido.                                           |

---

## Conclusão
Este documento define as bases para o desenvolvimento inicial do sistema de e-commerce, priorizando funcionalidades essenciais e regras de negócio críticas. Os próximos passos incluem a modelagem detalhada dos casos de uso e a implementação inicial.

