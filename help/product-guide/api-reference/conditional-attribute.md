---
title: API REST per funzionare con gli attributi condizionali
description: Scopri l’API REST per lavorare con gli attributi condizionali
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552eid: c6d09140-3c91-45d3-b7ed-b681af752f43
subfeature_v2: id: d27d524e-c4e5-4b77-b86b-3db049db0b25
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 5%

---

# API REST per funzionare con gli attributi condizionali {#id175UB30E05Z}

La seguente API REST consente di aggiungere attributi condizionali in un profilo di cartella.

## Aggiungere un attributo condizionale in un profilo a livello di cartella

Un metodo POST che aggiunge attributi condizionali a un determinato profilo a livello di cartella.

**URL richiesta**:\
http://*<server-guide-aem\>*: *<numero-porta\>*/bin/fmdita/folderprofiles

**Parametri**:

| Nome | Tipo | Obbligatorio | Descrizione |
|----|----|--------|-----------|
| `:operation` | Stringa | Sì | Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``ADDATTRIBUTEPROFILES``. <br> **Nota:** il valore non distingue tra maiuscole e minuscole. |
| `profilename` | Stringa | Sì | Nome visualizzato del profilo a livello di cartella in cui devono essere aggiunti gli attributi condizionali. |
| `conditionalprofiles` | Array JSON | Sì | Array JSON costituito dal nome e dai valori dell’attributo condizionale. Il seguente snippet di codice di esempio mostra l’array JSON con due attributi - `platform` e `product` a cui sono assegnati più valori. |

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Valori risposta**:\
Restituisce una risposta HTTP 200 \(Riuscito\).
