# Orientação a Objetos

> Essa parte requer o conhecimento do que são metatables, não sei se isso já foi explicado no slide

Lua, a principio, não é uma linguagem orientada a objetos mas comportamentos do tipo podem ser implementados com as ferramentas da linguagem.

O "estilo" de orientação a objetos implementado é chamado de prototype-based pois ele funciona como o padrão Prototype do livro dos 4.

Em prototype-based não existem classes em si, todos os objetos são independentes, mas eles podem ser clonados e modificados, e mensagens (chamadas de metodo) podem ser delegadas. Dessa forma as caracteristicas do prototipo são herdadas em outro objeto.

> Uma linguagem experimental chamada Self foi um "fork" de Smalltalk que era completamente Prototype-based.

## Herança

É possivel simular herança usando o metametodo `__index`, com ele é possivel delegar o acesso a um atributo de uma table.

```lua
Rectangle = {}

-- Essa metatable serve como prototipo
Rectangle.prototype = {
    x=0, y=0,
    width=100, height=100
}

Rectangle.__meta = {}

-- Por convenção um construtor é apenas uma função new
function Rectangle.new(r)
    setmetatable(r, Rectangle.__meta)
    return r
end

-- normalmente __index é uma função, mas por facilidade existe esse atalho que é explicado abaixo
Rectangle.__meta.__index = Rectangle.prototype

r = Rectangle.new{x=10, y=20}
print(r.width) --> 100
```

No exemplo acima `width` não está presente em `r`, então Lua usa o parametro `__index` no lugar e busca por `width` no prototype.

## Privacidade

Com um uso estratégico de variavel locais é possivel simular métodos privados, apesar que isso é geralmente desnecessário.

```lua
function Rectangle.new(r)
    local private = function(self)
        -- function body
    end

    local public = function(self)
        private()
    end

    r.public = public

    setmetatable(r, Rectangle.__meta)
    return r
end
```

## Polimorfismo de Subtipo / Despacho dinamico

Pela natureza da tipagem dinamica polimorfismo é obtido por duck typing:

```lua
-- se caminha como um pato e quacka como um pato então é um pato
if possivel_pato.walk ~= nil and 
   possivel_pato.quack ~= nil 
then
    possivel_pato.walk()
    possivel_pato.quack()
end
```

> De preferencia esteja certo que todos seus patos estejam no lugar certo com antecedencia
