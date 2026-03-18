Projeto: Carregamento Autônomo de Caminhões

1. Identificação do Grupo
Instituição: Faculdade Engenheiro Salvador Arena (FESA)
Curso: Engenharia de Controle e Automação
Grupo: GRUPO C
Integrantes:
Guilherme Henrique Alves Vieira - RA: 062220021
Gustavo de Freitas Lima - RA: 062220015
Gabriel Santos de Oliveira - RA: 062220028
Auro Manoel de Oliveira - RA: 062220018

3. Área Problema Selecionada
Selecione a trilha tecnológica do projeto (marque com um [x]):
[ ] Saúde 4.0: Robótica Assistiva (Controladores Inteligentes/Fuzzy)
[ ] Smart Grid: Eficiência Energética e Descarbonização
[ ] Agtech: Automação de Precisão e Visão Computacional
[x] Logística Autônoma: Coordenação de AGVs e Otimização de Rotas

4. Diagnóstico e Definição do Agente
Nesta seção, descrevemos o cenário de atuação e a modelagem do agente inteligente.

Contexto: Logística 4.0 / Intralogística em Centros de Distribuição.
Problema: Lentidão e periculosidade no carregamento manual de carretas, operando em ambientes escuros, confinados e sujeitos a erros de empilhamento e fadiga humana.
Impacto: Otimização instantânea do espaço (Tetris 3D), eliminação de danos à carga, redução de gargalos operacionais e garantia de segurança total aos colaboradores.

Modelagem PEAS (Agente Inteligente)
| Componente | Descrição |
| :--- | :--- |
| Performance (P) | Preenchimento de $\ge$ 95% da capacidade; tempo de carga < 25 min; índice de zero acidentes; precisão de $\pm$ 2cm. |
| Ambiente (E) | Interior de baús de caminhões, docas de carga e armazéns (ambientes confinados e de baixa luminosidade). |
| Atuadores (A) | Motores de tração elétrica (locomoção), torres de elevação (posicionamento vertical) e deslocadores laterais (side-shifters). |
| Sensores (S) | LiDAR 3D e câmeras de profundidade (mapeamento), sensores de torque nos garfos e encoders nas rodas. |

5. Arquitetura de Dados e IA
Definição das fontes de dados e da inteligência por trás da solução.

Origem dos Dados: Dados de telemetria via simulação (ROS/Gazebo) e datasets de volumetria de carga (3D Bin Packing).
Lógica de IA: Algoritmos de Otimização Combinatória (Heurística de Empacotamento 3D) e Busca A* para navegação interna.
Justificativa: A técnica de Tetris 3D é ideal para maximizar a densidade de carga em tempo real, superando a capacidade humana de organizar volumes heterogêneos sob pressão de tempo.

6. Plano de Tratamento de Dados (ETL)
O fluxo de processamento dos dados segue estas etapas:
Extração: Coleta de nuvens de pontos (Point Clouds) do LiDAR e dados de torque via protocolo industrial ou simulação.
Transformação: Filtragem de ruído sensorial, normalização de coordenadas cartesianas e cálculo de centro de massa para distribuição nos eixos.
Carga: Envio das coordenadas de destino ($x, y, z$) para os controladores de movimento do agente.

7. Estrutura do Repositório
Organização simplificada para o Milestone 1:
`/data`: Arquivos de dados originais (raw) e tratados (processed).
`/notebooks`: Experimentos iniciais e análise exploratória.
`/scripts`: Códigos Python (.py) contendo a lógica do agente e do ETL.
`requirements.txt`: Lista de bibliotecas para rodar o projeto.
`README.md`: Documentação atual do projeto.

8. Instruções para Execução
Para reproduzir o ambiente e testar o diagnóstico:
Clone este repositório.
Instale as dependências:
```bash
   pip install -r requirements.txt
