---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender を有効にする
description: Microsoft 365 Defender を有効にして、セキュリティ インシデントと対応の統合を開始する方法について説明します。
keywords: 開始する、Microsoft 365 Defender、Microsoft 365 Defender、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの適格性、設定ページを有効にする
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
ms.openlocfilehash: 2d69ae70b137c9e5378958721f7f9958e57c0306
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935643"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity を統合することで、インシデント対応プロセスを統合します。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティ センターにアクセスすると、Microsoft 365 Defender が自動的にオンになります。 この記事では、さまざまな前提条件と Microsoft 365 Defender のプロビジョニング方法について説明します。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの適格性と必要なアクセス許可を確認する

Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンスコストなしで Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用できます。 Microsoft 365 E5、E5 Security、A5、または A5 セキュリティ ライセンス、またはサポートされているサービスへのアクセスを提供するライセンスの有効な組み合わせを取得することをお勧めします。

ライセンスの詳細については、「ライセンス [要件」を参照してください](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>役割を確認する

Microsoft 365 Defenderを有効 **にするには**、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。 [Azure AD でロールを表示AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>サポートされているサービス

Microsoft 365 Defender は、既に展開したさまざまなサポートされているサービスのデータを集計します。 データを一元的に処理して保存し、新しい分析情報を特定し、一元的な応答ワークフローを可能にします。 これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく行います。

Microsoft 365 Defender の最適な保護と最適化を行う場合は、該当するサポート対象のすべてのサービスをネットワークに展開することをお勧めします。 詳細については、「サポート [されているサービスの展開」を参照してください](deploy-supported-services.md)。

## <a name="onboard-to-the-service"></a>サービスにオンボードする
Microsoft 365 Defender へのオンボーディングは簡単です。 ナビゲーション メニューから、[エンドポイント] セクションの下のアイテム (インシデント、ハンティング、アクション センター、脅威分析など) を選択してオンボーディング プロセスを開始します。 

### <a name="data-center-location"></a>データ センターの場所

Microsoft 365 Defender は、Microsoft Defender for Endpoint で使用されるのと同じ場所にデータを格納 [して処理します](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 Microsoft Defender for Endpoint を使用しない場合は、アクティブな Microsoft 365 セキュリティ サービスの場所に基づいて、新しいデータ センターの場所が自動的に選択されます。 選択したデータ センターの場所が画面に表示されます。

Microsoft  365 セキュリティ センターで [ヘルプが必要ですか] を選択して、Microsoft 365 Defender を別のデータ センターの場所にプロビジョニングする方法について Microsoft サポートに問い合わせします。

> [!NOTE]
> Microsoft Defender for Endpoint は、Azure Defender を使用してオンにした場合、EU (EU) データ センターで自動的にプロビジョニングします。 Microsoft 365 Defender は、この方法で Defender for Endpoint をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する

サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [アラート キュー](investigate-alerts.md)
- [自動化された調査と対応](m365d-autoir.md)を管理するアクション センター
- [高度なハンティング](advanced-hunting-overview.md) 機能
- 脅威の分析

![Microsoft 365 Defender を備えた Microsoft 365 セキュリティ センター ナビゲーション ウィンドウのイメージインシデント管理などの Microsoft 365 Defender 機能を備えた ](../../media/overview-incident.png)
 *Microsoft 365* セキュリティ センター

### <a name="getting-microsoft-defender-for-identity-data"></a>Id データの Microsoft Defender の取得 
Microsoft Cloud App Security との統合を有効にするには、少なくとも 1 回は Microsoft Cloud App Security にログインする必要があります。

## <a name="get-assistance"></a>サポートを利用する

Microsoft 365 Defender のオンに関する最も一般的な質問に対する回答を取得するには、FAQ [を参照してください](m365d-enable-faq.md)。

Microsoft サポート スタッフは、テナントのサービスおよび関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。 サポートについては、Microsoft 365 **セキュリティ** センターで [ヘルプが必要か] を選択します。 サポートに連絡する場合は、Microsoft 365 Defender について説明します。

## <a name="related-topics"></a>関連項目

- [よく寄せられる質問](m365d-enable-faq.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [Microsoft 365 Defender の概要](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint の概要](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365 の概要](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security の概要](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity の概要](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint data storage](../defender-endpoint/data-storage-privacy.md)
