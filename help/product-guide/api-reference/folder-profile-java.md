---
title: API basata su Java per lavorare con i profili di cartelle
description: Scopri l’API basata su Java per lavorare con i profili delle cartelle
exl-id: 388ae654-c4f9-4bb7-ba98-370b8919e3a6
feature: Java-Based API Folder Profiles
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/-rZBkRHgOJDh0hpvpMgRx7jyvcYstElA4ztdjXmpATU'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: bc523de0-ab16-4d84-a1f2-ab36dfeb1a6d
    internal-label: Java Based API Folder Profiles
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%
---
# API basata su Java per lavorare con i profili di cartelle {#id175UB30E05Z}

>[!NOTE]
>
> Puoi utilizzare le API basate su Java disponibili in Experience Manager Guides per creare plug-in personalizzati ed estendere flussi di lavoro preconfigurati. Questo articolo verrà archiviato a novembre 2024.
> Visualizza [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) per la documentazione più recente e dettagliata sull&#39;utilizzo dell&#39;API basata su Java.




La seguente API basata su Java consente di aggiungere attributi condizionali a un profilo a livello di cartella. Questa API è disponibile sotto forma di bundle. Per utilizzare queste API, devi includere questo bundle nel codice.

Dettagli bundle:

- ID gruppo: **com.adobe.fmdita**

- ID artefatto: **api**

- Versione: **3.2**

- Pacchetto: **com.adobe.fmdita.api.profiles**

- Dettagli classe:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  La classe **`FolderProfileUtils`** contiene un metodo per aggiungere attributi condizionali in un profilo di cartella.


## Aggiungere attributi condizionali a un profilo di cartella

Il metodo ``addAttributeProfiles`` aggiunge attributi condizionali a un profilo a livello di cartella.

**Sintassi**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parametri**:

| Nome | Tipo | Descrizione |
|----|----|-----------|
| ``attributeNames`` | Stringa | Elenco di nomi di attributi. |
| ``values`` | Stringa | Elenco di valori per gli attributi specificati. |
| `labels` | Stringa | Elenco di etichette per le coppie `attribute`- `value`. [1](#fntarg_1) |
| `profileName` | Stringa | Il nome del profilo a livello di cartella a cui devono essere applicati questi attributi, valori ed etichette. **Importante:** tutti gli attributi-valori-etichette esistenti definiti nel profilo vengono sovrascritti. |
| `session` | javax.jcr.Session | Una sessione JCR valida. |

**Restituisce**:
`true` per il completamento. In caso di errore, genera un’eccezione.

**Eccezione**:
Genera ``java.lang.Exception`` nei seguenti scenari:

- Se l&#39;API non è riuscita a ottenere l&#39;oggetto `resourceResolverFactory`. In tal caso, è necessario riavviare il bundle.
- Se i parametri passati all’API non sono validi.
- Se l’API viene chiamata tramite una sessione utente non autorizzata, ad esempio un utente che non è un amministratore per il profilo di cartella specificato.

[1](#fnsrc_1) `attributeNames`, `values` e `labels` nello stesso indice in un elenco array devono corrispondere alla stessa voce.
