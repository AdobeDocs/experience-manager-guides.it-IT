---
title: Configurare l’Assistente IA in modalità Agentic
description: Scopri come configurare l’Assistente di IA per l’agente in Experience Manager Guides
source-git-commit: 5ed0a5191e1852dd65e0461f02d520b195f7cc39
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 1%
---

# Configurare l’Assistente AI in modalità Agentic per Cloud Service

In qualità di amministratore, puoi configurare l’Assistente IA in modalità Agente per la tua organizzazione in Experience Manager Guides. I passaggi di configurazione variano a seconda che l’impostazione Unified Shell sia abilitata o meno nell’ambiente AEM as a Cloud Service e che gli utenti abbiano eseguito l’accesso tramite autenticazione SSO o non SSO. Questo articolo descrive il processo di configurazione per ogni scenario.

## Prerequisito

Prima di configurare l&#39;Assistente di intelligenza artificiale in modalità Agentic, è necessario che la tua organizzazione sia integrata in **CX Enterprise Coworker**.

## Configurare IA Assistant in base all’ambiente in uso

Utilizza la tabella seguente per identificare il percorso di configurazione applicabile agli utenti, quindi segui i passaggi corrispondenti.

| Unified Shell | Tipo di accesso | Configurazione obbligatoria |
|---|---|---|
| Abilitato | SSO | Nessuna configurazione aggiuntiva. Tutto funziona come previsto |
| Abilitato | Non SSO | Aggiungere la configurazione IMS all’ambiente |
| Disabilitato | SSO | Aggiungere la configurazione IMS all’ambiente |
| Disabilitato | Non SSO | Aggiungere la configurazione IMS all’ambiente |

### Utenti con Unified Shell abilitata

**Accesso SSO**

Se Unified Shell è abilitato e gli utenti accedono tramite SSO, non è necessaria alcuna configurazione aggiuntiva. L’Assistente AI in modalità Agentic funziona automaticamente una volta che l’organizzazione è stata integrata in CX Enterprise Coworker.

**Accesso non SSO**

Se Unified Shell è abilitato ma gli utenti accedono senza SSO, devi [aggiungere la configurazione IMS all&#39;ambiente](#add-ims-configuration-to-the-environment) di seguito.

### Utenti con Unified Shell disabilitata

Se Unified Shell è disabilitata, è necessario [Aggiungere la configurazione IMS all&#39;ambiente](#add-ims-configuration-to-the-environment) per entrambi:

- Accesso SSO
- Accesso non SSO

## Aggiungere la configurazione IMS all’ambiente

Per aggiungere la configurazione IMS all’ambiente, effettua le seguenti operazioni:

1. Apri Experience Manager, quindi seleziona il programma contenente l’ambiente da configurare.

2. Passa alla scheda **Ambienti**.

3. Seleziona il nome dell’ambiente da configurare. Viene visualizzata la pagina **Informazioni sull&#39;ambiente**.

4. Passa alla scheda **Configurazione**.

5. Incolla i dettagli del servizio JSON (scaricati quando hai creato la configurazione IMS in Adobe Developer Console) nel campo **Valore** corrispondente a `SERVICE_ACCOUNT_DETAILS`. Assicurati di utilizzare lo stesso nome e la stessa configurazione previsti dall’ambiente.

>[!NOTE]
>Se non hai ancora creato le credenziali OAuth/IMS per il tuo ambiente, esegui questa operazione in Adobe Developer Console prima di completare questo passaggio.

![configurazione account del servizio ims](assets/ims-service-account-config.png){width="800"}

## Abilita la modalità agente

Una volta completata la configurazione per l’ambiente, contatta il team Customer Success per abilitare la modalità Agentic.

Con la modalità Agentic abilitata per il tuo ambiente, passa a **Impostazioni Workspace** e abilita l&#39;opzione **Agentic** nella scheda **General** della sezione **Assistente AI**.
