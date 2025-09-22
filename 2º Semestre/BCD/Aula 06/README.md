# Funções SQL

## Funções de Agregação Numérica

- <p>SUM(): Soma os valores de uma coluna numérica</p>

```sql
SELECT SUM(quantidade) AS total_itens_vendidos FROM pedidos;
```

```sql
SELECT SUM(quantidade * preco_unitario) AS faturamento_total FROM pedidos;
```

- <p>AVG(): Média dos valores</p>

```sql
SELECT AVG(preco_unitario) AS preco_medio FROM pedidos;
```

```sql
SELECT AVG(quantidade) AS media_quantidade_por_pedido FROM pedidos;
```

- <p>COUNT(): Contagem de registros</p>

```sql
SELECT COUNT(*) AS total_pedidos FROM pedidos;
```

```sql
SELECT COUNT(DISTINCT cliente_nome) AS clientes_unicos FROM pedidos;
```

- <p>MAX(): Valor máximo</p>

```sql
SELECT MAX(preco_unitario) AS maior_preco FROM pedidos;
```

```sql
SELECT MAX(quantidade) AS maior_quantidade FROM pedidos;
```

- <p>MIN(): Valor mínimo</p>

```sql
SELECT MIN(preco_unitario) AS menor_preco FROM pedidos;
```

```sql
SELECT MIN(data_pedido) AS pedido_mais_antigo FROM pedidos;
```

## Funções de Texto

- <p>CONCAT(): Concatenação de colunas</p>

```sql
SELECT CONCAT(cliente_nome, ' comprou ', produto) AS descricao FROM pedidos;
```

```sql
SELECT CONCAT(produto, ' - ', status) AS item_status FROM pedidos;
```

- <p>LENGTH(): Tamanho do texto</p>

```sql
SELECT cliente_nome, LENGTH(cliente_nome) AS tamanho_nome FROM pedidos;
```

```sql
SELECT produto, LENGTH(produto) AS tamanho_produto FROM pedidos;
```

- <p>LOWER(): Texto em minúsculas</p>

```sql
SELECT LOWER(produto) AS produto_minusculo FROM pedidos;
```

```sql
SELECT LOWER(status) AS status_minusculo FROM pedidos;
```

- <p>UPPER(): Texto em maiúsculas</p>

```sql
SELECT UPPER(cliente_nome) AS nome_maiusculo FROM pedidos;
```

```sql
SELECT UPPER(produto) AS produto_maiusculo FROM pedidos;
```

## Funções Matemáticas

- <p>ROUND(): Arredondamento</p>

```sql
SELECT ROUND(preco_unitario) AS preco_inteiro FROM pedidos;
```

```sql
SELECT ROUND(quantidade * preco_unitario, 1) AS valor_total_arredondado FROM pedidos;
```

- <p>POW(): Potência</p>

```sql
SELECT produto, POW(quantidade, 2) AS quantidade_ao_quadrado FROM pedidos;
```

```sql
SELECT id, POW(2, id) AS dois_elevado_id FROM pedidos;
```

- <p>MOD(): Módulo (resto da divisão)</p>

```sql
SELECT id, MOD(id, 2) AS par_ou_impar FROM pedidos;
```

```sql
SELECT quantidade, MOD(quantidade, 3) AS resto_div_3 FROM pedidos;
```

## Funções de Data e Hora

- <p>NOW(): Data e hora atual</p>

```sql
SELECT NOW() AS data_hora_atual;
```

```sql
SELECT * FROM pedidos WHERE data_pedido < NOW();
```

- <p>CURDATE(): Data atual</p>

```sql
SELECT CURDATE() AS data_atual;
```

```sql
SELECT * FROM pedidos WHERE data_pedido < CURDATE();
```

- <p>DAY(), MONTH(), YEAR(): Partes da data</p>

```sql
SELECT data_pedido, DAY(data_pedido) AS dia FROM pedidos;
```

```sql
SELECT data_pedido, MONTH(data_pedido) AS mes, YEAR(data_pedido) AS ano FROM pedidos;
```
