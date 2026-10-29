# HealthPod V0 — Primeiro MVP | Blueprint de bancada (v0.2)

**Atualização:** 28/10/2026  
**Status real:** design experimental/documentação atualizados; hardware **não montado**, dados **não coletados**, segurança **não validada**.  
**Finalidade:** investigação físico-química de aerossóis em laboratório, **não** protótipo para inalação humana.

## Pergunta científica
Podemos aumentar o sinal visual/óptico de uma nuvem de aerossol **sem aumentar proporcionalmente a massa produzida**, sob condições controladas? Se sim, isso permanece uma vantagem física exploratória, **não** evidência de redução de risco clínico.

A hipótese será testada primeiro com uma plataforma de **malha vibratória (VMN)** e depois, se viável, com **atomização por ondas acústicas de superfície (SAW)**. SAW é a rota principal de investigação futura; VMN é o primeiro MVP pela maturidade experimental e facilidade de obter dados reprodutíveis.

## Documento de execução e dados
- **[Protocolo experimental completo — MVP0_BENCH_PROTOCOL.md](MVP0_BENCH_PROTOCOL.md)**: fluxo de montagem e verificação, instrumentação, sequência de corrida, equações, limitações e critérios de parada.
- **[Modelo de registro de corridas — MVP0_RUN_TEMPLATE.csv](MVP0_RUN_TEMPLATE.csv)**: cabeçalhos para dados primários e metadados, uma linha por replicata.
- **[Matriz científica de líquidos](FORMULATION-CANDIDATES.md)**: candidatos e evidências, sem formulação humana.
- **[Regras do projeto](../SAFETY.md)** e **[roteiro científico](ROADMAP.md)**.

## Arquitetura prevista
```text
                                  CONTROLE ELÉTRICO ISOLADO
                                       fonte + driver
                                            |
água purificada --> reservatório --> atomizador VMN/SAW --> câmara óptica FECHADA
                                                         |        |
                                                      câmera     LED
                                                         |
                                                   sensores T/UR
                                                         |
                                                 coletor/filtro
                                                         |
                                               exaustão controlada
```
**Limites de projeto:** sem bocal, sem bateria Li-ion portátil, sem produção de névoa em ambiente aberto e sem aplicação em pessoas ou animais. Usar driver e alimentação especificados pelo fabricante e revisar risco elétrico, de vazamento e de exaustão com responsáveis competentes.

## Escopo do experimento 1 — VMN + água
1. **Pré-requisitos (M1)**: selecionar VMN com documentação, definir contenção/coleta, verificar alimentação e sensores, fixar ótica e câmera, registrar análise de riscos.
2. **Brancos e controle**: fundo óptico, ensaio sem acionamento e controle de evaporação; não ligar o módulo a seco se contraindicado pelo fabricante.
3. **Pilotagem (M2)**: mesmo fluido e geometria, intervalo igual por corrida (10 s apenas como sugestão exploratória), pelo menos 5 replicatas por condição; registrar amostras, temperatura, UR, energia, massa e vídeos brutos.
4. **Análise (M3)**: extrair série temporal de intensidade óptica corrigida pelo fundo, integral do sinal, massa consumida pelo reservatório, massa retida no coletor (se método viável), estatísticas de variação e incerteza.
5. **Relatório**: resultados positivos e negativos, artefatos brutos, configurações, limitações e decisão GO/NO-GO. Não inventar resultados não medidos.

## Métricas primárias
| Grandeza | Interpretação obrigatória |
| --- | --- |
| `m_consumida` (mg) | Massa perdida pelo reservatório; **não** confundir com massa emitida, inalada ou depositada |
| `m_coletada` (mg) | Massa capturada, dependente de eficiência de coleta |
| `A_optica` (unidade relativa × s) | Integral do sinal de câmera corrigido pelo branco, dependente de calibração e geometria |
| `OAE_proxy = A_optica / m_consumida` | Métrica exploratória **enquanto a massa efetivamente emitida não estiver validada** |
| `OAE = A_optica / m_emitida` | Somente após método validado de massa emitida |
| `energia/massa` (J/mg) | Eficiência elétrica segundo denominador explicitamente indicado |
| CV (%), temperatura, UR | Repetibilidade e contexto operacional |

**NÃO inferir tamanho de gotículas, dose pulmonar ou toxicidade de vídeo/smartphone.** Instrumentos apropriados e caracterização química pertencem aos portões seguintes.

## Papel dos fluidos
| Condição | Decisão v0.2 |
| --- | --- |
| Água purificada | **Única referência do primeiro piloto físico**, em sistema fechado |
| Salina 0,9% | Comparador posterior condicionado a plano de corrosão/resíduo e revisão do método |
| PG e VG | Referências de literatura/controles químicos posteriores; **não usar no piloto inicial** |
| Misturas, aromas, óleos, vitaminas, nicotina e substâncias ativas | **Excluídos do MVP-0** |

Nenhum ingrediente é considerado "saudável para inalar" por ser alimentício, isento de nicotina ou nebulizado a baixa temperatura.

## Critérios de decisão (GO/NO-GO)
- **G0 — Segurança e rastreabilidade:** documentação elétrica e de materiais, contenção e plano de coleta. Se faltar, não acionar.
- **G1 — Física reprodutível:** brancos válidos, série óptica sem saturação, gravimetria acima do limite do método e resultados com variação explicitada. GO aqui é **somente** permissão para melhorar o experimento.
- **G2 — Exposição prevista:** distribuição de tamanho validada e modelo respiratório com hipóteses transparentes; não converter massa emitida em massa depositada sem modelo.
- **G3 — Química/materiais:** metais, VOCs, carbonilas e estabilidade do fluido, adequados ao sistema.
- **G4 — Biologia pré-clínica:** respostas respiratórias e limites de exposição avaliados por equipe competente.
- **G5 — Eventual pesquisa humana:** apenas com evidências, supervisão e avaliação ética/regulatória apropriadas; **fora do MVP-0**.

**Parada imediata:** vazamento ou escape de névoa, falha elétrica, aquecimento anormal, falha na exaustão, contaminação não explicada ou ausência de medidas rastreáveis.

## Entregáveis e status
| Entrega | Estado em 28/10/2026 |
| --- | --- |
| Blueprint v0.2 e protocolo escrito | ✅ Documentados |
| Template CSV de aquisição | ✅ Criado (sem dados fictícios) |
| Lista de peças com modelos efetivamente selecionados e custos verificados | ⬜ Pendente |
| Câmara e instrumentação montadas | ⬜ Pendente |
| Validação de contenção e segurança | ⬜ Pendente |
| Corridas experimentais reais | ⬜ Pendente |
| Comparação VMN × SAW | ⬜ Pendente |
| Exposição respiratória, química e biologia | ⬜ Futuras fases |

## Próximas tarefas práticas
1. Desenhar e revisar esquema de contenção e integração dos sensores.
2. Selecionar VMN com documentação, alimentação certificada, câmera, balança, medição de T/UR e coletor; registrar **o que já existe** e **o que falta**.
3. Verificar viabilidade metrológica: a balança detecta o sinal esperado? O branco óptico é estável? O coletor permite balanço de massa ou apenas limite inferior?
4. Executar piloto somente após revisões de segurança, salvar vídeos e CSV com IDs reprodutíveis.
5. Definir protocolo pareado SAW × VMN e endpoints avançados.

## Fontes e ressalvas
- ISO 27427:2023 — *Anaesthetic and respiratory equipment — Nebulizing systems and components*. Referência técnica para nebulizadores; **não certifica** este protótipo. https://www.iso.org/standard/78542.html
- Roudini et al. (2024), sistemas SAW: https://doi.org/10.1080/02786826.2024.2343377
- Anvisa, RDC 855/2024: https://anvisalegis.datalegis.net/action/ActionDatalegis.php?acao=abrirTextoAto&cod_menu=9431&cod_modulo=310&link=S&numeroAto=00000855&orgao=RDC%2FDC%2FANVISA%2FMS&seqAto=000&tipo=RDC&valorAno=2024. Antes de qualquer desenvolvimento com finalidade de fumar, obter orientação regulatória/institucional específica.

**Princípio metodológico:** caracterização de pluma ≠ ensaio de segurança pulmonar; protótipo de bancada ≠ dispositivo autorizado para uso pessoal.
