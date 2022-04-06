---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: a0651f0f0b104c243115dc86a72cf3e363bdb9a4
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635366"
---
# <a name="device-states"></a>デバイス状態

この記事は、ユーザーにMicrosoft 365 Business Premium。

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../security/defender-business/mdb-overview.md)。

[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状態**|**説明**|
|:-----|:-----|
|Intune で管理  |ユーザーによって管理Microsoft 365 Business Premium。  |
|インベントリからの削除待ち  |Microsoft 365 Business Premiumから会社のデータを削除する準備が整っています。  |
|回収を実行中です  |Microsoft 365 Business Premium現在、デバイスから会社のデータを削除しています。  |
|インベントリからの削除失敗  | 会社データの削除アクションが失敗しました。  |
|取り消しを取り消す  |削除アクションが取り消されました。  |
|ワイプの保留中  |出荷時のリセットを開始するのを待っています。  |
|ワイプを実行中です  |出荷時のリセットが発行されました。  |
|ワイプ失敗  |出荷時のリセットが行えなかった。  |
|ワイプがキャンセルされました  |出荷時のワイプが取り消されました。  |
|異常  |アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインされません。  |
|削除の保留中  |削除アクションが保留中です。  |
|検出  |Microsoft 365 Business Premiumデバイスが検出されました。  |
   

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)