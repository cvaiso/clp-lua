# Encapsulamento
Na linguagem Lua, não há o conceito de pacotes ou módulos. Mas é possivel ter algo semelhante com a função nativa `require`.

A função `require(path)` vai procurar por um arquivo correspondente ao argumento, geralmente `path.lua`, e executa-lo como parte do ambiente, alem disso a função garante que o mesmo arquivo não pode ser executado duas vezes.

```lua
------- Em main.lua -------
local sm = require 'simple_math'

sm.add(4, 3) -- 7

------- Em simple_math.lua -------
local SM = {}

-- Define a função add dentro de SM
function SM.add(a, b) return check(a) + check(b) end

-- check é marcado como local então não será acessivel por fora, variaveis globais continuariam globais
local function check(x) 
  if type(x) == 'number' then return x end
  error('Not a number')
end

-- Um arquivo em lua pode ter um return, que é o valor recebido por um require
return SM
```

Não existem modificadores de acesso em tabelas em lua, mas o comportamento pode ser alterado com a sobrecarga do metamétodo `__index`.


