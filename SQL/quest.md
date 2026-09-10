# Questão 01 FGV

Considere um banco de dados relacional contendo as tabelas T, R e S, cujo instâncias são exibidas a seguir.
No contexto da instância da tabela S, considere a execução do comando SQL a seguir.

Assinale o conjunto de linhas que corresponde ao resultado produzido pelo referido comando 

a) 
| G | H | I |
|----|-------|----|
| 10 | 12040 | 12 |
| 10 | 12041 | 12 | 
                                                                                                
b) 
| G | H | I |
|----|-------|----|
| 10 | 12040 | 12 | 
| 10 | 12041 | 12 |  
| 50 | 1497 | 12 | 
   
c) 
| G | H | I |
|----|-----|----|
| 50 | 215 | 12 | 
| 70 |  214 |  20 | 

d)
| G | H | I |
|----|-------|----|
| 10 | 12040 | 12 |
| 10 | 12041 | 12 |
| 50 | 1497 | 12  |
| 50 | 1498 |  12 |

e)
| G | H | I |
|----|-------|----|
| 50 | 1497 | 12 |
| 50 | 1498 | 10 |

```
SELECT * FROM S WHERE (NOT G=10 OR I=12) AND NOT (H > 100 and H < 1000)
```


<img width="225" height="315" alt="image" src="https://github.com/user-attachments/assets/f0e90fc4-53cb-487b-be70-e25fde45c9a7" />

   
