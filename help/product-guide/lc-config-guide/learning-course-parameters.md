---
title: Metriche chiave SCORM per l’avanzamento dell’Allievo e il completamento del corso
description: Scopri le metriche chiave SCORM per l’avanzamento dell’Allievo e il completamento del corso
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 1%

---

# Metriche chiave SCORM per l’avanzamento dell’Allievo e il completamento del corso

Nell&#39;articolo vengono elencati i parametri chiave acquisiti in un pacchetto SCORM, insieme ai campi corrispondenti e agli esempi. Questi parametri forniscono informazioni critiche sull’avanzamento dell’Allievo, sul completamento del corso, sui dettagli dell’interazione e sulle prestazioni dei quiz. Gli amministratori possono utilizzare queste informazioni per convalidare il tracciamento, configurare il reporting e garantire analisi accurate all’interno dell’ambiente LMS. Di seguito sono riportati i valori di esempio forniti per ciascun parametro così come viene visualizzato nel pacchetto SCORM.

| **Nome parametro** | **Descrizione** | **Campi** | **Esempio** |
|---|---|---|---|
| **Stato completamento corso** | Indica se il corso è completato o meno | cmi.completion_status | incompleto |
| **Numero tentativi** | Numero di tentativi effettuati dall’Allievo | Contatore/contenuto tentativi lato LMS | Tentativi: 1 |
| **Posizione del pacchetto SCORM** | Segnalibro o posizione corrente nel corso | cmi.location | - |
| **Avanzamento completato** | Avanzamento dell’Allievo | cmi.progress_measure | 0,87 |
| **Tempo totale (tentativo)** | Tempo totale trascorso nel tentativo corrente | cmi.total_time | 0000:01:09.87 |
| **Visibilità sommario e numero di argomenti** | Mostra la visibilità del sommario e i dettagli di completamento degli argomenti | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
| **Stato per argomento** | Stato completamento e passaggio per ciascun argomento | Stato personalizzato per lezione | - |
| **Stato scelta per domanda** | Tiene traccia delle scelte selezionate dall’Allievo in base alla domanda | value, generated_id, selezionato | - |
| **Punteggio domande complessivo** | Punteggio ottenuto a livello di domanda e aggregato | {&quot;score&quot;:0,&quot;maxScore&quot;:1} e % | &quot;score&quot;:33.33,&quot;maxScore&quot;:100,&quot;minScore&quot;:0 |
| **Interazioni a ogni livello di domanda** | Dettagli dell’interazione dell’Allievo in base alla domanda | id/type/timestamp/correct_response/learner_response/result/latency | - |
| **Stato generale del corso** | Indica il superamento/fallimento e l’avanzamento complessivo | success_status, completion_status, score, progress_measure | Indica se è stato superato o meno |
| **Dettagli Allievo** | Identifica l’Allievo per ID e nome | cmi.learner_id, cmi.learner_name | Albert |
| **Parametri quiz** | Configurazioni per la tempistica dei quiz e il passaggio del punteggio | cmi.max_time_allowed, cmi.scaled_pass_score, cmi.time_limit_action | Valori non definiti o configurati |
