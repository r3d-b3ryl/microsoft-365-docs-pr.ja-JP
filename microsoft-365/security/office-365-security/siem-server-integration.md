---
title: SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: この記事では、SIEM server と Microsoft 365 との統合の概要について説明します。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677510"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合

## <a name="summary"></a>Summary

組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用している場合、または SIEM サーバーを近いうちに購入する予定の場合は、Microsoft 365 または Office 365 との統合について不思議に思うかもしれません。 この記事では、Microsoft 365 サービスとアプリケーションとの SIEM サーバー統合のセットアップに使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーは必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。 Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。 組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。 次に例を示します。

- *Fabrikam*には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。 すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。 

- *Contoso 社*は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server と Microsoft 365 の統合

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。 次の表に、SIEM サーバーの入力と共に Microsoft 365 サービスとアプリケーションをいくつかと、SIEM サーバー統合の詳細を理解するためのリソースを示します。 

| Microsoft 365 サービスまたはアプリケーション | SIEM サーバーの入力 | 追加情報 |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | 監査ログ | [Office 365 Advanced Threat Protection との SIEM の統合](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Azure でホストされている HTTPS エンドポイント <br/>REST API| [SIEM ツールに通知を取得する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | ログの統合 | [SIEM と Microsoft Cloud App Security との統合](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> 「 [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)」に目を通してください。これには、microsoft のソリューションのためのさまざまなコネクタが用意されており、Microsoft の脅威保護ソリューションや microsoft の365ソース (Office 365、azure AD、azure ATP、Microsoft Cloud App Security など) を含むリアルタイム統合が提供されています。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。 

- SharePoint Online、OneDrive for Business、および Azure Active Directory で[は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)ています。

- Exchange Online で[は、Windows PowerShell を使用して監査ログを有効に](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)します。
 
## <a name="additional-resources"></a>その他の技術情報

[Azure セキュリティセンターでのセキュリティソリューションの統合](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](https://docs.microsoft.com/graph/security-integration)