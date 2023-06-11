# Sistema de Tipos
- Tipos primitivos
	- nil: representa o valor indefinido. Todas as variáveis ainda não inicializadas assumem o valor nil.
	- boolean: Pode assumir o valor true ou o valor false.
	- table: É o único tipo de dado composto em Lua, que permitem indexação por valores de qualquer outro tipo, com exceção do tipo nil, numa mesma estrutura.
	- number: Pode ser inteiro ou em notação de ponto flutuante. Não há distinção entre tipos inteiros e de ponto flutuante, pois o tipo number pode assumir valores inteiros e de ponto flutuante.
	- string: Sequência de caracteres.
	- function: Função em Lua é um tipo de valor. Funções podem ser armazenadas em variáveis, passadas como argumentos para outras funções e retornadas como valores de outras funções.A definição de uma função equivale a atribuir a uma variável global o valor do código que executa a função
	- userdata: É um tipo genérico que permite a alocação de qualquer tipo de dado em Lua. Usado para interoperabilidade com a API de C. Permite a manipulação direta de memória.
	- thread: Corrotinas em Lua são um tipo de valor que permite a execução de múltiplas tarefas simultaneamente de forma colaborativa (não paralela).
	
- Em Lua, não existem classes ou tipos primitivos com wrappers equivalentes, todos os tipos são tratados como valores em si mesmos.
- A linguagem Lua possui um sistema de tipos dinâmico, o que significa que a verificação de tipos é feita em tempo de execução. Veja abaixo algumas informações sobre as estruturas de tipos em Lua:

- Cadeia de Caracteres
	- Em Lua, a string é uma estrutura nativa da linguagem;
	- Strings são cadeias dinâmicas e podem ser manipuladas facilmente;
	- Não existe a diferença entre strings estáticas e dinâmicas;
	- Em Lua, strings são imutáveis;
```
str1 = "ABC"
str2 = "ABC"
str1 = str1 .. "D" -- a concatenação de strings é feita com ".."
```

- Vetores/Matrizes
	- Em Lua, podemos utilizar tabelas como listas;
	- Tabelas podem ter índices numéricos ou de texto;
	- Tabelas não têm tamanho fixo;
	- Tabelas podem ser manipuladas facilmente com funções como table.insert e table.remove;
	```
	vetor = {}
	for i = 1, 10 do
		vetor[i] = 0
	end
	
	matriz = {}
	for i = 1, 3 do
		matriz[i] = {}
		for j = 1, 3 do
			matriz[i][j] = 0
		end
	end
	```

- Verificação
	- Lua é uma linguagem fracamente tipada, o que significa que existem algumas coerções;
	- Lua realiza a coerção de tipos automaticamente, convertendo um dos valores para o tipo do outro valor antes da comparação ser realizada.
	Qualquer operação aritmética aplicada sobre cadeias de caracteres tenta converter a cadeia de caracteres no valor numérico correspondente. Quando a conversão não é possível, a linguagem reporta um erro de execução.
	```
	b = "53"
	c = 2 + b
	--resulta no armazenamento do valor numérico 55 na variável c, tendo em vista que a cadeia de caracteres 53 foi convertida para o valor numérico 53 antes da operação
	```
	- Dois valores podem ser equivalentes, mesmo que sejam de tipos diferentes, desde que tenham o mesmo valor semântico. Como no exemplo acima.
	- Por outro lado, quando utilizamos um valor numérico onde espera-se uma cadeia de caracteres, o valor numérico é convertido para a cadeia de caracteres correspondente.
	```
	print("resultado: " .. 23)
	--tem como saída a cadeia de caracteres:
	resultado: 23.
	```

	- É possível converter tipos de forma explícita com a função tonumber para números
	-Quando se atribui um valor a uma variável, é armazenado na variável um valor de um determinado tipo. Se é feita uma outra atribuição à mesma variável, ela passa a armazenar um valor de um tipo possivelmente diferente.
	- Ao tentar efetuar uma operação de soma sobre uma variável que armazena o valor de uma função, a linguagem reporta um erro de execução.


