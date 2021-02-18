---
title: SIEM サーバーと Microsoft 365 サービスおよびアプリケーションの統合
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
description: セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 クラウド サービスおよびアプリケーションの統合の概要を説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290383"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報およびイベント管理 (SIEM) サーバーと Microsoft 365 サービスおよびアプリケーションの統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>要約

組織でセキュリティ情報およびイベント管理 (SIEM) サーバーを使用するか、または取得を計画していますか。 Microsoft 365 または Office 365 と統合する方法を疑問に思う可能性があります。 この記事では、SIEM サーバーを Microsoft 365 サービスおよびアプリケーションと統合するために使用できるリソースの一覧を示します。

> [!TIP]
> SIEM サーバーをまだお持ちで、オプションを検討している場合は **[、Microsoft Azure Sentinel を検討してください](https://docs.microsoft.com/azure/sentinel/overview)**。

## <a name="do-i-need-a-siem-server"></a>SIEM サーバーは必要ですか?

SIEM サーバーが必要かどうかは、組織のセキュリティ要件やデータの保存場所など、多くの要因によって異なります。 Microsoft 365 には、SIEM サーバーなどの追加サーバーを使用せずに、多くの組織のセキュリティ ニーズを満たすさまざまなセキュリティ機能が含まれています。 組織によっては、SIEM サーバーの使用が必要な特殊な状況があります。 次に、いくつかの例を示します:

- *Fabrikam には* オンプレミスのコンテンツとアプリケーションと、クラウド内のコンテンツとアプリケーションがあります (ハイブリッド クラウド展開があります)。 Fabrikam は、すべてのコンテンツとアプリケーションのセキュリティ レポートを取得するために、SIEM サーバーを実装しています。

- *Contoso* 社は、特に厳しいセキュリティ要件を持つ金融サービス組織です。 ユーザーは、必要な追加のセキュリティ保護を利用するために、環境に SIEM サーバーを追加しました。

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM サーバーと Microsoft 365 の統合

SIEM サーバーは、さまざまな Microsoft 365 サービスおよびアプリケーションからデータを受信できます。 次の表に、いくつかの Microsoft 365 サービスとアプリケーション、SIEM サーバーの入力、詳細を確認するリソースを示します。

****

|Microsoft 365 サービスまたはアプリケーション|SIEM サーバーの入力/メソッド|追加情報|
|---|---|---|
|[Microsoft Defender for Office 365](office-365-atp.md)|監査ログ|[siem integration with Microsoft Defender for Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)|Azure でホストされている HTTPS エンドポイント <p> REST API|[SIEM ツールにアラートをプルする](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|ログ統合|[SIEM と Microsoft Cloud App Security の統合](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> [Azure Sentinel を確認してください](https://docs.microsoft.com/azure/sentinel/overview)。 Azure Sentinel には、Microsoft ソリューションのコネクタが付属しています。 これらのコネクタは、"既定で" 使用可能であり、リアルタイム統合を実現します。 Azure Sentinel は、Microsoft 365 Defender ソリューションと Microsoft 365 サービス (Office 365、Azure AD、Id 用 Microsoft Defender、Microsoft Cloud App Security など) と一緒に使用できます。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要があります

SIEM サーバー統合を構成する前に、監査ログが有効になっていることを確認してください。

- SharePoint Online、OneDrive for Business、および Azure Active Directory の場合、セキュリティ/コンプライアンス センターで監査 [ログ&オンになります](../../compliance/turn-audit-log-search-on-or-off.md)。

- Exchange Online については、「メールボックス監査 [の管理」を参照してください](../../compliance/enable-mailbox-auditing.md)。

## <a name="more-resources"></a>その他のリソース

[Azure Defender でのセキュリティ ソリューションの統合](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](https://docs.microsoft.com/graph/security-integration)
