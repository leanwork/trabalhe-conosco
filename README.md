# Vagas disponíveis

* Sem vagas no momento, volte mais tarde ;)

Observação: Apesar de home-office, o candidato deve residir em Londrina/PR.

# Porque trabalhar na Leanwork?

Somos especialistas em desenvolvimento de software WEB e outsourcing com foco em gestão e resultados, construindo Plataformas de Ecommerce e sistemas customizados por meio de metodologias ágeis e tecnologia de ponta. 

Somos apaixonados por novas tecnologias e buscamos continuamente aplicar a inovação em todo nosso processo de trabalho, seja na gestão, nos projetos, em nossos produtos ou no relacionamento com nossos clientes.

Como nosso próprio nome diz, trabalhamos de forma enxuta e ágil. Isso quer dizer que gostamos de manter nossa equipe pequena para facilitar a comunicação, colaboração, aprendizado e evitar desperdício com processos burocráticos que não agregam valor à empresa ou as nossos clientes.

Atuamos em sinergia com grandes empresas como Centauro, Avalia Educacional, Netfarma, Syngenta entre outras e por isso nossa equipe é formada de profissionais competentes, responsáveis e comprometidos em fazer um trabalho bem feito e com excelência.
Procuramos criar um ambiente de trabalho de liberdade total para que as equipes busquem a melhora contínua e para isso todos os membros são incentivados a colaborarem entre si, seja ajudando um ao outro em um problema, decidindo sobre o uso de uma nova tecnologia e/ou maneiras de implementar uma nova funcionalidade ou até mesmo novas idéias que possam alavancar os negócios de nossos clientes.

# Quem procuramos?

Trabalhamos a maior parte do tempo com tecnologias Microsoft e adoramos escrever código simples, com testes e usar boas práticas de desenvolvimento de software.

Competências obrigatórias:
* Escrever código limpo e legível para pessoas
* Conhecimentos sólidos em OOP
* Experiência com C#, ASP.NET (de preferência MVC)
* Experiência com desenvolvimento WEB (HTML, CSS, Javascript, jQuery, etc)
* Experiência com banco de dados relacional (MSSQL ou MySQL)

Competências que gostaríamos que tivesse:
* Ter conhecimento e experiência em design e arquitetura de software
* Tenha familiaridade com algum versionador de código (TFS, Git, etc)
* Saber escrever código com testes
* Conhecimento em banco de dados não relacional (NoSQL)

Trabalhar com tecnologia é fácil, mas nosso maior desafio é trabalhar com pessoas. Sabemos que ninguém é perfeito, por isso procuramos profissionais com as seguintes atitudes:
* Seja responsável.
* Escrever bem e saber se comunicar.
* Tenha facilidade em aprender.
* Não minta. Mentir sobre seu conhecimento, prazos ou sobre o andamento das atividades não vai funcionar com nosso modo de trabalho.
* Seja verdadeiro e sincero. Nossos clientes valorizam a transparência que temos com eles e também somos assim entre nós.
* Tenha senso crítico para questionar decisões.
* Saiba se virar e não tenha medo de perguntar.
* Tenha atitudes positivas, sempre. Somos pagos para resolver problemas e não criar novos. A frase "é impossível fazer isso" só é dita até que se prove o contrário.
* Seja humilde para assumir erros. Todo mundo erra, mas a capacidade de assumi-los é para poucos.

Nossa rotina de trabalho é diferente da maioria das empresas e precisamos que você se adapte a elas:
* Atualmente trabalhamos 100% em Home Office, por isso precisamos de pessoas confiáveis e responsáveis.
* Temos flexibilidade de horários.
* Tenha disponibilidade para viagens. Pode ser que um dia você precise ir até a alguns de nossos clientes resolver algum problema ou participar de alguma homologação.

# Estou interessado! O que preciso fazer?

Como parte do nosso processo queremos que resolva um desafio de programação para assim conhecer você melhor.

Gostamos de usar ASP.NET MVC, Git, desenvolver usando TDD e ter uma boa cobertura de teste. Utilizar estas tecnologias e/ou métodos certamente serão pontos positivos a seu favor, apesar de não ser necessário. Obs: Não é permitido o uso de biblioteca de terceiros que auxiliem na resolução do problema, somente biblioteca de testes, caso utilize.

Esperamos que você solucione o desafio sozinho.

### Desafio: Verificador de cartão de crédito

Antes de enviar um cartão de crédito para um gateway de pagamento, é importante que façamos algumas validações sobre o número.

Uma verificação comum é realizar antecipadamente a validação do tipo de cartão com base nos dígitos iniciais e seu comprimento. Os principais padrões que validamos são os seguintes:

| Tipo de Cartão | começa com | Número Comprimento |
| -------------- | ---------- | ------------------ |
| AMEX           | 34 ou 37   | 15                 |
| Discover       | 6011       | 16                 |
| MasterCard     | 51-55      | 16                 |
| Visa           | 4          | 13 ou 16           |

Todos esses tipos de cartão podem ser validados pelo [algoritmo Luhn](http://en.wikipedia.org/wiki/Luhn_algorithm). As etapas de verificação são:

1. Tome uma sequência de números inteiros positivos e a inverta.
2. Começando pelo segundo número, dobre o valor de cada número de forma alternada (`"24145...` = `"28185...`).
3. Para dígitos maiores que 9 será necessário que some cada dígito (`"10", 1 + 0 = 1`) ou subtraia por 9 (`"10", 10 - 9 = 1`).
4. Some todos os números da sequência.
3. Se o total for múltiplo de 10, o número é válido.

Por exemplo, dado o número do cartão `4408 0412 3456 7893`:

| 4 | 4  | 0 | 8  | 0 | 4  | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 3 |
|---|----|---|----|---|----|---|---|---|---|---|---|---|---|---|---|
| 3 | 9  | 8 | 7  | 6 | 5  | 4 | 3 | 2 | 1 | 4 | 0 | 8 | 0 | 4 | 4 |
| 3 | 18 | 8 | 14 | 6 | 10 | 4 | 6 | 2 | 2 | 4 | 0 | 8 | 0 | 4 | 8 |
| 3 | 9  | 8 | 5  | 6 | 1  | 4 | 6 | 2 | 2 | 4 | 0 | 8 | 0 | 4 | 8 |

    3 + 9 + 8 + 5 + 6 + 1 + 4 + 6 + 2 + 2 + 4 + 0 + 8 + 0 + 4 + 8 = 70
    70 % 10 == 0

Este cartão é `VÁLIDO`.

Vamos tentar mais uma, `4417 1234 5678 9112`:

| 4 | 4 | 1 | 7  | 1 | 2  | 3 | 4  | 5 | 6 | 7 | 8 | 9 | 1 | 1 | 2 |
|---|---|---|----|---|----|---|----|---|---|---|---|---|---|---|---|
| 2 | 1 | 1 | 9  | 8 | 7  | 6 | 5  | 4 | 3 | 2 | 1 | 7 | 1 | 4 | 4 |
| 2 | 2 | 1 | 18 | 8 | 14 | 6 | 10 | 4 | 6 | 2 | 2 | 7 | 2 | 4 | 8 |
| 2 | 2 | 1 | 9  | 8 | 5  | 6 | 1  | 4 | 6 | 2 | 2 | 7 | 2 | 4 | 8 |

    2 + 2 + 1 + 9 + 8 + 5 + 6 + 1 + 4 + 6 + 2 + 2 + 7 + 2 + 4 + 8 = 69
    69 % 10 != 0

Este cartão é `INVÁLIDO`.

Seu objetivo é escrever um programa em C# que valide números de cartão de crédito. Quando o usuário informar um número de cartão, o programa deverá imprimir a resposta no seguinte formato `"TIPO: NÚMEROS (válido/inválido)"`.

Para os seguintes cartões de crédito:

    4111111111111111
    4111111111111
    4012888888881881
    378282246310005
    6011111111111117
    5105105105105100
    5105 1051 0510 5106
    9111111111111111

Espera-se o seguinte resultado:

    VISA: 4111111111111111 (válido)
    VISA: 4111111111111 (inválido)
    VISA: 4012888888881881 (válido)
    AMEX: 378282246310005 (válido)
    Discover: 6011111111111117 (válido)
    MasterCard: 5105105105105100 (válido)
    MasterCard: 5105105105105106 (inválido)
    Desconhecido: 9111111111111111 (inválido)

Após a conclusão do desafio envie um email para `vagas@leanwork.com.br` com o assunto `Solução: verificador de cartão de crédito` e siga as seguintes instruções:
* Não envie a solução como anexo. Suba os fontes para o seu Github ou Bitbucket e passe o link. Caso não tenha nenhum desses serviços coloque os fontes em um arquivo .zip e compartilhe pelo seu Dropbox, Google Drive, One Drive, ou algum outro serviço de compartilhamento de arquivo.
* Envie o link da solução no corpo do email junto com o link do seu perfil no Linkedin. Caso não tenha Linkedin, pode enviar seu CV (Currículo) pelo anexo.
