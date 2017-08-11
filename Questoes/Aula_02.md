1. Quais as diferenças entre os barramentos de dados e de endereços?
- Os barramentos de dados se referem às portas I/O enquanto que os de endereços definem o destino na memória para os dados.

2. Quais são as diferenças entre as memórias RAM e ROM?
- A memória ROM (Read-Only Memory) permite a gravação de dados na memória apenas uma vez, deixando os dados disponíveis apenas para leitura. Já na memória RAM (Random-Access Memory) os dados podem ser gravados e regravados, no entanto quando o computador é desligado os dados se perdem; é uma memória volátil.

3. Considere o código abaixo:

```C
#include <stdio.h>
int main(void)
{
	int i;
	printf("Insira um número inteiro: ");
	scanf("%d", &i);
	if(i%2)
		printf("%d eh impar.\n");
	else
		printf("%d eh par.\n");
	return 0;
}
```

Para este código, responda: (a) A variável `i` é armazenada na memória RAM ou ROM? Por quê? (b) O programa compilado a partir deste código é armazenado na memória RAM ou ROM? Por quê?

- a) A variável é armazenada na memória RAM, pois ela é mais rápida de ser acessada e o programa em .c não demora muito para ser executado.
- b) O programa é armazenado na ROM, pois ela é uma memória não-volátil e armazena o programa de forma que ele seja executado novamente.

4. Quais são as diferenças, vantagens e desvantagens das arquiteturas Harvard e Von Neumann?
- A arquitetura Harvard é um tipo de arqy

5. Considere a variável inteira `i`, armazenando o valor `0x8051ABCD`. Se `i` é armazenada na memória a partir do endereço `0x0200`, como ficam este byte e os seguintes, considerando que a memória é: (a) Little-endian; (b) Big-endian.
- a) 0xCDAB5180
- b) 0x8051ABCD

6. Sabendo que o processador do MSP430 tem registradores de 16 bits, como ele soma duas variáveis de 32 bits?
- Para isso é necessário utilizar dois registradores para cada número da soma, carregando metade em um registrador, e metade em outro. Dessa forma serão utilizados quatro registradores.
