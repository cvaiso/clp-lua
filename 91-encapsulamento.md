# Encapsulamento
Na linguagem Lua, não há suporte nativo para pacotes e classes como em Java. Lua é uma linguagem de programação orientada a objetos baseada em protótipos, o que significa que as estruturas de dados e o comportamento são definidos por meio de objetos e seus protótipos.

No entanto, ainda é possível obter encapsulamento em Lua usando convenções de nomenclatura e funções locais para simular escopo privado. Por exemplo, em Lua, é comum usar o prefixo _ em nomes de variáveis e funções que não devem ser acessados diretamente por outros módulos ou arquivos.

Também é possível usar o operador local para criar variáveis e funções locais dentro de um escopo específico, impedindo que elas sejam acessadas por outros escopos. Por exemplo:

```
	local function funcaoPrivada()
	  -- Esta função só pode ser chamada dentro deste arquivo
	end
	
	function funcaoPublica()
	  -- Esta função pode ser chamada de outros arquivos
	  funcaoPrivada()
	end
```
Note que, embora seja possível restringir o acesso a variáveis e funções em Lua, não há suporte nativo para modificadores de acesso como public, private e protected em Java.

