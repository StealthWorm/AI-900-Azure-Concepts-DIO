# Criando e Testando um Modelo Preditivo com Azure Machine Learning

Neste tutorial, vamos abordar os passos básicos para criar um modelo preditivo e testar um ponto de extremidade configurado utilizando o ambiente da Azure Machine Learning.

## Passo 1: Configuração do Ambiente

1. Acesse o portal da Azure e navegue até o serviço Azure Machine Learning.
2. Crie ou selecione um workspace/Recurso de Azure Machine Learning.
   - Não é necessário mecher em nenhuma das configurações de Rede, Criptografia, Identidade e Marcas em um teste simples.
   - Caso não exista um Grupo de Recursos, crie-o.
3. Clique em "Examinar + Criar" ou no botão inferior "Criar".
4. Acesse o Azure Machine Learning Studio através da opção "Ir para o recurso" e "Iniciar o estúdio".
5. Caso não exista um ambiente de trabalho, será necessário criar um.

## Passo 2: Desenvolvimento do Modelo

1. Carregue seus dados no ambiente da Azure Machine Learning.
   - Acesse a opção do menu esquerdo "ML Automatizado".
   - Clique em "Novo trabalho de ML automatizado".
   - Preencha as informações básicas.
   - Em "tipo de tarefa", selecione Regressão.
   - Na tabela de Seleção de dados clique em "Criar". Será aberto um modal para seleçãod e dados.
   - Preencha as nomenclaturas e em "Tipo" selecione "Tabular".
   - Em "Fonta de Dados" selecione "De arquivos da Web" e clique em avançar.
   - Na "URL da web", forneça a URL base utilizada para testes fornecida pela documentação da Azure. Aguarde a validação dos dados após clicar em "Avançar".
   - > **_https://aka.ms/bike-rentals_**
   - Mantenhas as opções padrão para "Formato do arquivo", "Delimitador" e "Codificação". Para o campo "Cabeçalhos de coluna" altere para "Somente o primeiro arquivo tem cabeçalhos" e clique em "Avançar".
   - Avance a parte de Esquemas, revise e então clique em "Criar".
   - Ele retornará para a etapa Tipo de tarefa e dados", selecione os dados criados na tabela e clique em "Avançar".
   - Em "Configurações de tarefas" selecione "rentals(Integer)" na "coluna de destino".
   - Clique em "Exibir definições de configuração adicionais":
      - Métrica primária: NormalizedRootMeanSquaredError
      - Desmarque os checks de "Explicar melhor o modelo" e "Usar todos os modelos suportados", casos estejam marcados.
      - Modelos permitidos: "RandomForest" e "LightGBM".
      - Salvar.
   - Em "Limites":
      -  Máximo de avaliações = 3
      - Máximo de avaliações simultâneas = 3
      - Máximo de nós = 3
      - Limite de pontuação da métrica = 0.085
      - Tempo limite do experimento (minutos) = 15
      - Tempo limite de iteração (minutos) = 15
      - Habilitar encerramento antecipado = true
      - As demais informações manter padrão.
    - Computação: manter seleção padrão
    - clique em "Enviar trabalho de terinamento". **Essa etapa pode demorar alguns minutos dependendo da base utilizada.**
   
2. Realize a divisão dos dados em conjuntos de treinamento e teste. Quando o trabalho automatizado de aprendizado de máquina for concluído, você poderá revisar o melhor modelo treinado.
3. Selecione o melhor caso ao acessar os procedimentos realizados na aba "Tarefas (Jobs)".
4. Selecione a aba Métricas e Visualize os gráficos Preditivos com a comparação dos valores experados X valores reais.

## Passo 3: Treinamento do Modelo

1. Acesse a aba de Modelo e crie um novo modelo baseado em saída  de trabalho.
2. Selecione a hash do melhor caso obtido e clique em "Avançar".
3. Ajuste os hiperparâmetros do modelo conforme necessário.
4. Preencha as demais informações para nomenclatura e clique em "Registro".
8. Avalie o desempenho do modelo utilizando métricas apropriadas.

## Passo 4: Implantação do Modelo

1. Crie um ponto de extremidade para o seu modelo treinado.
   - Selecione o modelo criado e va até a aba "Pontos de Extremidade" do meno esquerdo da tela.
   - Clique em "Criar" e seleicone o modelo desejado.
   - Mantenha os demais dados padrão ou altere conforme necessidade e clique em "Criar". Esse processo pode levar alguns minutos.
4. Configure as opções de implantação, como escalabilidade e recursos computacionais, caso necessário.
5. Implante o modelo e aguarde a conclusão do processo.

## Passo 5: Teste do Ponto de Extremidade

1. Utilize ferramentas de teste disponíveis na Azure Machine Learning para enviar solicitações ao ponto de extremidade do modelo.
   - Após a conclusão do processo de implantação, uma aba "Testar", acesse a mesma.
   - Configure o Json de teste no campo "Inserir dados para teste".
   - A documentação oficial informa um conjunto de dados que podem ser utilizados para a URL que estamos buscando os dados, para buscar com base em uma série de informações pré-configuradas.
  ```
  {
    "input_data": {
      "data": [
          {
           "day": 1,
           "mnth": 1,   
           "year": 2022,
           "season": 2,
           "holiday": 0,
           "weekday": 1,
           "workingday": 1,
           "weathersit": 2, 
           "temp": 0.3, 
           "atemp": 0.3,
           "hum": 0.3,
           "windspeed": 0.3 
         }
      ]
    },
    "GlobalParameters": 1.0
  }
  ```
3. Avalie as respostas retornadas pelo modelo no campo "Resultado do teste", para garantir que esteja funcionando corretamente.
4. Realize testes de carga para verificar a capacidade de resposta do ponto de extremidade em diferentes condições.

## Conclusão

Neste tutorial, cobrimos os passos fundamentais para criar e testar um modelo preditivo utilizando o ambiente da Azure Machine Learning. Este é apenas um ponto de partida, e você pode explorar ainda mais as capacidades avançadas oferecidas pela plataforma para aprimorar e escalar seus projetos de IA.

Para mais informações, basta acessar a [Documentação oficial da Microsoft Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)

