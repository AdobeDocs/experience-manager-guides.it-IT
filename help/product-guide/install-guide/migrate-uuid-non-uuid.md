---
title: Migrazione di contenuti da non-UUID a UUID
description: Scopri come migrare contenuti non UUID a UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: e38cd858201ea657ce276eb4b358b0d4eff502b2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# Migrazione di contenuti da non-UUID a UUID {#id226TI0U20XA}


Puoi migrare il contenuto non UUID in UUID in base alla versione corrente di Experience Manager Guides in uso.

>[!IMPORTANT]
>
> Prima di eseguire la migrazione del contenuto al server UUID, accertati di disporre di un server non UUID con una versione compatibile di AEM Guides installata.

## Matrice di compatibilità

Utilizza la seguente matrice per determinare il percorso di migrazione corretto in base alla versione corrente non UUID. Questo garantisce una transizione senza problemi dopo la migrazione.

| Versione non UUID richiesta per la migrazione | Versione UUID dopo la migrazione | Percorso di aggiornamento supportato dopo la migrazione |
|---|---|---|
| 4.3.1 non UUID | 4.3.2 UUID | Dopo la migrazione alla versione 4.3.2 UUID, puoi installare direttamente la versione 4.6.0 (UUID). Dopo aver eseguito l&#39;aggiornamento alla versione 4.6.0, eseguire l&#39;aggiornamento alla versione 5.1.0 e quindi installare 5.1.0 Service Pack 1. |
| 4.6.0 Service Pack 4 non UUID | 4.6.1 UUID | Dopo la migrazione alla versione 4.6.1 UUID, puoi effettuare l’aggiornamento direttamente alla versione 5.1.0 (UUID). Al termine dell’aggiornamento, installa la versione 5.1.0 del Service Pack 1. |

Per i passaggi dettagliati sulla migrazione dei contenuti, consulta i seguenti articoli:

- [Migrazione dei contenuti da **4.3.1 non UUID a 4.3.2 UUID**](./migrate-non-uuid-4-3.md)
- [Migrazione dei contenuti da **4.6.0 Service Pack 4 non UUID a 4.6.1 UUID**](./migrate-non-uuid-uuid-4-6.md)



