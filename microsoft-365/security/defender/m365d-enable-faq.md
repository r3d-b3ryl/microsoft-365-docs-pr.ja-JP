---
title: Microsoft 365 Defender をオンにするときによく寄せられる質問
description: Microsoft 365 Defender の有効化に関連するライセンス、アクセス許可、初期設定、その他の製品およびサービスに関する最も一般的な質問に対する回答を取得する
keywords: よく寄せられる質問、FAQ、GCC、開始、有効にする Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933435"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 Defender をオンにするときによく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など [、Microsoft 365 Defender](microsoft-365-defender.md)の有効に関する最も一般的な質問に対する回答を読み取る。

サービスを有効にする方法については [、「Microsoft 365 Defender](m365d-enable.md)を有効にする」を参照してください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 ライセンスを持ってない。 Microsoft 365 Defender は引き続き使用できますか?

次の E5 以外のライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)
 
サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?

いいえ、Microsoft 365 Defender は、既に展開した Microsoft 365 セキュリティ サービスのデータを統合します。 オンにした後、インシデント、オートメーション、およびハンティング エクスペリエンスは、展開された製品の範囲内で動作し始めるでしょう。 これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示し、何も実行できません。

Microsoft 365 Defender エクスペリエンスを最適化するには、サポートされている[Microsoft 365](deploy-supported-services.md)セキュリティ製品とサービスを展開することをお勧めします。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender はどこで自分のデータを処理して保存しますか?
Microsoft 365 Defender は、統合データが処理および保存されるデータ センターに最適な場所を自動的に選択します。 Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用される場所と同じ場所が選択されます。

>[!NOTE]
>Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。 Microsoft 365 Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。 

データ センターの場所は、Microsoft 365 Defender の設定ページ (Microsoft 365 Defender の設定ページ) でサービスを準備する前>**表示されます**。 別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [ヘルプが必要か] を選択して、Microsoft サポートに問い合わせください。

## <a name="where-can-i-access-microsoft-365-defender"></a>Microsoft 365 Defender にアクセスできる場所

Microsoft 365 Defender は、Microsoft 365 セキュリティ センターで利用できます。 セキュリティ センターに移動するには、URL を参照します [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターで Microsoft 365 Defender にアクセスするには、どのようなアクセス許可が必要ですか?

次の Azure Active Directory (AD) ロールが割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

>[!NOTE]
>Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響を与える。 詳細については [、「Microsoft 365 Defender](m365d-permissions.md)へのアクセスの管理」を参照してください。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender の既定のタイム ゾーンは何ですか?
既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。 この設定を変更して、ローカル タイム ゾーンを使用できます。 [タイム ゾーンの設定の詳細](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Microsoft 365 Defender の新しい機能と UI の更新プログラムについて、どのように確認できますか?

Microsoft は、以下を含むさまざまなチャネルを通じて定期的に情報を提供しています。

- Microsoft [](../../admin/manage/message-center.md) 365 管理センターのメッセージ センター
- コンプライアンス 技術コミュニティ [の Microsoft 365 セキュリティ &ブログ投稿](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

プレビュー機能をオンにして、一般に公開されている最新のエクスペリエンス [を取得します](preview.md)。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender は米国政府機関コミュニティ クラウド (GCC) または GCC High で利用できますか?
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
