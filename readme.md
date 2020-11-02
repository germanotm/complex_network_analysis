# Análise de Redes Complexas

Repositório criado com scripts usados para análise do relacionamentos entre posts no instagram. 

Os notebooks permitem buscar dados de posts no instagram com usas respectivas hashtags. Com os dados em mãos, usamos as hashtags de cada post para estabelecer relação semântica entre elas. Quando um par de hashtags é usado em um mesmo post, criamos uma relação entre essas duas hastags. 

O peso de um nó da rede é dado pela quantidade de posts em que essa hastag apareceu. O peso de cada aresta foi dado pelo número de vezes que esse par de tags apareceu nos posts analisados.

Por fim, foi usado o Gephi para criar um visualização do grafo de relacionamento entre as hashtags. 

A imagem abaixo mostra o resultado final do trabalho usando hashtags relacionadas à radiologia odontológica como ponto de partida:

![gephi graph](instagram.png)


# Instalação

Antes de começar a usar crie o ambiente virtual python. Use o [pyenv](https://github.com/pyenv/pyenv-installer) para instalar a versão do python correta. 

Depois crie o ambiente virtual com o comando:

```shell
python -m venv venv
source venv/bin/activate
```

Feito isso instale as dependências necessárias:
```
pip install -r requirements.txt
```

Para rodar o projeto inicie o jupyter e abre a porta indicada no browser:
```
jupyter notebook
```
*Nota: Tive problemas com o chrome devido a restrição de memória para abrir os arquivos json baixados, contornei o jupyter notebook diretamente vscode*

# Conteúdo

### parte1_instagram_crawler.ipynb

Notebook possui as funções python para pegar dados do instagram. Aqui você pode testar e garantir que tudo esta funcionado como e esperado antes de executar a parte 2 e 3.

### parte2_instagram_collect_data.ipynb

Esse notebook vai baixar os posts relacionados às hastags que desejamos. O conteúdo baixado é salvo em formato json para ser usado na parte 3.

### parte3_instagram_graph_generator.ipynb

O json baixado na parte 2 é processado para criar o grafo que pode ser carregado no gephi. Cada hashtag representa um nó do grafo e quando duas hastags aparecem no mesmo post é criado uma aresta entre esses

### instagram.gephi

Projeto do Gephi já com o grafo depois de calcular métricas e estilizar.

# Referências

[Creating and Visualizing a Complex Network of Instagram hashtags](https://medium.com/@marcosacj/creating-and-visualizing-a-complex-network-of-instagram-hashtags-based-on-posts-about-politics-2daf24f31088)\
  Usei esse artigo como base criar esses arquivos, nele tem tudo muito melhor explicado.

[CNA Instagram](https://github.com/marcosacj/cna-instagram)\
Github com código do artigo que cria uma rede para analisar hastags relacionadas à politica brasileira.

[Gephi](https://gephi.org/users/download/)\
Software utilizado para criar a representação da rede como grafo.
