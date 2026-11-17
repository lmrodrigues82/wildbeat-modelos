# WildBeat — modelos

Arquivos que o app WildBeat (protótipo de um app infantil que reconhece bichos pelo som e pela foto)
baixa uma única vez para funcionar sem internet. Este repositório só guarda modelos e listas de
espécies; nenhum dado de usuário.

Os arquivos ficam nas [Releases](../../releases).

| Arquivo | O que é | Origem e licença |
|---|---|---|
| `modelo-enxuto-v1.tflite` | Reconhecimento de sons (versão reduzida do Perch v2 para ~2.250 espécies do Brasil) | Derivado do [Perch](https://github.com/google-research/perch-hoplite), Google, Apache License 2.0 |
| `bioclip-imagem-int8.onnx` | Reconhecimento por foto (codificador de imagem do BioCLIP, quantizado em int8) | Derivado do [BioCLIP](https://huggingface.co/imageomics/bioclip), Imageomics Institute, MIT License |
| `foto-textos-v1.f16` | Um vetor do BioCLIP por espécie (float16) | Gerado com o BioCLIP a partir da taxonomia do iNaturalist |
| `foto-lista-v1.json` | Lista de ~25 mil animais com registro no Brasil: nome científico, nome popular, grupo e foto de referência (com autor e licença) | Dados do [iNaturalist](https://www.inaturalist.org); cada foto mantém o crédito e a licença do autor |

## Avisos de licença

- Perch: Copyright Google LLC. Licensed under the Apache License, Version 2.0. Este arquivo é uma
  modificação (redução do número de classes e conversão para TFLite).
- BioCLIP: Copyright (c) Imageomics Institute. MIT License. Este arquivo é uma modificação
  (exportação do codificador de imagem para ONNX e quantização int8).
- As fotos de referência listadas em `foto-lista-v1.json` pertencem aos seus autores, sob as licenças
  indicadas em cada item.
