---
title: API REST per funzionare con gli attributi condizionali
description: Scopri l’API REST per lavorare con gli attributi condizionali
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# API REST per funzionare con gli attributi condizionali {#id175UB30E05Z}

La seguente API REST consente di aggiungere attributi condizionali in un profilo di cartella.

## Aggiungere un attributo condizionale in un profilo a livello di cartella

Metodo POST che aggiunge attributi condizionali a un determinato profilo a livello di cartella.

**URL richiesta**:\
http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/folderprofiles

**Parametri**:\
|Nome|Tipo|Obbligatorio|Descrizione| ----|----|--------|-----------| |`:operation`|String|Yes|Nome dell&#39;operazione chiamata. Il valore di questo parametro è ``ADDATTRIBUTEPROFILES``. <br> **Nota:** Il valore non distingue tra maiuscole e minuscole.| |`profilename`|Stringa|Sì|Nome visualizzato del profilo a livello di cartella in cui devono essere aggiunti gli attributi condizionali.| |`conditionalprofiles`Matrice JSON|Sì|Matrice JSON costituita dal nome e dai valori dell&#39;attributo condizionale. Il seguente snippet di codice di esempio mostra l’array JSON con due attributi: `platform` e `product` con più valori assegnati.|

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

**Valori di risposta**:\
Restituisce una risposta HTTP 200 \(Riuscito\).
