---
title: デバイス状態
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: ビジネス向け Microsoft 365 の管理ホームのデバイス アクションの一覧では、さまざまなデバイスの状態について説明します。
ms.openlocfilehash: 8de91d71576bd9b6993583a0b30506431f9a02ac
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894950"
---
# <a name="device-states-in-microsoft-365-for-business"></a>一般法人向け Microsoft 365 のデバイスの状態

この記事は Microsoft 365 Business Premium に適用されます。

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

[ **デバイス アクション**] ([管理者のホーム] \> [ **デバイス アクション**]) の一覧にあるデバイスは、次のいずれかの状態になります。
  
![In the Device actions list, you can see the Devices states.](./../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**状態**|**説明**|
|:-----|:-----|
|Intune で管理  |Microsoft 365 Business Premium によって管理されます。  |
|インベントリからの削除待ち  |Microsoft 365 Business はデバイスから会社データを削除する準備をしています。  |
|回収を実行中です  |現在、Microsoft 365 Business はデバイスから会社データを削除しています。  |
|インベントリからの削除失敗  | 会社データの削除アクションが失敗しました。  |
|破棄がキャンセルされました。  |破棄アクションがキャンセルされました。  |
|ワイプの保留中  |出荷時のリセットを開始するのを待っています。  |
|ワイプを実行中です  |出荷時のリセットが発行されました。  |
|ワイプ失敗  |出荷時の設定へのリセットを実行できませんでした。  |
|ワイプが取り消されました  |出荷時のワイプがキャンセルされました。  |
|異常  |アクションは保留中 (または進行中) ですが、デバイスは 30 日以上チェックインしていません。  |
|削除の保留中  |削除アクションが保留中です。  |
|検出  |Microsoft 365 Business がデバイスを検出しました。  |
   

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)