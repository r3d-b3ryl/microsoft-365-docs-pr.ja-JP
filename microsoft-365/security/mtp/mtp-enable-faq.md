---
title: Microsoft 365 Defender をオンにするときによく寄せられる質問
description: ライセンス、アクセス許可、初期設定、Microsoft 365 Defender の有効化に関連するその他の製品とサービスに関してよく質問される質問に対する回答を提供します。
keywords: よく寄せられる質問, FAQ, GCC, 開始, MTP の有効化, Microsoft Threat Protection, M365, セキュリティ, データの場所, 必要なアクセス許可, ライセンスの利用資格, 設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930188"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 Defender をオンにするときによく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など [、Microsoft 365 Defender](microsoft-threat-protection.md)のオンに関してよく尋ねらた質問に対する回答をお読みください。

サービスを有効にする方法については [、「Microsoft 365 Defender](mtp-enable.md)を有効にする」をご覧ください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 ライセンスを持ってない。 Microsoft 365 Defender を引き続き使用できますか?

次の E5 以外のライセンスをお持ちのお客様は、Microsoft 365 Defender を使用できます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)
 
サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defender の使用を開始するには、何かをインストールまたは展開する必要がありますか?

いいえ。Microsoft 365 Defender は、展開済みの Microsoft 365 セキュリティ サービスからのデータを統合します。 この機能を有効にした後は、インシデント、自動化、および検索のエクスペリエンスが展開された製品の範囲内で動作し始めるでしょう。 これらの製品が適切に展開されていない場合、Microsoft 365 Defender はデータを表示しません。また、何も実行できません。

Microsoft 365 Defender のエクスペリエンスを最適化するには、サポートされている[Microsoft 365](deploy-supported-services.md)セキュリティ製品とサービスを展開することをお勧めします。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender はどこでデータを処理して保存しますか?
Microsoft 365 Defender は、統合データが処理および保存されるデータ センターの最適な場所を自動的に選択します。 Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用されているのと同じ場所が選択されます。

>[!NOTE]
>Microsoft Defender for Endpoint は、Azure Defender を通じて有効になっている場合、欧州連合 (EU) データ センターで自動的にプロビジョニングします。 Microsoft 365 Defender は、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。 

データ センターの場所は、サービスがプロビジョニングされる前と後に、Microsoft 365 Defender の設定ページに表示されます **(Microsoft 365 Defender**>設定)。 別のデータ センターの場所を使用する場合は、Microsoft 365 セキュリティ センターで [サポートが必要ですか? ] を選択して、Microsoft サポートにお問い合わせください。

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
>Microsoft Defender for Endpoint の役割ベースのアクセス制御設定は、データへのアクセスに影響します。 詳細については [、Microsoft 365 Defender へのアクセスの管理に関する記事を参照してください](mtp-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender は既定でどのタイム ゾーンに設定されていますか?
既定では、Microsoft 365 Defender は UTC タイム ゾーンで時刻情報を表示します。 この設定は、ローカル タイム ゾーンを使用するために変更できます。 [タイム ゾーンの設定について](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Microsoft 365 Defender の新しい機能と UI の更新プログラムについて知る方法

Microsoft は、次に示すさまざまなチャネルを通じて定期的に情報を提供しています。

- Microsoft [](../../admin/manage/message-center.md) 365 管理センターのメッセージ センター
- [Microsoft 365 セキュリティ/コンプライアンス 技術コミュニティ&ブログ記事](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

プレビュー機能をオンにして、最新の一般公開エクスペリエンス [を取得します](preview.md)。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender は、米国政府機関向けコミュニティ クラウド (GCC) または GCC High で利用できますか?
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender を有効にする](mtp-enable.md)。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
