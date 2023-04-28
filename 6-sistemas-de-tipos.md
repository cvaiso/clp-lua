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
- Tipos ordinais definidos pelo usuário:
	- Em Lua, podemos utilizar tabelas para criar tipos ordinais definidos pelo usuário;
	- As tabelas podem ter índices numéricos ou de texto e podem conter qualquer tipo de valor, incluindo funções e outras tabelas;
```
Carta = {
	J = 11,
	Q = 12,
	K = 13,
	A = 14
}
```
- Vetores/Matrizes
	- Em Lua, podemos utilizar tabelas como vetores/matrizes;
	- Tabelas podem ter índices numéricos ou de texto;
	- Tabelas não têm tamanho fixo;
	- Há suporte para vetores associativos;
	- Tabelas podem ser manipuladas facilmente com funções como table.insert e table.remove;
	- Há suporte para fatias;
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

- Registros e uniões
	- Em Lua, podemos utilizar tabelas para simular registros e uniões;
	- Lua usa o nome do campo como um índice.
	- Uma tabela pode conter chaves com nomes e valores correspondentes, simulando um registro;
	- Uma tabela pode conter uma chave especial __tag que indica o tipo de união que a tabela representa;
	```
	pessoa = {
		nome = "João",
		idade = 30,
		salario = 1000.00
	}
	
	-- União de tipos
	pessoa = {
		__tag = "Pessoa",
		nome = "João",
		idade = 30,
		salario = 1000.00
	}
	
	animal = {
		__tag = "Animal",
		especie = "Cão",
		nome = "Rex"
	}
	```

- Ponteiros e referências
	- Em Lua, não existem ponteiros;
	- Todos os valores em Lua são referências;
	- É possível usar o tipo Userdata para armazenar ponteiros para objetos externos ou valores em C/C++ usando a API de Lua.
	- O coletor de lixo é responsável por desalocar a memória não utilizada automaticamente;
	```
	p = {}
	
	```
- Verificação
	- Lua é uma linguagem fracamente tipada, o que significa que a verificação de tipos é feita em tempo de execução;
	- É possível converter tipos de forma explícita com a função tonumber para números
	-Quando se atribui um valor a uma variável, é armazenado na variável um valor de um determinado tipo. Se é feita uma outra atribuição à mesma variável, ela passa a armazenar um valor de um tipo possivelmente diferente.
	- Ao tentar efetuar uma operação de soma sobre uma variável que armazena o valor de uma função, a linguagem reporta um erro de execução.

- Equivalência de Tipos
	- Em Lua, existe o conceito de "equivalência de tipos".Quando dois valores são comparados em Lua, eles podem ser do mesmo tipo ou de tipos diferentes.
	- Lua realiza a coerção de tipos automaticamente, convertendo um dos valores para o tipo do outro valor antes da comparação ser realizada.
	- Dois valores podem ser equivalentes, mesmo que sejam de tipos diferentes, desde que tenham o mesmo valor semântico.
