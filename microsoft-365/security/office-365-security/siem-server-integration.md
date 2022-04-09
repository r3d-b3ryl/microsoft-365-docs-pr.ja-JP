---
title: SIEM サーバーとMicrosoft 365サービスとアプリケーションの統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: セキュリティ情報とイベント管理 (SIEM) サーバーとMicrosoft 365クラウド サービスとアプリケーションの統合の概要を確認する
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 978319cca91322c7eb737d89cbfc167574f14093
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731419"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報とイベント管理 (SIEM) サーバーとMicrosoft 365サービスとアプリケーションの統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>概要

組織は、セキュリティ情報とイベント管理 (SIEM) サーバーを使用しているか、または取得する予定ですか? Microsoft 365またはOffice 365と統合する方法を疑問に思うかもしれません。 この記事では、SIEM サーバーとMicrosoft 365サービスとアプリケーションを統合するために使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーがまだない場合で、オプションを検討している場合は、 **[Microsoft Sentinel](/azure/sentinel/overview)** を検討してください。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーは必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの場所など、さまざまな要因によって異なります。 Microsoft 365には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。 一部の組織には、SIEM サーバーの使用が必要な特別な状況があります。 次に、いくつかの例を示します:

- *Fabrikam* には、一部のコンテンツとアプリケーションがオンプレミスにあり、一部はクラウド内にあります (ハイブリッド クラウドデプロイがあります)。 すべてのコンテンツとアプリケーションでセキュリティ レポートを取得するために、Fabrikam は SIEM サーバーを実装しました。
- *Contoso* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 環境に SIEM サーバーを追加して、必要な追加のセキュリティ保護を利用しました。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM サーバーとMicrosoft 365の統合

SIEM サーバーは、さまざまなMicrosoft 365サービスとアプリケーションからデータを受信できます。 次の表に、複数のMicrosoft 365 サービスとアプリケーション、SIEM サーバーの入力とリソースの一覧を示します。

<br/><br/>

|Microsoft 365 サービスまたはアプリケーション|SIEM サーバーの入力/メソッド|追加情報|
|---|---|---|
|[Microsoft Defender for Office 365](defender-for-office-365.md)|監査ログ|[SIEM と Microsoft Defender for Office 365の統合](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/)|Azure でホストされる HTTPS エンドポイント <p> REST API|[SIEM ツールにアラートをプルする](../defender-endpoint/configure-siem.md)|
|[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)|ログ統合|[SIEM と Microsoft Defender for Cloud Appsの統合](/cloud-app-security/siem)|

> [!TIP]
> [Microsoft Sentinel](/azure/sentinel/overview) を見てみましょう。 Microsoft Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは"すぐに使用できる" ので、リアルタイムの統合が可能です。 Office 365、Azure AD、Microsoft Defender for Identityなど、Microsoft 365 Defender ソリューションとMicrosoft 365 サービスで Microsoft Sentinel を使用できます。Microsoft Defender for Cloud Appsなど。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバー統合を構成する前に、監査ログがオンになっていることを確認してください。

- SharePoint Online、OneDrive for Business、Azure Active Directoryについては、「[監査を有効または無効にする」を](../../compliance/turn-audit-log-search-on-or-off.md)参照してください。
- Exchange Onlineについては、「[メールボックス監査の管理](../../compliance/enable-mailbox-auditing.md)」を参照してください。

## <a name="more-resources"></a>その他のリソース

[Microsoft Defender for Cloudでセキュリティ ソリューションを統合する](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](/graph/security-integration)
