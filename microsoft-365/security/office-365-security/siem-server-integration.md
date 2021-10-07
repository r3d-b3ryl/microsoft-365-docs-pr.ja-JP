---
title: SIEM サーバーとサービスMicrosoft 365アプリケーションとの統合
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
description: セキュリティ情報とイベント管理 (SIEM) サーバーとクラウド サービスとアプリケーションMicrosoft 365概要を確認する
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71fff15b1493f6e8e15becbd87ad55947c8eddc4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169421"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報とイベント管理 (SIEM) サーバーとサービスMicrosoft 365アプリケーションとの統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>要約

組織がセキュリティ情報とイベント管理 (SIEM) サーバーを使用または取得する計画を立てましたか? どのように統合されるか疑問に思うMicrosoft 365またはOffice 365。 この記事では、SIEM サーバーとサービスおよびアプリケーションを統合するために使用できるリソースMicrosoft 365示します。

> [!TIP]
> SIEM サーバーがまだない場合で、オプションを検討している場合は **[、Sentinel Microsoft Azure検討してください](/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーが必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの場所など、多くの要因によって異なります。 Microsoft 365には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。 一部の組織では、SIEM サーバーの使用が必要な特別な状況があります。 次に、いくつかの例を示します:

- *Fabrikam には* 、オンプレミスのコンテンツとアプリケーションと、クラウド内の一部があります (ハイブリッド クラウド展開があります)。 Fabrikam は、すべてのコンテンツとアプリケーションのセキュリティ レポートを取得するために、SIEM サーバーを実装しました。
- *Contoso* は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 ユーザーは、必要な追加のセキュリティ保護を利用するために、環境に SIEM サーバーを追加しました。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM サーバーとサーバー Microsoft 365

SIEM サーバーは、さまざまなサービスやアプリケーションからデータMicrosoft 365受信できます。 次の表に、SIEM サーバー Microsoft 365リソースと共に、複数のサービスとアプリケーションの一覧を示します。

<br/><br/>

|Microsoft 365サービスまたはアプリケーション|SIEM サーバーの入力/メソッド|追加情報|
|---|---|---|
|[Microsoft Defender for Office 365](defender-for-office-365.md)|監査ログ|[SIEM との Microsoft Defender との統合 (Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/)|Azure でホストされる HTTPS エンドポイント <p> REST API|[SIEM ツールにアラートをプルする](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|ログの統合|[SIEM とMicrosoft Cloud App Security](/cloud-app-security/siem)|

> [!TIP]
> [Azure Sentinel を見てみろ](/azure/sentinel/overview)。 Azure Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは「箱から出して」利用できます。リアルタイムの統合を実現します。 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security など、Microsoft 365 Defender ソリューションと Microsoft 365 サービスで Azure Sentinel を使用できます。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要があります

SIEM サーバー統合を構成する前に、監査ログが有効になっていることを確認してください。

- オンラインSharePoint、OneDrive for Business、Azure Active Directoryについては、「監査を有効またはオフ[にする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。
- 詳細については、「Exchange Online監査[の管理」を参照してください](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>その他のリソース

[Azure Defender にセキュリティ ソリューションを統合する](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](/graph/security-integration)
