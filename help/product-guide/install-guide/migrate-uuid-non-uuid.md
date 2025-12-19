---
title: Migrazione di contenuti da non-UUID a UUID
description: Scopri come migrare contenuti non UUID a UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
source-git-commit: 56f1bd81e74ad9b479b2dcbcf04e1ee82e9a9041
workflow-type: tm+mt
source-wordcount: '320'
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
| 4.3.1 non UUID | 4.3.2 UUID | Dopo aver eseguito la migrazione alla versione 4.3.2 di UUID, devi installare direttamente la versione 4.6.0 (UUID). Dopo aver eseguito l&#39;aggiornamento alla versione 4.6.0, eseguire l&#39;aggiornamento alla versione 5.1.0 e quindi installare 5.1.0 Service Pack 3. |
| 4.6.0 Service Pack 4 non UUID | 4.6.1 UUID | Dopo aver eseguito la migrazione alla versione 4.6.1 UUID, devi eseguire direttamente l’aggiornamento alla versione 5.1.0 (UUID). Al termine dell’aggiornamento, installa la versione 5.1.0 del Service Pack 3. |

## Stima del tempo di migrazione

L’utility di migrazione elabora le risorse a una velocità media di circa 50 ms per risorsa. La tabella seguente fornisce le stime dei tempi di migrazione per un sistema configurato con 64 vCPU, 128 GB di RAM e storage basato su SSD. I requisiti di memoria possono aumentare per archivi o risorse più grandi con molte rappresentazioni o file binari ad alta risoluzione.

>[!NOTE]
>
> I tempi di migrazione effettivi possono variare in base alle prestazioni dell&#39;hardware, alla velocità effettiva di storage, alle attività AEM simultanee e al carico complessivo del sistema.


| **Numero risorse** | **Circa Ora** |
|-----------------|-------------------------|
| 10K | ~8-9 minuti |
| 50 K | ~42 minuti |
| 100K | ~1,4 ore |
| 250 K | ~3,5 ore |
| 500 K | ~7 ore |
| 750 K | ~10,5 ore |
| 1 M | ~14 ore |
| 2 M | ~28 ore (~1,2 giorni) |
| 3 M | ~42 ore (~1,75 giorni) |
| 5 M | ~69 ore (~2,9 giorni) |
| 10 M | ~139 ore (~5,8 giorni) |


Per i passaggi dettagliati sulla migrazione dei contenuti, consulta i seguenti articoli:

- [Migrazione dei contenuti da **4.3.1 non UUID a 4.3.2 UUID**](./migrate-non-uuid-4-3.md)
- [Migrazione dei contenuti da **4.6.0 Service Pack 4 non UUID a 4.6.1 UUID**](./migrate-non-uuid-uuid-4-6.md)



