# Consultas SQL

- Operadores Relacionais:
    - <p>= (Igual)</p>
    ```sql
    SELECT * FROM pedidos WHERE status = "entregue";
    ```
    - <p><> (Diferente)</p>
    ```sql
    SELECT * FROM pedidos WHERE produto <> "Café";
    ```
    - <p>> (Maior)</p>
    ```sql
    SELECT * FROM pedidos WHERE quantidade > 10;
    ```
    - <p>>= (Maior Igual)</p>
    ```sql
    SELECT * FROM pedidos WHERE preco_unitario >= 20;
    ```
    - <p>< (Menor)</p>
    ```sql
    SELECT * FROM pedidos WHERE quantidade < 5;
    ```
    - <p><= (Menor Igual)</p>
    ```sql
    SELECT * FROM pedidos WHERE preco_unitario <= 10;
    ```

- BETWEEN, LIKE, IN

    - BETWEEN: intervalo entre valores
    ```sql
    SELECT * FROM pedidos WHERE data_pedido BETWEEN "2025-01-01" AND "2025-06-30";
    ```
    
    - LIKE: busca por padrão (contém)
    ```sql
    SELECT * FROM pedidos WHERE produto LIKE "%café%";
    ```
    
    - IN: múltiplos valores
    ```sql
    SELECT * FROM pedidos WHERE produto IN ("Arroz", "Feijão", "Macarrão");
    ```


- ASC, DESC

    - ASC: ordem crescente
    ```sql
    SELECT * FROM pedidos ORDER BY quantidade ASC;
    ```
    
    -- DESC: ordem decrescente
    ```sql
    SELECT * FROM pedidos ORDER BY data_pedido DESC;
    ```

- AS: Renomeia uma coluna

    ```sql
    SELECT 
      cliente_nome AS "cliente",
      produto AS "item",
      quantidade AS "qtde",
      preco_unitario AS "preco"
    FROM pedidos;
    ```

- LIMIT, OFFSET
  
     - LIMIT: Define o número de registros a ser exibido
    ```sql
    SELECT * FROM pedidos LIMIT 5;
    ```
    
    -- OFFSET: Retorna registros a partir de uma posição
    ```sql
    SELECT * FROM pedidos LIMIT 5 OFFSET 5;
    ```
