# 🤖 Transformers para Geração de Texto com GPT-2

Este projeto demonstra o uso de modelos Transformers (especificamente o **GPT-2**) para geração de textos contextualizados. Implementado no Google Colab, explora componentes-chave como tokenização, positional encoding, self-attention e geração de sequências, utilizando a biblioteca Hugging Face Transformers.

---

## 🎯 Objetivo

Treinar um pipeline de geração de texto utilizando o GPT-2, compreendendo:
- Preparação de texto via tokenização
- Codificação posicional para contexto sequencial
- Mecanismos de self-attention
- Geração de textos coerentes em diferentes contextos

---

## ⚙️ Tecnologias Utilizadas

- Python 3.10+
- Transformers 4.30+
- PyTorch / TensorFlow (via Hugging Face)
- Google Colab (com suporte opcional a GPU/TPU)
- Bibliotecas auxiliares: `bertviz`, `matplotlib`, `numpy`

---

## 🔑 Componentes Principais

### 1. **Tokenização com BERT**
- Convertemos texto em tokens numéricos usando `BertTokenizer`.
- Exemplo: `"I read a good novel."` → `['[CLS]', 'i', 'read', 'a', 'good', 'novel', '.', '[SEP]']`

### 2. **Positional Encoding**
- Codificação senoidal para representar posições de tokens.
- Visualização matricial das relações posicionais.

### 3. **Self-Attention**
- Visualização interativa com `bertviz` para interpretar como o modelo relaciona palavras (ex: ambiguidade de "novel").

### 4. **GPT-2 para Geração**
- Geração de textos com o modelo pré-treinado GPT-2 (137M parâmetros).
- Customização de parâmetros como `max_length` e `num_return_sequences`.

---

## 🛠️ Configuração Rápida

```python
!pip install transformers matplotlib bertviz numpy

from transformers import pipeline
generator = pipeline('text-generation', model='gpt2')
generator("AI will change the future because", max_length=50, num_return_sequences=3)
```

---

## 📊 Exemplos de Saída

**Input**: `"Star Trek"`  
**Output** (truncado):
```text
[{'generated_text': 'Star Trek: Deep Space Nine...'},
 {'generated_text': 'Star Trek: Voyager - The Voyage Home...'},
 {'generated_text': 'Star Trek: The Next Generation episode...'}]
```

**Input**: `"This movie seemed really long."`  
**Output**: Gera críticas cinematográficas contextualizadas com até 300 tokens.

---

# ⚠️ Limitações Computacionais

A execução do **GPT-2 Large** para geração de textos apresenta os seguintes desafios técnicos:

## 🔧 **Requisitos de Hardware**
- **GPUs Dedicadas Recomendadas**:  
  - Tesla T4 / V100 (Google Colab Pro)  
  - NVIDIA A100 (AWS/GCP)  
  - *CPU não é recomendada*: Processamento extremamente lento (~10x mais demorado).

## 🚨 **Problemas Comuns**
- **Memória Insuficiente**:  
  O modelo consome > 5GB de VRAM (risco de `CUDA Out of Memory` em GPUs básicas).  
- **Latência Elevada**:  
  Gerações longas (`max_length > 100`) podem levar minutos sem GPU.  
- **Compatibilidade**:  
  Versões antigas do PyTorch/Transformers podem causar conflitos.

---

**Nota**: O código para GPT-2 Large está comentado por padrão. Se tiver recursos adequados, descomente-o para testar o modelo completo.  

## 🧠 Conceitos Abordados

- Arquitetura Transformer
- Tokenização e Embeddings Contextuais
- Mecanismos de Atenção Multi-Head
- Geração Autoregressiva
- Interpretabilidade de Modelos via Visualização

---

## 🌍 Aplicações Práticas

- Geradores de conteúdo para marketing
- Assistência à escrita criativa
- Chatbots contextualizados
- Expansão de datasets para NLP
- Pesquisa em modelos de linguagem

---

## ✅ Conclusão

Este projeto ilustra o poder do GPT-2 para geração de texto, desde a preparação de dados até a produção de sequências complexas. A integração de visualizações (`bertviz`) e técnicas como positional encoding oferece insights valiosos sobre o funcionamento interno de modelos Transformers.

---

- 📌 **Autor**: Hian Stafford
- 📩 **Email**: hian.correa@gmail.com
```text
  /\_/\  
 ( -.- ) 
  > ^ < 
```
