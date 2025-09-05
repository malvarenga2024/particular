# DBA Challenge 20240802
# Projeto SQL - Sistema de Vendas

Projeto em SQL para criação e manipulação de um banco de dados de vendas, contendo tabelas de usuários, produtos e pedidos.

## Tecnologias

Este projeto utiliza as seguintes tecnologias:

- Linguagem: SQL
- Banco de Dados: MySQL 
- Ferramenta recomendada:DBeaver

## Instalação e Uso

1. **Clone este repositório**:
   ```bash
   git clone https://github.com/seu-usuario/projeto-sql.git
Acesse a pasta do projeto:

sql

-- Create Produtos_nao_comprados

select * from products p
inner join order_itens oi on oi.product_id = p.product_id;

-- Create Produtos_em_estoque

select * from products p
inner join stocks s on s.product_id = p.product_id
where quantity > 0;

-- Funcionarios_sem_pedido

select *
from staffs s
inner join orders o on o.store_id = s.staff_id;

-- Cliente_sem_compra

select * from customers c
inner join orders o on o.customer_id = c.customer_id;


-- Create Agrupar_marca_por_loja

select b.brand_name, s.store_name, count(1)
from stores s
inner join orders o on o.store_id = s.store_id
inner join order_itens oi on oi.order_id = o.order_id
inner join products p on p.product_id = oi.product_id
inner join brands b on b.brand_id = p.brand_id
group by b.brand_name, s.store_name;


vidas sobre o processo envie uma mensagem diretamente a um especialista no chat da plataforma. 
