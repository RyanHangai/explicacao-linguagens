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

Tem o "else" e o "else if", assim como a maioria das linguagens

|| -> Or
&& -> And

No Rust, tudo pode ser uma expressão, ou seja, eu posso criar uma variavel que recebe como valor o resultado de um "if else". Lembrando que para um valor ser considerado o retorno de uma expressão, precisa remover o ";" do final da linha e só colocar (caso queira) no final do bloco todo

Ex: let condicao = if idade > 18 {"maior"} else {"menor"};

---

Estruturas de repeticoes

While:
	Funciona do mesmo jeito que em outras linguagens, voce pode definir uma variavel que vai servir de contador e um limite para o loop. Também temos o "continue;" que serve para pular uma interação
	Ex: 	
		while contador < 10 {
		contador += 1;
		println!("{}", contador);
	}

Loop: 
	Funciona como um "while true", colocando o bloco do código em um loop infinito propositalmente, e para sair do loop infinito, basta escrever um "break;". Também temos o "continue;" que serve para pular uma interação

For:
	Funciona da seguinte forma "for X in 1..11", sendo o "X" a variavel que vai usar, e o "in 1..11" sendo o intervalo que vai ter nesta repetição, aonde o 1 é o começo e o 11 é a "barreira", que quer dizer que a repetição para antes do final, neste caso sendo o 10.
	Para que pare no número escolhido, pode escrever "1..=10" que agora vai até o final, que é 10

---

Match Statement:

Match Statement (ou match expression), é parecido com um _switch case_ do C ou o _match case_ do python, porém com diferenças.

Match Statement em Rust é **sempre** uma expressão e se não for definido nem tratado  um caso para o valor "Default", o compilador vai retornar um warning e nao vai compilar, para compilar precisaria adicionar o "unsafe{}", porém não é indicado. Para adicionar um valor para "Default" precisa adicionar o "\_" 
```
let <variavel_x> match <variavel_y> {
<valor_variavel_y> => <valor_atribuido_variavel_x>,
_ => <valor_padrao_variavel_x>
}
```

Ex:
```

let linguagem = "";
let proposito = match linguagem {
"PHP" => "Web",
_ => "Desconhecido"
}
```

---

