# Sistema de Tipos
- Tipos primitivos
	- nil: Indica a ausência de valor. É diferente de uma variável não inicializada ou de um valor nulo, é um valor em si mesmo.
	- boolean: Pode assumir o valor true ou o valor false.
	- number: Pode ser inteiro ou em notação de ponto flutuante. Não há distinção entre tipos inteiros e de ponto flutuante, pois o tipo number pode assumir valores inteiros e de ponto flutuante.
	- string: Sequência de caracteres.
	- function: Função em Lua é um tipo de valor. Funções podem ser armazenadas em variáveis, passadas como argumentos para outras funções e retornadas como valores de outras funções.
	- userdata: É um tipo genérico que permite a alocação de qualquer tipo de dado em Lua. É útil quando se deseja alocar um tipo de dado específico, como uma estrutura ou objeto.
	- thread: Corrotina em Lua é um tipo de valor que permite a execução de múltiplas tarefas simultaneamente, sem a necessidade de utilizar múltiplos threads do sistema operacional.
	- table: É o único tipo de dado composto em Lua, que permite armazenar qualquer tipo de valor como índices e seus valores correspondentes.
- Em Lua, não existem classes ou tipos primitivos com wrappers equivalentes, todos os tipos são tratados como valores em si mesmos.
- Para Lua, temos algumas diferenças em relação ao sistema de tipos em comparação com Java. A linguagem Lua possui um sistema de tipos dinâmico, o que significa que a verificação de tipos é feita em tempo de execução. Veja abaixo algumas informações sobre as estruturas de tipos em Lua:

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
	- Não há suporte para matrizes associativas;
	- Tabelas podem ser manipuladas facilmente com funções como table.insert e table.remove;
	- Não há suporte para fatias;
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
	- O coletor de lixo é responsável por desalocar a memória não utilizada automaticamente;
	```
	p = {}
	
	```
- Verificação
	- Lua é uma linguagem fracamente tipada, o que significa que a verificação de tipos é feita em tempo de execução;
	- É possível converter tipos de forma explícita com a função tonumber para números

