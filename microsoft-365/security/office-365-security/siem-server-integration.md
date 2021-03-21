---
title: SIEM サーバーと Microsoft 365 サービスとアプリケーションの統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Microsoft 365 クラウド サービスとアプリケーションとのセキュリティ情報とイベント管理 (SIEM) サーバーの統合の概要を確認する
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21aaad71f40a01a3bea2f9535d1c3256ae667bae
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916588"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Microsoft 365 サービスおよびアプリケーションとのセキュリティ情報とイベント管理 (SIEM) サーバーの統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>要約

組織がセキュリティ情報とイベント管理 (SIEM) サーバーを使用または取得する計画を立てましたか? Microsoft 365 または Microsoft 365 と統合する方法Officeがあります。 この記事では、SIEM サーバーと Microsoft 365 サービスおよびアプリケーションを統合するために使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーがまだない場合で、オプションを検討している場合は **[、Microsoft Azure Sentinel を検討してください](/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーが必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの場所など、多くの要因によって異なります。 Microsoft 365 には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。 一部の組織では、SIEM サーバーの使用が必要な特別な状況があります。 次に例を示します。

- *Fabrikam には* 、オンプレミスのコンテンツとアプリケーションと、クラウド内の一部があります (ハイブリッド クラウド展開があります)。 Fabrikam は、すべてのコンテンツとアプリケーションのセキュリティ レポートを取得するために、SIEM サーバーを実装しました。

- *Contoso* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 ユーザーは、必要な追加のセキュリティ保護を利用するために、環境に SIEM サーバーを追加しました。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM サーバーと Microsoft 365 との統合

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからデータを受信できます。 次の表に、いくつかの Microsoft 365 サービスとアプリケーション、および SIEM サーバーの入力と詳細を確認するリソースを示します。

****

|Microsoft 365 サービスまたはアプリケーション|SIEM サーバーの入力/メソッド|追加情報|
|---|---|---|
|[Microsoft Defender for Office 365](office-365-atp.md)|監査ログ|[SIEM との Microsoft Defender との統合 (Office 365)](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/)|Azure でホストされる HTTPS エンドポイント <p> REST API|[SIEM ツールにアラートをプルする](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|ログの統合|[SIEM と Microsoft Cloud App Security の統合](/cloud-app-security/siem)|
|

> [!TIP]
> [Azure Sentinel を見てみろ](/azure/sentinel/overview)。 Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは「箱から出して」利用できます。リアルタイムの統合を実現します。 Azure Sentinel は、Microsoft 365 Defender ソリューションと Microsoft 365 サービス (Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security など) で使用できます。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要があります

SIEM サーバー統合を構成する前に、監査ログが有効になっていることを確認してください。

- SharePoint Online、OneDrive for Business、Azure Active Directory の場合は、セキュリティ コンプライアンス センターで監査ログ [&オンになります](../../compliance/turn-audit-log-search-on-or-off.md)。

- Exchange Online の場合は、「メールボックス監査 [の管理」を参照してください](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>その他のリソース

[Azure Defender にセキュリティ ソリューションを統合する](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](/graph/security-integration)