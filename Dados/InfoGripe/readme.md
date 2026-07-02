# InfoGripe Dataset

<details open>
<summary><strong>PT-BR</strong></summary>

## AVISO

Dados provenientes de sistemas de notificação de caso, como o SIVEP-Gripe que alimenta o InfoGripe, podem conter eventuais erros de digitação ou preenchimento, afetando um ou mais campos de registro.

Em função disso, as notificações estão em constante avaliação para correções realizadas pela rede de vigilância e equipes locais responsáveis.

Todos os casos utilizam como data de referência a semana de início de sintomas, mesmo quando referente a óbitos. Ou seja, os óbitos são contados com base na data de início dos sintomas dos casos que evoluíram para óbito por SRAG.

---

## InfoGripe

Dados gerados pelo sistema InfoGripe, em parceria entre MAVE e o GT-Influenza da Secretaria de Vigilância em Saúde do Ministério da Saúde.

Uso público permitido mediante citação adequada.

Autores: MAVE (PROCC/Fiocruz e EMap/FGV) e GT-Influenza (Ministério da Saúde)  
http://covid-19.procc.fiocruz.br/  
http://info.gripe.fiocruz.br  

---

## Conjuntos de dados

Este repositório disponibiliza dois recortes do SIVEP-Gripe com diferentes filtros de sintomas.

---

### SRAG sem exigência de febre

Filtro intermediário (Ministério da Saúde):

- Tosse OU dor de garganta E
- Dispneia OU saturação < 95% OU desconforto respiratório E
- Internação OU óbito

Arquivos com prefixo `_sem_filtro_febre.csv`

---

### Apenas internação ou óbito

Filtro mais amplo:

- Internação OU óbito

Arquivos com prefixo `_sem_filtro_sintomas.csv`

---

## Dicionário de dados

### SRAG com as estimativas de nowcasting

#### Dados agregados

- `estados_e_pais_serie_estimativas_tendencia_sem_filtro_febre.csv` (nível de estado)
- `capitais_serie_estimativas_tendencia_sem_filtro_febre.csv` (nível de capital)

| Variável | Descrição |
|----------|-----------|
| Q1 | Primeiro quartil da distribuição |
| Q3 | Terceiro quartil da distribuição |
| IC80I | Limite inferior do intervalo de confiança de 80% |
| IC80S | Limite superior do intervalo de confiança de 80% |
| IC90I | Limite inferior do intervalo de confiança de 90% |
| IC90S | Limite superior do intervalo de confiança de 90% |
| IC95I | Limite inferior do intervalo de confiança de 95% |
| IC95S | Limite superior do intervalo de confiança de 95% |
| Casos semanais reportados até a última atualização | Número de casos notificados no sistema até a última atualização |
| casos estimados | Estimativa do número de casos recentes (nowcasting) |
| média móvel | Média móvel (3 semanas) dos casos |
| tendência de longo prazo | Tendência das últimas 6 semanas |
| tendência de curto prazo | Tendência das últimas 3 semanas |
| Semana epidemiológica | Semana epidemiológica de referência (início de sintomas) |
| Ano epidemiológico | Ano epidemiológico da semana de início de sintomas |
| População | População residente da localidade |
| CO_UF | Código IBGE da Unidade da Federação |
| DS_UF_SIGLA | Sigla da UF (Estado) |
| Grupo Jurídico | Classificação administrativa da localidade |
| escala | Tipo de medida (casos ou incidência por 100 mil habitantes) |

---

#### Estimativa por faixa etária

- `estados_e_pais_serie_estimativas_fx_etaria_sem_filtro_febre.csv` (estado e país)
- `capitais_serie_estimativas_fx_etaria_sem_filtro_febre.csv` (capital)

| Variável | Descrição |
|----------|-----------|
| fx_etaria | Faixa etária |
| casos_notificados | Número de casos notificados |
| mediana_da_estimativa | Mediana da estimativa |
| Q1 | Primeiro quartil da distribuição |
| Q3 | Terceiro quartil da distribuição |
| IC80I | Limite inferior do intervalo de credibilidade de 80% |
| IC80S | Limite superior do intervalo de credibilidade  de 80% |
| IC90I | Limite inferior do intervalo de credibilidade de 90% |
| IC90S | Limite superior do intervalo de credibilidade de 90% |
| LI | Limite inferior |
| LS | Limite superior |
| media_movel | Média móvel |
| SG_UF_NOT | Código da Unidade da Federação de notificação |
| DS_UF_SIGLA | Sigla da Unidade da Federação |
| epiweek | Semana epidemiológica |
| epiyear | Ano epidemiológico |

---

#### Dados com trajetórias do modelo

Arquivos:

- `estados_amostras_sem_filtro_febre.csv` (nível de estado)
- `capitais_amostras_sem_filtro_febre.csv` (nível de capital)

| Variável | Descrição |
|----------|-----------|
| sample | Identificador da amostra |
| Time | Tempo |
| fx_etaria | Faixa etária |
| fx_etaria.num | Faixa etária numérica |
| Y | Variável de desfecho |
| CO_UF | Código IBGE da Unidade da Federação |
| epiweek | Semana epidemiológica |
| epiyear | Ano epidemiológico |

---

## Dados por sexo e faixa etária

- `casos_semanais_fx_etaria_virus_sem_filtro_febre.csv`
- `casos_semanais_fx_etaria_virus_sem_filtro_sintomas.csv`

| Variável | Descrição |
|----------|-----------|
| SG_UF_NOT | Código da Unidade da Federação de notificação |
| fx_etaria | Faixa etária |
| SRAG | Síndrome Respiratória Aguda Grave (total) |
| SARS2 | SARS-CoV-2 |
| VSR | Vírus sincicial respiratório |
| FLU | Influenza (geral) |
| FLU_A | Influenza A |
| FLU_AH1N1 | Influenza A H1N1 |
| FLU_AH3N2 | Influenza A H3N2 |
| FLU_ANSUBTPD | Influenza A não subtipado (detectado) |
| FLU_ANSUBTPV | Influenza A não subtipado (variável) |
| FLU_AINC | Influenza A inconclusivo |
| FLU_AOUT | Outros Influenza A |
| FLU_B | Influenza B |
| FLU_BVIC | Influenza B Victoria |
| FLU_BYAM | Influenza B Yamagata |
| FLU_BNLIN | Influenza B linhagem não identificada |
| FLU_BINC | Influenza B inconclusivo |
| FLU_BOUT | Outros Influenza B |
| RINO | Rinovírus |
| ADNO | Adenovírus |
| BOCA | Bocavírus |
| METAP | Metapneumovírus |
| PARA1 | Parainfluenza 1 |
| PARA2 | Parainfluenza 2 |
| PARA3 | Parainfluenza 3 |
| PARA4 | Parainfluenza 4 |
| OUTROS | Outros vírus respiratórios |
| positivos | Total de resultados positivos |
| negativos | Total de resultados negativos |
| aguardando | Resultados aguardando processamento |
| DS_UF_SIGLA | Sigla da Unidade da Federação |
| epiyear | Ano epidemiológico |
| epiweek | Semana epidemiológica |
| Semana epidemiológica | Semana epidemiológica de referência |
| Ano epidemiológico | Ano epidemiológico de referência |


</details>

---

<details>
<summary><strong>EN</strong></summary>

## NOTICE

Data from notification systems, such as SIVEP-Gripe which feeds InfoGripe, may contain occasional data entry or reporting errors affecting one or more fields.

Because of this, records are continuously reviewed and corrected by surveillance teams and local responsible units.

All cases use the week of symptom onset as the reference date, even for deaths. In other words, deaths are counted based on the symptom onset week of cases that eventually progressed to SRAG-related death.

---

## InfoGripe

Data generated by the InfoGripe system, in partnership between MAVE and the Influenza Working Group of the Brazilian Ministry of Health.

Public use is allowed provided proper citation is given.

Authors: MAVE (PROCC/Fiocruz and EMap/FGV) and GT-Influenza (Ministry of Health)  
http://covid-19.procc.fiocruz.br/  
http://info.gripe.fiocruz.br  

---

## Datasets

This repository provides two subsets of SIVEP-Gripe data with different symptom-based filters.

---

### SRAG without fever requirement

Intermediate filter (Ministry of Health):

- Cough OR sore throat AND
- Dyspnea OR oxygen saturation < 95% OR respiratory distress AND
- Hospitalization OR death

Files with prefix `_sem_filtro_febre.csv`

---

### Hospitalization or death only

Broader filter:

- Hospitalization OR death

Files with prefix `_sem_filtro_sintomas.csv`

---

## Data dictionary

### SRAG with nowcasting estimates

#### Aggregated data

- `estados_e_pais_serie_estimativas_tendencia_sem_filtro_febre.csv` (state level)
- `capitais_serie_estimativas_tendencia_sem_filtro_febre.csv` (capital level)

| Variable | Description |
|----------|-------------|
| Q1 | First quartile of the distribution |
| Q3 | Third quartile of the distribution |
| IC80I | Lower bound of the 80% credible interval |
| IC80S | Upper bound of the 80% credible interval |
| IC90I | Lower bound of the 90% credible interval |
| IC90S | Upper bound of the 90% credible interval |
| IC95I | Lower bound of the 95% credible interval |
| IC95S | Upper bound of the 95% credible interval |
| Casos semanais reportados até a última atualização | Number of reported cases in the system up to the latest update |
| casos estimados | Estimated number of recent cases (nowcasting) |
| média móvel | 3-week moving average of cases |
| tendência de longo prazo | Trend over the last 6 weeks |
| tendência de curto prazo | Trend over the last 3 weeks |
| Semana epidemiológica | Reference epidemiological week (symptom onset week) |
| Ano epidemiológico | Epidemiological year of symptom onset week |
| População | Resident population of the location |
| CO_UF | IBGE code of the Federal Unit |
| DS_UF_SIGLA | Abbreviation of the Federal Unit (state) |
| Grupo Jurídico | Administrative/legal classification of the location |
| escala | Type of measure (cases or incidence per 100,000 inhabitants) |

---

#### Age-stratified estimates

- `estados_e_pais_serie_estimativas_fx_etaria_sem_filtro_febre.csv` (state and country level)
- `capitais_serie_estimativas_fx_etaria_sem_filtro_febre.csv` (capital level)

| Variable | Description |
|----------|-------------|
| fx_etaria | Age group |
| casos_notificados | Number of reported cases |
| mediana_da_estimativa | Median estimate |
| Q1 | First quartile of the distribution |
| Q3 | Third quartile of the distribution |
| IC80I | Lower bound of the 80% credible interval |
| IC80S | Upper bound of the 80% credible interval |
| IC90I | Lower bound of the 90% credible interval |
| IC90S | Upper bound of the 90% credible interval |
| LI | Lower limit |
| LS | Upper limit |
| media_movel | Moving average |
| SG_UF_NOT | Code of the reporting Federal Unit |
| DS_UF_SIGLA | Abbreviation of the Federal Unit |
| epiweek | Epidemiological week |
| epiyear | Epidemiological year |

---

#### Model trajectory data

Files:

- `estados_amostras_sem_filtro_febre.csv` (state level)
- `capitais_amostras_sem_filtro_febre.csv` (capital level)

| Variable | Description |
|----------|-------------|
| sample | Sample identifier |
| Time | Time |
| fx_etaria | Age group |
| fx_etaria.num | Numeric age group |
| Y | Outcome variable |
| CO_UF | IBGE code of the Federal Unit |
| epiweek | Epidemiological week |
| epiyear | Epidemiological year |

---

## Sex and age-stratified data

- `casos_semanais_fx_etaria_virus_sem_filtro_febre.csv`
- `casos_semanais_fx_etaria_virus_sem_filtro_sintomas.csv`

| Variable | Description |
|----------|-------------|
| SG_UF_NOT | Code of the reporting Federal Unit |
| fx_etaria | Age group |
| SRAG | Severe Acute Respiratory Syndrome (total) |
| SARS2 | SARS-CoV-2 |
| VSR | Respiratory syncytial virus |
| FLU | Influenza (general) |
| FLU_A | Influenza A |
| FLU_AH1N1 | Influenza A H1N1 |
| FLU_AH3N2 | Influenza A H3N2 |
| FLU_ANSUBTPD | Influenza A unsubtyped (detected) |
| FLU_ANSUBTPV | Influenza A unsubtyped (variable) |
| FLU_AINC | Influenza A inconclusive |
| FLU_AOUT | Other Influenza A |
| FLU_B | Influenza B |
| FLU_BVIC | Influenza B Victoria |
| FLU_BYAM | Influenza B Yamagata |
| FLU_BNLIN | Influenza B non-lineage |
| FLU_BINC | Influenza B inconclusive |
| FLU_BOUT | Other Influenza B |
| RINO | Rhinovirus |
| ADNO | Adenovirus |
| BOCA | Bocavirus |
| METAP | Metapneumovirus |
| PARA1 | Parainfluenza 1 |
| PARA2 | Parainfluenza 2 |
| PARA3 | Parainfluenza 3 |
| PARA4 | Parainfluenza 4 |
| OUTROS | Other respiratory viruses |
| positivos | Total positive results |
| negativos | Total negative results |
| aguardando | Pending results |
| DS_UF_SIGLA | Abbreviation of the Federal Unit |
| epiyear | Epidemiological year |
| epiweek | Epidemiological week |
| Semana epidemiológica | Reference epidemiological week |
| Ano epidemiológico | Reference epidemiological year |



</details>
