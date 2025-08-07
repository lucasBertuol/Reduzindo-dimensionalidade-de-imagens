# Redução de dimensionalidade 
A redução de dimensionalidade é um processo que busca **diminuir a complexidade** de um conjunto de dados e ao mesmo tempo **preservar informações importantes**. No caso de imagens, elas carregam diversas informações, como sua resolução, formato e pixels. Imagens coloridas são formadas por combinações de pixels com valores RGB (Red, Green, Blue), cada um variando de 0 a 255. Porém, para certas tarefas, esse nível de detalhamento não é necessário. Imagens em níveis de cinza por exemplo, carregam menos informações e geram um menor custo computacional. Por esse motivo, nesse projeto será analisado como **reduzir os canais de cores** de uma imagem para alcançar uma **maior eficiência** em projetos de Machine Learning e Análise de Dados.
## Objetivos 🎯
- Descobrir como **reduzir a dimensionalidade** de imagens usando a biblioteca Pillow e a linguagem Python
- Implementar um programa para **manipular a cor de imagens** e analisar o seu funcionamento 

## Estrutura do projeto 🗂️
- **Redução_dimensionalidade.ipynb:** Jupyter notebook com o código utilizado e explicações
- **Imagens dos resultados:** Imagem original,  imagem em níveis de cinza e imagem binária

## Recursos Utilizados ⚒️
-   **Linguagem:**  Python 3.x
- **Bibliotecas**: pillow 11.3.0 (`pip install pillow`)

## Implementação 🧑‍💻
1. **Importações**
Com a biblioteca Pillow instalada, a importamos juntamente com o nosso sistema operacional (será usado mais adiante).
2. **Carregar a imagem**
Usando o caminho da nossa imagem como argumento, essa função carrega a imagem e a converte para RGB. Essa normalização é importante porque formatos diferentes de imagens podem usar modelos de cor diferentes (PNG usa RGBA, por exemplo). Se houver erro no carregamento a função irá exibir um erro. 
3. **Converter imagem colorida para níveis de cinza**
Aqui nós iremos reduzir os canais RGB para um único canal de cor: cinza (0 a 255). Desse modo a imagem se torna mais simples e fácil de ser processada.  Para fazer isso poderíamos simplesmente usar o método .convert() do Pillow, mas para fins didáticos eu irei demonstrar o funcionamento de um método como esse passo a passo. 
A função abaixo percorre cada pixel individualmente, pegando o seu valor RGB e aplicando uma fórmula especial para definir o novo valor de cada pixel. 
Essa é a fórmula da Luminância Ponderada, a mesma usada pelo Pillow com `.convert()`. 
4. **Converter imagem cinza para binária (preto e branco)**
Usando um processo similar, iremos converter a nossa imagem em níveis de cinza para binário: preto e branco. Esta função novamente irá percorrer toda a imagem para obter o valor de cada pixel. Dependendo se um pixel específico estiver acima ou abaixo de um ponto de corte (chamado de limiar, 128 no nosso caso), a função tornará esse pixel totalmente branco (255) ou preto (0). 
5. **Função principal e execução do programa**
Por fim, este último bloco de código será responsável por chamar cada uma das funções criadas anteriormente em ordem e realizar as conversões de cor na nossa imagem. Esta mensagem de output ilustra o fluxo seguido pelo nosso programa: 
**Imagens geradas:**
Figura1: Imagem colorida (RGB), em níveis de cinza (0 a 255) e preto e branca (0 e 255).

# **Conclusão**📸
Este projeto demonstrou uma **implementação prática** de técnicas de redução de dimensionalidade para imagens, com foco nos fundamentos por trás de tarefas comuns de pré-processamento. Em vez de usar bibliotecas avançadas como a OpenCV, foi priorizada a implementação manual das funções em Python. Essa decisão tornou possível obter um **maior entendimento** de como esses processos de manipulação de imagens funcionam. 
As técnicas exploradas são cruciais para **sistemas de visão computacional**. Elas servem como base para tarefas como detecção de bordas, segmentação de objetos e a otimização de datasets para o treinamento de redes neurais.
