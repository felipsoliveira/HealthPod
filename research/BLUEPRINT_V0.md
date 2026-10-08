# HealthPod V0 — Blueprint conceitual e plano experimental

Status: conceito de bancada; não destinado a inalação humana.

## Objetivo
Comparar atomização SAW e nebulização por malha vibratória em termos de massa emitida, distribuição de gotículas, sinal óptico, energia, contaminação e exposição respiratória modelada.

## Arquitetura funcional
Reservatório de fluido de referência -> módulo atomizador isolado -> câmara fechada de coleta -> instrumentação de partículas e massa -> filtros/descarte.
Controlador elétrico e sensores de temperatura/energia ficam separados do caminho do fluido.

## Primeiro experimento
- Fluido: água purificada, somente em bancada fechada.
- Controles: branco instrumental, ensaio sem acionamento e referência de nebulizador comercial.
- Leituras: distribuição de tamanho, massa coletada, temperatura, potência, repetibilidade e sinal óptico.
- Métrica exploratória: OAE = sinal óptico / massa emitida; não é métrica de segurança.
- Critérios de interrupção: contaminação detectável não caracterizada, falhas de contenção, aquecimento inesperado ou medições não reproduzíveis.

## Matriz de formulações
Água purificada: referência física, não receita de inalação.
Solução salina: possível comparador de laboratório após avaliação de método.
PG/VG: controles de literatura e avaliação química; não presumir seguros.
Aromatizantes/óleos essenciais: não incluir no MVP. Segurança alimentar não prova segurança inalatória.

## Portões de decisão
G0 revisão de literatura e análise de riscos;
G1 caracterização física e repetibilidade;
G2 modelagem de dose depositada;
G3 química e materiais;
G4 avaliação biológica pré-clínica independente;
G5 somente após evidência adequada, revisão ética/regulatória de eventual pesquisa humana.

## Próximas entregas
1. Matriz de evidências por tecnologia e endpoint.
2. Diagrama de instrumentação e lista de equipamentos de laboratório.
3. Protocolo de coleta e caracterização sem exposição humana.
4. Planilha de dados e relatório comparativo SAW vs VMN.

Não converter este blueprint em instruções de automedicação ou uso inalatório caseiro.
