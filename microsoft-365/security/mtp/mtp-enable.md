---
title: Microsoft 365 セキュリティ センターで Microsoft Threat Protection を有効にする
description: Microsoft Threat Protection を有効にし、セキュリティ インシデントと応答の統合を開始する方法について説明します。
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
ms.openlocfilehash: 0badae0d81b52b89c47f950b889109d4b9d35dda
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844599"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft Threat Protection を有効にする

**適用対象:**
- Microsoft Threat Protection

[Microsoft の脅威保護](microsoft-threat-protection.md)は、Microsoft Defender Advanced Threat PROTECTION (ATP)、OFFICE 365 ATP、Microsoft Cloud App Security、および Azure ATP 全体で主要な機能を統合することによって、インシデント対応プロセスを統一します。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

必要なアクセス許可を持つ対象ユーザーが Microsoft 365 セキュリティセンターにアクセスすると、microsoft の脅威保護が自動的に有効になります。 この記事では、さまざまな前提条件と、Microsoft の脅威の保護をプロビジョニングする方法について説明します。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの利用資格と必要なアクセス許可を確認する
Microsoft 365 セキュリティ製品のライセンスでは、通常、追加のライセンス費用を必要とせずに microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用することができます。 マイクロソフトは、サポートされているすべてのサービスへのアクセスを提供する、Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンスまたはライセンスの有効な組み合わせを取得することをお勧めします。

ライセンスの詳細については、[ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。

### <a name="check-your-role"></a>役割を確認する
Microsoft の脅威保護を有効にするには、Azure Active Directory の**グローバル管理者**または**セキュリティ管理者**である必要があります。 [Azure AD でのロールの表示](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>サポートされるサービス
Microsoft の脅威保護は、既に展開したさまざまなサポートされているサービスからデータを集約します。 データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。 これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく実行されます。

最適な保護を実現し、Microsoft の脅威保護を最適化するには、ネットワークにすべての該当するサポートされているサービスを展開することをお勧めします。 詳細については、「[サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。

## <a name="before-starting-the-service"></a>サービスを開始する前に
サービスを有効にする前に、Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com)) で、[**インシデント**]、[**アクションセンター**]、または [ナビゲーション] ウィンドウから**探し**ているものを選択すると、[microsoft Threat Protection の設定] ページが表示されます。 これらのナビゲーション項目は、Microsoft の脅威保護を使用する資格がない場合は表示されません。

![Microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 セキュリティセンターの*microsoft threat protection 設定で microsoft threat protection が有効になっていない場合に表示される [microsoft threat protection の設定] ページの画像

## <a name="starting-the-service"></a>サービスを開始する
Microsoft の脅威保護を有効にするには、[ **microsoft の脅威保護を有効**にする] を選択して変更を適用します。 このオプションにアクセスするには、ナビゲーションウィンドウで [**設定**] ([security.microsoft.com/settings](https://security.microsoft.com/settings)) を選択してから、[ **microsoft Threat Protection**] を選択することもできます。

>[!NOTE]
>ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。

### <a name="data-center-location"></a>データセンターの場所
Microsoft の脅威保護は、 [Microsoft DEFENDER ATP で使用されて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)いるのと同じ場所にデータを保存して処理します。 Microsoft Defender ATP を使用していない場合は、アクティブな Microsoft 365 セキュリティサービスの場所に基づいて、新しいデータセンターの場所が自動的に選択されます。 選択したデータセンターの場所が画面に表示されます。

>[!NOTE]
>Microsoft 365 セキュリティセンターの microsoft サポートに連絡して、別のデータセンターの場所に Microsoft の脅威保護をプロビジョニングする方法については、[**ヘルプが必要ですか?** ] を選択します。 

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する
サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [自動化された調査と対応](mtp-autoir.md)を管理するアクション センター
- [高度な](advanced-hunting-overview.md)検索機能

![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと Microsoft の脅威保護機能のイメージ microsoft ](../../media/mtp-enable/mtp-on.png)
 *365 セキュリティセンターとインシデント管理およびその他の Microsoft の脅威保護機能*

### <a name="getting-azure-atp-data"></a>Azure ATP データを取得する
Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。 [この統合に関する詳細情報](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft Threat Protection を無効にする
Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。 選択解除**Microsoft の脅威保護を有効**にして変更を適用します。

対応する機能は、Microsoft 365 セキュリティセンターから削除されます。

## <a name="get-assistance"></a>サポートを利用する

Microsoft の脅威保護を有効にすることに関してよく寄せられる質問への回答を得るには、 [FAQ を参照](mtp-enable-faq.md)してください。

Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。 詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。 サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。

## <a name="related-topics"></a>関連項目

- [よく寄せられる質問](mtp-enable-faq.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされるサービスを展開する](deploy-supported-services.md)
- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [Microsoft Defender ATP の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP のデーター ストレージ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)