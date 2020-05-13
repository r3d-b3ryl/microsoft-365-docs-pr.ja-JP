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
ms.openlocfilehash: 9a57929e42f08db8abda170c889441d3a50ade72
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209249"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft Threat Protection を有効にする

**適用対象:**
- Microsoft Threat Protection

Microsoft Threat Protection は、Microsoft Defender Advanced Threat Protection (ATP)、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP の主要機能を統合することで、インシデント対応プロセスを統合します。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

最適な保護を実現し、Microsoft の脅威保護を最適化するには、ネットワークにすべての該当するサポートされているサービスを展開することをお勧めします。 詳細については、「[サポートされるサービスの展開について](deploy-supported-services.md)」を参照してください。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの利用資格と必要なアクセス許可を確認する
Microsoft 365 E5、E5 セキュリティ、A5、または A5 セキュリティライセンス、あるいはライセンスの有効な組み合わせによって、サポートされているサービスへのアクセスが可能になり、ライセンス料を追加することなく microsoft 365 セキュリティセンターで Microsoft の脅威保護を使用できるようになります。

ライセンスの詳細については、[ライセンス要件を参照して](prerequisites.md#licensing-requirements)ください。

### <a name="check-your-role"></a>役割を確認する
Microsoft の脅威保護を有効にするには、Azure Active Directory の**グローバル管理者**または**セキュリティ管理者**である必要があります。 [Azure AD でのロールの表示](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>サービスの使用を開始する

>[!IMPORTANT]
>2020年5月12日から、Microsoft は、[ライセンス要件](prerequisites.md#licensing-requirements)に関して最適化された新しいエクスペリエンスを徐々にロールアウトし、Microsoft の脅威保護を有効にします。 この期間中、一部のお客様は、ポータルエクスペリエンスへの変更を確認し始めます。 この記事では、新しいエクスペリエンスに関する情報を**新しいエクスペリエンス**としてマークしています。

Microsoft の脅威保護は、さまざまな統合サービスからのデータを集約します。 データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。 これは、統合サービスに関連付けられている既存の展開、設定、またはデータに影響を与えることなく実行されます。

サービスを有効にする前に、「Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com))」では、[**インシデント**]、[**アクションセンター**]、または**Hunting** [ナビゲーション] ウィンドウから選択したときに microsoft Threat Protection のウェルカムページが表示されます。 これらのナビゲーションオプションは、Microsoft の脅威保護を使用する資格がない場合は表示されません。

![Microsoft 365 セキュリティセンターの microsoft threat protection の ](../../media/mtp-welcome.png)
 *ウェルカムページ*に microsoft threat protection が有効になっていない場合に表示される、microsoft threat protection のウェルカムページの画像

Microsoft の脅威保護を有効にするには、単にウェルカムページからプロセスを完了します。 ナビゲーションウィンドウで [**設定**] ([security.microsoft.com/settings](https://security.microsoft.com/settings)) にアクセスし、[ **microsoft threat protection**] を選択することによって、microsoft の脅威保護を有効にすることもできます。

>[!NOTE]
>ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。

### <a name="select-data-center-location"></a>データセンターの場所を選択する
Microsoft Defender ATP が組織にプロビジョニングされている場合、データは、[Microsoft Defender ATP データ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)用に選択した同じデータ センターの場所に保存および処理されます。 Microsoft Defender ATP がない場合は、Microsoft Threat Protection 専用の新しいデータ センターの場所を選択するよう求められます。 
 
サービス間でデータを共有し、集約する前に、同意を得る必要があります。

**新しい作業:** 2020年5月12日から、ユーザーはこの操作に対する変更を段階的に受け取ります。 新しい環境では、このサービスによって、既存の Microsoft 365 セキュリティサービスに基づいて、集計データに最適なデータセンターの場所が自動的に選択されます。 選択したデータセンターの場所が画面に表示されます。

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する
サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [自動化された調査と対応](mtp-autoir.md)を管理するアクション センター
- [高度な](advanced-hunting-overview.md)検索機能

![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと Microsoft の脅威保護機能のイメージ microsoft ](../../media/mtp-on.png)
 *365 セキュリティセンターとインシデント管理およびその他の Microsoft の脅威保護機能*

### <a name="getting-azure-atp-data"></a>Azure ATP データを取得する
Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。 [この統合に関する詳細情報](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft Threat Protection を無効にする
Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。 [**Microsoft Threat Protection を有効にする**] の選択を解除し、変更を保存します。

対応する機能は、Microsoft 365 セキュリティセンターから削除されます。

## <a name="get-assistance"></a>サポートを利用する

Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。 詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。 サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。

## <a name="related-topics"></a>関連項目

- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [サポートされるサービスを展開する](deploy-supported-services.md)
- [Microsoft Defender ATP の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP のデーター ストレージ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)