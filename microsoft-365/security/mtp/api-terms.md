---
title: Microsoft 365 Defender API のライセンスと使用条件
description: Microsoft 365 Defender での API のライセンスと使用条件の説明
keywords: api、apis、ライセンス、条項、API、法律、通知、行動規範
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
ms.openlocfilehash: 06926bc58f29fcf80d09819545e2455813f27a5f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922164"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Defender API のライセンスと使用条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="official-terms"></a>公式の用語

Microsoft 365 Defender API は、Microsoft API ライセンスと使用条件 [によって管理されます](/legal/microsoft-apis/terms-of-use)。

## <a name="legal-notices"></a>法的通知

Microsoft および任意の投稿者は、このリポジトリ内の Microsoft ドキュメントおよび[](https://github.com/MicrosoftDocs/microsoft-365-docs)他のコンテンツに対して、クリエイティブ コモンズアトリビューション 4.0 国際公開ライセンスの下でライセンスを付与します。 詳細については、「LICENSE ファイル」 [を参照](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) してください。

Microsoft、Windows、Microsoft Azure、および/またはドキュメントで参照されているその他の Microsoft 製品およびサービスは、米国およびその他の国における Microsoft の商標または登録商標です。

このプロジェクトのライセンスは、Microsoft の名前、ロゴ、または商標を使用する権利を付与しません。 Microsoft の一般的な商標ガイドラインは [、Microsoft の商標に記載されています](https://go.microsoft.com/fwlink/?LinkID=254653)。

プライバシーに関する情報は [、Microsoft のプライバシー で確認できます](https://privacy.microsoft.com)。

Microsoft および投稿者は、それぞれの著作権、特許、または商標の下で、意味、estoppel、その他の方法で、その他すべての権利を有します。

## <a name="other-restrictions"></a>その他の制限

高度な検索 API[](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations)には、返される結果の数とクエリ可能なデータにいくつかの制限があります。

1. クエリを実行できるのは、過去 30 日間のデータのみです。
1. 結果には、最大 100,000 行が含まれます。

### <a name="quotas-and-resource-allocation"></a>クォータとリソース割り当て

Microsoft 365 Defender API には調整しきい値があります。

- **インシデント API**: 1 分あたり最大 50 回の呼び出し、または 1 時間あたり 1500 回の呼び出し。
- **高度なハンティング API**: 1 分あたり最大 15 回の通話、1 時間あたり 10 分の実行時間、1 日あたり 4 時間の実行時間。

調整を示す HTTP 応答状態コードはです `429` 。

要求が調整されている場合、応答本文には、要求を再度開始できる時刻が示されます。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [サポートされている Microsoft 365 Defender API](api-supported.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)