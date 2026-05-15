---
title: Migrazione di contenuti da non-UUID a UUID
description: Scopri come migrare contenuti non UUID a UUID
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/pZ0HRoSRWcGz2IT9tWAZ-vZYLc-Zc4kyYt8OXRohmTU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
subfeature_v2:
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 320
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

- [**4.3.1 da non UUID a migrazione contenuti UUID 4.3.2**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 non-UUID per la migrazione del contenuto UUID 4.6.1**](./migrate-non-uuid-uuid-4-6.md)



