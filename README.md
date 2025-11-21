# 🕵️ Detector de Phishing com Inteligência Artificial

> **Projeto Acadêmico - Unifeob**: Desenvolvido para o **Projeto Integrado** das disciplinas de **Inteligência Artificial** e **Segurança em Sistemas Computacionais**.

## 🎓 Sobre o Projeto

Este trabalho foi desenvolvido como requisito avaliativo na faculdade **Unifeob**, integrando conhecimentos de Cibersegurança e Machine Learning para resolver problemas reais de proteção de dados.

### O Cenário: Mundial Eletrônica
O estudo de caso foca na empresa fictícia **Mundial Eletrônica**, que enfrentava riscos de segurança com funcionários caindo em golpes de engenharia social. A solução proposta atua como uma barreira de defesa automatizada, analisando a semântica de e-mails para identificar ameaças antes que elas causem danos.

## 🚀 Tecnologias Utilizadas

* **Python 3**: Linguagem base para processamento de dados.
* **Scikit-Learn**: Framework para construção do pipeline de Inteligência Artificial.
* **TfidfVectorizer (NLP)**: Técnica para transformar texto cru em vetores numéricos.
* **MLPClassifier (Redes Neurais)**: Algoritmo de classificação para detectar padrões de fraude.

## 🧠 Como Funciona

O sistema não utiliza regras estáticas (como listas de palavras proibidas). Ele emprega um pipeline de aprendizado de máquina:

1.  **Vetorização:** O algoritmo `TF-IDF` converte as palavras dos e-mails em números, atribuindo pesos maiores para termos que definem o contexto da mensagem.
2.  **Classificação:** Uma **Rede Neural (MLP)** analisa esses pesos e identifica padrões não lineares típicos de phishing (ex: senso de urgência + solicitação financeira), gerando um **score de confiança**.

```python
# Exemplo do Pipeline implementado
modelo = make_pipeline(
    TfidfVectorizer(),
    MLPClassifier(hidden_layer_sizes=(12,), max_iter=2000, random_state=42)
)

```

# 📦 Instalação e Execução
Certifique-se de ter o Python instalado e execute:

Instale as dependências:

```python

pip install scikit-learn numpy

```
Execute:

```python
python phishing_detector.py

```

💻 Exemplo de Resultado
Ao analisar um e-mail suspeito no terminal:

Entrada:

"Sua conta foi bloqueada, clique aqui urgente para recadastrar sua senha."

Saída do Modelo:


------------------------------------------------------------
🚨 RESULTADO: PHISHING DETECTADO!
📊 Confiança da IA: 99.98%
🛡️  Recomendação: Cuidado! Possível Engenharia Social.
------------------------------------------------------------
✒️ Autoria
Projeto desenvolvido para o curso de ADS da Unifeob.

Vinicius da Silva Giovaneli - RA: 24000478
João Gabriel da Silva - RA: 25001142
Luis Felipe da Silva Nogueira - RA: 24000897
Antonio Gabriel Moraes Vieira - RA: 24001919
