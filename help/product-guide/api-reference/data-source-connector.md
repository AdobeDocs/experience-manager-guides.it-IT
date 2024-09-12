---
title: API REST per registrare un connettore di origine dati
description: Scopri l’API REST per registrare un connettore di origine dati
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: 45ae1471fe0f0586764ede9dd96530b7f75f69ee
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 7%

---

# API REST per registrare un connettore di origine dati {#id236LG0Y0CXA}

La seguente API REST consente di registrare un connettore dell’origine dati.

## Registrare un connettore di origine dati

Metodo di GET che registra un connettore di origine dati.

**URL richiesta**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parametri**:

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `path` | Stringa | Sì | Stringa che punta a un percorso nell’archivio AEM. Può essere un percorso in `/content/dam or /var/dxml`. |

**Esempio**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
