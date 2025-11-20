# Macroeconomic-Random-Forest
Implementação do modelo Macroeconomic Random Forest (MRF) em R, que adapta o Random Forest para modelar parâmetros macroeconômicos variáveis no tempo (GTVPs). Foco na previsão de indicadores dos EUA (Produto Interno Bruto, Desemprego e Inflação) usando o dataset FRED-QD.

Este repositório contém o código R para replicar e estender o modelo Macroeconomic Random Forest (MRF), conforme proposto no artigo de Philippe Goulet Coulombe (2024). O MRF é uma técnica inovadora que aplica o Machine Learning - ML para estimar coeficientes em equações macroeconômicas que mudam ao longo do tempo.

# Principais Contribuições do MRFParâmetros Variáveis no Tempo Generalizados (GTVPs): 
- O MRF produz GTVPs, uma ferramenta versátil que engloba não-linearidades populares como quebras estruturais, transição suave e chaveamento de regime (regime switching).
- Interpretabilidade: Ao contrário de muitas abordagens puras de ML, o MRF é diretamente interpretável através de seus GTVPs.
- Ganho Preditivo: O modelo demonstra ganhos de previsão, notavelmente na previsão da drástica alta no desemprego em 2008.

#Engenharia de Recursos (St):
O sucesso do MRF depende criticamente do seu vetor de estado (St), um conjunto rico de features que impulsiona o componente Random Forest. O código implementa todas as etapas de engenharia de recursos para a construção do St:
- Fatores PCA Tradicionais: Compressão de dados cross-sectional das 248 séries macroeconômicas.
- Moving Average Factors (MAFs): Fatores de componentes principais aplicados sobre as defasagens de cada variável, projetados para comprimir a informação do polinômio de defasagem e aumentar o poder preditivo.
- Defasagens da Variável Alvo e de todas as Séries: Incluídas para capturar dinâmicas endógenas e comportamentos de chaveamento.
- Tendência Temporal: Inclusão explícita de $t$ para modelar mudanças estruturais lentas.


