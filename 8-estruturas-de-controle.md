# Estruturas de Controle
- Estruturas de seleção de dois caminhos:
	 - if-then-else:
		 - O else pertence ao if anterior mais próximo;
		 - Permite else-if aninhados;
	```
	    if a > b then
	       maior = a
	    else
	       maior = b
	    end
	```

- Estruturas de seleção múltiplas:
	- switch-case:
		- Em Lua, essa estrutura é implementada como uma sequência de if-then-else encadeados;
		- O caso padrão é representado pelo else no final da sequência;

```
    if a == 1 then
       print("Digitou um")
    elseif a == 2 then
       print("Digitou dois")
    else
       print("Digitou outra coisa")
    end
```

- Estruturas de iteração com contador:
	- for:
		 - Em Lua, o for pode ser utilizado para iteração com contador ou para iteração sobre uma lista de valores;
		 - No caso de iteração com contador, a sintaxe é semelhante à do for em Java, com a diferença que a variável de iteração é local ao loop;
		```
		for i = 1, 5 do
		   print(i)
		end
		```

- Iteração baseada em estruturas de dados:
	- for-in:
	- Essa estrutura é utilizada para iteração sobre uma lista de valores;
	```
    vetor = {1, 2, 3, 4, 5}
    for _, a in ipairs(vetor) do
       print(a)
    end
	```

- Estruturas de iteração condicional:
	- while:
		 - O while em Lua funciona de forma semelhante ao while em Java;
		```
		i = 0
		while i < 5 do
		   print(i)
		   i = i + 1
		end
		```

- repeat-until:
	- Essa estrutura é semelhante ao do-while em Java;
	- A execução do bloco de código é feita pelo menos uma vez, e a condição de continuidade é verificada no final;
	```
	i = 0
	repeat
	   print(i)
	   i = i + 1
	until i >= 5
	```
