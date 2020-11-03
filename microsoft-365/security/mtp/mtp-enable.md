---
title: Microsoft 365 セキュリティセンターで Microsoft 365 Defender をオンにする
description: Microsoft 365 Defender を有効にし、セキュリティインシデントと応答の統合を開始する方法について説明します。
keywords: 作業の開始、MTP の有効化、Microsoft Threat Protection、M365、セキュリティ、データの場所、必要なアクセス許可、ライセンスの資格情報のページ
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843638"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender をオンにする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) では、エンドポイントの microsoft defender、microsoft Defender for Office 365、Microsoft Cloud App Security、および id の microsoft defender で主要な機能を統合することにより、インシデント対応プロセスを統一しています。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

Microsoft 365 Defender は、必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティセンターにアクセスしたときに自動的にオンになります。 この記事を読むと、さまざまな前提条件と、Microsoft 365 Defender のプロビジョニング方法を理解できます。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの利用資格と必要なアクセス許可を確認する
Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンス費用を必要とせずに microsoft 365 セキュリティセンターの Microsoft 365 Defender を使用することができます。 マイクロソフトは、サポートされているすべてのサービスへのアクセスを提供する、Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンスまたはライセンスの有効な組み合わせを取得することをお勧めします。

ライセンスの詳細については、 [ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。

### <a name="check-your-role"></a>役割を確認する
Microsoft 365 Defender を有効にするには、Azure Active Directory の **グローバル管理者** または **セキュリティ管理者** である必要があります。 [Azure AD でのロールの表示](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>サポートされるサービス
Microsoft 365 Defender は、既に展開したさまざまなサポートされているサービスからデータを集約します。 データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。 これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく実行されます。

最適な保護を得るために、Microsoft 365 Defender を最適化するには、ネットワーク上に該当するすべてのサポートされているサービスを展開することをお勧めします。 詳細については、「 [サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。

## <a name="before-starting-the-service"></a>サービスを開始する前に
サービスを有効にする前に、Microsoft 365 セキュリティセンター ( [security.microsoft.com](https://security.microsoft.com)) で、[ **インシデント** ]、[ **アクションセンター** ]、または [ナビゲーション] ウィンドウから **探し** ているものを選択すると、[microsoft 365 Defender 設定] ページが表示されます。 これらのナビゲーション項目は、Microsoft 365 Defender を使用する資格がない場合は表示されません。

![Microsoft 365 Defender が microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 セキュリティセンターの Microsoft 365 defender 設定* で有効になっていない場合に表示される microsoft 365 defender 設定ページのイメージ

## <a name="starting-the-service"></a>サービスを開始する
Microsoft 365 Defender をオンにするには、[ **microsoft 365 defender をオン** にする] を選択して変更を適用します。 このオプションにアクセスするには、ナビゲーションウィンドウで [ **設定** ] ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択してから、[ **microsoft 365 Defender** ] を選択する方法もあります。

>[!NOTE]
>ナビゲーションウィンドウに **設定** が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。

### <a name="data-center-location"></a>データセンターの場所
Microsoft 365 Defender は、 [エンドポイントとして Microsoft Defender で使用されて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)いるのと同じ場所にデータを格納し、処理します。 エンドポイントに Microsoft Defender がインストールされていない場合は、アクティブな Microsoft 365 セキュリティサービスの場所に基づいて、新しいデータセンターの場所が自動的に選択されます。 選択したデータセンターの場所が画面に表示されます。 

Microsoft 365 セキュリティセンターの microsoft サポートに連絡して、異なるデータセンターの場所に Microsoft 365 Defender をプロビジョニングする方法については、[ **ヘルプが必要ですか?** ] を選択します。 

>[!NOTE]
>エンドポイントの Microsoft Defender は、Azure Defender * を使用してオンにした場合に、欧州連合 (EU) のデータセンターで自動的にプロビジョニングされます。 Microsoft 365 Defender は、この方法でエンドポイント用の Defender をプロビジョニングしたお客様に対して、同じ EU データセンターで自動的にプロビジョニングを行います。 

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する
サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [自動化された調査と対応](mtp-autoir.md)を管理するアクション センター
- [高度な](advanced-hunting-overview.md) 検索機能

![Microsoft 365 セキュリティセンターのナビゲーションウィンドウのイメージ Microsoft 365 Defender 機能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 セキュリティセンターとインシデント管理およびその他の Microsoft 365 Defender 機能*

### <a name="getting-microsoft-defender-for-identity-data"></a>Id データの Microsoft Defender を取得する
Microsoft 365 Defender を使用して Id データの Microsoft Defender を共有するには、Id 統合のための microsoft Cloud App Security と Microsoft Defender が有効になっていることを確認してください。 [この統合に関する詳細情報](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Microsoft 365 Defender をオフにする
Microsoft 365 defender の使用を停止するには、microsoft 365 セキュリティセンターの [ **設定** ] の [microsoft  >  **365 Defender**  >  **オプトイン/オプトアウト** ] に移動します。 選択解除 **Microsoft 365 Defender をオンに** して、変更を適用します。

対応する機能は、Microsoft 365 セキュリティセンターから削除されます。

## <a name="get-assistance"></a>サポートを利用する

Microsoft 365 Defender を有効にする方法に関してよく寄せられる質問への回答を得るには、 [FAQ を参照](mtp-enable-faq.md)してください。

Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。 詳細については、「Microsoft 365 セキュリティセンターで **ヘルプが必要ですか?** 」を参照してください。 サポートに連絡する際は、Microsoft 365 Defender にお問い合わせください。

## <a name="related-topics"></a>関連項目

- [よく寄せられる質問](mtp-enable-faq.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされるサービスを展開する](deploy-supported-services.md)
- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [エンドポイントの Microsoft Defender の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 の Defender の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Id の Microsoft Defender の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [エンドポイントのデータストレージの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
