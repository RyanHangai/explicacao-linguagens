Tudo começa na função main

---

Toda linha de código tem que terminar com ";"

---

Criar função:
fn \<nome_funcao>(){

}

---

para compilar:
rustc \<caminho>

---

Declarar variavel:
let \<nome>;
Para declara variavel voce pode ou nao definir um tipo para ela

let x:i8 = 12;
No exemplo acima, o x é do tipo int de 8 bits, e recebe o valor 12.

OBS: Por padrão, variaveis no Rust são imutaveis, ou seja, deposi de atribuido um valor uma vez, não da para mudar o seu valor depois, esse valor pode ser uma expressção, chamada, etc. Então é diferente de uma constante. Para deixar uma variavel mutavel, tem que usar o "mut" depois do "let"

let mut \<nome>;

let x:char = 'E';
Para definir um char, tem que estar entre apostrofo (aspas simples) ''

---

print:
print("");
printa e continua na mesma linha

println!("");
printa e pula uma linha

println!("Hello {}", variavel)
As chaves "{}" vão ser substituidas pelo valor da "variavel" 

---

Constantes:

Quando você usa uma variavel, o Rust aloca um endereço na memoria, e nesse espaco ele guardar o valor, pensando em usar este valor futuramente para qualquer fim.

Já as constantes, não são manipulados em memoria, são um valor que nao mudam, não sofrem alterações e nem são realocados ou mudados de lugar, e que podem ser repetidos. Se você chamar uma constante ela vai substituir diretamente pelo valor dessa constante.
Precisa definir o tipo dela e atribuir um valor, e o valor tem que ser constante, não pode ser retorno de uma função ou algo do genero

const \<NOME> = x;

---

Static:

É como se fosse uma constante, porem ela tem um lugar na memoria e pode ser mutavel. Porém, uma variavel globa mutável, é perigoso e arriscado.
Serve mais para criar uma variavel global. Para criar um static, precisa definir o tipo dela e atribuir um valor, e o valor tem que ser constante, não pode ser retorno de uma função ou algo do genero

static \<NOME>:u8 = 1;

---

Unsafe:

Quando você quer executar um bloco de código potencialmente inseguro (variavel global mutavel, vazamento de memoria, etc.), voce tem que adicionar um bloco chamado "unsafe" para que o Rust permita ser compilado

unsafe{

}

---

If:

No Rust a condição do if não precisa estar dentro do parenteses "()"

If  x >= y {

}