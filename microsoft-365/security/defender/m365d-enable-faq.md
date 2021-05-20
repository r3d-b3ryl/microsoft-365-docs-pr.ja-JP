---
title: Defender をオンにするときによく寄せられるMicrosoft 365質問
description: ライセンス、アクセス許可、初期設定、および Defender の有効化に関連するその他の製品およびサービスに関する最も一般的な質問に対する回答をMicrosoft 365する
keywords: よく寄せられる質問、FAQ、GCC、開始、Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページの有効化
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572767"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Defender をオンにするときによく寄せられるMicrosoft 365質問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md)の有効に関する最も一般的な質問 (必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など) に対する回答を読み取る。

サービスを有効にする方法については、「Defender を有効にする」[をMicrosoft 365してください](m365d-enable.md)。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>ライセンスを持Microsoft 365 E5。 Defender で引き続きMicrosoft 365できますか?

次の E5 以外のライセンスをお持ちのお客様は、Defender Microsoft 365使用できます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)
 
サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Defender の使用を開始するには、何かをインストールまたは展開するMicrosoft 365ですか?

いいえ、Microsoft 365 Defender は、既に展開Microsoft 365サービスからのデータを統合します。 オンにした後、インシデント、オートメーション、およびハンティング エクスペリエンスは、展開された製品の範囲内で動作し始めるでしょう。 これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示し、何も実行できません。

Defender エクスペリエンスを最適化Microsoft 365、サポートされているセキュリティ製品とサービスMicrosoft 365[展開することをお勧めします](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Defender のプロセスMicrosoft 365保存する場所
Microsoft 365Defender は、統合データが処理および保存されるデータ センターの最適な場所を自動的に選択します。 Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用される場所と同じ場所が選択されます。

>[!NOTE]
>Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。 Microsoft 365Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。 

データ センターの場所は、サービスがプロビジョニングされる前と後に、Defender (Defender) の設定ページMicrosoft 365表示設定 > Microsoft 365 **されます**。 別のデータ センターの場所を使用する場合は、Microsoft サポートに問い合Microsoft 365セキュリティ センターで [ヘルプが必要か] を選択します。

## <a name="where-can-i-access-microsoft-365-defender"></a>Defender へのアクセス先Microsoft 365?

Microsoft 365Defender はセキュリティ センター Microsoft 365利用できます。 セキュリティ センターに移動するには、URL を参照します [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>セキュリティ センターで Defender にアクセスMicrosoft 365アクセスするにはMicrosoft 365必要がありますか?

次のアカウント (Azure Azure Active Directory) AD割り当てられたアカウントは、Defender のMicrosoft 365データにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

>[!NOTE]
>Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響を与える。 詳細については、「Defender へのアクセス[の管理」をMicrosoft 365してください](m365d-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Defender の既定のMicrosoft 365タイム ゾーンは何ですか?
既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。 この設定を変更して、ローカル タイム ゾーンを使用できます。 [タイム ゾーンの設定の詳細](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Defender 機能と UI の更新プログラムMicrosoft 365方法を学ぶには?

Microsoft は、以下を含むさまざまなチャネルを通じて定期的に情報を提供しています。

- 管理[センターの](../../admin/manage/message-center.md)Microsoft 365センター
- コンプライアンス 技術コミュニティMicrosoft 365[セキュリティ&ブログ投稿](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

プレビュー機能をオンにして、一般に公開されている最新のエクスペリエンス [を取得します](preview.md)。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>米国Microsoft 365 (Government Community Cloud) または GCC High で Defender をGCCか。
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft 365Defender の概要](microsoft-365-defender.md)
- [Defender を有効Microsoft 365します](m365d-enable.md)。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
