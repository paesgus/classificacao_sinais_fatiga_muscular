# Análise Biomecânica com Visão Computacional para Detecção de Fadiga Muscular

Este repositório reúne os notebooks e artefatos de um pipeline de pesquisa para:

- aumento de dados em vídeo;
- detecção de landmarks;
- extração e preparação de features;
- treinamento de modelos de deep learning (como LSTM);
- validação e testes em tempo real.

O projeto está organizado em etapas numeradas para facilitar a reprodução dos experimentos e a escrita da tese.

## Estrutura do repositório

Arquivos principais:

- `01-data_augmentation.ipynb`: geração de variações dos vídeos de entrada.
- `02-landmarks_detector.ipynb`: detecção de pontos/chaves (landmarks) por frame.
- `03-extract_features.ipynb`: transformação de landmarks em features tabulares.
- `04-data_preparation.ipynb`: limpeza, padronização e preparação do dataset final.
- `05-deep_learning.ipynb`: variações de treinamento e avaliação de modelos de deep learning.
- `06-real_time.ipynb`: inferência em fluxo ao vivo.
- `09-views.ipynb`: visualizações e inspeção de resultados.
- `teste.ipynb`: notebook para testes e testes de hipóteses de código.
- `requirements.txt`: dependências Python.

Diretórios de dados e publicações:

- `entrada/`: dados brutos de entrada (vídeos) - não disponibilizados devido LGPD.
- `entrada/aug/`: dados aumentados (vídeos) - não disponibilizados devido LGPD.
- `rotulo/`: rótulos (ex.: `labels_falha.csv`).
- `saida/landmarks/`: landmarks extraídos.
- `saida/feature_extraction/`: features extraídas por arquivo.
- `saida/feature_extraction_labeled/`: features consolidadas com rótulos.
- `saida/resultados/`: resultados de experimentos.
- `saida/videos/`: vídeos processados.
- `documento/`: arquivos da tese em LaTeX.
- `artigo/`: arquivos do artigo submetido, em LaTeX.
- `slides/`: material de apresentação.

## Pipeline recomendado

Para reproduzir o fluxo completo, execute os notebooks na ordem abaixo:

1. `01-data_augmentation.ipynb`
2. `02-landmarks_detector.ipynb`
3. `03-extract_features.ipynb`
4. `04-data_preparation.ipynb`
5. `05-deep_learning.ipynb`
6. `06-real_time.ipynb` para teste online
7. `09-views.ipynb` para análise visual

Observação: alguns notebooks representam tentativas/abordagens alternativas. Use-os para comparação experimental, mantendo um registro dos parâmetros utilizados.

## Requisitos

- Python 3.10+ (recomendado)
- Jupyter Notebook ou JupyterLab
- Dependências listadas em `requirements.txt`

Principais bibliotecas utilizadas:

- `mediapipe`
- `opencv-python` e `opencv-contrib-python`
- `numpy`, `pandas`, `scikit-learn`, `scipy`
- `matplotlib`, `seaborn`
- `jax`, `jaxlib`

## Configuração do ambiente

No Windows (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Para abrir os notebooks:

```powershell
jupyter notebook
```

## Organização de dados esperada

Antes de rodar o pipeline, confirme:

1. Vídeos de entrada em `entrada/`.
2. Arquivo de rótulos em `rotulo/`.
3. Permissão de escrita na pasta `saida/`.

Se necessário, ajuste caminhos nos notebooks para refletir sua estrutura local.

## Resultados e rastreabilidade

Recomendação para experimentos reprodutíveis:

1. Registrar versão do notebook usado.
2. Salvar parâmetros de treino (janela temporal, arquitetura, taxa de aprendizado, épocas).
3. Exportar métricas e matrizes de confusão em `saida/resultados/`.
4. Versionar arquivos relevantes da pasta `documento/` para sincronizar texto e evidências experimentais.

## Problemas comuns

- Erros de webcam/captura: verificar permissões do sistema e índice da câmera no OpenCV.
- Erros de pacote ausente: reativar o ambiente virtual e reinstalar `requirements.txt`.
- Diferença de caminhos entre máquinas: usar caminhos relativos a partir da raiz do projeto.


## Autor

Projeto de pesquisa desenvolvido no contexto de tese (USP/PPgSI).
