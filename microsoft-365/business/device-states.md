---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Microsoft 365 for business の管理者ホームの [デバイスの操作] リストに表示されるさまざまなデバイスの状態について説明します。
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400956"
---
# <a name="device-states"></a>デバイス状態

[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状態**|**説明**|
|:-----|:-----|
|Intune で管理  <br/> |Microsoft 365 Business Premium によって管理されます。  <br/> |
|インベントリからの削除待ち  <br/> |Microsoft 365 Business Premium は、デバイスから会社のデータを削除する準備をしています。  <br/> |
|回収を実行中です  <br/> |Microsoft 365 Business Premium は現在、デバイスから会社データを削除しています。  <br/> |
|インベントリからの削除失敗  <br/> | 会社データの削除アクションが失敗しました。  <br/> |
|削除の取り消し  <br/> |"削除" アクションが取り消されました。  <br/> |
|ワイプの保留中  <br/> |出荷時のリセットを開始するのを待っています。  <br/> |
|ワイプを実行中です  <br/> |出荷時のリセットが発行されました。  <br/> |
|ワイプ失敗  <br/> |出荷時の設定に戻すことができませんでした。  <br/> |
|ワイプの取り消し  <br/> |ファクトリワイプがキャンセルされました。  <br/> |
|異常  <br/> |アクションが保留中 (または進行中) ですが、デバイスは30日以上チェックインされていません。  <br/> |
|削除の保留中  <br/> |削除アクションが保留中です。  <br/> |
|検出  <br/> |Microsoft 365 Business Premium はデバイスを検出しました。  <br/> |
   
