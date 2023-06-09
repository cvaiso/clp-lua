# Tratamento de Exceção

O sistema de lua é rudimentar por ser uma linguagem embarcada de extensão, todas as ações de Lua começam a partir do código no programa hospedeiro que chama uma função da biblioteca de Lua. Sempre que um erro ocorre durante a compilação ou execução, o controle retorna para o hospedeiro, que pode tomar as medidas apropriadas. 

Um erro em lua pode ser levantado com a função `error`, ou com a função `assert` que só da erro caso uma condição falhe.

`error (message [, level])` 

Termina a última função protegida chamada e retorna `message` como uma mensagem de erro. Geralmente, `error` adiciona alguma informação sobre a posição do erro no início da mensagem. O argumento `level` especifica como obter a posição do erro.

```lua
if type(x) ~= 'number' then
    error('Not a number!!')
end

assert(type(x) == 'number', 'Not a number!!')
```

Em casos simples lua prefere retornar um valor errôneo como `nil`, como é o caso da função `tonumber` quando não encontra um numero.

A recomendação na documentação é lançar erros quando algo pode ser evitado facilmente, caso contrario retornar um código de erro, como `nil`, graças ao retorno multiplo tambem é conveniente retornar uma mensagem com o erro.

```lua
local file = assert(io.read(filename))
```

`io.read` retorna nil e uma mensagem em caso de falha, `assert` mostra a mensagem no codigo acima, em caso de sucesso ele retorna o primeiro argumento, como se o assert não estivesse alí.

## Tratamento

Se você precisa capturar erros em Lua, você pode usar a função `pcall` (protected call). Isto significa que qualquer erro dentro da função passada como parâmetro não é propagado. Ao invés disso, `pcall` captura o erro e retorna um código indicando o status.

```lua
function divide(a, b)
  if b == 0 then
    error("Divisão por zero")
  else
    return a / b
  end
end

-- chama a função divide(10, 0) em modo protegido
local ok, resultado = pcall(divide, 10, 0)
if ok then
    -- sem erros
else
    print("Houve um erro: " .. resultado)
end

-- Usando uma função anonima como bloco catch
local ok, err = pcall(function()
    divide(10, 0)
end)
```

Seu primeiro resultado é o código de status (um booleano), que é verdadeiro se a chamada aconteceu sem erros. Neste caso, `pcall` também retorna todos os resultados da chamada, depois deste primeiro resultado.

No caso de acontecer um erro, pcall retorna false mais a mensagem de erro.
