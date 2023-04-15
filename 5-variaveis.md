# Variáveis
- Vinculação de tipo: dinâmica e implícita.
	```
	x = 10 
	nome = "João"
	```
- Todas as variáveis em Lua são consideradas "globais" por padrão. Para criar uma variável local, utiliza-se o comando local.
	```
	local y = 20
	```
- Tipos de dados:
	- Números: são representados internamente como ponto flutuante de dupla precisão. A declaração de uma variável numérica é feita automaticamente quando um valor é atribuído a ela.
	- Strings: são sequências de caracteres delimitadas por aspas simples ou duplas.
	- Booleanos: representam os valores verdadeiro (true) ou falso (false).
	- Tabelas: são estruturas de dados que podem armazenar múltiplos valores associados a chaves.
	- Funções: são valores que podem ser armazenados em variáveis, passados como argumentos e retornados por outras funções.
- Escopo
	- Variáveis locais têm escopo definido pelo bloco onde são declaradas;
	- Variáveis globais podem ser acessadas de qualquer parte do código, mas é necessário declará-las com o comando global antes de utilizá-las dentro de funções.
- Constantes nomeadas: em Lua, é possível definir constantes criando uma variável local e não alterando seu valor. 
```
local PI = 3.1415
```
