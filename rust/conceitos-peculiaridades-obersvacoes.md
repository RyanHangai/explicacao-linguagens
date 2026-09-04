
Tem foco em performance, produtividade, confiabilidade 

* Performance: Rust, é uma linguagem compilada, diferente de linguagens interpretadas e de linguagens que rodam em VMs. Ou seja, esse código passa por um compilador e esse compilador, gera um arquivo binário direto.
* Confiabilidade: Rust tem um sistema de "tipos" bem amplo nativamente, poupando memoria quando necessario ou alocando mais memoria caso o desenvolvedor queira, deixando a gestão de memoria mais "automatico", dando mais segurança para o sistema, já que previne vazamento de mémoria
* Produtividade: Rust gere de maneira mais "automática" o uso de memoria do sistema, ou avisando quando tem algum possivel uso de mémoria indevido. Logo, o desenvolvedor não precisa se preocupar tanto com a gestão de mémoria. E as mensgens de erro do compilador são mais amigaveis e mais explicativas 

---

As variaveis de rust soa sempre imutaveis por padrao, ou seja, 

let x = 6

o x sempre vai ser 6 e nao pode mudar este valor

para mudar o valor precisa adicionar o "mut"

let mut x = 6

agora ele pode mudar o valor de x

---

O Rust nao usa o NULL ou  undefined, ele usa enums Option\<T> (para valores que nao podem existir) e Result\<T, E> para operacoes que podem dar certo ou falhar

---

Rust é uma linguagem multi paradigma, tendo alguns conceitos de POO, programcao estruturada, etc.

---

std::mem::size_of_val(&variavel): Pega o tamanho de bytes

---

Macro: Magia do rust
println!()

---

Rust usa escopos para separar bloco de códigos, ou seja, precisa de chaves "{}". A variavel, funcao, etc. So existe dentro do escopo.

---

No Rust, você pode redeclarar uma variavel, porem, gera um aviso (warning) caso voce redeclare sem usar ela antes. Quando você redeclara uma variavel, o Rust ele aloca um outro espaço na memoria, não usando o mesmo espaço "original" da variavel, ou seja, redeclarar uma variavel **não** transforma ela em mutavel, já que os espaços das memorias são diferentes quando redeclarada

Gera warning:
let x = 1;
let x = 2;
print("{}", x);

Não gera warning:
let x = 1;
print("{}", x);
let x = 2;
print("{}", x);

Quando voce redeclara uma variavel dentro de um outro escopo, o Rust trata aquela variavel redeclarada como uma nova variavel totalmente diferente da variavel original

---

Você pode criar escopo (bloco de código) sem nada (anonimo), sem if, while, fn, etc.
Ex:
```
fn main(){

	{
		let x = 1;
	}

}
```

Lembrando que para acessar uma variavel, etc. Você precisa estar dentro do mesmo escopo (bloco).

---

String:

Em outras linguagens, string é uma lista ou um vetor de caracteres. Porém no Rust string é uma referência para uma "static str", aonde "str" é um pedaço de uma string, ou seja, um pedaço de um vetor de caracteres

Não consegue pegar a posição de uma string do jeito tradicional (string\[0]), sendo mais complexo

---

Funções:

Para fazer uma funcao que receba parametros, voce tem que definir o tipo delas, e para definir um tipo de retorno, voce tem que colocar uma seta com o tipo de retorno no final da funcao "-> i32"
Ex:
fn soma(a:i32, b:i32) -> i32{

}

Quando você quer retornar o resultado ou valor de algo na função, você pode não adiciona o ";" na linha que deve retornar, mas se quiser você pode colocar ";" porém no começo da linha voce deve adicionar o "return ..."

---

Operadores matematicos:

* Padrão: \*, +,  -, % (resto da divisão)
* Divsão: A divisão de 2 inteiros retorna um numero inteiro, e se for necessario arredondado para baixo. Para fazer uma divisão precisa, os dois valores precisam ser do tipo float. Pode ser adicionado funções de arredondamentos como: .trunc(), .ceil(), .floor(), .round()
* Raiz quadrada e log: so adicionar o ".sqrt()" ou ".log\<base>()"

---

Ponto e virgula (;):

No Rust, tudo pode ser uma expressão, porém quando você adiciona um ";" no final da linha, o Rust ignora o **resultado** dessa expressão, ou seja, se retornar algo o Rust vai ignorar esse retorno

---

Definir funcoes:

Voce nao precisar definir tudo antes da funcao main(), nem declarar cabeçalhos 


