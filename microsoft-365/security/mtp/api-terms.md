---
title: Microsoft 365 Defender API のライセンスと使用条件
description: Microsoft 365 Defender の API のライセンスと使用条件の説明
keywords: api, apis, ライセンス, 条項, api, 法律, 通知, 実施基準
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930956"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API のライセンスと使用条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>公式の用語

Microsoft 365 Defender API は、Microsoft API のライセンスと使用条件 [によって管理されます](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)。

## <a name="legal-notices"></a>法的通知

Microsoft およびすべての投稿者は、クリエイティブ Commons Attribution 4.0 International Public License の下にある Microsoft ドキュメントおよびこのリポジトリ内のその他のコンテンツに対するライセンスを付与します。 [](https://github.com/MicrosoftDocs/microsoft-365-docs) 詳細については [、LICENSE](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) ファイルを参照してください。

ドキュメントで参照されている Microsoft、Windows、Microsoft Azure、およびその他の Microsoft 製品およびサービスは、米国およびその他の国における Microsoft の商標または登録商標である場合があります。

このプロジェクトのライセンスは、Microsoft の名前、ロゴ、または商標を使用する権利を付与しません。 Microsoft の一般的な商標に関するガイドラインは [、Microsoft 商標に記載されています](https://go.microsoft.com/fwlink/?LinkID=254653)。

プライバシーに関する情報については [、Microsoft のプライバシーに関するサイトをご覧ください](https://privacy.microsoft.com)。

Microsoft および投稿者は、その他すべての権利を、意味、ストップスペル、その他の方法で、それぞれの著作権、特許、または商標の下で、すべて予約します。

## <a name="other-restrictions"></a>その他の制限

高度な検索 API[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations)には、返される結果の数と照会できるデータにいくつかの制限があります。

1. 過去 30 日間のデータのみをクエリできます。
1. 結果には、最大 100,000 行が含まれます。

### <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

Microsoft 365 Defender API には調整しきい値があります。

- **インシデント API**: 1 分あたり最大 50 回の呼び出し、または 1 時間あたり 1500 回の呼び出し。
- **高度な検索 API**: 1 分あたり最大 15 回の呼び出し、1 時間あたり 10 分の実行時間、1 日あたり 4 時間の実行時間。

調整を示す HTTP 応答状態コード `429` 。

要求が調整されている場合、応答本文には、要求を再び開始できる時間が示されます。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [サポートされている Microsoft 365 Defender API](api-supported.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)
