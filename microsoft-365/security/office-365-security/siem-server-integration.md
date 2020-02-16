---
title: " セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Microsoft 365 クラウドサービスおよびアプリケーションとのセキュリティ情報およびイベント管理 (SIEM) サーバーの統合の概要を理解する
ms.openlocfilehash: d5adf0a72ac78475cb47f06732375ce01c0d72be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082196"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合

## <a name="summary"></a>概要

組織は、セキュリティ情報およびイベント管理 (SIEM) サーバーの取得を使用または計画していますか。 Microsoft 365 または Office 365 との統合について疑問があるかもしれません。 この記事では、SIEM サーバーと Microsoft 365 のサービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーは必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。 Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。 組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。 次に例を示します。

- *Fabrikam*には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。 すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。 

- *Contoso 社*は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server と Microsoft 365 の統合

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。 次の表に、SIEM server のサービスとアプリケーションと、詳細について説明するリソースを365示します。 

| Microsoft 365 サービスまたはアプリケーション | SIEM サーバーの入力/メソッド | 追加情報 |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | 監査ログ | [Office 365 Advanced Threat Protection との SIEM の統合](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Azure でホストされている HTTPS エンドポイント <br/>REST API| [SIEM ツールに通知を取得する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | ログの統合 | [SIEM と Microsoft Cloud App Security との統合](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)を見てみましょう。 Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは、"すぐに使用可能" となり、リアルタイム統合のために提供されます。 Microsoft の脅威保護ソリューションおよび Microsoft 365 サービスでは、Office 365、Azure AD、Azure ATP、Microsoft Cloud App Security などを含む Azure Sentinel を使用できます。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。 

- SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。

- Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。
 
## <a name="more-resources"></a>その他のリソース

[Azure セキュリティセンターでのセキュリティソリューションの統合](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](https://docs.microsoft.com/graph/security-integration)
