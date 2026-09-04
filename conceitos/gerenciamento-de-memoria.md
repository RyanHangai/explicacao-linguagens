# Introdução

Todo programa, quando é inicializado, ele reserva um espaço na memoria ram do computador. E a maioria das linguagens e compiladores obedecem a seguinte ordem:
![[explicacao-linguagens-conceitos/assets/conceitos/gerenciamento-de-memoria/memory-layout.png | 450]]

* Stack: É a memória que o sistema operacional reserva para o programa gerenciar os blocos de códigos, funções e variaveis locais
* Heap: É aonde o programa aloca de forma dinamica a memoria
* Uninitializaed data: Local aonde o programa aloca um espaço para variaveis globais ou estaticas nao inicializadas ainda
* Data: É aonde o programa aloca espaço para dados, ou seja, variaveis ja iniciadas, strings constantes, etc.
* Text/Code: É o espaço aondde o código vai ser carregado em si, texto do código e as instruções em assembly

# Garbage collector

Garbage collector (coletor de lixo), se refere a como a linguagem gerencia o uso de mémoria ram, na heap ,durante o programa. Esse gerenciamento acontece exclusivamente na heap (que é a área aonde o programa vai alocando dinamicamente espaço na memoria).

Temos 3 estratégias de gerenciamento de memoria ram 

* Manual: C, e outras poucas
	* Pros:
		* Controle total da gestão de memoria, podendo alocar o quanto quiser, deixando o programa mais leve
		* Gestão muito eficiente de mémoria, deixando o programa usar apenas o que realmente vai usar, desde que feito da forma correta
	* Contras:
		* Quando você aloca um espaço, você tem que explicitamente liberar ela depois.
		* O programa pode alocar mais memoria do que vai usar de fato
		* Mais díficil de gerenciar a memoria, deixando o programa propenso a erros
* Meio termo: Rust e C++
	* Pros: 
		* Possibilidade de gerenciar manualmente a memoria, mas na propria linguagem tem meios automaticos de gerenciamento de memoria.
		* Junta a eficiente da gestão de memoria (estrategia manual) com a facilidade de alocação e libereção da memoria de forma mais automatica (estrategia automatica).
		* Menor possibilidade  de erros e bugs, já que na propria linguagem tem ajudas em relacao a gestão de memoria, como não precisar ter que pensar em liberar a memoria alocada depois ou do programa invadir espaco de memoria de outro programa.
	* Contras:
		* Requer um conhecimento mais aprofundado sobre alocação de memoria, como o programa aloca e usa a memoria, como o sistema distribui memoria, etc.
* Automática: Python, PHP, Java, C#, etc.
	* Pros:
		* A linguagem faz todo o gerenciamento de memoria automatica, assim, o programador nao tem que se preocupar com a gestão de memoria ram
		* Evita erros relacionados a má gestão de memoria, como memoria invadindo outro espaco, falta de memoria
	* Contras:
		* Gestão de memoria pouco eficiente, deixando o programa mais pesado
		*  Quase nenhum controle sobre a memoria que o seu programa vai usar ou alocar

Nas linguagens automáticas (linguagens gerenciadas) tem um agente externo que roda o código, por exemplo, quando um código em Java é executado, é a JVM que roda o código, ou em PHP que é a zend-engine, etc.
E esse agente externo, execulta também o Garbage Collector (coletor de lixo), ou seja, esse coletor de lixo fica toda hora analisando o código para ver se ele pode ou não liberar memoria. E isso é custoso em performance

Temos 2 principais estrategias de execultar um garbage collector:

* ARC (automatic reference counting): Contagem automatica de referencia, é quando a linguagem 
* Mark-and-sweep: