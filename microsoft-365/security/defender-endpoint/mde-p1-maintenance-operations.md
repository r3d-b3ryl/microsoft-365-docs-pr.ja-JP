---
title: Microsoft Defender for Endpoint Plan 1 の管理 (プレビュー)
description: Defender for Endpoint Plan 1 を維持および更新します。 設定を管理し、更新プログラムを取得し、誤検知/負に対処します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 09/13/2021
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 298f63a0df664cada6cf6d2a67a06770b66ea6ea
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194119"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1-preview"></a>Microsoft Defender for Endpoint Plan 1 の管理 (プレビュー)

> [!TIP]
> ユーザーまたは A3 Microsoft 365 E3が、Microsoft 365 E5 A5 を使用していない場合は、プレビュー プログラムに [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) サインアップしてください。

組織内で Defender for Endpoint Plan 1 (プレビュー) を使用する場合、セキュリティ チームはセキュリティ ソリューションを維持するために特定の手順を実行できます。 セキュリティ チームがメンテナンスと運用計画をまとめる場合は、少なくとも次のアクティビティを含める必要があります。

- [セキュリティ インテリジェンスと製品更新プログラムの管理](#manage-security-intelligence-and-product-updates)
- [エンドポイントの Defender の微調整と調整](#fine-tune-and-adjust-defender-for-endpoint)
- [誤検知/負のアドレス](#address-false-positivesnegatives)

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Defender for Endpoint Plan 1 (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

## <a name="manage-security-intelligence-and-product-updates"></a>セキュリティ インテリジェンスと製品更新プログラムの管理

新Microsoft Defender ウイルス対策攻撃の手法から保護するために、最新の状態を維持する必要があります。 Microsoft は、セキュリティ インテリジェンス、ウイルス対策、マルウェア対策保護の定期的な更新プログラムをリリースします。 更新プログラムは、次の 2 つのカテゴリに分類されます。 

- セキュリティ インテリジェンスの更新プログラム
- 製品の更新 

セキュリティ インテリジェンスと製品の更新プログラムを管理するには、「更新プログラムの管理Microsoft Defender ウイルス対策[ベースラインの適用」を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>エンドポイントの Defender の微調整と調整

Defender for Endpoint は、柔軟性と構成のオプションを提供します。 組織のニーズに合わせて設定を調整および調整できます。 たとえば、エンドポイントセキュリティ設定を管理Microsoft エンドポイント マネージャーグループ ポリシー、その他の方法を使用できます。 

詳細については、「Manage [Defender for Endpoint」を参照してください](manage-atp-post-migration.md)。

## <a name="address-false-positivesnegatives"></a>誤検知/負のアドレス

誤検知とは、ファイルやプロセスなどのアーティファクトであり、実際には脅威ではないにもかかわらず、悪意のあるものとして検出されました。 false negative は、実際には脅威として検出されていないエンティティです。 False positives/negatives は、Defender for Endpoint を含む任意のエンドポイント保護ソリューションで発生する可能性があります。 ただし、次の図に示す手順に従って、これらの種類の問題に対処し、ソリューションを微調整できます。

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="誤検知と負の処理の概要":::

Defender for Endpoint で誤検知/陰性が表示される場合は [、「Address false positives/negatives in Microsoft Defender for Endpoint」を参照してください](defender-endpoint-false-positives-negatives.md)。

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Endpoint の新機能を確認する](whats-new-in-microsoft-defender-atp.md)