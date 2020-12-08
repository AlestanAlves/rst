## Como escrever um ReStructuredText (arquivo .rst)

reStructuredText é um formato de arquivo para dados textuais usado principalmente na comunidade da linguagem de programação Python para documentação técnica.

### Titulos e subtitulos de texto 

Como em Markdown você usa # para definir o tamanho da letra do titulo ou como em HTML que você usa h1, h2 e etc em .rst você usa este estilo do maior para o menor:

```
Chapter 1 Title
===============

Section 1.1 Title
-----------------

Subsection 1.1.1 Title
~~~~~~~~~~~~~~~~~~~~~~

Section 1.2 Title
-----------------

Chapter 2 Title
===============
```

### Edição de texto

| Tipo          | syntax                               | HTML      |
| ------------- |:------------------------------------:| ---------:|
| italic        | `*italic*`                           | italic    |
| bold          | `**bold**`                           |   bold    |
| link          | `python <www.python.org>`            |    python |
| link external | `Python <http://www.python.org/>`_   |    python |

### Imagem 

Exemplo de tipo de inserção de imagem no .rst

```
.. image:: images/biohazard.png
   :height: 100
   :width: 200
   :scale: 50
   :alt: alternate text
 ```
 
### Listas

```
 * This is a bulleted list.
* It has two items, the second
  item uses two lines. (note the indentation)

1. This is a numbered list.
2. It has two items too.

#. This is a numbered list.
#. It has two items too.

```

### Exemplo de código dentro do texto

```
.. code-block:: html
    :linenos:

    <h1>code block example</h1>
```

return: ```<h1>code block example</h1>```

### Tabelas

```
+------------+------------+-----------+
| Header 1   | Header 2   | Header 3  |
+============+============+===========+
| body row 1 | column 2   | column 3  |
+------------+------------+-----------+
| body row 2 | Cells may span columns.|
+------------+------------+-----------+
| body row 3 | Cells may  | - Cells   |
+------------+ span rows. | - contain |
| body row 4 |            | - blocks. |
+------------+------------+-----------+
```

### Toctree

Mais cedo ou mais tarde, você desejará estruturar a documentação do projeto com vários arquivos RST. A diretiva toctree permite inserir outros links para arquivos em um arquivo RST. A razão para usar esta diretiva é que o RST não tem recursos para interconectar vários documentos ou dividir documentos em vários arquivos de saída. A diretiva toctree se parece com o código abaixo:

```
.. toctree::
    :maxdepth: 2
    :numbered:
    :titlesonly:
    :glob:
    :hidden:

    intro.rst
    chapter1.rst
    chapter2.rst
```

- **maxdepth:** é usado para indicar a profundidade da árvore.
- **numbered:** adiciona números de seção relevantes.
- **titlesonly:** adiciona apenas o título principal de cada documento
- **glob:** pode ser usado para indicar que * e? caracteres são usados para indicar padrões.
- **hidden:** oculta a árvore toc. Pode ser usado para incluir arquivos que não precisam ser mostrados (por exemplo, uma bibliografia).

### Avisos

Segue abaixo alguns exemplos de aviso que pode ser colocados dentro da documentação:

```
.. warning:: Instale `dependências`_  antes de rodar a aplicação.
```

**Return:**

![Screenshot from 2020-11-24 17-55-48](https://user-images.githubusercontent.com/48387196/100150603-a097ec00-2e7e-11eb-90fa-dfc7ca43a62a.png)


```
.. seealso:: Sem o `docker-compose` e o `Docker` a aplicação não poderá rodar, pois tudo está dentro de um container do docker.
```

**Return:**

![Screenshot from 2020-11-24 17-56-00](https://user-images.githubusercontent.com/48387196/100150673-b9a09d00-2e7e-11eb-8944-cb30120b4d17.png)


### Extensões

Em `conf.py` no arquivo criado junto com o sphinx, pode se adicionar mais extensões e acrescentar ainda mais as funções ao rst, como por exemplo adicionar tabs usando a extensão `sphinx_tabs.tabs` adicionando em `extensions = [.., 'sphinx_tabs.tabs']`

Exemplo da implementação da extensão tabs:

```
.. tabs::

   .. tab:: Apples

      Apples are green, or sometimes red.

   .. tab:: Pears

      Pears are green.

   .. tab:: Oranges

      Oranges are orange.
```

**Return exemplo:**


![Group Tabs](https://raw.githubusercontent.com/executablebooks/sphinx-tabs/master/images/tabs.gif)

