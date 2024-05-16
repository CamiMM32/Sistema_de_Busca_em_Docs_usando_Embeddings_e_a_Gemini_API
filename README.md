## Sistema de Busca em Documentos usando Embeddings e a Gemini API
Este código demonstra um sistema simples de busca em documentos utilizando embeddings gerados pela Gemini API do Google.

# - O sistema realiza os seguintes passos:
  * Geração de Embeddings:

     Utiliza a biblioteca google-generativeai para gerar embeddings de documentos.
     Define uma função embed_fn para encapsular a chamada à API de embeddings.
     Aplica a função embed_fn a um DataFrame Pandas contendo títulos e conteúdos de documentos, armazenando os embeddings na coluna "embedding".

  * Busca por Similaridade:

    Define uma função gerar_e_buscar_consulta que recebe uma consulta como entrada.
    Gera embeddings para a consulta usando a Gemini API.
    Calcula a similaridade entre os embeddings da consulta e os embeddings dos documentos no DataFrame usando o produto escalar.
    Retorna o conteúdo do documento mais similar à consulta.

  * Reescrita do Texto:

    Utiliza o modelo de linguagem gemini-1.0-pro para reescrever a resposta da busca de forma mais informal.
    Define um prompt que instrui o modelo a reescrever o texto sem adicionar novas informações.

# - Como utilizar:

  * Instalar a biblioteca google-generativeai:

    !pip install -U -q google-generativeai

  * Definir a chave da API do Google:

    Substitua "API_Key" pela sua chave da API.
    GOOGLE_API_KEY = "API_Key"
    genai.configure(api_key=GOOGLE_API_KEY)

# - Executar o código:

  * Execute as células do notebook para gerar os embeddings dos documentos, definir a consulta, realizar a busca e reescrever o resultado.

# - Exemplo:

  * A consulta "Como faço para trocar marchas em um carro do Google?" 
  * Retorna o seguinte resultado:
      Seu Googlecar tem uma transmissão automática. Para trocar marchas, basta mover a alavanca de câmbio para a posição desejada
  * O modelo de linguagem então reescreve o resultado da seguinte forma:
      Ei, seu Googlecar maneiro! Ele tem uma transmissão automática, então você não precisa se preocupar em trocar marchas. Só precisa dar uma cutucadinha na alavanca de câmbio e pronto,       marcha trocada!

# - Observações:

  * O modelo de embeddings utilizado é o "models/embedding-001".
  * As configurações de temperatura e número de candidatos para o modelo de geração de texto podem ser ajustadas na variável generation_config.

# - Conclusão

  * Este código apresenta um exemplo básico de como utilizar embeddings e a Gemini API para criar um sistema de busca em documentos. É possível estender este sistema para lidar com           conjuntos de dados maiores, refinar o processo de busca e incorporar outros recursos da Gemini API.
