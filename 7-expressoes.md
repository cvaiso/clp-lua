# Expressões
- Precedência e associatividade dos operadores:
| Precedência | Operador | Comentários | Associatividade |
| ----------- | ---------- | -------------------- | --------------- |
| 1 | ++ -- ! | Operadores Unários | R |
| 2 | * / % | Multi., Divi., Resto | L |
| 3 | + - | Add, Sub. | L |
| 4 | << >> | Shift | L |
| 5 | < > <= >= | Relacionais | L |
| 6 | == != | Igualdade | L |
| 7 | & | Bit/Loginal AND | L |
| 8 | ^ | XOR (ou exclusivo) | L |
| 9 | pipeline | Bit/Logical OR | L |
| 10 | && | AMD | L |
| 11 | 2 pipeline | OR | L |
| 12 | ?: | Condicional | R |
| 13 | = op= | Atribuição | R |

A tabela apresenta a ordem de precedência e associatividade dos operadores do Lua, em que os operadores de menor precedência aparecem no final da tabela. A coluna "Operador" apresenta o símbolo que representa o operador em questão, enquanto a coluna "Comentários" oferece um breve comentário sobre a função do operador. A coluna "Associatividade" indica se o operador é associativo à esquerda (L) ou à direita (R).
- A ordem de avaliação das expressões em Lua é definida pela ordem de precedência e associatividade dos operadores. Expressões com operadores de maior precedência são avaliadas primeiro. Quando há operadores com a mesma precedência, a associatividade é usada para determinar a ordem de avaliação.
- É importante destacar que Lua não possui transparência referencial, pois permite efeitos colaterais. Além disso, todos os operadores lógicos em Lua realizam avaliação curto-circuito.
- Lua permite a sobrecarga de operadores por metatables, mas não há como criar novos operadores.
