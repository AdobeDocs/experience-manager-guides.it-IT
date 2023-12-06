---
title: Pubblicazione tramite FrameMaker Publishing Server (FMPS) nelle guide AEM
description: Pubblicazione con FMPS tramite AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
source-git-commit: c31a569c009155dacef00b6b3f1e6d64e556cf29
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 0%

---

# Pubblicazione tramite FrameMaker Publishing Server (FMPS) nelle guide AEM

L’integrazione di AEM Guides con FrameMaker Publishing Server potrebbe essere la soluzione ideale per chi cerca una pubblicazione automatizzata di alta qualità.\
L’articolo ti aiuta a configurare ed eseguire FMPS con le guide AEM.

## Compatibilità del FMPS con le guide dell’AEM

- Compatibilità con il punto 4.1 delle guide AEM: [Matrice di compatibilità 4.1](/help/product-guide/release-info/release-notes-4.1.md#compatibility-matrix)
- Compatibilità con le guide AEM 4.0: [Matrice di compatibilità 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Ultima versione: [Informazioni sull’ultima versione](/help/product-guide/release-info/latest-release-info.md)

## Installazione

Fare riferimento a quanto segue per l&#39;installazione e la configurazione delle guide AEM e FMPS

### Guide AEM

Per informazioni sull&#39;installazione e la configurazione, vedere: [4.1 installazione e configurazioni](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Per l&#39;installazione di FMPS è possibile fare riferimento a [Collegamento YouTube](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) o [Installazione e configurazione di FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Configurazioni richieste

È possibile utilizzare FrameMaker Publishing Server (FMPS) per generare il contenuto DITA. FMPS supporta un&#39;ampia gamma di formati di output. Modifica le seguenti proprietà del &quot;bundle com.adobe.fmdita.config.ConfigManager&quot; nella console Web per configurare le guide AEM per l’utilizzo di FMPS.

Per aprire la console Web, vai all&#39;URL Accesso http://\&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr.

**Proprietà di configurazione e relativa descrizione** [4.1 installazione e configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test in esecuzione:

Utilizzando FMPS, puoi pubblicare automaticamente **PDF, Responsive HTML5**, e **Epub** per le risorse DITA e FM.

Dal menu &quot;Genera PDF utilizzando&quot;, scegliete FrameMaker Publishing Server.

L’utente può fornire &quot;settings File(.sts)&quot; e &quot;ditaval&quot;. Il filtro viene eseguito utilizzando ditaval in base alle condizioni specificate.

- **File di impostazione**: file di impostazione di pubblicazione del FrameMaker /FMPS contenente tutte le impostazioni che si desidera vengano rispettate da FMPS durante la pubblicazione. Ad esempio, la creazione di output con un modello personalizzato, la creazione di indicatori e pagine al vivo (PDF) e la creazione di PDF con il sommario.
- **Predefinito FMPS:** Si tratta di una combinazione predefinita di ditaval e file di impostazioni. Invece di fornire file ditaval e impostazioni separati, l’utente può pre-creare un predefinito FMPS che può essere riutilizzato per le esigenze di pubblicazione.

**Nota:** L&#39;impostazione di sistema predefinita viene utilizzata da FMPS per la pubblicazione se non si sceglie alcuna delle impostazioni o del predefinito FMPS.

Si tratta di un conflitto se si sceglie il predefinito FMPS e si forniscono anche impostazioni personalizzate o un file ditaval da AEM. In questo caso, il predefinito FMPS ha la precedenza sulle impostazioni personalizzate o sul file ditaval.

### Pubblicazione della linea di base tramite FMPS:

È possibile pubblicare le linee di base già create con FMPS2020.0.2 o versione successiva.

**File di esempio delle impostazioni FMPS (file .sts) per iniziare:** [Esempio di file di impostazioni FMPS](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimi questo file)

## Domande frequenti e risoluzione dei problemi:

- ### La pubblicazione di FMPS non riesce con &quot;Eccezione di timeout&quot;

>Controlla e aumenta il valore di &quot;Timeout FMPS&quot; (secondi) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### Impossibile ottenere il predefinito FMPS nel menu a discesa

>Verificare che sul server sia stato creato un predefinito FMPS predefinito e che le impostazioni di connessione siano corrette.

- ### Ricevo PDF vuoti durante la pubblicazione

>Se utilizzi UUID, assicurati di aver selezionato &quot;Usa riferimenti basati su UUID&quot; in Preferenze di modifica del FrameMaker e viceversa per le guide AEM non UUID.

- ### Le mie impostazioni/ditaval non vengono applicate nell&#39;output pubblicato finale

>Verificate che non si stia scegliendo contemporaneamente il predefinito FMPS e il file di impostazione/diaval. Utilizza il FrameMaker per controllare manualmente l’output.

- ### La baseline non viene pubblicata da FMPS

>FMPS2020.0.2 o versioni successive sono compatibili con la pubblicazione di base.
>Verificare che la baseline sia stata creata correttamente. Per verificare, passare a Map Dashboard (Argomenti)— Download Map (Scarica mappa) e scegliere &quot;Use Baseline&quot; (Usa baseline).
- ### Le attività di pubblicazione da FMPS richiedono più tempo rispetto ad altri motori

>Durante la pubblicazione da FMPS, il tempo di intestazione fisso ideale è di circa 3-4 minuti; se ritieni che sia più lungo, contatta l’amministratore FMPS o contatta il supporto Adobe.

## Altre risorse:

[Formazione e supporto per FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Informazioni e supporto su guide AEM](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker e community FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Community delle guide dell’AEM](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
