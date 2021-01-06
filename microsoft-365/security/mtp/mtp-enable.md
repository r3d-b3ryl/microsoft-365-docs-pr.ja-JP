---
title: Microsoft 365 セキュリティ センターで Microsoft 365 Defender を有効にする
description: Microsoft 365 Defender を有効にして、セキュリティ インシデントと対応の統合を開始する方法について説明します。
keywords: 開始, MTP を有効にする, Microsoft Threat Protection, M365, セキュリティ, データの場所, 必要なアクセス許可, ライセンスの利用資格, 設定ページ
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
ms.openlocfilehash: b052f70c1b618adef12c4f70c2b3fe55741697d5
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760508"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) は、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity を統合することで、インシデント対応プロセスを統合します。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティ センターにアクセスすると、Microsoft 365 Defender が自動的にオンになります。 この記事では、さまざまな前提条件と Microsoft 365 Defender のプロビジョニング方法について説明します。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの利用資格と必要なアクセス許可を確認する

Microsoft 365 セキュリティ製品のライセンスは、通常、追加のライセンス コストなしで Microsoft 365 セキュリティ センターで Microsoft 365 Defender を使用することができます。 Microsoft 365 E5、E5 Security、A5、または A5 Security ライセンスを取得するか、サポートされているサービスへのアクセスを提供するライセンスの有効な組み合わせを取得することをお勧めします。

ライセンスの詳細については、ライセンス [要件を参照してください](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>ロールを確認する

Microsoft 365 Defenderを **有効** にする場合は、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。 [Azure AD でロールを表示する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>サポートされているサービス

Microsoft 365 Defender は、既に展開済みのサポートされているさまざまなサービスからデータを集約します。 データを一元的に処理して保存し、新しい分析情報を特定し、一元的な応答ワークフローを可能にします。 これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく行います。

最適な保護を得て Microsoft 365 Defender を最適化するには、該当するサポート対象のすべてのサービスをネットワークに展開することをお勧めします。 詳細については、サポート [されているサービスの展開に関する記事を参照してください](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>サービスを開始する前に

サービスを有効にする前に、ナビゲーション ウィンドウから [インシデント]、[アクション センター]、または [ハンティング] を選択すると、Microsoft 365 セキュリティセンター[(security.microsoft.com)](https://security.microsoft.com)に Microsoft 365 Defender 設定ページが表示されます。  Microsoft 365 Defender を使用できない場合、これらのナビゲーション項目は表示されません。

![Microsoft 365 セキュリティ センターで Microsoft 365 Defender が Microsoft 365 Defender 設定をオンにしていない場合に表示される ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender* 設定ページの画像

## <a name="starting-the-service"></a>サービスの開始

Microsoft 365 Defender を有効にする場合は **、Microsoft 365 Defender** をオンにし、変更を適用します。 このオプションにアクセスするには、ナビゲーション ウィンドウで [ **設定(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択し **、Microsoft 365 Defender** を選択します。

> [!NOTE]
> ナビゲーション ウィンドウに [設定] **が表示** されていない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認します。

### <a name="data-center-location"></a>データ センターの場所

Microsoft 365 Defender は、Microsoft Defender for Endpoint と同じ場所に [データを保存して処理します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 Microsoft Defender for Endpoint をお持ちない場合は、アクティブな Microsoft 365 セキュリティ サービスの場所に基づいて、新しいデータ センターの場所が自動的に選択されます。 選択したデータ センターの場所が画面に表示されます。

Microsoft  365 セキュリティ センターで[ヘルプが必要ですか?] を選び、Microsoft サポートに連絡して、別のデータ センターの場所で Microsoft 365 Defender をプロビジョニングします。

> [!NOTE]
> Microsoft Defender for Endpoint は、Azure Defender を通じて有効になっている場合、欧州連合 (EU) データ センターで自動的にプロビジョニングします。 Microsoft 365 Defender は、この方法でエンドポイント用 Defender をプロビジョニングしたお客様に対して、同じ EU データ センターで自動的にプロビジョニングします。

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する

サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [自動化された調査と対応](mtp-autoir.md)を管理するアクション センター
- [高度な検索](advanced-hunting-overview.md) 機能

![インシデント管理などの Microsoft 365 Defender 機能を備えた Microsoft 365 Defender の Microsoft 365 セキュリティ センター機能を備えた ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365* セキュリティ センター ナビゲーション ウィンドウの画像

### <a name="getting-microsoft-defender-for-identity-data"></a>Id データ用の Microsoft Defender の取得

Id データ用の Microsoft Defender を Microsoft 365 Defender と共有するには、Microsoft Cloud App Security と Id 統合のための Microsoft Defender がオンになっていることを確認します。 [この統合について詳しくは、次のリンクを参照してください](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="get-assistance"></a>サポートを利用する

Microsoft 365 Defender をオンに関してよく寄せられる質問に対する回答については [、FAQ をお読みください](mtp-enable-faq.md)。

Microsoft サポート スタッフは、テナントのサービスと関連リソースのプロビジョニングまたはプロビジョニング解除を支援できます。 サポートが必要な場合 **は、Microsoft** 365 セキュリティ センターで [サポートが必要ですか? ] を選択します。 サポートに問い合わせがある場合は、Microsoft 365 Defender に言及してください。

## <a name="related-topics"></a>関連項目

- [よく寄せられる質問](mtp-enable-faq.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされているサービスを展開する](deploy-supported-services.md)
- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Defender for Office 365 の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Id 用 Microsoft Defender の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint データ ストレージ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
