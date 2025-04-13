#  Projeto de Banco de Dados - E-commerce

Este projeto consiste na modelagem de um banco de dados relacional para um sistema de e-commerce que suporta múltiplos vendedores (terceiros), diferentes tipos de clientes (PF e PJ), controle de estoque, formas de pagamento, e sistema de entrega com rastreio.

---

## Entidades Principais

- **Produto**: Itens disponíveis para compra.
- **Cliente**: Pessoas físicas ou jurídicas que realizam pedidos.
- **Pedido**: Compras realizadas por clientes.
- **Fornecedor**: Responsável por fornecer os produtos vendidos.
- **Estoque**: Locais que armazenam produtos.
- **Terceiro (Vendedor)**: Comercializa os produtos na plataforma.
- **Pagamento**: Formas de pagamento associadas a um pedido.
- **Entrega**: Informações de envio, status e rastreamento.
- **Cliente_PF / Cliente_PJ**: Representação específica do tipo de cliente.

---

## 🔗 Relacionamentos

- Um **cliente** pode fazer **múltiplos pedidos**.
- Um **pedido** pode conter **vários produtos** (relação N:N).
- Um **pedido** pode possuir **várias formas de pagamento**.
- Cada **pedido** possui uma **entrega** com código de rastreio e status.
- Cada **produto** é fornecido por um único **fornecedor**.
- Cada **produto** pode estar em **múltiplos estoques**.
- Cada **produto** pode ser vendido por **múltiplos vendedores terceiros**.
- Um **cliente** pode ser **Pessoa Física ou Jurídica**, mas não ambos.
- O **endereço do cliente** impacta no cálculo do frete.

---

## Regras de Negócio

- Um cliente deve se registrar com **CPF ou CNPJ**, nunca ambos.
- Produtos são vendidos **exclusivamente pela plataforma**, mas **enviados por vendedores terceiros**.
- Produtos podem ter **estoques em locais distintos**.
- Um **pedido pode ser cancelado** e também **devolvido em um prazo de carência**.

---

## Ferramentas Utilizadas

- **Draw.io** para modelagem do diagrama entidade-relacionamento (ER).
- **Modelo Relacional** com chaves primárias (PK) e estrangeiras (FK) identificadas.

---

##  Estrutura do Modelo

O modelo ER contempla as seguintes tabelas:

- `Cliente`, `Cliente_PF`, `Cliente_PJ`
- `Pedido`, `Entrega`, `Pagamento`
- `Produto`, `Produto_has_Estoque`, `Produtos_por_Vendedor`
- `Fornecedor`, `Estoque`
- Tabela associativa: `Relação de Produto/Pedido` (N:N entre pedido e produto)

---
