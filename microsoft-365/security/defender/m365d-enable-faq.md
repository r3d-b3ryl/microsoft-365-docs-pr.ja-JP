---
title: ディフェンダーをオンにする際によくある質問Microsoft 365
description: ライセンス、アクセス許可、初期設定、およびMicrosoft 365 Defender の有効化に関連するその他の製品やサービスに関する最も一般的な質問への回答を得る
keywords: よく寄せられる質問, FAQ, GCC, 開始, Microsoft 365ディフェンダーを有効にします, Microsoft 365 ディフェンダー, M365, セキュリティ, データの場所, 必要な権限, ライセンスの適格性, 設定ページ
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
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>ディフェンダーをオンにする際によくある質問Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など、最も一般的な質問に対する回答[をMicrosoft 365 Defender](microsoft-365-defender.md)に関する質問を参照してください。

サービスを有効にする方法については[、「defender を有効にする」Microsoft 365参照](m365d-enable.md)してください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>私はMicrosoft 365 E5ライセンスを持っていません。 ディフェンダー Microsoft 365使用できますか?

次の非 E5 ライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)
 
サポートされているライセンスの完全なリストについては、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?

いいえ、Microsoft 365 Defender は、既に展開されているセキュリティ サービスMicrosoft 365データを統合します。 電源を入れると、インシデント、自動化、および狩猟のエクスペリエンスが、デプロイされた製品の範囲内で作業を開始します。 これらの製品がいずれも適切に展開されていない場合、Microsoft 365 Defender はデータを表示せず、何も操作を実行できません。

Microsoft 365 Defender のエクスペリエンスを最適化するために *、サポートされているすべての*[Microsoft 365セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365ディフェンダーはどこでデータを処理して保存しますか?
Microsoft 365Defender は、統合データが処理され、保存されるデータセンターに最適な場所を自動的に選択します。 エンドポイントの Microsoft Defender がある場合は、エンドポイントの Defender で使用されるのと同じ場所が選択されます。

>[!NOTE]
>エンドポイントのマイクロソフトディフェンダーは、Azure Defender を使用してオンにすると、欧州連合 (EU) のデータ センターで自動的にプロビジョニングされます。 Microsoft 365Defender は、この方法でエンドポイント用の Microsoft Defender をプロビジョニングした顧客に対して、同じ EU データ センターで自動的にプロビジョニングされます。 

データセンターの場所は、サービスがプロビジョニングされる前と後に、Microsoft 365 Defender ( 設定 > Microsoft 365 **Defender**) の設定ページに表示されます。 別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [**ヘルプが必要ですか?**

## <a name="where-can-i-access-microsoft-365-defender"></a>ディフェンダー Microsoft 365どこでアクセスできますか?

Microsoft 365保護機能はMicrosoft 365セキュリティ センターで利用できます。 セキュリティ センターに移動するには、 URL を参照 [https://security.microsoft.com](https://security.microsoft.com) します。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>セキュリティ センターの Microsoft 365 Defender にアクセスするには、どのようなアクセス許可Microsoft 365必要がありますか?

次の Azure Active Directory (Azure AD) ロールが割り当てられたアカウントは、Microsoft 365 Defender 機能とデータにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

>[!NOTE]
>エンドポイントの Microsoft Defender のロール ベースのアクセス制御設定は、データへのアクセスに影響を与えます。 詳細については、「 defender Microsoft 365[へのアクセスの管理](m365d-permissions.md)について」を参照してください。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>ディフェンダーのデフォルトのタイムゾーンMicrosoft 365?
既定では、Microsoft 365 Defender は UTC タイム ゾーンに時刻情報を表示します。 この設定を変更して、ローカル タイム ゾーンを使用できます。 [タイムゾーンの設定の詳細](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>新しいMicrosoft 365 Defender 機能と UI の更新について学習するにはどうすればよいですか?

マイクロソフトは、次のチャネルを通じて定期的に情報を提供しています。

- 管理[センターのメッセージ センター](../../admin/manage/message-center.md) Microsoft 365
- [Microsoft 365セキュリティ&コンプライアンス技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)のブログ記事

[プレビュー機能](preview.md)を有効にして、最新の公開エクスペリエンスを取得する 。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365ディフェンダーは米国Government Community Cloud(GCC)またはGCCハイで利用可能ですか?
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft 365ディフェンダーの概要](microsoft-365-defender.md)
- [Microsoft 365ディフェンダーをオンに](m365d-enable.md)します。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
