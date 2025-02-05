# Face Recognition Model for HIMYM Characters

Este repositório contém o código para um modelo de reconhecimento facial para personagens da série "How I Met Your Mother" (HIMYM). O modelo utiliza o MobileNetV2 pré-treinado, adaptado para classificar imagens de personagens específicos da série.

## Objetivo

O objetivo principal deste projeto é construir um modelo de classificação de imagens que seja capaz de identificar personagens da série HIMYM em fotos. O modelo foi treinado usando um conjunto de dados de imagens coletadas da internet.

## Tecnologias Utilizadas

- **TensorFlow** e **Keras**: Para construção e treinamento do modelo de aprendizado profundo.
- **MTCNN**: Para detecção de faces nas imagens.
- **OpenCV**: Para manipulação de imagens durante o pré-processamento.
- **BeautifulSoup** e **requests**: Para baixar imagens automaticamente da web.
- **Matplotlib**: Para exibição das imagens resultantes.

## Estrutura do Repositório

```
/dataset
    /Robin_Scherbatsky
    /Barney_Stinson
    /Ted_Mosby
    /Lily_Aldrin
    /Marshall_Eriksen
/test_images
/face_recognition_model.py
/requirements.txt
```

### Principais Arquivos

- **face_recognition_model.py**: Contém o código para treinamento do modelo, predição de imagens e detecção de faces.
- **/dataset**: Contém as imagens dos personagens coletadas da web.
- **/test_images**: Imagens de teste utilizadas para validar o modelo.

## Como Usar

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu_usuario/repo_face_recognition.git
    cd repo_face_recognition
    ```

2. Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```

3. Treine o modelo:
    ```bash
    python face_recognition_model.py
    ```

4. Para testar o modelo com suas próprias imagens, basta colocar suas imagens dentro da pasta `/test_images` e rodar o código.

## Dificuldades Enfrentadas

Durante o desenvolvimento do modelo, enfrentei algumas dificuldades:

- **Desequilíbrio nas classes**: Algumas classes (como "Barney") tinham um número maior de imagens do que outras, o que resultou em um modelo que frequentemente classificava imagens como "Barney". Uma solução mais robusta será balancear o dataset ou aplicar técnicas de aumento de dados (data augmentation).
  
- **Desempenho do modelo**: Inicialmente, o modelo estava com dificuldades para aprender a diferenciação entre algumas classes, devido à falta de diversidade nos dados e ao congelamento excessivo das camadas da rede neural. 

- **Detecção de faces**: A detecção de faces nas imagens também apresentou desafios, já que o modelo às vezes falha em detectar corretamente as faces nas imagens em que elas estão parcialmente visíveis.

## Melhorias Futuras

Este modelo ainda precisa de ajustes para aumentar sua acurácia e garantir uma maior robustez. Algumas melhorias previstas incluem:

- **Balanceamento de Classes**: Ajustar o número de imagens de cada classe para evitar que o modelo favoreça classes mais representadas.
- **Data Augmentation**: Aplicar técnicas de aumento de dados para diversificar as imagens de treinamento e melhorar a generalização do modelo.
- **Descongelamento de Camadas**: Experimentar descongelar algumas camadas do modelo MobileNetV2 para melhorar a adaptação do modelo aos dados específicos.
- **Avaliação e Ajuste do Modelo**: Após os ajustes nos dados e arquitetura, será feita uma avaliação detalhada do modelo, e as métricas de acurácia serão analisadas para ajustes finos.

## Como Contribuir

Se você gostaria de contribuir para este projeto, por favor, faça um fork deste repositório, faça suas alterações e envie um pull request. Qualquer sugestão para melhorias é bem-vinda!
