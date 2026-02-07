# Controle de Qualidade do Processo de Aerolevantamento para REURB

**Assunto:** Diretrizes Técnicas para o Controle de Qualidade em Projetos de Aerolevantamento com Drones Aplicados à Regularização Fundiária Urbana (REURB)

**Data:** 07 de fevereiro de 2026

**Autor:** Manus IA, a pedido de Erison Barros

---

## 1. Introdução

A Regularização Fundiária Urbana (REURB), instituída pela Lei nº 13.465/2017, depende fundamentalmente de uma base cartográfica precisa e confiável para garantir a segurança jurídica e a correta individualização dos imóveis. O aerolevantamento com Aeronaves Remotamente Pilotadas (RPA), popularmente conhecidas como drones, emergiu como uma tecnologia essencial para a produção desta cartografia em núcleos urbanos informais, oferecendo um excelente equilíbrio entre custo, agilidade e acurácia.

Contudo, a simples utilização de drones não garante a qualidade do produto final. Um processo de aerolevantamento é uma cadeia complexa de etapas, onde falhas em qualquer uma delas podem comprometer a acurácia posicional e a fidedignidade dos dados, tornando-os inadequados para fins cadastrais e de registro imobiliário. Portanto, a implementação de um rigoroso **processo de controle de qualidade** é um requisito indispensável, não apenas técnico, mas também legal.

Este documento descreve as etapas, os critérios e as boas práticas para o controle de qualidade em projetos de aerolevantamento com drones para fins de REURB, alinhado às normas técnicas brasileiras e à legislação vigente.

## 2. Arcabouço Normativo e Legal

O controle de qualidade em aerolevantamentos para REURB deve ser fundamentado em um conjunto de normas e legislações que garantem a padronização e a aceitabilidade dos produtos cartográficos.

| Norma/Legislação | Descrição e Relevância para o Controle de Qualidade |
| :--- | :--- |
| **Lei nº 13.465/2017** | Define a REURB e exige, para o projeto de regularização, a apresentação de "planta e memorial descritivo da área". A qualidade destes documentos é a base para a segurança jurídica do processo. |
| **Decreto nº 9.310/2018** | Regulamenta a REURB e detalha no Art. 30 que o projeto deve conter um "levantamento topográfico georreferenciado" que demonstre unidades, construções, sistema viário, etc. |
| **Decreto nº 89.817/1984** | Instituiu o Padrão de Exatidão Cartográfica (PEC), que classifica os produtos cartográficos em Classes (A, B, C) com base em sua exatidão posicional. Embora antigo, ainda é a base legal. |
| **ET-CQDG (DSG)** | A Especificação Técnica para Controle de Qualidade de Dados Geoespaciais, do Exército Brasileiro, modernizou o PEC para o ambiente digital, criando o **PEC-PCD**. É a referência técnica principal para avaliar a acurácia de produtos digitais como ortoimagens e modelos de elevação. |
| **ABNT NBR 17.047:2022** | Estabelece os procedimentos para levantamento cadastral territorial para registro público, definindo requisitos de precisão específicos (ex: 8 cm para vértices de imóveis urbanos). |
| **ABNT NBR 13.133:2021** | Norma geral para execução de levantamento topográfico, fundamental para o levantamento dos pontos de controle em solo. |
| **ANAC / DECEA / MD** | Regulamentam a operação de drones no Brasil (RBAC-E nº 94), o acesso ao espaço aéreo e o registro de entidades para aerolevantamento, sendo requisitos legais para a execução do voo. |

## 3. Fases do Controle de Qualidade no Aerolevantamento

O controle de qualidade deve ser um processo contínuo, aplicado em todas as fases do projeto, desde o planejamento até a entrega final. A seguir, detalha-se um checklist de verificação para cada etapa.

### Fase 1: Planejamento e Preparação (Pré-Voo)

Nesta fase, a qualidade é projetada. Erros de planejamento são difíceis e caros de corrigir posteriormente.

| Item de Controle | Critério de Aceitação / Ação de Verificação |
| :--- | :--- |
| **Definição do GSD** | O *Ground Sample Distance* (GSD) deve ser compatível com a escala final e a necessidade de identificação de feições. Para REURB, GSDs entre 2 cm e 5 cm são recomendados. |
| **Plano de Voo** | Verificar a altura de voo (consistente com o GSD), a velocidade da aeronave, e principalmente a **sobreposição de imagens (mínimo de 80% frontal e 70% lateral)**. Voos duplos (grid cruzado) são recomendados em áreas urbanas densas. |
| **Pontos de Controle (GCPs)** | Planejar a distribuição homogênea de Pontos de Apoio (GCPs) e Pontos de Verificação (Checkpoints) na área. Mínimo de 5 GCPs e 4 Checkpoints. Os Checkpoints devem ser independentes e não utilizados no processamento. |
| **Levantamento dos Pontos** | Os pontos de controle devem ser levantados com métodos de precisão superior à do produto final (ex: GNSS RTK/PPK), seguindo a NBR 13.133. A qualidade do levantamento dos GCPs limita a qualidade final do aerolevantamento. |
| **Documentação Legal** | Verificar se a aeronave, o piloto e a empresa estão com todos os registros válidos na ANAC, DECEA e Ministério da Defesa. |

### Fase 2: Execução (Aquisição de Dados)

Nesta fase, a qualidade é executada conforme o planejado.

| Item de Controle | Critério de Aceitação / Ação de Verificação |
| :--- | :--- |
| **Condições Meteorológicas** | O voo deve ser realizado em condições ideais: céu limpo ou com poucas nuvens (para evitar sombras), e ventos de baixa intensidade. |
| **Qualidade das Imagens** | Realizar uma verificação em campo da qualidade das imagens capturadas, observando a ausência de borrões de movimento (*motion blur*), exposição correta e foco adequado. |
| **Execução do Plano de Voo** | Monitorar o voo para garantir que a aeronave seguiu o plano de voo, cobrindo toda a área com a sobreposição planejada. |
| **Log de Dados GNSS** | Para voos com sistema PPK/RTK, garantir que os dados brutos do receptor GNSS da base e do drone foram corretamente gravados durante todo o voo. |

### Fase 3: Processamento Fotogramétrico

Nesta fase, a qualidade é processada e os produtos são gerados.

| Item de Controle | Critério de Aceitação / Ação de Verificação |
| :--- | :--- |
| **Relatório de Aerotriangulação** | Analisar o relatório de processamento: verificar o erro médio quadrático (RMSE) nos GCPs e o erro de reprojeção das imagens. Valores altos indicam problemas no levantamento dos pontos ou na calibração da câmera. |
| **Nuvem de Pontos Densa** | Inspeção visual da nuvem de pontos para verificar a densidade, a ausência de ruídos excessivos e a correta representação das feições do terreno e das edificações. |
| **Modelo Digital de Terreno (MDT)** | Verificar se o processo de classificação e filtragem da nuvem de pontos removeu eficientemente os objetos acima do solo (edificações, vegetação) para gerar um MDT limpo e representativo. |
| **Ortoimagem (Mosaico)** | Inspeção visual detalhada da ortoimagem final para identificar distorções, artefatos, duplicidade de feições, e garantir a homogeneidade radiométrica (cores e brilho) em toda a área. |

### Fase 4: Análise de Qualidade e Validação Final

Esta é a fase final de verificação, onde a acurácia do produto é quantitativamente medida e classificada.

| Item de Controle | Critério de Aceitação / Ação de Verificação |
| :--- | :--- |
| **Acurácia Posicional (PEC-PCD)** | Utilizando os **Pontos de Verificação (Checkpoints)**, calcular as discrepâncias entre as coordenadas conhecidas (medidas em campo) e as coordenadas medidas no produto final (ortoimagem/MDT). Calcular o RMSE para as componentes X, Y e Z. |
| **Classificação do Produto** | Comparar o RMSE obtido com os valores da ET-CQDG para a escala de referência do projeto. Por exemplo, para um produto na escala **1:1000**, os valores para a **Classe A** do PEC-PCD são: **RMSE Planimétrico ≤ 0,17 m** e **RMSE Altimétrico ≤ 0,17 m**. |
| **Análise de Completude** | Verificar se todos os elementos necessários para a REURB (limites de lotes, edificações, muros, vias) são claramente visíveis e passíveis de vetorização a partir da ortoimagem. |
| **Relatório de Controle de Qualidade** | Elaborar um relatório técnico detalhado, apresentando toda a metodologia de controle de qualidade, os resultados da análise de acurácia posicional (incluindo a lista de discrepâncias nos checkpoints) e a classificação final do produto segundo o PEC-PCD. |

## 4. Conclusão

O controle de qualidade em aerolevantamentos para REURB não é um mero formalismo técnico, mas sim o pilar que sustenta a validade jurídica e a utilidade prática dos dados gerados. A adoção de um fluxo de trabalho estruturado, com verificações em todas as etapas e uma avaliação final de acurácia baseada em normas consagradas como o PEC-PCD, garante que os produtos cartográficos sejam precisos, confiáveis e adequados para a finalidade de regularização fundiária.

A fiscalização e a exigência, por parte do contratante, de um **Relatório de Controle de Qualidade** detalhado são as ferramentas mais eficazes para assegurar que o investimento em aerolevantamento se traduza em uma base cadastral sólida e perene para o município.

---

## 5. Referências

1.  Associação Brasileira de Normas Técnicas (ABNT). **NBR 17047:2022** - Levantamento cadastral territorial para registro público — Procedimento.
2.  Brasil. **Decreto nº 89.817, de 20 de junho de 1984**. Estabelece as Instruções Reguladoras das Normas Técnicas da Cartografia Nacional.
3.  Brasil. **Decreto nº 9.310, de 15 de março de 2018**. Institui as normas gerais e os procedimentos aplicáveis à Regularização Fundiária Urbana.
4.  Brasil. **Lei nº 13.465, de 11 de julho de 2017**. Dispõe sobre a regularização fundiária rural e urbana.
5.  Diretoria do Serviço Geográfico (DSG). **Especificação Técnica para Controle de Qualidade de Dados Geoespaciais (ET-CQDG)**. 1ª Edição. 2016.
