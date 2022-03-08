---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: ビジネス向け管理ホームの [デバイスの操作] リストで、さまざまなMicrosoft 365を確認します。
ms.openlocfilehash: 798a753f6d523a3f586ac32698cda80a127c44b5
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313819"
---
# <a name="device-states"></a>デバイス状態

この記事は、ユーザーにMicrosoft 365 Business Premium。

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。
  
![In the Device actions list, you can see the Devices states.](../../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状態**|**説明**|
|:-----|:-----|
|Intune で管理  <br/> |ユーザーによって管理Microsoft 365 Business Premium。  <br/> |
|インベントリからの削除待ち  <br/> |Microsoft 365 Business Premiumから会社のデータを削除する準備が整っています。  <br/> |
|回収を実行中です  <br/> |Microsoft 365 Business Premium現在、デバイスから会社のデータを削除しています。  <br/> |
|インベントリからの削除失敗  <br/> | 会社データの削除アクションが失敗しました。  <br/> |
|取り消しを取り消す  <br/> |削除アクションが取り消されました。  <br/> |
|ワイプの保留中  <br/> |出荷時のリセットを開始するのを待っています。  <br/> |
|ワイプを実行中です  <br/> |出荷時のリセットが発行されました。  <br/> |
|ワイプ失敗  <br/> |出荷時のリセットが行えなかった。  <br/> |
|ワイプがキャンセルされました  <br/> |出荷時のワイプが取り消されました。  <br/> |
|異常  <br/> |アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインされません。  <br/> |
|削除の保留中  <br/> |削除アクションが保留中です。  <br/> |
|検出  <br/> |Microsoft 365 Business Premiumデバイスが検出されました。  <br/> |
   

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../security-and-compliance/secure-your-business-data.md)