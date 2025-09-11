# Consultas SQL

- Operadores Relacionais:
    - <p>= (Igual)</p>
    - <p><> (Diferente)</p>
    - <p>> (Maior)</p>
    - <p>>= (Maior Igual)</p>
    - <p>< (Menor)</p>
    - <p><= (Menor Igual)</p>

    -- = (Igual)
    SELECT * FROM pedidos WHERE status = 'entregue';
    
    -- <> (Diferente)
    SELECT * FROM pedidos WHERE produto <> 'Café';
    
    -- > (Maior)
    SELECT * FROM pedidos WHERE quantidade > 10;
    
    -- >= (Maior ou Igual)
    SELECT * FROM pedidos WHERE preco_unitario >= 20;
    
    -- < (Menor)
    SELECT * FROM pedidos WHERE quantidade < 5;
    
    -- <= (Menor ou Igual)
    SELECT * FROM pedidos WHERE preco_unitario <= 10;

- BETWEEN, LIKE, IN

    -- BETWEEN: intervalo de datas
    SELECT * FROM pedidos WHERE data_pedido BETWEEN '2025-01-01' AND '2025-06-30';
    
    -- LIKE: busca por padrão (contém “café”)
    SELECT * FROM pedidos WHERE produto LIKE '%café%';
    
    -- IN: múltiplos valores
    SELECT * FROM pedidos WHERE produto IN ('Arroz', 'Feijão', 'Macarrão');


- ASC, DESC

    -- ASC: ordem crescente
    SELECT * FROM pedidos ORDER BY quantidade ASC;
    
    -- DESC: ordem decrescente
    SELECT * FROM pedidos ORDER BY data_pedido DESC;

- AS

    SELECT 
      cliente_nome AS cliente,
      produto AS item,
      quantidade AS qtde,
      preco_unitario AS preco
    FROM pedidos;

- LIMIT, OFFSET
     -- LIMIT: mostra os 5 primeiros registros
    SELECT * FROM pedidos LIMIT 5;
    
    -- OFFSET: pula os 5 primeiros e mostra os próximos 5
    SELECT * FROM pedidos LIMIT 5 OFFSET 5;
