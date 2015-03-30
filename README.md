# Porque trabalhar na Leanwork?

Somos especialistas em desenvolvimento de software WEB customizado e outsourcing com foco em plataformas de ecommerce, integrações e ferramentas inteligentes. 

Somos apaixonados por novas tecnologias e buscamos continuamente aplicar a inovação em nossos produtos. Acreditamos que a tecnologia é um meio para resolvermos os problemas, mas nunca o fim.

Como nosso próprio nome diz, trabalhamos de forma enxuta e ágil. Isso quer dizer que gostamos de manter nossa equipe pequena para facilitar a comunicação, colaboração, aprendizado e evitar desperdício com processos burocráticos que não agregam valor à empresa ou as nossos clientes.

Atuamos em sinergia com grandes empresas como Centauro, CNova, Walmart e B2W e por isso nossa equipe é formada de profissionais competentes, responsáveis e comprometidos em fazer um trabalho bem feito e com excelência.
Procuramos criar um ambiente de trabalho de liberdade total para que as equipes busquem a melhora contínua e para isso todos os membros são incentivados a colaborarem entre si, seja ajudando um ao outro em um problema, decidindo sobre o uso de uma nova tecnologia e/ou maneiras de implementar uma nova funcionalidade ou até mesmo novas idéias que possam alavancar os negócios de nossos clientes.

# Quem procuramos?

Trabalhamos a maior parte do tempo com tecnologias Microsoft e adoramos escrever código simples, com testes e usar boas práticas de desenvolvimento de software.

Competências aceitáveis:
* Escrever código limpo e legível para pessoas
* Ter conhecimento e experiência em design e arquitetura de software
* Experiência com C#, ASP.NET (de preferência MVC)
* Experiência com desenvolvimento WEB (HTML, CSS, Javascript, jQuery, etc)

Competências que gostaríamos que tivesse:
* Tenha familiaridade com algum versionador de código (TFS, Git, etc)
* Saber escrever código com testes
* Conhecimento em banco de dados relacional e não relacional (NoSQL)

Trabalhar com tecnologia é fácil, mas nosso maior desafio é trabalhar com pessoas. Sabemos que ninguém é perfeito, por isso procuramos pessoas com as seguintes atitudes:
* Seja responsável.
* Escrever bem e saber se comunicar bem.
* Tenha facilidade em aprender.
* Não minta. Mentir sobre seu conhecimento, prazos ou sobre o andamento das atividades não vai funcionar com nosso modo de trabalho.
* Seja verdadeiro e honesto. Nossos clientes valorizam a transparência que temos com eles e também somos assim entre nós.
* Tenha senso crítico para questionar decisões.
* Saiba se virar e não tenha medo de perguntar.
* Tenha atitudes positivas, sempre. Somos pagos para resolver problemas e não criar novos. A frase "é impossível fazer isso" só é dita até que se prove o contrário.
* Seja humilde para assumir erros. Todo mundo erra, mas a capacidade de assumi-los é para poucos.

Nossa rotina de trabalho é diferente da maioria das empresas e precisamos que você se adapte a elas:
* Atualmente trabalhamos 100% em Home Office, por isso precisamos de pessoas confiáveis e responsáveis.
* Temos flexibilidade de horários.
* Tenha disponibilidade para viagens. Pode ser que um dia você precise ir até a alguns de nossos clientes resolver algum problema ou participar de alguma homologação.

# Estou interessado! O que preciso fazer?

Como parte do nosso processo para conhecer melhor suas habilidades, queremos que resolva um problema de programação para assim conhecer você melhor. A seguir preparamos dois (03) problemas a serem resolvidos, escolha apenas um (01) deles.

Gostarmos de usar ASP.NET MVC, Git, desenvolver usando TDD e ter uma boa de cobertura de teste de código. Utilizar estas tecnologias e/ou métodos certamente serão pontos positivos a seu favor, apesar de não ser necessário. Fique a vontade para usar bibliotecas de terceiro caso julguem necessário.

Esperamos que você solucione o problema sozinho e por favor não exponha a solução na internet.

### Problema 1: Verificador de cartão de crédito

Antes de apresentar um cartão de crédito a um gateway de pagamento, é importante que façamos algumas checagens sobre o número.

Uma verificação comum é realizar antecipadamente a validação do tipo de cartão com base nos dígitos iniciais e seu comprimento. Os principais padrões que que validamos são os seguintes:

    + + ============= ============ + =============== +
    | Tipo de Cartão | começa com | Número Comprimento |
    + + ============= ============ + =============== +
    | AMEX | 34 ou 37 | 15 |
    + ------------ + ------------- + --------------- +
    | Discover | 6011 | 16 |
    + ------------ + ------------- + --------------- +
    | MasterCard | 51-55 | 16 |
    + ------------ + ------------- + --------------- +
    | Visa | 4 | 13 ou 16 |
    + ------------ + ------------- + --------------- +

Todos esses tipos de cartão podem ser validados pelo algoritmo Luhn, de modo que é o segundo sistemas de verificação normalmente usado. As etapas de verificação são:

1. Começando com o próximo a última casa e continuar com todos os outros dígitos de voltar para o início do cartão, o dobro do dígito
2. Soma todos os dígitos dobrados e sem tocar no número. Para dígitos maiores que 9 será necessário dividi-los e somar o independente (ou seja, `"10", 1 + 0`).
3. Se o mesmo total é um múltiplo de 10, o número é válido.

Por exemplo, dado o número do cartão `4408 0412 3456 7893`:

    1. 8 4 8 0 0 4 2 2 4 6 10 6 14 8 18 3
    2. 8 + 4 + 0 + 8 + 0 + 4 + 2 + 2 + 6 + 4 + 1 + 0 + 6 + 1 + 4 + 8 + 1 + 8 + 3 = 70
    3. 70% 10 == 0

Este cartão é válido.

Vamos tentar mais uma, `4417 1234 5678 9112`:

    1. 8 4 7 2 2 2 6 4 10 6 14 8 18 1 2 2
    2. 8 + 4 + 2 + 7 + 2 + 2 + 6 + 4 + 1 + 0 + 6 + 1 + 4 + 8 + 1 + 8 + 1 + 2 + 2 = 69
    3. 69% 10! = 0

Este cartão é inválido.

Seu objetivo é escrever um programa em C# que valide números de cartão de crédito. Quando o usuário informar um número de cartão, o programa deverá imprimir a resposta no seguinte formato `"TIPO: NÚMEROS (válido/inválido)"`.

Tendo em conta os seguintes cartões de crédito:

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
    Descubra: 6011111111111117 (válido)
    MasterCard: 5105105105105100 (válido)
    MasterCard: 5105105105105106 (inválido)
    Desconhecido: 9111111111111111 (inválido)

### Problema 2: Contando as letras dos números

Se os números de 1 a 5 fossem escritos em palavras: um, dois, três, quatro, cinco, então teríamos utilizado 2 + 4 + 4 + 6 + 5 = 21 letras no total.

Seu objetivo é escrever um programa que mostre quantas letras será utilizado para todos os números de 1 até 1000.

### Problema 3) Extrair informações de uma página web

Um crawler é um software desenvolvido para realizar uma varredura na internet de maneira sistemática através de informação vista como relevante a sua função. Eles capturam os textos das páginas e cadastram os links encontrados e assim possibilitam encontrar novas páginas. São uma das bases das Search Engines, eles são os responsáveis pela indexação dos sites, armazenando-os na base de dados dos motores de busca.

Seu objetivo é escrever um programa que dada URL da página de um produto de um Ecommerce seja retornado as seguintes informações:
* Título
* Descrição (Metatag)
* Keywords (Metatag)
* Preço final do produto

Exemplo:
Ao informar a URL (http://www.extra.com.br/Informatica/EquipamentosdeRedeWireless/Roteadores/Roteador-TP-Link-TL-WR841N-300Mbps-com-2-Antenas-3112344.html) deve ser retornado:
* Título: Roteador TP-Link TL-WR841N 300Mbps com 2 Antenas - Roteadores no Extra.com.br
* Descrição: Roteador TP-Link TL-WR841N 300Mbps com 2 Antenas. Confira nossa linha de roteadores TP-Link.
* Keywords: 3112344, TL-WR841N, Roteador TP-Link TL-WR841N 300Mbps com 2 Antenas, roteador, roteador TP-Link, tplink, TPLINK, informática, acessórios, periféricos, redes, sem fio, Wireless, roteador 2 antenas, 
* Preço final do prodto: 118,70

Usar como base o site do http://www.extra.com.br/

# Enviando a solução

(texto aqui)
