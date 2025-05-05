
# Classificação de Imagens com MobileNetV2

Projeto desenvolvido como parte da disciplina **Resolução de Problemas com Deep Learning** do MBA em BI & Data Science, Ibmec.

## 🧠 Objetivo

Utilizar o modelo pré-treinado **MobileNetV2**, disponibilizado pelo TensorFlow, para realizar a **classificação de imagens** a partir de categorias do conjunto de dados **ImageNet**. As imagens utilizadas nos testes foram retiradas do **COCO Dataset**.

## 🔧 Tecnologias Utilizadas

- Python 3.x
- TensorFlow
- Matplotlib
- NumPy

## 📁 Estrutura do Projeto

```
/
├── datasets/
│   ├── val/
│   │   └── val2017/          # Imagens de validação originais COCO
│   └── val_classified/       # Imagens organizadas por classe prevista
├── img_classifier.ipynb      # Notebook principal com o código de classificação
└── README.md                 # Este arquivo
```

## ▶️ Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
   ```

2. Crie e ative um ambiente virtual opcional:
   ```bash
   python -m venv venv
   source venv/bin/activate  # ou venv\Scripts\activate no Windows
   ```

3. Instale as dependências:
   ```bash
   pip install tensorflow matplotlib
   ```

4. Baixe o conjunto val2017 do **COCO Dataset** e coloque as imagens em `datasets/val/val2017/`.

5. Execute o notebook:
   ```bash
   jupyter notebook img_classifier.ipynb
   ```

## 🖼️ Saída Esperada

Para cada imagem em `datasets/val/val2017`, o notebook irá:

- Mostrar os três rótulos mais prováveis segundo o modelo MobileNetV2
- Exibir a imagem original com o rótulo de maior confiança
- Informar a probabilidade associada a cada classe prevista
- Copiar a imagem para uma subpasta em `datasets/val_classified/`, com o nome da classe prevista

## 🗂️ Fonte dos Dados

As imagens foram retiradas do **COCO Dataset**  
https://cocodataset.org/#home

## 📝 Impressões

Durante a execução do código, foi possível observar que o modelo MobileNetV2 apresenta um desempenho bastante satisfatório ao identificar objetos predominantes em imagens simples. Sua capacidade de classificação é eficaz principalmente quando o objeto de interesse está bem destacado, centralizado e em um fundo neutro.

No entanto, ao lidar com imagens mais complexas, especialmente aquelas com múltiplos elementos visuais, sobreposição de objetos ou fundo poluído, o modelo tende a apresentar limitações. Em muitos casos, ele reconhece apenas o objeto mais evidente ou realiza previsões incorretas, o que é compreensível considerando que foi treinado com a base ImageNet, onde cada imagem possui apenas um rótulo principal.

Quanto à organização do projeto, as alterações propostas foram adaptadas de forma prática. Em vez de utilizar múltiplos diretórios como treino, validação e teste, optou-se por usar apenas um diretório de entrada com imagens não rotuladas. O modelo pré-treinado foi então utilizado para classificar automaticamente essas imagens, que foram organizadas em subpastas dentro da estrutura `datasets/val_classified`, com base no rótulo previsto. Essa abordagem facilitou a visualização dos resultados e permitiu analisar facilmente os acertos e erros de classificação.

## 📸 Exemplos de Resultados

- Imagem original com o rótulo previsto corretamente, com alta confiança (Zebra classificada como Zebra)

![alt text](image-2.png)

- Imagem original com o rótulo previsto incorretamente ou com baixa confiança (Girafa classificada como Zebra)

![alt text](image-3.png)

- Visualização da estrutura de diretórios gerada automaticamente em `datasets/val_classified`, mostrando imagens agrupadas por classe prevista

![alt text](image-4.png)

---

**Desenvolvido por Guilherme Caldas**  
MBA em BI & Data Science, Ibmec
