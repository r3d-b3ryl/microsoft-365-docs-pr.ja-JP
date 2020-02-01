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
ms.openlocfilehash: a85680e323c7a8fba6f2d74d5cc00c58c2013d23
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662053"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft Threat Protection を有効にする

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection は、Microsoft Defender Advanced Threat Protection (ATP)、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP の主要機能を統合することで、インシデント対応プロセスを統合します。 この統合されたエクスペリエンスにより、Microsoft 365 セキュリティ センターでアクセスできる強力な機能が追加されました。

## <a name="check-license-eligibility-and-required-permissions"></a>ライセンスの利用資格と必要なアクセス許可を確認する
Microsoft 365 E5、Microsoft 365 E5 セキュリティ、またはそれと同等のライセンスの組み合わせを使用しているお客様は、Microsoft の脅威保護を使用できます。 詳細については、[ライセンス要件を参照してください](prerequisites.md#licensing-requirements)。

Microsoft の脅威保護を有効にするには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)の**グローバル管理者**または**セキュリティ管理者**である必要があります。

## <a name="start-using-the-service"></a>サービスの使用を開始する
Microsoft の脅威保護は、さまざまな統合サービスからのデータを集約します。 データを一元的に処理および保存して、新しい洞察を識別し、集中管理された応答ワークフローを実現できるようにします。

サービスを有効にする前に、Microsoft 365 セキュリティセンター ([security.microsoft.com](https://security.microsoft.com)) では、ナビゲーションウィンドウの [**インシデント**] および [**アクションセンター** ] オプションが表示されません。

![Microsoft 365 セキュリティセンターのナビゲーションウィンドウのイメージ microsoft の脅威保護](../images/mtp-off.png)
機能のない microsoft*365 セキュリティセンターと microsoft の脅威保護がオフになっている*

Microsoft の脅威保護を有効にするには、ナビゲーションウィンドウで [**設定**] を選択します。 [**[設定] ページ](https://security.microsoft.com/settings)** で、[ **Microsoft Threat Protection** > **オプトイン/オプトアウト**] に移動します。

>[!NOTE]
>ナビゲーションウィンドウに**設定**が表示されない場合や、ページにアクセスできなかった場合は、アクセス許可とライセンスを確認してください。

### <a name="select-data-center-location"></a>データセンターの場所を選択する
Microsoft Defender ATP が組織にプロビジョニングされている場合、データは、[Microsoft Defender ATP データ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)用に選択した同じデータ センターの場所に保存および処理されます。 Microsoft Defender ATP がない場合は、Microsoft Threat Protection 専用の新しいデータ センターの場所を選択するよう求められます。 

サービス間でデータを共有し、集約する前に、同意を得る必要があります。

### <a name="confirm-that-the-service-is-on"></a>サービスが有効になっていることを確認する
サービスがプロビジョニングされると、次の機能が追加されます。

- [イベント管理](incidents-overview.md)
- [自動化された調査と対応](mtp-autoir.md)を管理するアクション センター
- 既存の [**捜索**] ページへの[高度な捜索](advanced-hunting-overview.md)機能

![Microsoft 365 セキュリティセンターのナビゲーションウィンドウと microsoft の脅威保護機能](../images/mtp-on.png)
のイメージ microsoft*365 セキュリティセンターとインシデント管理およびその他の microsoft の脅威保護機能*

### <a name="getting-azure-atp-data"></a>Azure ATP データを取得する
Azure ATP データを Microsoft Threat Protection と共有するには、Microsoft Cloud App Security と Azure ATP の統合を有効にします。 [この統合に関する詳細情報](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft Threat Protection を無効にする
Microsoft Threat Protection を使用しない場合、Microsoft 365 セキュリティ センターの [**設定**]  >  [**Microsoft Threat Protection**]  >  [**オプトイン/オプトアウト**] の順に移動します。 [**Microsoft Threat Protection を有効にする**] の選択を解除し、変更を保存します。

データは完全に削除され、対応する機能は Microsoft 365 セキュリティセンターから削除されます。

## <a name="get-assistance"></a>サポートを利用する

Microsoft サポートスタッフは、テナントのサービスおよび関連するリソースのプロビジョニングまたはプロビジョニング解除に役立ちます。 詳細については、「Microsoft 365 セキュリティセンターで**ヘルプが必要ですか?** 」を参照してください。 サポートに連絡するときは、「Microsoft Threat Protection」をお伝えください。

## <a name="related-topics"></a>関連項目

- [Microsoft Threat Protection の概要](microsoft-threat-protection.md)
- [ライセンス要件およびその他の前提条件](prerequisites.md)
- [Microsoft Defender ATP の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP の概要](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security の概要](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP の概要](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP のデーター ストレージ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
