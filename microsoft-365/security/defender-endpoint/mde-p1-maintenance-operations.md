---
title: Microsoft Defender for Endpointプラン 1 の管理
description: Defender for Endpoint プラン 1 を維持および更新します。 設定を管理し、更新プログラムを取得し、誤検知/否定に対処します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 417dd33eed846e45453464e63ff403374ce224dc
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667408"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1"></a>Microsoft Defender for Endpointプラン 1 の管理

**適用対象**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

組織内で Defender for Endpoint Plan 1 を使用すると、セキュリティ チームはセキュリティ ソリューションを維持するために特定の手順を実行できます。 セキュリティ チームがメンテナンスと運用計画をまとめるので、少なくとも次のアクティビティを含める必要があります。

- [セキュリティ インテリジェンスと製品の更新プログラムを管理する](#manage-security-intelligence-and-product-updates)
- [Defender for Endpoint の微調整と調整](#fine-tune-and-adjust-defender-for-endpoint)
- [false positives/negatives に対処する](#address-false-positivesnegatives)

## <a name="manage-security-intelligence-and-product-updates"></a>セキュリティ インテリジェンスと製品の更新プログラムを管理する

Microsoft Defender ウイルス対策を最新の状態に保つことは、新しいマルウェアや攻撃手法から保護するために不可欠です。 Microsoft では、セキュリティ インテリジェンス、ウイルス対策、マルウェア対策の保護に関する定期的な更新プログラムをリリースしています。 更新プログラムは、次の 2 つのカテゴリに分類されます。 

- セキュリティ インテリジェンスの更新プログラム
- 製品の更新プログラム 

セキュリティ インテリジェンスと製品の更新プログラムを管理するには、「[Microsoft Defender ウイルス対策更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>Defender for Endpoint の微調整と調整

Defender for Endpoint には、柔軟性と構成オプションが多数用意されています。 組織のニーズに合わせて設定を調整し、微調整できます。 たとえば、Microsoft エンドポイント マネージャー、グループ ポリシー、その他の方法を使用して、エンドポイントのセキュリティ設定を管理できます。 

詳細については、「 [Defender for Endpoint の管理」を参照してください](manage-mde-post-migration.md)。

## <a name="address-false-positivesnegatives"></a>false positives/negatives に対処する

偽陽性は、ファイルやプロセスなどのアーティファクトであり、実際には脅威ではないにもかかわらず、悪意のあるものとして検出されました。 偽陰性は、実際には脅威として検出されなかったエンティティです。 Defender for Endpoint を含むすべてのエンドポイント保護ソリューションで、偽陽性/陰性が発生する可能性があります。 ただし、次の図に示すように、このような問題に対処し、ソリューションを微調整するための手順があります。

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="False positives と negatives プロセスの概要" lightbox="../../media/defender-endpoint/false-positives-overview.png":::

Defender for Endpoint に誤検知/陰性が表示される場合は、「[Microsoft Defender for Endpointで誤検知/否定に対処する](defender-endpoint-false-positives-negatives.md)」を参照してください。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpointの新機能を確認する](whats-new-in-microsoft-defender-endpoint.md)