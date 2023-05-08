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
- Escopo
	- Variáveis locais têm escopo definido pelo bloco onde são declaradas;
	- Variáveis globais podem ser acessadas de qualquer parte do código, mas é necessário declará-las com o comando global antes de utilizá-las dentro de funções.
- Constantes nomeadas: em Lua, é possível definir constantes criando uma variável local e não alterando seu valor. 
```
local PI = 3.1415
```
