---
title: Configura nomi file
description: Scopri come disabilitare la postelaborazione per una cartella caricata in Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
hidefromtoc: true
source-git-commit: 564ee1731be2378744ffd2ed54a2fd423901a0b3
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Disattiva la postelaborazione per una cartella

Per impostazione predefinita, tutte le risorse caricate vengono elaborate utilizzando il flusso di lavoro Risorsa di aggiornamento DAM. Nell’ambito di questo flusso di lavoro, Experience Manager Guides esegue un’ulteriore elaborazione, denominata postelaborazione. Questo aiuta anche a generare gli UUID

Durante il caricamento dei file e delle cartelle nel server *Adobe Experience Manager Assets*, puoi anche disabilitare la postelaborazione e la generazione di UUID.

Utilizza le istruzioni in [Sostituzioni configurazione](download-install-additional-config-override.md#) per creare il file di configurazione. Nel file di configurazione, fornisci i seguenti dettagli (proprietà) per disabilitare la post-elaborazione in un determinato percorso o ignorare la post-elaborazione per una cartella:

>[!NOTE]
>
> Puoi anche utilizzare espressioni regolari (regex) per definire regole che si applicano a più cartelle o a un’intera gerarchia di cartelle. Per ulteriori dettagli, visualizzare la sezione [Usa regex per abilitare o disabilitare la post-elaborazione](#use-regex-to-enable-or-disable-post-processing).

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `ignored.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine o regex) <br> **Valore predefinito**: `/content/dam/projects/translation_output` |

| PID | Chiave proprietà | Valore proprietà |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `enabled.post.processing.paths` | Valore stringa per impostare qualsiasi proprietà standard NODE_OPTIONS (proprietà multivalore, stringhe con percorso che omette `/` alla fine o regex) <br> **Valore predefinito**: `/content/dam` |

## Regole per abilitare o disabilitare la post-elaborazione

Per impostazione predefinita, la postelaborazione viene eseguita per ogni percorso di cartella nella cartella DAM di Experience Manager. Le configurazioni vengono applicate a qualsiasi cartella in base alle seguenti regole:

* Se il padre viene ignorato per la postelaborazione ma la cartella figlio è abilitata, il figlio e tutti i suoi successori vengono considerati abilitati.
* Se il padre è abilitato per la postelaborazione ma il figlio viene ignorato, il figlio e tutti i suoi successori vengono considerati ignorati.
* Se lo stesso percorso di cartella esiste in entrambe le configurazioni `ignored.post.processing.paths` e `enabled.post.processing.paths`, viene considerato ignorato per la post-elaborazione.

## Usa regex per abilitare o disabilitare la post-elaborazione

Invece di specificare singoli percorsi di cartelle, puoi utilizzare espressioni regolari (regex) per definire regole che si applicano a più cartelle o gerarchie di cartelle intere.

I pattern Regex vengono valutati rispetto al percorso completo della risorsa durante la post-elaborazione.

Quando si utilizzano espressioni regolari (regex) per configurare percorsi di post-elaborazione ignorati e abilitati, AEM Guides valuta entrambe le configurazioni in base al percorso della risorsa. Se un percorso corrisponde sia a una regola di ignoramento che a una regola di abilitazione, le regole di ignoramento hanno sempre la precedenza.

Gli esempi seguenti illustrano come vengono valutate le regole di abilitazione e ignora basate su regex.

## Scenari di valutazione Regex per il post-trattamento

### Ignora gerarchia principale, abilita cartella specifica

**Ignora regex**

`regex:/content/dam/lang-test/.*`

**Abilita regex**

`regex:/content/dam/lang-test/.*/parent1`

Nell&#39;esempio precedente, la post-elaborazione verrà disabilitata per `/content/dam/lang-test/en/parent1`.

Anche se il percorso corrisponde all’abilitazione regex, corrisponde già all’ignora regex. Ignora le regole ha la precedenza, pertanto la post-elaborazione non è abilitata.

### Ignora cartella specifica, abilita gerarchia più ampia

**Ignora regex**

`regex:/content/dam/lang-test/.*/parent1`

**Abilita regex**

`regex:/content/dam/lang-test/.*`

Nell&#39;esempio precedente, la post-elaborazione verrà disabilitata per `/content/dam/lang-test/en/parent1` e abilitata per `/content/dam/lang-test/en/parent2`.

Il percorso `parent1` viene esplicitamente ignorato e rimane disabilitato. Vengono elaborate altre cartelle che corrispondono solo all’abilitazione regex.

### Ignora cartella principale, abilita cartella secondaria

**Ignora regex**

`regex:/content/dam/lang-test/.*/parent1`

**Abilita regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

Nell&#39;esempio precedente, la post-elaborazione verrà disabilitata per `/content/dam/lang-test/en/parent1` e `/content/dam/lang-test/en/parent1/child2` e abilitata per `/content/dam/lang-test/en/parent1/child1`.

Viene elaborata la cartella secondaria abilitata esplicitamente da regex. Altre cartelle secondarie rimangono disabilitate perché il loro percorso principale corrisponde a ignora regex.

### Ignora una cartella figlio specifica, abilita gerarchia padre

**Ignora regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Abilita regex**

`regex:/content/dam/lang-test/.*/parent1`

Nell&#39;esempio precedente, la post-elaborazione verrà disabilitata per `/content/dam/lang-test/en/parent1/child1` e abilitata per `/content/dam/lang-test/en/parent1` e `/content/dam/lang-test/en/parent1/child2`.

Viene ignorata solo la cartella secondaria ignorata in modo esplicito. La cartella principale e le altre cartelle secondarie vengono elaborate perché corrispondono a enable regex e non corrispondono a ignore regex.

