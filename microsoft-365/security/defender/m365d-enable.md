---
title: Microsoft 365 Defender を有効にする
description: Microsoft 365 Defenderを有効にして、セキュリティ インシデントと対応の統合を開始する方法について説明します。
keywords: get started, enable Microsoft 365 Defender, Microsoft 365 Defender, M365, security, data location, required permissions, license eligibility, settings page
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
ms.collection:
- M365-security-compliance
- m365solution-getstarted
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0fa1a47bb5a4a09c22649866bb6c5c6039dc2850
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895033"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md)、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、およびMicrosoft Defender for Cloud Apps、およびMicrosoft Defender for Identity。 この統合エクスペリエンスにより、Microsoft 365 Defender ポータルでアクセスできる強力な機能が追加されます。

Microsoft 365 Defenderは、必要なアクセス許可を持つ対象顧客がポータルMicrosoft 365 Defenderアクセスしたときに自動的にオンになります。 この記事では、さまざまな前提条件とMicrosoft 365 Defenderのプロビジョニング方法について説明します。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの資格と必要なアクセス許可を確認する

Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンス コストなしでMicrosoft 365 Defenderを使用する権利があります。 Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティ ライセンス、またはサポートされているすべてのサービスへのアクセスを提供する有効なライセンスの組み合わせを取得することをお勧めします。

ライセンス情報に関する詳細については、[ライセンス要件をお読みください](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>ロールを確認する

Microsoft 365 Defenderを有効にするには、次のいずれかのロールである必要があります。

- グローバル管理者
- セキュリティ管理者
- セキュリティ オペレーター
- グローバル閲覧者
- セキュリティ閲覧者
- コンプライアンス管理者
- コンプライアンス データ管理者
- アプリケーション管理者
- クラウド アプリケーション管理者

[Azure AD でロールを表示する](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>サポートされているサービス

Microsoft 365 Defender は、ユーザーがすでに展開しているさまざまなサポート対象のサービスからデータを集約します。 データは一元的に処理および保存され、新しい分析情報が特定され、一元化された応答ワークフローが可能になります。 これは、既存の展開、設定、統合されたサービスに関連するデータに影響を与えることなく実行されます。

最適な保護を取得し、Microsoft 365 Defenderを最適化するために、ネットワークに適用可能なすべてのサポートされているサービスをデプロイすることをお勧めします。 詳細については、 [サポートされているサービスのデプロイに関するページを参照](deploy-supported-services.md)してください。

## <a name="onboard-to-the-service"></a>サービスにオンボードする
Microsoft 365 Defenderへのオンボードは簡単です。 ナビゲーション メニューから、 **インシデント&アラート**、 **ハンティング**、 **アクション センター**、 **脅威分析** など、任意の項目を選択してオンボード プロセスを開始します。 

### <a name="data-center-location"></a>データ センターの場所

Microsoft 365 Defenderは、[Microsoft Defender for Endpointが使用するのと同じ場所](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)にデータを格納して処理します。 Microsoft Defender for Endpointがない場合は、アクティブな Microsoft 365 セキュリティ サービスの場所に基づいて、新しいデータ センターの場所が自動的に選択されます。 選択したデータ センターの場所が画面に表示されます。

Microsoft 365 Defender ポータルで [**ヘルプが必要ですか?**] を選択して、別のデータ センターの場所でのMicrosoft 365 Defenderのプロビジョニングに関する Microsoft サポートにお問い合わせください。

> [!NOTE]
> 以前は、Microsoft Defender for Cloud を使用してオンにすると、Microsoft Defender for Endpoint欧州連合 (EU) データ センターで自動的にプロビジョニングされました。 Microsoft 365 Defenderは、過去にこの方法で Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングされます。

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する

サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [アラート キュー](investigate-alerts.md)
- [自動化された調査と対応](m365d-autoir.md)を管理するアクション センター
- [高度なハンティング](advanced-hunting-overview.md) 機能
- 脅威の分析

:::image type="content" source="../../media/overview-incident.png" alt-text="Microsoft 365 Defender機能を備えたMicrosoft 365 Defender ポータルのナビゲーション ウィンドウ" lightbox="../../media/overview-incident.png":::
*インシデント管理やその他の機能を備えたMicrosoft 365 Defender ポータル*

### <a name="getting-microsoft-defender-for-identity-data"></a>Microsoft Defender for Identity データの取得 
Microsoft Defender for Cloud Appsとの統合を有効にするには、少なくとも 1 回Microsoft Defender for Cloud Appsにログインする必要があります。

## <a name="get-assistance"></a>サポートを利用する

Microsoft 365 Defenderを有効にする方法についてよく寄せられる質問に対する回答については、[FAQ を参照してください](m365d-enable-faq.md)。

Microsoft サポート スタッフは、テナント上のサービスと関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。 サポートについては、Microsoft 365 Defender ポータルで [**ヘルプが必要ですか?** ] を選択します。 サポートにお問い合わせの際は、Microsoft 365 Defenderに言及してください。

## <a name="related-topics"></a>関連項目

- [よく寄せられる質問](m365d-enable-faq.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft Defender for Endpointの概要](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365の概要](../office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps の概要](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identityの概要](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpointデータ ストレージ](../defender-endpoint/data-storage-privacy.md)
