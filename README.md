# Recuperação da Informação e Busca na Web
## Laboratório 01: Crawlers

### Descrição

Neste laboratório exploraremos o conceito de *Focused Crawler*. Como forma de exercício, buscaremos conteúdo de forma automatizada em portais de notícias. Para tanto, será preciso reconhecer o conteúdo útil em cada página acessada. Com este objetivo, utilizares um estratégia simples baseada no próprio layout HTML do site alvo. Felizmente as páginas HTML publicadas em portais deste tipo seguem um layout HTML recorrente, o qual pode ser reconhecido de forma automática facilmente. Este será o objetivo deste laboratório.

Com o intuito de evitar prejuízos quanto à disponibilidade de acesso do site alvo, elencamos seis domínios diferentes para serem distribuídos entre os alunos. Cada domínio será explorado por doze alunos diferentes de forma independente (sem formação de grupos). Seguem os domínios possíveis abaixo;

- brasil247.com
- brasil.elpais.com
- cartacapital.com.br
- diariodocentrodomundo.com.br
- gazetadopovo.com.br
- oantagonista.com

Durante a aula faremos a distribuição destes domínios.

### Objetivos

O objetivo principal é reunir um mínimo de 100 notícias posteriores a 01/01/2018 e exportá-las para um arquivo CSV conforme *layout* abaixo.

| Campo     | Tipo     | Descrião                      |
| --------- | -------- | ------------------------------ |
| title     | String   |                                |
| sub_title | String   |                                |
| author    | String   |                                |
| date      | Datetime | dd/mm/yyyy hh:mi:ss            |
| section   | String   | Esportes, Saúde, Política, etc |
| text      | String   |                                |
| url       | String   |                                |


Deste modo, pretendemos explorar o conceito de Crawler na prática. Assim sendo, não apenas o resultado final será avaliado, mas o código. A presença de *politeness practices*, a leitura do arquivo *robots.txt*, a verificação do *sitemap* ou do *feed* de notícias serão diferenciais.

### O Código

O código a seguir já foi utilizado em projeto do departamento de Computação da UFCG, foi testado para todos os portais mencionados e em seguida teve trechos removidos com o intuito de servir a propósitos didáticos. Trata-se de um programa desenvolvido em Python que emprega um *framework* chamado Scrapy. Scrapy é uma crawler de código aberto que provê o arcabouço principal deste laboratório.

Para compreender este código é necessário ler a [documentação básica](http://docs.scrapy.org/en/latest/intro/tutorial.html) do Scrapy, caso no a conheça.

O projeto está dividido em quatro pastas

- frontier
- ri_lab_01
- seeds
- output

A pasta `seeds` traz em arquivo JSON as sementes do algoritmo de *crawling*, ou seja, os links iniciais a serem utilizados pelo seu código. O código opera a partir de cópias destes arquivos na pasta `frontier`. A pasta `ri_lab_01` traz o projeto em si. Para fins de correção, é importante utilizar apenas as sementes disponibilizadas nos arquivos em `seeds`. Já na pasta `output`, consta apenas o arquivo `results.csv`, que está vazio, mas deverá conter seus resultados.

### Comandos para executar o projeto

> ```shell
> scrapy list # lista todos os spiders do projeto
> scrapy crawl __nome_do_spider__ -o output/results.csv # subistitua pelo nome do spider atribuido a você.
> ```
