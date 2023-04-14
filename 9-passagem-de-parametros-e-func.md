# Passagem de parametros e funções
Em Lua, assim como em outras linguagens, é possível passar parâmetros para funções e métodos. A passagem de parâmetros em Lua é posicional e pode ser realizada de forma explícita ou implícita. Além disso, Lua permite uma flexibilidade maior na quantidade de parâmetros que podem ser passados em uma função, inclusive permitindo que sejam passados mais parâmetros do que o número definido de parâmetros formais da função.

Veja abaixo algumas informações sobre passagem de parâmetros e funções em Lua:

- Passagem de parâmetros:
	- A passagem de parâmetros em Lua é posicional, assim como em Java.
	- É possível passar parâmetros de forma explícita ou implícita.
	- Para passar parâmetros de forma implícita, utiliza-se a variável global "arg", que é uma tabela que contém os parâmetros passados para a função.
	- Em Lua, a quantidade de parâmetros reais pode ser maior do que a quantidade de parâmetros formais, sem gerar um erro. Os parâmetros excedentes serão ignorados pela função.
	- Lua não realiza verificação de tipo nos parâmetros.
- Passagem de parâmetros com valores default:
	-   Em Lua, é possível definir valores default para os parâmetros de uma função, assim como em Java.
	-   A definição dos valores default é feita na própria definição da função, utilizando a seguinte sintaxe:
	```
	function nome_da_funcao(parametro1, parametro2, parametro3, ...)
		-- corpo da função
	end
	 ```
	- Para definir valores default, basta atribuir um valor padrão ao parâmetro desejado:
	```
	function soma(a, b, c)
		c = c or 0 -- valor default do parâmetro c é 0
		return a + b + c
	end
	```
- Passagem de parâmetros com número indefinido de parâmetros:
   - Em Lua, é possível definir uma função que aceite um número indefinido de parâmetros.
   - Para isso, basta utilizar a expressão "..." na definição da função:
	```   
	function nome_da_funcao(...)
		-- corpo da função
	end
	```   
   - Dentro da função, os parâmetros podem ser acessados através da variável global "arg", que é uma tabela que contém todos os parâmetros passados para a função:
 ```
	 function soma(...)
		local resultado = 0
		for i=1, select("#", ...) do
			resultado = resultado + select(i, ...)
		end
		return resultado
	end
 ```
   - Na função acima, utilizamos a função "select" para ppercorrer todos os parâmetros assados papra a função e somá-los.
   - Passagem de parâmetros por referência:
	- Em Lua, todos os parâmetros são passados por valor. Não é possível passar parâmetros por referência diretamente.
	- No entanto, é possível simular a passagem por referência utilizando uma tabela como parâmetro.
	- Dessa forma, é possível modificar o valor da tabela dentro da função e essa modificação será refletida fora da função:
 ```
	function trocaRG(pessoa, novoRG)
		pessoa.RG = novoRG
	end
	
	local p = {nome = "João", RG = 123}
 ```
