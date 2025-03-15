# Audio Quality Metrics

Esse repositório contém um script em Python para avaliar a qualidade do áudio utilizando três métricas principais:

- **STOI (Short-Time Objective Intelligibility):** Mede a inteligibilidade da fala.
- **PESQ (Perceptual Evaluation of Speech Quality):** Mede a qualidade perceptual do áudio.
- **SI-SDR (Scale-Invariant Signal-to-Distortion Ratio):** Mede a relação sinal-ruído.

## Instalação
Antes de executar o script, instale as dependências necessárias:

```bash
pip install torch torchaudio torchmetrics[audio] pesq pystoi tqdm
```

## Uso
O script compara arquivos de áudio limpos e com ruído e gera um arquivo CSV com as métricas de qualidade.

### Executando o script

```bash
python audio_quality_assessment_torchmetrics.py -c caminho/para/audio_limpo.wav -n caminho/para/audio_ruidoso.wav -o resultados.csv
```

### Parâmetros
- `-c`, `--clean`: Caminho para o arquivo de áudio limpo.
- `-n`, `--noisy`: Caminho para o arquivo de áudio com ruído.
- `-o`, `--output`: Nome do arquivo de saída (padrão: `output_quality.csv`).

## Interpretação dos Resultados
O script gera um arquivo CSV com os seguintes valores:

| Arquivo | STOI | PESQ | SI-SDR |
|---------|------|------|--------|
| audio.wav | 0.85 | 3.2 | 15.0 |

- **STOI**: Valores próximos de 1 indicam melhor inteligibilidade.
- **PESQ**: Varia de -0.5 a 4.5, onde valores mais altos indicam melhor qualidade perceptual.
- **SI-SDR**: Quanto maior o valor, menor a distorção do sinal.

