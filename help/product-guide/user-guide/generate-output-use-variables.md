---
title: Utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file
description: Scopri come utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file. Conoscere le variabili pronte all’uso supportate in AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# Utilizzare le variabili per impostare le opzioni Percorso di destinazione, Nome sito o Nome file


Durante la generazione di output in PDF o siti AEM, è possibile utilizzare le variabili per definire le opzioni Percorso di destinazione, Nome sito AEM o Nome file PDF. Puoi utilizzare una singola variabile o una combinazione di variabili per definire queste opzioni.

Nella tabella seguente sono elencate le variabili supportate come predefinite:

| Variabile | Percorso di destinazione finale | Esempio |
| --- | --- | --- |
| `${map_filename}` | Utilizza il nome file mappa DITA per creare il percorso di destinazione. | **Nome file mappa DITA**:<br>`AEMGuides.ditamap`<br><br>**Percorso di destinazione** configurato come:<br>`/content/output/sites/${map_filename}`<br><br>**Percorso di output finale**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Utilizza il titolo della mappa DITA per creare il percorso di destinazione. | **Nome file mappa DITA**:<br>`AEMGuides.ditamap`<br><br>**Titolo mappa DITA**:<br>`AEMGuides`<br><br>**Percorso destinazione** configurato come:<br>`/content/output/sites/${map_title}`<br><br>**Percorso output finale**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Utilizza il nome del predefinito di output per creare il percorso di destinazione. | **Nome predefinito di output**:<br>`AEM Guides PDF Output`<br><br>**Nome file mappa DITA**:<br>`SampleDita.ditamap`<br><br>**Percorso di destinazione** configurato come:<br>`/content/output/sites/${preset_name}`<br><br>**Percorso di output finale**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Utilizza il codice della lingua in cui si trova il file di mappa per creare il percorso di destinazione. | **Nome file mappa DITA**:<br>`SampleDita.ditamap`<br><br>**Percorso file mappa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Percorso destinazione** configurato come:<br>`/content/output/sites/${language_code}`<br><br>**Percorso output finale**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Utilizza il percorso completo del file di mappa per creare il percorso di destinazione.<br><br>**Nota**: questa variabile non può essere utilizzata per specificare il nome del sito AEM o il nome del file PDF. | **Nome file mappa DITA**:<br>`SampleDita.ditamap`<br><br>**Percorso file mappa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Percorso destinazione** configurato come:<br>`/content/output/sites/${map_parentpath}`<br><br>**Percorso output finale**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Utilizza il percorso del file mappa dopo la cartella della lingua per creare il percorso di destinazione.<br><br>**Nota**: questa variabile non può essere utilizzata per specificare il nome del sito AEM o il nome del file PDF. | **Nome file mappa DITA**:<br>`SampleDita.ditamap`<br><br>**Percorso file mappa DITA**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Percorso destinazione** configurato come:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Percorso output finale**:<br>`/content/output/sites/user-guide/SampleDita.html` |
| `${system_date}` | Utilizza la data del server corrente per creare il percorso di destinazione. | **Nome file mappa DITA**: <br> `SampleDita.ditamap` <br><br> **Percorso file mappa DITA:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Percorso di destinazione** configurato come: <br> `/content/output/sites/${system_date}` <br> <br> **Percorso di output finale:** <br> /`content/output/sites/08252023/SampleDita.html` |
| `${system_time}` | Utilizza l’ora del server corrente per creare il percorso di destinazione. | **Nome file mappa DITA:** <br>`SampleDita.ditamap` <br> <br> **Percorso file mappa DITA:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Percorso di destinazione** configurato come: <br> `/content/output/sites/${system_time}`<br><br>**Percorso di output finale:**<br>`/content/output/sites/055612/SampleDita.html` |

È inoltre possibile utilizzare come variabili i metadati definiti per il file mappa DITA o mappa di un libro. I metadati si trovano nel nodo `/jcr:content/metadata` della mappa DITA o del file di mappa di libri. Ad esempio, una delle proprietà dei metadati definite nel nodo `/jcr:content/metadata` è `dc:title`. È possibile specificare `${dc:title}` e il valore del titolo viene utilizzato nell&#39;output finale.
**Argomento padre:**&#x200B;[ Generazione output](generate-output.md)
