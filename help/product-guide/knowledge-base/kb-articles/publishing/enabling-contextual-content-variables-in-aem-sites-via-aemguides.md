---
title: Abilitazione delle variabili di contenuto contestuale (CCVAR) nelle pagine AEM Sites generate da AEM Guides
description: Utilizzo delle variabili di contenuto contestuale (CCVAR) nelle pagine AEM Sites generate da AEM Guides
feature: Web Editor
role: User, Admin
exl-id: f9adbb3f-6c1c-4d6f-b55d-1fb45acca91a
source-git-commit: 4020534552bdb77545c2a283f2a90adc3aebc729
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 2%

---

# Abilitazione delle variabili di contenuto contestuale (CCVAR) nelle pagine AEM Sites generate da AEM Guides

Le variabili di contenuto contestuali (CCVAR) sono una funzionalità ACS Commons che consente agli autori di utilizzare variabili di contenuto dinamiche direttamente nel testo creato. Anche se CCVAR è comunemente utilizzato in AEM Sites, questo articolo spiega come ottenere funzionalità simili tramite pagine generate da contenuto creato in **AEM Guides** *principalmente utilizzando parole chiave definite nella mappa DITA*.


## Cosa sono le variabili di contenuto contestuali (CCVAR)?

CCVAR consente agli autori di inserire nel contenuto variabili dinamiche che vengono risolte in fase di esecuzione in base al contesto. Ad esempio, variabili come `((page_properties.pageTitle))` possono richiamare dinamicamente il titolo della pagina durante il rendering del contenuto.


## Come abilitare il CCVAR nelle pagine AEM Sites generate da AEM Guides?

Considerando che AEM Guides viene utilizzato come origine di tutti i contenuti (inclusi AEM Sites, PDF o HTML5), per abilitare i CCVAR sulle pagine generate da AEM Guides, è necessario utilizzare parole chiave per definire il nome del CCVAR. Per eseguire questa operazione nelle Guide, definire **parole chiave** nella mappa DITA utilizzando `<keydef>` elementi. Queste parole chiave possono corrispondere a valori dinamici (o nomi CCVAR), consentendo di farvi riferimento negli argomenti DITA.


## Prerequisiti

Prima di procedere, verifica che siano soddisfatti i seguenti prerequisiti:

1. **Comuni ACS AEM installati**:
   - Assicurati che **ACS AEM Commons** sia installato nell&#39;istanza AEM. Questa opzione è necessaria per l’utilizzo di CCVAR.

2. **Configurazione variabili di contenuto contestuali**:
   - Completa la configurazione per **Variabili di contenuto contestuali** in AEM utilizzando la [documentazione ufficiale](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). Ciò include:
      - Abilitazione dell&#39;aggregazione di proprietà ****.
      - Configurazione della riscrittura di **HTML** (se si utilizza l&#39;output di HTML).
      - Configurazione della riscrittura **JSON** (se si utilizza l&#39;output JSON).



## Passaggi per abilitare CCVAR in AEM Guides

### 1. Definire le parole chiave nella mappa DITA

- In AEM Guides, definisci le parole chiave utilizzando gli elementi `<keydef>` nella mappa DITA per corrispondere al CCVAR.
- Ad esempio:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```

- L&#39;attributo `keys` (`product` in questo esempio) verrà utilizzato per fare riferimento a questa variabile negli argomenti DITA.


## 2. Utilizzare le parole chiave negli argomenti DITA

- Nell&#39;argomento, utilizzare la parola chiave ovunque debba essere utilizzato CCVar.
- Ad esempio:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```

- L&#39;attributo `keyref` punta al valore `keys` definito nell&#39;elemento `<keydef>` (`product` in questo caso).
- Durante la generazione dell’output, la parola chiave verrà sostituita con il valore CCVar corrispondente.


## 3. Genera output

- Quando si genera l&#39;output per AEM Sites, i riferimenti delle parole chiave vengono risolti nei valori dinamici corrispondenti.
- Ad esempio:
   - Se `((page_properties.pageTitle))` viene risolto in `My Product`, l&#39;output verrà visualizzato:

```xml
   This is the title of the product: My Product.
```


## Caso d’uso di esempio

Si supponga di voler inserire in modo dinamico la lingua della pagina negli argomenti DITA. Ecco come ottenere questo:

**Definire la parola chiave nella mappa DITA**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

**Riferimento alla parola chiave in un argomento DITA**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

**Output generato**:

Se `((inherited_page_properties.jcr:language))` viene risolto in `en`, l&#39;output verrà visualizzato:

```
     The language of this page is: en.
```


### Riferimenti

Per ulteriori dettagli sulle **variabili di contenuto contestuali**, consulta la documentazione ufficiale:\
[Variabili di contenuto contestuali in AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)
