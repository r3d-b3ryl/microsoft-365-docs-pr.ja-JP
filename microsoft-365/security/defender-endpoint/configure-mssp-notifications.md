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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166055"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>MSSP に送信されるアラート通知を構成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>この手順は、MSSP カスタマーまたは MSSP によって実行できます。 MSSP のお客様に代わってこれを構成するための適切なアクセス許可を MSSP に付与する必要があります。

ポータルへのアクセスが許可されると、アラート通知ルールを作成して、テナントに関連付けられたアラートが作成され、条件が満たされた場合にメールが MSSP に送信されます。

 
詳細については、「アラート通知の [ルールを作成する」を参照してください](configure-email-notifications.md#create-rules-for-alert-notifications)。
 

次のチェック ボックスをオンにする必要があります。
- **[組織名を含** める] - 顧客名が電子メール通知に追加されます
- **[テナント固有のポータル リンクを含める** ] - アラート リンク URL には、ターゲット テナント ポータルに直接アクセスできるテナント固有のパラメーター (tid=target_tenant_id) が含まれます。


## <a name="related-topics"></a>関連項目
- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
