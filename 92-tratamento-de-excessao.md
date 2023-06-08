# Tratamento de Exceção

Um erro em lua pode ser levantado com a função `error`, ou com a função `assert` que só da erro caso uma condição falhe.

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

Para detectar um erro em lua é usado a função `pcall` (protected call).

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

Quando não há erros `pcall` retorna `true` mais os valores normais da função chamada, caso contrario retorna `false` mais a mensagem de erro.

> O sistema de lua é rudimentar pelo objetivo de ser uma linguagem embarcada. Geralmente o tratamento de erros é feito pelo código da aplicação, aquele que usa lua como biblioteca.
