## Classificação dos Comandos (Linguagens)

| Categoria | Sigla | Função | Comandos Chave | 
|-----------|-------|--------|----------------|
| **Data Definition Language** | DDL | Define/altera a estrutura do banco | `CREATE`, `ALTER`, `DROP`, `TRUNCATE`, `RENAME`, | 
| **Data Manipulation Language** | DML | Manipula os dados nas tabelas | `INSERT`, `UPDATE`, `DELETE`, `SELECT*` | 
| **Data Control Language** | DCL | Controla permissões de acesso | `GRANT`, `REVOKE` | 
| **Transaction Control Language** | TCL / DTL | Gerencia transações | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | 


*Nota de prova: O SELECT é classificado como DML em quase todas as bancas (embora alguns autores o chamem de DQL — Data Query Language).

### 2. Ordem de Execução Lógica do SELECT
A banca tenta enganar você com a ordem em que você escreve o código vs. a ordem em que o SGBD executa.


```Plaintext

Ordem de ESCRITA                  Ordem de EXECUÇÃO LÓGICA
1. SELECT                         1. FROM / JOIN
2. FROM                           2. WHERE
3. WHERE                          3. GROUP BY
4. GROUP BY                       4. HAVING
5. HAVING                         5. SELECT
6. ORDER BY                       6. DISTINCT
7. LIMIT / OFFSET                 7. ORDER BY
                                  8. LIMIT / OFFSET

```

## 3. Guia Rápido de JOINs

| Tipo | O que faz | Retorno | 
|------|-----------|---------|
| `INNER JOIN` | Intersecção | Apenas registros que existem em ambas as tabelas. | 
| `LEFT JOIN` | Tabela da esquerda + correspondentes | Todos da esquerda; se não houver par na direita, traz `NULL`. | 
| `RIGHT JOIN` | Tabela da direita + correspondentes | Todos da direita; se não houver par na esquerda, traz `NULL`. | 
| `FULL OUTER JOIN` | União completa | Todos os registros de ambas as tabelas, preenchendo com `NULL` onde não há correspondência. | 
| `CROSS JOIN` | Produto cartesiano | Combina cada linha da Tabela A com todas as linhas da Tabela B (**N** \times **M** linhas). Não usa `ON`. | 


## 4. As Pegadinhas Clássicas de Prova
`WHERE` vs. `HAVING`
  * `WHERE`: Filtra linhas antes do agrupamento. NÃO aceita funções de agregação (ex: `WHERE SUM(valor) > 100` gera erro!).
  * `HAVING`: Filtra grupos após o `GROUP BY`. Aceita funções de agregação (ex: `HAVING COUNT(*) > 5`).

`DELETE` vs. `TRUNCATE`
  * `DELETE` (DML): Apaga linhas especificadas (usa `WHERE`). É mais lento, gera log para cada linha apaga e aceita `ROLLBACK`.
  * `TRUNCATE` (DDL): Esvazia a tabela inteira de uma vez. É mais rápido, reseta auto-incremento e geralmente não permite `ROLLBACK` direto.

Comportamento do `NULL`
  * `NULL` representa a ausência de valor (desconhecido).
  * `NULL = NULL` resulta em `UNKNOWN` (falso em condições `WHERE`). Para testar, use obrigatoriamente `IS NULL` ou `IS NOT NULL`.
  * Funções de agregação como `AVG()`, `SUM()`, `COUNT(coluna)` ignoram valores NULL no cálculo. A exceção é o `COUNT(*)`, que conta todas as linhas incluindo nulas.

`GROUP BY` e as Colunas do `SELECT`
Se você usa `GROUP BY`, toda coluna presente na cláusula `SELECT` que não seja uma função de agregação (`SUM`, `COUNT`, `AVG`, etc.) deve constar obrigatoriamente na cláusula `GROUP BY`.


## 5. Funções de Agregação e Texto Frequentes
  * **Agregação**: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
  * **Opções** `LIKE`:
    * `%`: Representa zero ou vários caracteres.
    * `_` (underline): Representa exatamente um caractere.
    * Exemplo: `WHERE nome LIKE 'A_o%'` (Começa com 'A', segunda letra qualquer, terceira 'o', e qualquer coisa depois).

