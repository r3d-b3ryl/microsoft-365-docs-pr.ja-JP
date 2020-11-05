---
title: SIEM server と Microsoft 365 のサービスおよびアプリケーションの統合
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
- seo-marvel-apr2020
description: Microsoft 365 クラウドサービスおよびアプリケーションとのセキュリティ情報およびイベント管理 (SIEM) サーバーの統合の概要を理解する
ms.openlocfilehash: 17e21d19463187744afe855b2304ac71956545d2
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919766"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 のサービスおよびアプリケーションとの統合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>要約

組織は、セキュリティ情報およびイベント管理 (SIEM) サーバーの取得を使用または計画していますか。 Microsoft 365 または Office 365 との統合について疑問があるかもしれません。 この記事では、SIEM サーバーと Microsoft 365 のサービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーがまだなく、オプションを調査している場合は、 **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)** を検討してください。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーは必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの格納場所など、さまざまな要因によって異なります。 Microsoft 365 には、SIEM サーバーのような追加のサーバーを使用せずに、多くの組織のセキュリティニーズに合ったさまざまなセキュリティ機能が含まれています。 組織によっては、SIEM サーバーの使用を必要とする特別な状況があります。 次に、いくつかの例を示します:

- *Fabrikam* には、オンプレミスのコンテンツとアプリケーションがあります。クラウドには、ハイブリッドクラウド展開があります。 すべてのコンテンツとアプリケーションでセキュリティレポートを取得するために、Fabrikam は SIEM サーバーを実装しています。

- *Contoso 社* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 SIEM サーバーを環境に追加して、必要な追加のセキュリティ保護を利用しています。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM server と Microsoft 365 の統合

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからのデータを受信できます。 次の表に、SIEM server のサービスとアプリケーションと、詳細について説明するリソースを365示します。

****

|Microsoft 365 サービスまたはアプリケーション|SIEM サーバーの入力/メソッド|追加情報|
|---|---|---|
|[Microsoft Defender for Office 365](office-365-atp.md)|監査ログ|[Office 365 用の Microsoft Defender との SIEM の統合](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)|Azure でホストされている HTTPS エンドポイント <br/>REST API|[SIEM ツールに通知を取得する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|ログの統合|[SIEM と Microsoft Cloud App Security との統合](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)を見てみましょう。 Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは、"すぐに使用可能" となり、リアルタイム統合のために提供されます。 Azure Sentinel は、Microsoft 365 Defender ソリューションおよび Microsoft 365 サービスで使用できます。これには、Office 365、Azure AD、Id の Microsoft Defender、Microsoft Cloud App Security などが含まれます。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバーの統合を構成する前に、監査ログが有効になっていることを確認してください。

- SharePoint Online、OneDrive for Business、および Azure Active Directory で [は、セキュリティ & コンプライアンスセンターで監査ログが有効になっ](../../compliance/turn-audit-log-search-on-or-off.md)ています。

- Exchange Online の場合は、「 [メールボックスの監査を管理](../../compliance/enable-mailbox-auditing.md)する」を参照してください。

## <a name="more-resources"></a>その他のリソース

[Azure Defender でセキュリティソリューションを統合する](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](https://docs.microsoft.com/graph/security-integration)
