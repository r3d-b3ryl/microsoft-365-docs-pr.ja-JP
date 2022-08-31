---
title: Microsoft 365 Defenderを有効にする際によく寄せられる質問
description: ライセンス、アクセス許可、初期設定、およびMicrosoft 365 Defenderの有効化に関連するその他の製品やサービスに関してよく寄せられる質問への回答を取得します。
keywords: よく寄せられる質問, FAQ, GCC, get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55a5dbaf78ff19b9ef70d77493f7ac8568a0039d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483412"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 Defenderを有効にする際によく寄せられる質問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポート サービスの展開、初期設定など、[Microsoft 365 Defender](microsoft-365-defender.md)の有効化に関してよく寄せられる質問に対する回答をお読みください。

サービスを有効にする方法については、「[Microsoft 365 Defenderを有効にする」を参照](m365d-enable.md)してください。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 ライセンスがありません。 Microsoft 365 Defenderを引き続き使用できますか?

次の E5 以外のライセンスをお持ちのお客様は、Microsoft 365 Defenderを使用できます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Defender for Office 365 (プラン 2)

サポートされているライセンスの完全な一覧については、 [ライセンス要件を参照](prerequisites.md#licensing-requirements)してください。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defenderの使用を開始するには、何かをインストールまたはデプロイする必要がありますか?

いいえ。Microsoft 365 Defenderは、既にデプロイした Microsoft 365 セキュリティ サービスのデータを統合します。 これを有効にすると、インシデント、自動化、およびハンティング のエクスペリエンスが、デプロイされた製品の範囲内で動作し始めます。 これらの製品のいずれも適切にデプロイされていない場合、Microsoft 365 Defenderはデータを表示せず、何もアクションを実行できません。

Microsoft 365 Defenderエクスペリエンスを最適化するには、サポート *されているすべての* [Microsoft 365 セキュリティ製品とサービス](deploy-supported-services.md)を展開することをお勧めします。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>データの処理と保存Microsoft 365 Defender場所

Microsoft 365 Defender統合データが処理および格納されるデータ センターに最適な場所が自動的に選択されます。 Microsoft Defender for Endpointがある場合は、Defender for Endpoint で使用されているのと同じ場所が選択されます。

>[!NOTE]
>Microsoft Defender for Endpoint Microsoft Defender for Cloud を使用してオンにすると、欧州連合 (EU) データ センターで自動的にプロビジョニングされます。 Microsoft 365 Defenderは、この方法でMicrosoft Defender for Endpointをプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングされます。

データ センターの場所は、Microsoft 365 Defenderの設定ページ (**設定> Microsoft 365 Defender**) にサービスがプロビジョニングされる前と後に表示されます。 別のデータ センターの場所を使用する場合は、Microsoft 365 Defender ポータルで [**ヘルプが必要ですか?**] を選択して Microsoft サポートにお問い合わせください。

## <a name="where-can-i-access-microsoft-365-defender"></a>Microsoft 365 Defenderにアクセスできる場所

Microsoft 365 Defenderは次<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>の場合に使用できます。

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>Microsoft 365 Defenderにアクセスするには、どのようなアクセス許可が必要ですか?

次の Azure Active Directory (Azure AD) ロールが割り当てられたアカウントは、Microsoft 365 Defender機能とデータにアクセスできます。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者
- コンプライアンス管理者
- コンプライアンス データ管理者
- アプリケーション管理者
- クラウド アプリケーション管理者


> [!NOTE]
> Microsoft Defender for Endpoint でのロールベースのアクセス制御設定は、データへのアクセスに影響を与えます。 詳細については、「[Microsoft 365 Defender へのアクセスの管理](m365d-permissions.md)」をお読みください。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>既定Microsoft 365 Defenderタイム ゾーンは何ですか?

既定では、Microsoft 365 Defenderは UTC タイム ゾーンに時刻情報を表示します。 この設定は、ローカル タイム ゾーンを使用するように変更できます。 [タイム ゾーンの設定の詳細](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>新しいMicrosoft 365 Defender機能と UI 更新プログラムについて学習するにはどうすればよいですか?

Microsoft は、次のようなさまざまなチャネルを通じて定期的に情報を提供しています。

- Microsoft 365 管理センターの[メッセージ センター](../../admin/manage/message-center.md)
- [Microsoft 365 セキュリティ&コンプライアンス 技術コミュニティ](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)のブログ投稿

[プレビュー機能](preview.md)をオンにして、公開されている最新のエクスペリエンスを取得します。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft 365 Defenderをオンにします](m365d-enable.md)。
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
