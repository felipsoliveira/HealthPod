# HealthPod — MVP-0 | Protocolo experimental de bancada (v0.2)
**Revisado:** 2026-10-28  
**Estado:** planejamento operacional; montagem, medições e validação ainda NÃO executadas.  
**Escopo:** caracterização de aerossol em sistema fechado, sem inalação humana, sem bocal e sem produto destinado a consumo.

> **Pergunta falsificável:** sob condições ópticas e ambientais controladas, um atomizador consegue produzir mais sinal visual por unidade de massa de aerossol efetivamente emitida/coletada? Isso NÃO comprova menor risco pulmonar.

## 1. Limites do MVP
- O MVP-0 NÃO é um pod doméstico e NÃO desenvolve uma formulação para autoinalação.
- Primeiro ensaio: **água purificada, somente em câmara de bancada**. Não adicionar nicotina, mentol, aroma, óleo essencial, terpeno, vitamina, corante, fármaco ou PG/VG nesta etapa.
- Não operar sistema aberto nem apontar a pluma a pessoas/animais. Não improvisar alimentação de bateria, driver piezoelétrico de alta tensão ou nebulizador modificado para uso pessoal.
- Consultar responsável institucional de biossegurança/segurança elétrica e regras locais antes da montagem. O enquadramento de um futuro dispositivo para fumar é distinto do de instrumentação genérica de bancada.
- "Não térmico" não equivale a frio nem a biologicamente seguro. Medir temperatura e contaminação é obrigatório.

## 2. Estratégia de implementação
**MVP-0A (primeiro):** malha vibratória (VMN), módulo comercial com controlador original. Serve para estabelecer o método de medição de névoa, massa e repetibilidade.

**MVP-0B (comparador):** módulo SAW de laboratório, depois que o protocolo do VMN for estável e existir acesso a driver, proteção elétrica e contenção apropriados. Não construir um circuito de potência RF improvisado.

A ordem é de **viabilidade experimental**, não de segurança para inalação. Não atribuir superioridade ao SAW antes das medições.

### Esquema funcional
```text
Fonte certificada --> controlador original do atomizador
                             |
[Reservatório rastreável] --> [VMN / SAW] --> [CÂMARA FECHADA]
                                                   |       |
                                            LED estável  Câmera fixa
                                                   |       |
                                                sensores T / UR
                                                        |
                                          [Coletor gravimétrico]
                                                        |
                                             [Filtro / exaustão]
```
Requisitos: separação de circuitos elétricos/rota úmida, coleta identificada, integridade das vedações, ausência de escape para área ocupada, possibilidade de limpeza, desligamento de emergência e contenção secundária.

## 3. Inventário mínimo e função
| Elemento | Requisito / registro | Status inicial |
| --- | --- | --- |
| VMN comercial com driver do fabricante | Modelo, materiais em contato, tensão nominal e advertências | A adquirir/selecionar |
| Fonte externa certificada e seccionamento | Compatibilidade com driver, proteção contra líquidos | A definir |
| Câmara transparente fechada | Volume/geometria documentados, acesso de limpeza, conexões vedadas | A projetar |
| Coletor/filtro e exaustão adequada | Coleta sem dispersão na sala; eficiência a avaliar | A especificar |
| LED com brilho fixo + difusor/fundo escuro | Mesma geometria e iluminação em cada corrida | Disponibilidade a verificar |
| Câmera com exposição manual/tripé | Trava de exposição, ISO, obturação, foco, balanço de branco | Disponibilidade a verificar |
| Balança | Resolução e estabilidade compatíveis com variação de massa observada | A verificar |
| Sensores de temperatura e umidade | Calibração/rastreabilidade registradas | A verificar |
| Medidor elétrico compatível | Potência média, tempo e energia; sem acessar circuito RF desprotegido | A verificar |
| Instrumentação de tamanho de partículas | Difração laser / impactador / método validado conforme parâmetro buscado | **Não disponível até confirmação** |

**Não declarar que diâmetro aerodinâmico, dose depositada ou metais foram medidos enquanto não houver equipamento/método adequado.** Smartphone + LED medem *sinal óptico relativo*, não distribuição de tamanho.

## 4. Pré-operação — checklist de segurança
1. Aprovação técnica do desenho, riscos de eletricidade, aerossol e exaustão; documentação de compatibilidade entre líquido, materiais e método de limpeza.
2. Verificar ausência de vazamentos, proteção contra respingos, alimentação externa certificada e botão de corte.
3. Conferir coletor e exaustão sem acesso direto da névoa ao operador.
4. Fixar câmera, LED, fundo, volume de câmara, região de interesse (ROI) e escala espacial; salvar configurações manuais.
5. Registrar temperatura e UR do ambiente; verificar estabilidade da balança com recipiente de referência.
6. Fazer vídeo/foto de fundo e branco **sem acionamento** do módulo. Não operar VMN seco se o fabricante proibir.
7. Fazer um controle de evaporação sem atomização, nas mesmas condições, se a massa do reservatório for usada.
8. Identificar o lote de água e condições de armazenamento; preparar apenas o volume necessário ao ensaio. Água nebulizada não é um controle clinicamente seguro.

Se qualquer etapa crítica falhar: **NO-GO; sem acionamento**.

## 5. Sequência de cada corrida
1. Atribuir `run_id`, data, operador, versão de protocolo e condição experimental antes de medir.
2. Registrar `m_reservatorio_inicial`, `m_coletor_inicial`, temperatura/UR, configurações fixas de câmera e estado do aparelho.
3. Gravar linha de base óptica com a câmara fechada, usando o mesmo enquadramento e iluminação.
4. Operar apenas no regime nominal documentado pelo fabricante, por um intervalo idêntico entre corridas. **10 s é somente um ponto de partida exploratório**, sujeito a ajuste após checar resolução gravimétrica e capacidade da contenção.
5. Continuar vídeo durante a dissipação/remoção controlada do aerossol. Não abrir enquanto houver névoa suspensa.
6. Desligar e isolar eletricamente. Depois de contenção/limpeza adequada, registrar massas finais, temperaturas, energia consumida e ocorrências.
7. Salvar mídia bruta e dados *antes* de qualquer processamento. Repetir branco para detectar deriva/depósito óptico.
8. Executar **5 replicatas piloto por condição** como mínimo exploratório; esse n não é validação estatística. Planejar n definitivo a partir da variância e do efeito mínimo de interesse.

**Não medir uma referência VMN e depois SAW sob condições ambientais/ópticas diferentes sem registrar/corrigir a diferença.** Comparações exigem protocolos equivalentes ou normalização declarada.

## 6. Grandezas, fórmulas e limitações
- **Consumo do reservatório** (mg) = `1000 × (m_res_i - m_res_f)`. Pode incluir evaporação, perda no equipamento e depósitos; não chamar isso de "massa inalada" nem de "massa emitida".
- **Massa coletada** (mg) = `1000 × (m_col_f - m_col_i) - branco_coleta`. É um **limite inferior** potencial da massa produzida se a eficiência da captura não foi validada.
- **Massa emitida estimada**: só relatar após desenvolver um balanço de massa e/ou método de coleta com eficiência caracterizada; reportar frações não recuperadas.
- **Sinal óptico relativo**: `S(t) = média_ROI_corrida(t) - média_ROI_branco(t)` com câmera linearizada ou parâmetros fixos documentados. Registrar saturação e sensibilidade à iluminação.
- **Integral do sinal**: `A = ∫ max(S(t),0) dt` em unidade instrumental × s.
- **OAE experimental**: `A / m_emitida`, **somente** se `m_emitida` for estimada por método validado. Enquanto não houver: `OAE_proxy_reservatorio = A / m_consumida`, declarando o viés.
- **Energia específica**: `E_eletrica / m_consumida` (J/mg), com definição de massa no rótulo.
- **Repetibilidade**: média, desvio-padrão e CV (%) por condição, com corridas e brancos identificados.
- **Persistência aparente**: duração do sinal acima de limite instrumental pré-definido; dependente de câmera, câmara, fluxo e UR.

**Importante:** OAE é uma métrica experimental de engenharia, não é endpoint toxicológico ou medida de segurança. Um sinal elevado pode decorrer de gotículas maiores, espalhamento, geometrias e índices de refração distintos. Não inferir deposição pulmonar a partir dele.

## 7. Qualidade, incertezas e decisões
**Critérios de parada imediata (NO-GO):** falha de contenção/exaustão, vazamento, falha elétrica, aquecimento inesperado, resíduo/contaminação não explicado, incerteza de massa maior que o sinal disponível, imagem saturada que invalide análise, ausência de rastreabilidade.

**Aceitar como ensaio piloto (GO apenas para medir melhor)** quando: (a) controles e brancos completos; (b) vídeos brutos arquivados; (c) massas e energia com incertezas/limites identificados; (d) no mínimo cinco replicatas registradas; (e) falhas explicitamente anotadas; (f) todos os mecanismos de contenção funcionais. Replicabilidade e limites analíticos devem ser avaliados; **não impor aprovação de segurança por porcentagem arbitrária de CV**.

**GO para comparação VMN × SAW**: depois de consolidar protocolo, normalizar condições (fluido, duração, UR/temperatura, geometria, iluminação e base de massa), especificar medidas de tamanho, avaliar materiais e revisar riscos elétricos/RF do sistema SAW.

**NO-GO para alegação de saúde em todas as fases MVP-0:** não existe ensaio humano, dosimetria pulmonar validada, perfil toxicológico completo ou aprovação regulatória.

## 8. Plano de dados reproduzível
Usar `research/MVP0_RUN_TEMPLATE.csv` para registro de **uma linha por corrida**; resultados negativos não devem ser descartados. Manter:
- vídeos e imagens brutas com nomes ligados ao `run_id` e checksum/hash;
- ficha técnica do equipamento e configuração elétrica;
- logs de branco, calibração, limpeza e interrupção;
- scripts versionados para extrair ROI/área sob a curva, com versão e parâmetros;
- tabela de medições com campos ausentes como vazios, **não como zero**;
- resumo descritivo com barras de incerteza e caveats.

Não declarar instrumento "calibrado" sem documentação de verificação/ajuste rastreável.

## 9. Entregáveis e sprints
| Marco | Resultado exigido | Situação |
| --- | --- | --- |
| M0 — Evidências & riscos | Blueprint, evidências, plano de segurança | Documentado; revisão local pendente |
| M1 — Instrumentação VMN | Diagrama final, lista concreta, contenção validada | **Pendente** |
| M2 — Piloto água | Brancos + ≥5 corridas + vídeo + massa + T/UR + energia | **Pendente** |
| M3 — Análise | Script, gráficos de intensidade/massa, CV, limitações | **Pendente** |
| M4 — SAW | Comparação com método pareado e riscos revistos | **Pendente** |
| M5 — Química e deposição | Plano para metais, VOCs, carbonilas, tamanho e dosimetria | **Fora do MVP-0** |

Nenhum resultado experimental está sendo declarado neste documento.

## 10. Evidências, governança e legislação
- Revisar [FORMULATION-CANDIDATES.md](FORMULATION-CANDIDATES.md) e [SPRINT-2-NOTES.md](../evidence/SPRINT-2-NOTES.md) antes de qualquer expansão de composição.
- [SAFETY.md](../SAFETY.md) prevalece quanto a limites para testes humanos e alegações de saúde.
- **ISO 27427:2023:** referência para métodos e desempenho de sistemas de nebulização; aplicação a este protótipo de caracterização NÃO implica conformidade ou certificação. https://www.iso.org/standard/78542.html
- Roudini et al., *Aerosol Science and Technology* (2024), SAW: https://doi.org/10.1080/02786826.2024.2343377
- Mittal et al., *Scientific Reports*, PG/VG e epitélio: https://doi.org/10.1038/s41598-025-33023-5
- **Anvisa, RDC 855/2024:** regula/proíbe atividades envolvendo dispositivos eletrônicos para fumar, com exceção delimitada para importação institucional científica. A qualificação jurídica deste equipamento de bancada e de eventual produto futuro precisa de avaliação competente. https://anvisalegis.datalegis.net/action/ActionDatalegis.php?acao=abrirTextoAto&cod_menu=9431&cod_modulo=310&link=S&numeroAto=00000855&orgao=RDC%2FDC%2FANVISA%2FMS&seqAto=000&tipo=RDC&valorAno=2024

**Regra final:** um protótipo que faz névoa não é um protótipo aprovado para respirar.
