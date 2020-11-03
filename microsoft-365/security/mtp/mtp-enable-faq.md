---
title: Microsoft 365 Defender をオンにする際によく寄せられる質問
description: Microsoft 365 Defender を有効にするためのライセンス、アクセス許可、初期設定、その他の製品およびサービスに関してよく寄せられる質問への回答を取得します。
keywords: よく寄せられる質問、FAQ、GCC、作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンス資格情報、設定ページ
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842418"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 Defender をオンにする際によく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポートサービスの展開、初期設定など、 [Microsoft 365 Defender](microsoft-threat-protection.md)の有効化に関してよく寄せられる質問に対する回答を確認します。

サービスを有効にする方法については、「 [Microsoft 365 Defender を有効](mtp-enable.md)にする」を参照してください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 ライセンスがありません。 Microsoft 365 Defender を引き続き使用できますか?

次の E5 以外のライセンスを持つお客様は、Microsoft 365 Defender を使用できます。

- Microsoft Defender for Endpoint
- Id の Microsoft Defender
- Microsoft Cloud App Security
- Office 365 の Defender (プラン 2)
 
サポートされているライセンスの完全な一覧については、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defender の使用を開始するには、何をインストールまたは展開する必要がありますか?

いいえ。 Microsoft 365 Defender は、既に展開されている Microsoft 365 セキュリティサービスからのデータを統合します。 オンにすると、インシデント、自動化、および検索のエクスペリエンスは、展開された製品の範囲内で動作し始めます。 これらの製品のいずれも適切に展開されていない場合、Microsoft 365 Defender はデータを一切表示せず、操作を行うこともできません。

Microsoft 365 Defender エクスペリエンスを最適化するために、サポートされている *すべて* の [microsoft 365 セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender でのデータの処理と保存場所
Microsoft 365 Defender は、統合データを処理および保存するデータセンターの最適な場所を自動的に選択します。 エンドポイントに Microsoft Defender がある場合は、エンドポイントとして Defender で使用されているものと同じ場所を選択します。

>[!NOTE]
>エンドポイントの Microsoft Defender は、Azure Defender * を使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。 Microsoft 365 Defender は、この方法でエンドポイントとして Microsoft Defender をプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングを行います。 

データセンターの場所は、Microsoft 365 Defender の [設定] ページでサービスが準備される前と後に表示されます ( **設定 > microsoft 365 defender** )。 別のデータセンターの場所を使用する場合は、microsoft 365 セキュリティセンターの microsoft サポートに問い合わせて、[ **ヘルプが必要ですか?** ] を選択します。

## <a name="where-can-i-access-microsoft-365-defender"></a>Microsoft 365 Defender にはどこにアクセスできますか?

Microsoft 365 Defender は、Microsoft 365 セキュリティセンターで利用できます。 セキュリティセンターに移動するには、URL を参照し [https://security.microsoft.com](https://security.microsoft.com) ます。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターの Microsoft 365 Defender にアクセスするために必要なアクセス許可はどのようなものですか?

次の Azure Active Directory (AD) の役割が割り当てられているアカウントは、Microsoft 365 Defender の機能とデータにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者

>[!NOTE]
>エンドポイント用の Microsoft Defender の役割ベースのアクセス制御の設定は、データへのアクセスに影響します。 詳細については、「 [Microsoft 365 Defender へのアクセスの管理](mtp-permissions.md)について」を参照してください。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender の既定のタイムゾーンは何ですか。
既定では、Microsoft 365 Defender は UTC タイムゾーンで時間情報を表示します。 この設定を変更して、ローカルタイムゾーンを使用することができます。 [タイムゾーンの設定について](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Microsoft 365 Defender の新機能と UI の更新の詳細についてはどうすればよいですか?

Microsoft では、次のようなさまざまなチャネルで情報を定期的に提供しています。

- Microsoft 365 管理センターの[メッセージセンター](../../admin/manage/message-center.md)
- [Microsoft 365 security & コンプライアンスの技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)におけるブログ投稿

[プレビュー機能](preview.md)を有効にして、一般公開されている最新のエクスペリエンスを取得できます。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender は米国政府機関向けコミュニティクラウド (GCC) または GCC 高で利用できますか?
現時点では、使用できません。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender をオンに](mtp-enable.md)します。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされるサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
