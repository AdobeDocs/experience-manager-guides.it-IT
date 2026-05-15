---
title: Configurare Dispatcher
description: Scopri come configurare Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/RTgKeZZYjXP5ebOpTys9RL6-Q9IcPbkLZJ13ueRZwVI
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 6%

---

# Configurare Dispatcher {#id213BCM0M05U}

Se prevedi di utilizzare un’istanza Dispatcher su AEM Author insieme ad AEM Guides, per completare la configurazione devi eseguire le seguenti configurazioni aggiuntive:

>[!NOTE]
>
> Dispatcher è lo strumento di caching e/o bilanciamento del carico di Adobe Experience Manager. Per ulteriori dettagli sull&#39;utilizzo di Dispatcher, vedere [Panoramica di Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## Abilitare AllowEncodedSlashes negli URL

Gli URL con barre codificate non sono abilitati per impostazione predefinita nella configurazione di AEM Dispatcher, ma è necessario abilitarli mentre si lavora in AEM Guides. A questo scopo, è necessario impostare il parametro AllowEncodedSlashes su On nella configurazione di Apache, come illustrato nel seguente snippet:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configurare il file mime.types per DITA

Quando si utilizza un Dispatcher con AEM Guides, è necessario assicurarsi che i file di mappa e argomenti DITA vengano riprodotti come HTML affinché gli autori possano visualizzare il contenuto come previsto \(anziché in formato testo non elaborato\).

Per aggiornare il file mime.types, effettua le seguenti operazioni:

1. Connettiti al server Dispatcher utilizzando SSH e individua il file httpd.conf.

1. Controlla il percorso del file &quot;mime.types&quot;.

1. Apri il file mime.types e cerca &quot; text/html&quot;. La mappatura predefinita per &quot; text/html&quot; è:

   `text/html html htm`

1. Aggiorna la mappatura aggiungendo estensioni ditamap e dita come:

   `text/html html htm ditamap dita`

1. Salva e chiudi il file.


Questo aggiornamento della configurazione assicura che i file mappa DITA e i file degli argomenti sottoposti a rendering da Dispatcher vengano visualizzati come HTML nell’interfaccia utente di Assets.

## Consenti URL richiesta preferenze utente

Quando utilizzi un Dispatcher con AEM Guides, se l’istanza Autore ha in primo piano un dispatcher, apporta le due modifiche seguenti:

- Inserisci nella whitelist l’URL della richiesta POST. Di seguito è riportata una regola di esempio &quot; `/filters`&quot;. Aggiungere questa regola al file di configurazioni del dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Assicurati che il pattern URL &quot; /libs/cq/security/userinfo.json&quot; non sia memorizzato nella cache in Author Dispatcher, quindi aggiungi una regola \(simile a quella riportata di seguito\) in Author\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Argomento padre:**[ Scarica e installa](download-install.md)
