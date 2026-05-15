---
title: API REST per registrare un connettore di origine dati
description: Scopri l’API REST per registrare un connettore di origine dati
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/WkCyxrOF9CD7KpD9J2255WepzYLLJo8ilvB2keTxgJ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 81
ht-degree: 7%

---

# API REST per registrare un connettore di origine dati {#id236LG0Y0CXA}

La seguente API REST consente di registrare un connettore dell’origine dati.

## Registrare un connettore di origine dati

Metodo GET che registra un connettore origine dati.

**URL richiesta**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parametri**:

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `path` | Stringa | Sì | Stringa che punta a un percorso nell’archivio AEM. Può essere un percorso in `/content/dam or /var/dxml`. |

**Esempio**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
