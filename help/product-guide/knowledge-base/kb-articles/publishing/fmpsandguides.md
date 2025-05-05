---
title: Pubblicazione tramite FrameMaker Publishing Server (FMPS) in AEM Guides
description: Pubblicazione con FMPS tramite AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: f971be4be9e2d32618616727cd9c682941dd3fb2
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Pubblicazione tramite FrameMaker Publishing Server (FMPS) in AEM Guides

L’integrazione di AEM Guides con FrameMaker Publishing Server potrebbe essere la soluzione ideale per chi cerca una pubblicazione automatizzata di alta qualità.\
Article consente di configurare ed eseguire FMPS con AEM Guides.

## Compatibilità di FMPS con AEM Guides

- Compatibilità con AEM Guides 4.1: [matrice di compatibilità 4.1](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=it/#compatibility-matrix)
- Compatibilità con AEM Guides 4.0: [matrice di compatibilità 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Ultima versione: [Informazioni sulla versione più recente](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=it)

## Installazione

Fai riferimento a quanto segue per l’installazione e la configurazione di AEM Guides e FMPS

### Guide AEM

L&#39;installazione e la configurazione fanno riferimento a: [4.1 installazione e configurazioni](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Per l&#39;installazione di FMPS è possibile fare riferimento a [YouTube link](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) o [FMPS installazione e configurazione](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Configurazioni richieste

È possibile utilizzare FrameMaker Publishing Server (FMPS) per generare il contenuto DITA. FMPS supporta un&#39;ampia gamma di formati di output. Modifica le seguenti proprietà del bundle &quot;com.adobe.fmdita.config.ConfigManager&quot; nella console Web per configurare AEM Guides per l’utilizzo di FMPS.

Per aprire la console Web, passare all&#39;URL Accesso http://\&lt;nome server\>:\&lt;porta\>/system/console/configMgr.

**Proprietà di configurazione e relativa descrizione** [4.1 installazione e configurazione](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test in esecuzione:

Utilizzando FMPS, puoi pubblicare automaticamente **PDF, Responsive HTML5** e **Epub** per il tuo Assets DITA e FM.

Dal menu &quot;Genera PDF utilizzando&quot;, scegliete FrameMaker Publishing Server.

L’utente può fornire &quot;settings File(.sts)&quot; e &quot;ditaval&quot;. Il filtro viene eseguito utilizzando ditaval in base alle condizioni specificate.

- **File di impostazione**: file di impostazione di FrameMaker /FMPS Publish contenente tutte le impostazioni che si desidera vengano rispettate da FMPS durante la pubblicazione. Ad esempio, la creazione di output con un modello personalizzato, la creazione di indicatori e pagine al vivo (PDF) e la creazione di PDF con il sommario.
- **Predefinito FMPS:** Combinazione predefinita di file ditaval e impostazioni. Invece di fornire file ditaval e impostazioni separati, l’utente può pre-creare un predefinito FMPS che può essere riutilizzato per le esigenze di pubblicazione.

**Nota:** l&#39;impostazione di sistema predefinita viene utilizzata da FMPS per la pubblicazione se non si sceglie alcuna impostazione o il predefinito FMPS.

Si tratta di un conflitto se si sceglie il predefinito FMPS e si forniscono anche impostazioni personalizzate o un file ditaval da AEM. In questo caso, il predefinito FMPS ha la precedenza sulle impostazioni personalizzate o sul file ditaval.

### Pubblicazione della linea di base tramite FMPS:

È possibile pubblicare le linee di base già create con FMPS2020.0.2 o versione successiva.

**File di impostazioni FMPS di esempio (file con estensione sts) per iniziare:** [File di impostazioni FMPS di esempio](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimi il file)

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
>Verificare che la baseline sia stata creata correttamente. Per verificare, passare alla scheda Mappa dashboard— Argomenti— Download  Mappare e scegliere &quot;Usa baseline&quot;.
>- ### Le attività Publish di FMPS richiedono più tempo rispetto ad altri motori
>Durante la pubblicazione da FMPS, il tempo di intestazione fisso ideale è di circa 3-4 minuti; se ritieni che sia più lungo, contatta l’amministratore FMPS o contatta il supporto Adobe.

## Altre risorse:

[Informazioni e supporto su FMPS](https://helpx.adobe.com/it/support/framemaker-publishing-server.html)

[Informazioni e supporto su AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker e community FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Community AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
