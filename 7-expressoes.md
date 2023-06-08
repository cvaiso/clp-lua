# Expressões
- Precedência e associatividade dos operadores:

| Precedência | Operador | Comentários | Associatividade |
| ----------- | ---------- | -------------------- | --------------- |
| 1 | `^` | Exponencial | direita |
| 2 | `not - ~ #` | Unarios | esquerda |
| 3 | `* / // %` | Mult., Div., Resto | esquerda |
| 4 | `+ -` | Soma, Sub. | esquerda |
| 5 | `..` | Concatenação | direita |
| 6 | `<< >>` | Bit Shifts | esquerda |
| 7 | `&` | Bitwise And | esquerda |
| 8 | `~` | Bitwise Xor | esquerda |
| 9 | `\|` | Bitwise Or | esquerda |
|10 | `< > <= >= ~= ==` | Relacionais | esquerda |
|11 | `and` | E Lógico | esquerda |
|12 | `or` | Ou Lógico | esquerda |

A tabela apresenta a ordem de precedência e associatividade dos operadores do Lua, em que os operadores de menor precedência aparecem no final da tabela. 
A coluna "Operador" apresenta o símbolo que representa o operador em questão, enquanto a coluna "Comentários" oferece um breve comentário sobre a função do operador. 
A coluna "Associatividade" indica se o operador é associativo à esquerda ou à direita.

- A ordem de avaliação das expressões em Lua é definida pela ordem de precedência e associatividade dos operadores. Expressões com operadores de maior precedência são avaliadas primeiro. Quando há operadores com a mesma precedência, a associatividade é usada para determinar a ordem de avaliação.
- É importante destacar que Lua não possui transparência referencial, pois permite efeitos colaterais. 
- Os operadores lógicos em Lua realizam avaliação curto-circuito.
- Lua permite a sobrecarga de operadores apenas por metatables, mas não há como criar novos operadores.
Por exemplo, você pode definir o metamétodo __add para personalizar a operação de adição (+) para seus objetos personalizados. Quando o operador + é usado entre dois objetos com uma metatabela definida, o metamétodo __add é chamado para realizar a operação desejada.
- Os operadores relacionais retornam false e true.
- Não possui operadores de atribuição composta nem incremento ou decremento (++ e --);
- Há atribuição múltipla. Permite que multiplos valores sejam recebido de funções. permite a troca de valores armazenados em duas variáveis com um único comando.
```lua
  x, y = partir_metade({1, 2, 3, 4})
  -- uma função pode retornar multiplos valores

  a, b = b, a
  -- faz com que a receba o valor anteriormente armazenado por b e que b receba o valor anteriormente armazenado por a, sem necessidade de variáveis temporárias.
```
