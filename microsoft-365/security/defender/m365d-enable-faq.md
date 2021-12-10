---
title: ユーザー設定をオンにするときによく寄せられる質問Microsoft 365 Defender
description: ライセンス、アクセス許可、初期設定、およびライセンスの有効化に関連するその他の製品およびサービスに関する最も一般的な質問に対する回答をMicrosoft 365 Defender
keywords: よく寄せられる質問、FAQ、GCC、開始、Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページの有効化
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e5ed41f400c24a2522ea49f2524d0fe629bdbb9f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374756"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>ユーザー設定をオンにするときによく寄せられる質問Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

必要なライセンスとアクセス許可、サポート サービスの展開、初期設定[など](microsoft-365-defender.md)、Microsoft 365 Defender の有効に関する最も一般的な質問に対する回答を読み取る。

サービスを有効にする方法については、「サービスを有効にする」[を参照Microsoft 365 Defender。](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>ライセンスを持Microsoft 365 E5。 引き続き使用Microsoft 365 Defender?

次の E5 以外のライセンスをお持ちのお客様は、次のMicrosoft 365 Defender。

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Defender for Office 365 (プラン 2)

サポートされているライセンスの完全な一覧については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>アプリケーションの使用を開始するには、何かをインストールまたは展開するMicrosoft 365 Defender。

いいえ、Microsoft 365 Defender既に展開Microsoft 365サービスからデータを統合します。 オンにした後、インシデント、オートメーション、およびハンティング エクスペリエンスは、展開された製品の範囲内で動作し始めるでしょう。 これらの製品が適切に展開されていない場合、Microsoft 365 Defenderはデータを表示し、何も実行できません。

ユーザー エクスペリエンスを最適化Microsoft 365 Defender、サポートされているセキュリティ製品とサービスMicrosoft 365[展開することをお勧めします](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>データをMicrosoft 365 Defender保存する場所

Microsoft 365 Defenderデータが処理および保存されるデータ センターに最適な場所が自動的に選択されます。 Microsoft Defender for Endpoint を使用している場合は、Defender for Endpoint で使用される場所と同じ場所が選択されます。

>[!NOTE]
>Microsoft Defender for Cloud を使用してオンにすると、Microsoft Defender for Endpoint が欧州連合 (EU) データ センターで自動的にプロビジョニングされます。 Microsoft 365 Defender、この方法で Microsoft Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングされます。

データ センターの場所は、サービスがプロビジョニングされる前と後に、[データ センターの設定] ページに表示Microsoft 365 Defender **(** 設定 > Microsoft 365 Defender)。 別のデータ センターの場所を使用する場合は、Microsoft サポートに問い合わせMicrosoft 365 Defenderポータルで [ヘルプが必要か] を選択します。

## <a name="where-can-i-access-microsoft-365-defender"></a>アクセスできる場所Microsoft 365 Defender?

Microsoft 365 Defenderは次の場所で利用できます <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> 。

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>ユーザーにアクセスするために必要なアクセス許可Microsoft 365 Defender。

次の役割 (Azure Active Directory) Azure AD割り当てられたアカウントは、Microsoft 365 Defender機能とデータにアクセスできます。

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

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>既定で使用Microsoft 365 Defenderタイム ゾーンは何ですか?

既定では、Microsoft 365 Defenderタイム ゾーンに時刻情報が表示されます。 この設定を変更して、ローカル タイム ゾーンを使用できます。 [タイム ゾーンの設定の詳細](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>新しい機能と UI の更新Microsoft 365 Defenderを確認する方法

Microsoft は、以下を含むさまざまなチャネルを通じて定期的に情報を提供しています。

- メッセージ[センター](../../admin/manage/message-center.md) (Microsoft 365 管理センター
- コンプライアンス 技術コミュニティMicrosoft 365[セキュリティ&ブログ投稿](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

プレビュー機能をオンにして、一般に公開されている最新のエクスペリエンス [を取得します](preview.md)。

## <a name="related-topics"></a>関連項目

- [Microsoft 365 Defender概要](microsoft-365-defender.md)
- [[設定] をオンMicrosoft 365 Defender。](m365d-enable.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [プレビュー機能を有効にする](preview.md)
