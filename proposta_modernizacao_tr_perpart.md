# Proposta de Modernização do Termo de Referência da PERPART

**Assunto:** Atualização do item 3 (Representação Gráfica) da AÇÃO 4 (Levantamento Planialtimétrico Cadastral Georreferenciado)

**Data:** 07 de fevereiro de 2026

**Autor:** Manus IA, a pedido de Erison Barros

---

## 1. Introdução e Finalidade

Este documento apresenta uma proposta técnica para a modernização do item **3. Representação Gráfica**, contido na **AÇÃO 4 – Levantamento Planialtimétrico Cadastral Georreferenciado** do Termo de Referência (TR) da Pernambuco Participações e Investimentos S/A (PERPART) para serviços de Regularização Fundiária Urbana (REURB). A análise foi fundamentada no TR original (SEI 58008717), nas instruções técnicas fornecidas, em pesquisa no ambiente Google NotebookLM compartilhado, e em normativas técnicas e boas práticas de mercado.

A finalidade desta atualização é alinhar as especificações do TR com os padrões contemporâneos da produção cartográfica digital, garantindo que os produtos gerados possuam **interoperabilidade, qualidade e usabilidade** em Sistemas de Informação Geográfica (SIG), bancos de dados geoespaciais, e processos de Cadastro Territorial Multifinalitário (CTM), mantendo a conformidade com a legislação e as normas técnicas vigentes, como a ABNT NBR 13.133:2021 e a NBR 17.047:2022.

O texto atual, embora funcional, concentra-se em uma visão da cartografia analógica, baseada em pranchas impressas e arquivos CAD (DWG/DXF) como meros desenhos digitais. A modernização proposta desloca o foco para a entrega de **dados geoespaciais estruturados**, tratando o levantamento como uma fonte de informação precisa e reutilizável para diversas finalidades da administração pública.

## 2. Análise Comparativa e Proposta de Alteração

A tabela a seguir detalha a análise do texto original, identifica as lacunas e fragilidades, e apresenta uma proposta de redação modernizada, com as devidas justificativas técnicas.

| Tópico | Texto Original (Resumido) | Análise e Justificativa da Necessidade de Mudança | Proposta de Texto Modernizado |
| :--- | :--- | :--- | :--- |
| **Conceito Central** | "Os desenhos deverão ser apresentados na escala... em papel sulfite... arquivos eletrônicos... para montagem automática da sequência dos desenhos." | O foco está no "desenho" como produto final, seja em papel ou digital. A menção à "montagem automática" reflete uma lógica de pranchas CAD, não de um mapa digital contínuo e inteligente. Falta o conceito de dado geoespacial estruturado. | "A Representação Gráfica do levantamento é um produto cartográfico digital, composto por um conjunto de dados geoespaciais vetoriais estruturados, georreferenciados e com topologia validada, aptos para uso direto em Sistemas de Informação Geográfica (SIG) e bancos de dados espaciais." |
| **Formatos de Entrega** | "...em papel sulfite... Arquivo eletrônico dos trabalhos realizados em DWG ou DXF e Shapefile." | A entrega em papel é obsoleta como produto primário. A menção a DWG/DXF e Shapefile é positiva, mas não especifica a estrutura, o sistema de coordenadas, nem prioriza formatos mais modernos e robustos como o GeoPackage. | "Os dados geoespaciais deverão ser entregues, obrigatoriamente, nos seguintes formatos: **1. GeoPackage (.gpkg):** formato primário, contendo todas as camadas vetoriais com seus respectivos atributos e simbologia. **2. Shapefile (.shp):** como formato secundário para interoperabilidade. **3. DWG/DXF:** com sistema de coordenadas definido e georreferenciado. **4. PDF/A:** para as plantas e peças gráficas finalizadas." |
| **Estrutura de Dados** | "...deverão ser organizados em layers separados, informando a relação cor x pena utilizada." | A organização em *layers* é mencionada, mas de forma superficial e atrelada a aspectos visuais do CAD ("cor x pena"). Falta a exigência de uma nomenclatura padronizada, de atributos (tabela) associados a cada feição e de um dicionário de dados. | "Os dados devem ser estruturados em camadas temáticas (layers) com nomenclatura padronizada (ex: `limite_lote`, `edificacao`, `sistema_viario`, `hidrografia`). Cada feição vetorial deve possuir uma tabela de atributos com informações relevantes (ex: código do lote, área, perímetro, tipo de edificação). Um dicionário de dados explicando cada camada e seus atributos é obrigatório." |
| **Sistema de Referência** | "...adotando o sistema de coordenadas em UTM-SIRGAS 2000..." | A menção ao SIRGAS 2000 / UTM é correta e deve ser mantida. Contudo, a NBR 17.047:2022 detalha requisitos adicionais sobre a representação de coordenadas e projeção que devem ser incorporados. | "Todos os dados devem ser georreferenciados ao Sistema Geodésico de Referência **SIRGAS 2000**, utilizando a projeção cartográfica UTM, com fuso correspondente à localização do núcleo. As coordenadas geodésicas (latitude e longitude) devem ser apresentadas com no mínimo 4 casas decimais nos segundos de arco." |
| **Metadados** | (Não mencionado) | A ausência de metadados é uma falha grave. Sem eles, a origem, a qualidade, a data e a responsabilidade pelos dados se perdem, inviabilizando o reuso seguro e a integração à Infraestrutura Nacional de Dados Espaciais (INDE). | "Cada conjunto de dados entregue deverá ser acompanhado de metadados geoespaciais em conformidade com o perfil **MGB (Perfil de Metadados Geoespaciais do Brasil)**, contendo, no mínimo: título, data, resumo, método de levantamento, acurácia posicional, sistema de referência, responsável técnico e informações de contato." |
| **Qualidade e Acurácia** | "...em conformidade com a NBR 13.133/94 classe - IAPC e IIN..." | A norma citada (NBR 13.133) está desatualizada (a versão vigente é de 2021). Além disso, a NBR 17.047:2022 estabelece requisitos de precisão específicos para levantamento cadastral territorial que são mais adequados. | "A acurácia posicional do levantamento deve atender aos requisitos da **ABNT NBR 17.047:2022**, com uma precisão posicional planimétrica igual ou melhor que 8 cm para os vértices dos imóveis urbanos. O relatório técnico deve apresentar os resultados do controle de qualidade realizado." |
| **Peças Gráficas (Plantas)** | "...desenhos em escalas definidas... planta de articulação..." | A lógica de múltiplas folhas articuladas é herdada da cartografia em papel. Em um ambiente SIG, a visualização é contínua. As plantas impressas ou em PDF são representações do dado, não o dado em si. | "Serão geradas, a partir dos dados vetoriais, as seguintes peças gráficas em formato PDF/A: **1. Planta Individual do Lote:** para cada unidade imobiliária. **2. Planta Geral do Núcleo:** exibindo a totalidade da área levantada. Todas as plantas devem conter, no mínimo: norte magnético, escala gráfica e numérica, malha de coordenadas, tabela de coordenadas dos vértices, legenda de convenções, e carimbo completo conforme NBR 17.047:2022." |

---

## 3. Proposta de Novo Texto para o Item "3. Representação Gráfica"

A seguir, a sugestão de texto completo para substituir o item 3 da AÇÃO 4, incorporando todas as modernizações discutidas.

**3. REPRESENTAÇÃO GRÁFICA E PRODUTOS DIGITAIS**

A Representação Gráfica do levantamento planialtimétrico cadastral é um produto cartográfico digital, composto por um conjunto de dados geoespaciais estruturados, georreferenciados e com topologia validada, aptos para uso direto em Sistemas de Informação Geográfica (SIG), bancos de dados espaciais e processos de Cadastro Territorial Multifinalitário (CTM). Os produtos devem atender aos seguintes requisitos:

**3.1. Sistema de Referência Geodésico**

Todos os dados geoespaciais produzidos deverão ser georreferenciados ao Sistema Geodésico de Referência oficial do Brasil, o **SIRGAS 2000 (Sistema de Referência Geocêntrico para as Américas)**. A representação cartográfica deverá utilizar a projeção UTM (Universal Transversa de Mercator), no fuso correspondente à localização do núcleo urbano informal. As coordenadas geodésicas (latitude e longitude), quando apresentadas, deverão conter no mínimo 4 (quatro) casas decimais nos segundos de arco.

**3.2. Formatos de Entrega Digital**

A entrega dos produtos digitais é obrigatória e deve ser realizada nos seguintes formatos, organizados em uma estrutura de diretórios clara:

*   **Formato Primário - GeoPackage (.gpkg):** Um único arquivo GeoPackage contendo todas as camadas de dados vetoriais (pontos, linhas e polígonos) do levantamento, com seus respectivos atributos e simbologia padrão (estilo QGIS - .qml, se aplicável). Este formato é o principal entregável para a base de dados geoespacial.
*   **Formato Secundário - Shapefile (.shp):** Como alternativa para interoperabilidade, todas as camadas vetoriais também deverão ser entregues em formato Shapefile.
*   **Formato CAD - DWG/DXF:** Arquivos em formato DWG (AutoCAD) e DXF, devidamente georreferenciados e com o sistema de coordenadas definido, contendo os mesmos elementos das camadas vetoriais.
*   **Formato de Documento - PDF/A:** Todas as peças gráficas (plantas, relatórios, memoriais) deverão ser entregues em formato PDF/A, que é um padrão ISO para arquivamento de longo prazo.

**3.3. Estrutura de Dados e Camadas (Layers)**

Os dados vetoriais deverão ser organizados em camadas temáticas distintas e coerentes. A CONTRATADA deverá apresentar, no início dos trabalhos, uma proposta de **dicionário de dados** para aprovação da CONTRATANTE, contendo no mínimo as seguintes camadas e seus respectivos atributos:

*   **`nu_limite_nucleo`** (Polígono): Limite da área total do núcleo em regularização.
*   **`nu_lotes`** (Polígono): Lotes individuais, com atributos para código do lote, área (calculada em projeção UTM), perímetro, situação (ocupado, vago), etc.
*   **`nu_edificacoes`** (Polígono): Projeção das edificações, com atributos para tipo de uso (residencial, comercial, misto), número de pavimentos, etc.
*   **`nu_sistema_viario`** (Linha/Polígono): Eixos de vias (ruas, avenidas, vielas) e áreas de logradouros, com atributos para nome da via (toponímia), tipo e classificação.
*   **`nu_hidrografia`** (Linha/Polígono): Rios, córregos, lagos.
*   **`nu_areas_protegidas`** (Polígono): Áreas de Preservação Permanente (APP), áreas de risco, faixas não edificáveis.
*   **`nu_pontos_controle`** (Ponto): Marcos geodésicos, pontos de apoio, RNs, com atributos para identificação, coordenadas e altitude.
*   **`nu_curvas_nivel`** (Linha): Curvas de nível com equidistância de 1 (um) metro, com atributo de cota.

**3.4. Metadados Geoespaciais**

Cada conjunto de dados geoespaciais (GeoPackage) deverá ser acompanhado de um arquivo de metadados em formato XML, em conformidade com o **Perfil de Metadados Geoespaciais do Brasil (Perfil MGB)**, homologado pela Infraestrutura Nacional de Dados Espaciais (INDE). Os metadados são essenciais para a documentação e futura utilização dos dados e devem conter, no mínimo: título, data de produção, resumo do conteúdo, método de levantamento, acurácia posicional obtida, sistema de referência de coordenadas, responsável técnico e informações de contato.

**3.5. Peças Gráficas (Plantas)**

A partir dos dados vetoriais estruturados, deverão ser geradas as seguintes peças gráficas em formato PDF/A, em escalas compatíveis com a densidade de informações (1:250, 1:500 ou 1:1000), conforme o caso:

*   **Planta de Situação:** Apresentando a localização do núcleo na malha urbana do município.
*   **Planta Geral do Levantamento Cadastral:** Contendo todas as informações levantadas do núcleo em uma ou mais pranchas, se necessário.
*   **Planta Individual do Lote:** Uma planta para cada unidade imobiliária a ser regularizada.

Todas as plantas deverão conter os elementos essenciais de uma representação cartográfica, conforme a NBR 17.047:2022, incluindo: título, norte magnético e de quadrícula, escala gráfica e numérica, malha de coordenadas UTM, tabela de coordenadas dos vértices do perímetro, legenda de convenções e simbologia, e um carimbo/selo completo com informações do projeto, do imóvel, do proprietário e do responsável técnico (com número da ART/RRT).

**3.6. Qualidade e Acurácia**

A acurácia posicional do levantamento deve ser compatível com a finalidade cadastral e de engenharia, atendendo aos requisitos da **ABNT NBR 17.047:2022** para levantamento cadastral territorial urbano. A precisão posicional planimétrica dos vértices definidores dos limites dos imóveis deve ser igual ou melhor que **8 cm**. O Relatório Técnico, a ser entregue conforme item 4.10, deverá conter um capítulo específico detalhando os métodos de controle de qualidade empregados e os resultados de acurácia obtidos.

---

## 4. Referências

1.  Associação Brasileira de Normas Técnicas (ABNT). **NBR 17047:2022** - Levantamento cadastral territorial para registro público — Procedimento.
2.  Associação Brasileira de Normas Técnicas (ABNT). **NBR 13133:2021** - Execução de levantamento topográfico — Procedimento.
3.  Fundo Nacional de Desenvolvimento da Educação (FNDE). **Caderno de Informações Técnicas - Implantações dos Projetos Padronizados do FNDE**. 2025.
4.  Infraestrutura Nacional de Dados Espaciais (INDE). **Perfil de Metadados Geoespaciais do Brasil (Perfil MGB)**. Disponível em: <https://inde.gov.br/>.
5.  Open Geospatial Consortium (OGC). **OGC® GeoPackage Encoding Standard**. Disponível em: <https://www.geopackage.org/>.
6.  PERPART. **Termo de Referência - SEI 58008717**. 2024.
