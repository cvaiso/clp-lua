# Passagem de parametros e funções
Em Lua, assim como em outras linguagens, é possível passar parâmetros para funções e métodos. A passagem de parâmetros em Lua é posicional. Além disso, Lua permite uma flexibilidade maior na quantidade de parâmetros que podem ser passados em uma função, inclusive permitindo que sejam passados mais parâmetros do que o número definido de parâmetros formais da função.


- A passagem de parâmetros em Lua é posicional, assim como em Java.

- Em Lua, a quantidade de parâmetros reais pode ser maior do que a quantidade de parâmetros formais, sem gerar um erro. Os parâmetros excedentes serão ignorados pela função.

- Lua não realiza verificação de tipo nos parâmetros.

## Sintaxe

Funções normalmente são chamadas com parenteses, porem eles são opcionais se o parametro for uma unica string ou table, exemplos:
```lua
print "Hello World" -- equivale a print("Hello World")

fun {
    x=10,
    y=20
} -- equivale a fun({x=10, y=20})
```

A sintaxe `expr:fun()` é açucar sintático para simular metodos:
```lua
Dados = {a = 5}

-- equivale a function Dados.display(self, x)
function Dados:display(x, prefix)
  print(prefix .. self) -- self é um paramtro escondido
end

-- equivale a Dados.show(Dados, '> ')
Dados:display('> ')
```

## Funções variádicas (Passagem de parâmetros com número indefinido de parâmetros)

   - basta utilizar a expressão "..." na definição da função:
   - Dentro da função, os parâmetros podem ser acessados através do parametro escondido "arg", que é uma tabela que contém todos os parâmetros passados para a função:
 ```lua
	function print(...)
      for i, v in ipairs(arg) do
        printResult = printResult .. tostring(v) .. "\t"
      end
      printResult = printResult .. "\n"
    end
 ```

## Retorno multiplo

Funções em lua podem retornar multiplos valores, algo que é usado amplamente na biblioteca padrão:

```lua
function min_max(arr)
  local max, min = arr[0], arr[0]

  for i, val in ipairs(arr) do
    if val > max then max = val end
    if val < min then min = val end
  end
  
  -- a função retorna minimo e maximo juntos
  return min, max
end

-- os valores serão distribuidos nas variaveis
minimo, maximo = min_max({2, 3, 6, 4, 5})

-- nesse caso, no entanto, apenas o primeiro valor (minimo) é considerado
x = min_max({9, 3, 6, 2, 3})
```

# Menos importante:

- Passagem de parâmetros por referência:
	- Em Lua, todos os parâmetros são passados por valor. Não é possível passar parâmetros por referência diretamente.
	- No entanto, é possível simular a passagem por referência utilizando uma tabela como parâmetro.
	- Dessa forma, é possível modificar o valor da tabela dentro da função e essa modificação será refletida fora da função:
 ```lua
	function trocaRG(pessoa, novoRG)
		pessoa.RG = novoRG
	end
	
	local p = {nome = "João", RG = 123}
    trocaRG(p, 200)
    -- p.RG agora é 200
 ```
