---
title: MSSP に送信されるアラート通知を構成する
description: MSSP に送信されるアラート通知を構成する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 03d33f89ad4edc34ebc7aa6783442100c52fea87fd3681a0b752f521d40a9280
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857677"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>MSSP に送信されるアラート通知を構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>この手順は、MSSP カスタマーまたは MSSP によって実行できます。 MSSP のお客様に代わってこれを構成するための適切なアクセス許可を MSSP に付与する必要があります。

ポータルへのアクセスが許可されると、アラート通知ルールを作成して、テナントに関連付けられたアラートが作成され、条件が満たされた場合にメールが MSSP に送信されます。

 
詳細については、「アラート通知の [ルールを作成する」を参照してください](configure-email-notifications.md#create-rules-for-alert-notifications)。
 

次のチェック ボックスをオンにする必要があります。
- **[組織名を含** める] - 顧客名が電子メール通知に追加されます
- **[テナント固有のポータル リンクを含める** ] - アラート リンク URL には、ターゲット テナント ポータルに直接アクセスできるテナント固有のパラメーター (tid=target_tenant_id) が含まれます。


## <a name="related-topics"></a>関連トピック
- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
