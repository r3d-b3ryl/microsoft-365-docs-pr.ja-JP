---
title: MSSP に送信されるアラート通知を構成する
description: MSSP に送信されるアラート通知を構成する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0cead78048fcf8ef25637e969aae816b7a8d8e76
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217484"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>MSSP に送信されるアラート通知を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> この手順は、MSSP のお客様または MSSP によって行うことができます。 MSSP のお客様に代わってこれを構成するための適切なアクセス許可を MSSP に付与する必要があります。

ポータルへのアクセスが許可されたら、アラート通知ルールを作成して、テナントに関連付けられたアラートが作成され、条件が満たされたときに電子メールが MSSP に送信されるようにすることができます。

詳細については、「 [アラート通知のルールを作成する」を参照してください](configure-email-notifications.md#create-rules-for-alert-notifications)。

次のチェック ボックスをオンにする必要があります。

- **組織名を含める** - 顧客名が電子メール通知に追加されます
- **テナント固有のポータル リンクを含める** - アラート リンク URL には、ターゲット テナント ポータルへの直接アクセスを許可するテナント固有のパラメーター (tid=target_tenant_id) が含まれます

## <a name="related-topics"></a>関連項目

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
