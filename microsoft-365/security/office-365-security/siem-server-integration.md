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
ms.openlocfilehash: ffb457a378539691627eff3ad24b24ef782705c1
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65670204"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>セキュリティ情報とイベント管理 (SIEM) サーバーとMicrosoft 365サービスとアプリケーションの統合

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

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
> [Microsoft Sentinel](/azure/sentinel/overview) を見てみましょう。 Microsoft Sentinel には、Microsoft ソリューション用のコネクタが付属しています。 これらのコネクタは"すぐに使用できる" ので、リアルタイムの統合が可能です。 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft 365 Defender ソリューション、Microsoft 365 サービスで Microsoft Sentinel を使用できます。Microsoft Defender for Cloud Appsなど。

### <a name="audit-logging-must-be-turned-on"></a>監査ログを有効にする必要がある

SIEM サーバー統合を構成する前に、監査ログがオンになっていることを確認してください。

- SharePoint Online、OneDrive for Business、Azure Active Directoryについては、「[監査を有効または無効にする」を](../../compliance/turn-audit-log-search-on-or-off.md)参照してください。
- Exchange Onlineについては、「[メールボックス監査の管理](../../compliance/enable-mailbox-auditing.md)」を参照してください。

## <a name="integration-steps-if-your-siem-is-microsoft-sentinel"></a>SIEM が Microsoft Sentinel の場合の統合手順

現在のプランで Microsoft Sentinel 統合が許可されていること (たとえば、プラン 2 以降Microsoft Defender for Office 365)、Microsoft Defender for Office 365またはMicrosoft 365 Defenderのアカウントがセキュリティであることを確認します *管理者*。 最後に、 *Microsoft Sentinel で書き込みアクセス許可* があることを確認します。

1. Microsoft Sentinel に移動します。
1. 画面の左側にあるナビゲーションで **、構成** > **データ コネクタ**。
1. Microsoft 365 Defender **を検索** し、**Microsoft 365 Defender (プレビュー) コネクタ** を選択します。
1. 画面の右側にある [ **コネクタ ページを開く**] を選択します。
1. [**構成]** > Connect **インシデント&アラートを** 選択します
    1. 現在選択されている製品のすべての Microsoft インシデント作成ルールを無効にします。
1. ページ **の [Connect** イベント] セクションで **Microsoft Defender for Office 365** までスクロールします。

最後の手順 (以下) を完了している間は、他 *の Microsoft Defender 製品* からテーブルを選択できます。

7. **EmailEvents**、**EmailUrlInfo**、**EmailAttachmentInfo**、**EmailPostDeliveryEvents** >を選択し、**変更を適用します**。

## <a name="more-resources"></a>その他のリソース

[Microsoft Defender for Cloudでセキュリティ ソリューションを統合する](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Microsoft Graph Security API の警告と SIEM の統合](/graph/security-integration)
