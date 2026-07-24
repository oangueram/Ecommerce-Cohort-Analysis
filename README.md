# 🛒 E-Commerce Cohort & Retention Analysis

[![Obre a Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/oangueram/ecommerce-cohort-analysis/blob/main/notebooks/ecommerce_cohort_analysis.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue)
![DuckDB](https://img.shields.io/badge/DuckDB-SQL-yellow)
![Power BI](https://img.shields.io/badge/Power_BI-DAX-F2C811)

Com podem mesurar la fidelitat real dels nostres clients i predir els seus patrons de compra futurs? Aquest projecte desenvolupa un pipeline d'anàlisi de dades per construir una Matriu de Retenció, posant les bases matemàtiques i estructurals per a un futur càlcul del Customer Lifetime Value (CLV).

## Què fa

- **Defineix cohorts temporals** — agrupa els usuaris segons el mes de la seva primera compra per poder fer un seguiment del seu cicle de vida.
- **Calcula índexs temporals** — utilitza SQL per determinar la distància en mesos entre la primera interacció d'un client i les seves compres posteriors.
- **Modela l'arquitectura de dades** — genera una taula amb SQL que integra mètriques de retenció i canal d'adquisició.
- **Visualitza la supervivència** — dissenya un mapa de calor de retenció dinàmic utilitzant funcions DAX (`CALCULATE`, `DIVIDE`) per auditar visualment el percentatge de clients actius de cada cohort.

## Dades

Les dades s'han generat sintèticament mitjançant Python per simular l'entorn transaccional d'un e-commerce realista. Un cop processat el pipeline, el dataset net que alimenta la visualització és:

- `cohort_matrix_data.csv` — Taula analítica final amb les mètriques agregades de retenció i ingressos per cohort i índex, segmentada pel canal d'origen.

## Com visualitzar-ho

La manera més ràpida de veure l'impacte visual i la interactivitat del quadre de comandament és mitjançant aquesta demostració del mapa de calor final:

![Matriu de Retenció](assets/retention_matrix_demo.gif)

*(El fitxer original `.pbix` també es troba disponible en aquest repositori).*

## Com executar-ho

1. Premeu el botó de dalt "Obre a Colab" per executar el pipeline de Python i SQL i generar l'arxiu de dades.
2. Descarregar aquest arxiu i ubicar-lo a la carpeta `data/raw/` de l'entorn local.
3. Obrir el fitxer de Power BI on, a través de les dades i la mètrica DAX, es construeix la Matriu de Retenció.

## 📈 Conclusions

> **Nota metodològica:** Tot i que el dataset s'ha generat sintèticament i els patrons observables deriven de la variància estadística de l'algorisme, la següent anàlisi il·lustra com s'interpretaria aquest quadre de comandament per prendre decisions estratègiques en un escenari de negoci real.

- **Diagnòstic de Salut del Negoci:** L'anàlisi per cohorts aïlla l'adquisició de nous usuaris de la seva supervivència real. Això permet veure de manera clara si el negoci reté els seus clients a llarg termini o si depèn excessivament del màrqueting per suplir l'abandonament (*churn*). Aquesta matriu és el requisit indispensable per projectar models probabilístics de CLV.
- **Tendència Global (Early Churn):** A nivell general, l'e-commerce reté entre un 20% i un 25% dels usuaris el primer mes. Un cop superada aquesta caiguda inicial habitual, es consolida una base d'usuaris recurrents que es manté activa fins a 18 mesos després.
- **La resiliència del canal Orgànic:** Tot i tenir una entrada més discreta, el trànsit **Organic** demostra ser el més fidel a llarg termini. És el canal amb la "cua llarga" (long-tail) més densa, aconseguint retenir usuaris de manera molt constant a partir del cinquè mes (2%-5%), superant la longevitat dels canals de pagament.
- **L'oportunitat del Referral:** El canal de recomanacions (**Referral**) presenta pics de retenció durant el primer i segon mes (arribant a xifres del 40% i 50% en algunes cohorts). Tot i ser un canal de poc volum, porta usuaris altament qualificats. Escalar-lo hauria de ser una prioritat.
- **Comportament de Paid Media (Meta & Google Ads):** Els canals de pagament generen bon impacte a curt termini, però la seva retenció cau de manera més abrupta a partir del tercer mes en comparació amb l'orgànic. Això suggereix una dependència de campanyes de *retargeting* per reactivar aquests usuaris.

## 🤖 Desenvolupament Assistit per IA

Aquest projecte s'ha construït integrant eines de models de llenguatge (LLMs) per accelerar el cicle de creació. L'ús de la IA s'ha centrat estratègicament en:

- **Refactorització i Depuració (Debugging):** Diagnòstic i resolució d'errors.
- **Generació de Codi Estructural:** Creació de blocs estàndard.
- **Cerca de sintaxi:** Ús de la IA com a diccionari de Python, SQL i DAX per materialitzar en codi decisions analítiques i estructurals preses per l'autor.
- **Documentació i Format:** Estructuració d'aquest `README.md` i suport en la redacció de comentaris.

> **Nota d'auditoria:** Tot i l'assistència en el codi, **les decisions estructurals i de negoci** són d'autoria humana.

**Autor:** [Oriol Anguera Milà](https://github.com/oangueram)
