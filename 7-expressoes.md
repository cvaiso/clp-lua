# Expressões
- Precedência e associatividade dos operadores:
| Precedência | Operador | Comentários | Associatividade |
| ----------- | ---------- | -------------------- | --------------- |
| 1 | ^ | Exponencial | direita |
| 2 | not     -(unary)     # | neg., comprimento| esquerda |
| 3 | *     /     % | Mult., Div., Resto | esquerda |
| 4 | +     - | Soma, Sub. | esquerda |
| 5 | .. | Concatenação | direita |
| 6 | <     >     <=    >=    ~=    == | Relacionais | esquerda |
| 7 | and | e lógico | esquerda |
| 8 | or | ou lógico | esquerda |

A tabela apresenta a ordem de precedência e associatividade dos operadores do Lua, em que os operadores de menor precedência aparecem no final da tabela. 
A coluna "Operador" apresenta o símbolo que representa o operador em questão, enquanto a coluna "Comentários" oferece um breve comentário sobre a função do operador. 
A coluna "Associatividade" indica se o operador é associativo à esquerda ou à direita.
- A ordem de avaliação das expressões em Lua é definida pela ordem de precedência e associatividade dos operadores. Expressões com operadores de maior precedência são avaliadas primeiro. Quando há operadores com a mesma precedência, a associatividade é usada para determinar a ordem de avaliação.
- É importante destacar que Lua não possui transparência referencial, pois permite efeitos colaterais. 
- Os operadores lógicos em Lua realizam avaliação curto-circuito.
- Lua permite a sobrecarga de operadores apenas por metatables, mas não há como criar novos operadores.
Por exemplo, você pode definir o metamétodo __add para personalizar a operação de adição (+) para seus objetos personalizados. Quando o operador + é usado entre dois objetos com uma metatabela definida, o metamétodo __add é chamado para realizar a operação desejada.
