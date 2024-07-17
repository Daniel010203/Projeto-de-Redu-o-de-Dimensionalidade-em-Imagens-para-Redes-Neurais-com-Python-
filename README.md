Projeto de Redução de Dimensionalidade em Imagens para Redes Neurais com Python

Este projeto demonstra como realizar a redução de dimensionalidade em imagens, criando versões em escala de cinza e binária das imagens originais. O objetivo é facilitar o processamento e a análise de imagens em projetos de aprendizado de máquina, especialmente redes neurais.

Funcionalidades

- Carregar uma imagem a partir de um caminho especificado.
- Converter a imagem para escala de cinza.
- Converter a imagem para formato binário.
- Exibir as imagens original, em escala de cinza e binária.

Requisitos

- Python 3.x
- OpenCV
- NumPy
- Matplotlib

Você pode instalar as bibliotecas necessárias usando pip:

```bash
pip install opencv-python numpy matplotlib
```

## Uso

1. Clone o repositório:

```bash
git clone https://github.com/Daniel010203/Projeto-de-Redu-o-de-Dimensionalidade-em-Imagens-para-Redes-Neurais-com-Python-.git
```

2. Navegue até o diretório do projeto:

```bash
cd Projeto-de-Redu-o-de-Dimensionalidade-em-Imagens-para-Redes-Neurais-com-Python-
```

3. Modifique a variável `image_path` na função `main` do arquivo `image_reduction.py` para apontar para o arquivo de imagem desejado.

4. Execute o script:

```bash
python image_reduction.py
```

## Explicação do Script

### Funções

- **load_image(image_path)**: Carrega a imagem a partir do caminho especificado.
- **convert_to_grayscale(image)**: Converte a imagem para escala de cinza usando OpenCV.
- **convert_to_binary(image, threshold=127)**: Converte a imagem para formato binário usando um limiar especificado.
- **plot_images(original, gray, binary)**: Plota as imagens original, em escala de cinza e binária usando Matplotlib.

### Exemplo

Aqui está uma visão geral do script principal:

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

def load_image(image_path):
    image = cv2.imread(image_path)
    if image is None:
        raise ValueError(f"Não foi possível carregar a imagem do caminho: {image_path}")
    return image

def convert_to_grayscale(image):
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
    return gray_image

def convert_to_binary(image, threshold=127):
    gray_image = convert_to_grayscale(image)
    _, binary_image = cv2.threshold(gray_image, threshold, 255, cv2.THRESH_BINARY)
    return binary_image

def plot_images(original, gray, binary):
    plt.figure(figsize=(10, 4))
    
    plt.subplot(1, 3, 1)
    plt.title('Original')
    plt.imshow(cv2.cvtColor(original, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    
    plt.subplot(1, 3, 2)
    plt.title('Gray Scale')
    plt.imshow(gray, cmap='gray')
    plt.axis('off')
    
    plt.subplot(1, 3, 3)
    plt.title('Binary')
    plt.imshow(binary, cmap='gray')
    plt.axis('off')
    
    plt.tight_layout()
    plt.show()

def main():
    image_path = 'caminho/para/sua/imagem.jpg'
    original_image = load_image(image_path)
    gray_image = convert_to_grayscale(original_image)
    binary_image = convert_to_binary(original_image)
    plot_images(original_image, gray_image, binary_image)

if __name__ == "__main__":
    main()
```

## Contribuição

Sinta-se à vontade para fazer um fork deste repositório e enviar pull requests. Para mudanças significativas, abra uma issue primeiro para discutir o que você gostaria de alterar.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Este README fornece uma visão clara e concisa do projeto, incluindo instruções de configuração e uso, além de uma breve explicação das funcionalidades principais. Personalize-o conforme necessário para atender às especificidades do seu projeto.
