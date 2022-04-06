---
title: SaaS アプリに推奨される Microsoft Defender for Cloud Apps ポリシー - Microsoft 365 Enterprise |Microsoft Docs
description: Microsoft Defender for Cloud Apps との統合に関する推奨ポリシーについて説明します。
author: BrendaCarter
manager: laurawi
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.prod: m365-security
ms.openlocfilehash: 95b46e1c92354015ce6f8d9c5b1fa4b6e9642785
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683321"
---
# <a name="recommended-microsoft-defender-for-cloud-apps-policies-for-saas-apps"></a>推奨される SaaS アプリ用 Microsoft Defender for Cloud Apps ポリシー

Microsoft Defender for Cloud Apps は、Azure AD 条件付きアクセス ポリシーを基に構築され、ダウンロード、アップロード、コピー、貼り付け、印刷のブロックなど、SaaS アプリによる詳細なアクションをリアルタイムで監視および制御できます。 この機能は、企業リソースが管理されていないデバイスやゲスト ユーザーからアクセスされる場合など、固有のリスクを伴うセッションにセキュリティを追加します。

また、Defender for Cloud Apps は Microsoft Information Protection とネイティブに統合され、機密情報の種類と機密ラベルに基づいて機密データを検索し、適切なアクションを実行するためのリアルタイムコンテンツ検査を提供します。

このガイダンスには、次のシナリオに関する推奨事項が含まれています。

- SaaS アプリを IT 管理に取り込む
- 特定の SaaS アプリの保護を調整する
- データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する

## <a name="bring-saas-apps-into-it-management"></a>SaaS アプリを IT 管理に取り込む

Defender for Cloud Apps を使用して SaaS アプリを管理する最初の手順は、これらのアプリを検出し、そのアプリをクラウド テナントAzure ADです。 検出に関するヘルプが必要な場合は、「 [ネットワーク内の SaaS アプリを検出して管理する」を参照してください](/cloud-app-security/tutorial-shadow-it)。 アプリを検出した後、これらのアプリを[テナントにAzure ADします](/azure/active-directory/manage-apps/add-application-portal)。

これらを管理するには、次の手順を実行します。

1. 最初に、Azure AD条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御を使用する" に構成します。 これにより、要求が Defender for Cloud Apps にリダイレクトされます。 1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。
1. 次に、[Defender for Cloud Apps] でセッション ポリシーを作成します。 適用するコントロールごとに 1 つのポリシーを作成します。

SaaS アプリへのアクセス許可は、通常、アプリへのアクセスに関するビジネス上の必要性に基づいて行います。 これらのアクセス許可は、非常に動的な場合があります。 Defender for Cloud Apps ポリシーを使用すると、ユーザーが開始点、エンタープライズ、または特殊なセキュリティ保護に関連付けられた Azure AD グループに割り当てられているかどうかに関係なく、アプリ データを保護できます。

SaaS アプリのコレクション全体のデータを保護するために、次の図は、必要な Azure AD 条件付きアクセス ポリシーと、Defender for Cloud Apps で作成できる推奨ポリシーを示しています。 この例では、Defender for Cloud Apps で作成されたポリシーが、管理しているすべての SaaS アプリに適用されます。 これらは、デバイスが管理されるかどうか、およびファイルに既に適用されている感度ラベルに基づいて適切なコントロールを適用するように設計されています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png" alt-text="Defender for Cloud Apps で SaaS アプリを管理するためのポリシー。" lightbox="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png":::

次の表に、新しい条件付きアクセス ポリシーを作成する必要Azure AD。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|すべての保護レベル|[クラウド アプリの Defender で条件付きアクセス アプリ制御を使用する](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|これにより、IdP (Azure AD) が Defender for Cloud Apps で動作します。|
||||

次の表に、すべての SaaS アプリを保護するために作成できる上記のポリシー例を示します。 ビジネス、セキュリティ、コンプライアンスの目的を評価し、環境に対して最も適切な保護を提供するポリシーを作成してください。

|保護レベル|ポリシー|
|---|---|
|開始点|管理されていないデバイスからのトラフィックを監視する <p> 管理されていないデバイスからのファイルダウンロードに保護を追加する|
|大企業|機密または非管理対象デバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)|
|特殊なセキュリティ|すべてのデバイスから分類されたラベルが付いたファイルのダウンロードをブロックする (これにより、ブラウザーへのアクセスのみ可能)|
|||

条件付きアクセス アプリコントロールを設定する方法については、「Deploy Conditional [Access App Control for featured apps」を参照してください](/cloud-app-security/proxy-deployment-aad)。 この記事では、SaaS アプリの作成とテストに必要な条件付きアクセス Azure AD手順を説明します。

詳細については、「 [Protect apps with Microsoft Defender for Cloud Apps Conditional Access App Control」を参照してください](/cloud-app-security/proxy-intro-aad)。

## <a name="tune-protection-for-specific-saas-apps"></a>特定の SaaS アプリの保護を調整する

環境内の特定の SaaS アプリに追加の監視とコントロールを適用する場合があります。 Defender for Cloud Apps を使用すると、これを実行できます。 たとえば、Box のようなアプリが環境で多用されている場合は、追加のコントロールを適用する方が理にかなっています。 または、法務部門または財務部門が機密ビジネス データに特定の SaaS アプリを使用している場合は、これらのアプリに対する追加の保護をターゲットにできます。

たとえば、次の種類の組み込みの異常検出ポリシー テンプレートを使用して Box 環境を保護できます。

- 匿名 IP アドレスからのアクティビティ
- ほとんどアクセスがない国からのアクティビティ
- 疑わしい IP アドレスからのアクティビティ
- 不可能な移動
- 終了したユーザーが実行するアクティビティ (IdP AADが必要)
- マルウェアの検出
- 複数回のログイン試行の失敗
- ランサムウェアのアクティビティ
- 危険な Oauth アプリ
- 通常と異なるファイル共有アクティビティ

例を次に示します。 追加のポリシー テンプレートは、定期的に追加されます。 特定のアプリに追加の保護を適用する方法の例については、「接続されたアプリの保護 [」を参照してください](/cloud-app-security/protect-connected-apps)。

[Defender for Cloud Apps が Box](/cloud-app-security/protect-box) 環境の保護に役立つ方法は、Box や他のアプリのビジネス データを機密データで保護するのに役立つコントロールの種類を示しています。

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>データ保護規制に準拠するためにデータ損失防止 (DLP) を構成する

Defender for Cloud Apps は、コンプライアンス規制に対する保護を構成するための貴重なツールになります。 この場合、規制が適用される特定のデータを検索する特定のポリシーを作成し、適切なアクションを実行するために各ポリシーを構成します。

次の図と表に、一般データ保護規則 (GDPR) に準拠するように構成できるポリシーのいくつかの例を示します。 これらの例では、ポリシーは特定のデータを検索します。 データの感度に基づいて、各ポリシーは適切なアクションを実行するように構成されます。

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-dlp.png" alt-text="データ損失防止のためのクラウド アプリポリシーの例。" lightbox="../../media/microsoft-365-policies-configurations/mcas-dlp.png":::

|保護レベル|ポリシーの例|
|---|---|
|開始点|この機密情報の種類を含むファイル ("クレジット カード番号") が組織外で共有されている場合の警告 <p> >この機密情報の種類 ("クレジット カード番号") を含むファイルの管理されていないデバイスへのダウンロードをブロックする|
|大企業|この機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードを管理対象デバイスに保護する <p> 管理されていないデバイスへのこの機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードをブロックする <p> これらのラベルがオンのファイルが OneDrive for Business または Box にアップロードされると警告する (顧客データ、人事: 給与データ、人事、従業員データ)|
|特殊なセキュリティ|このラベルを持つファイル ("高度に分類された") が管理対象デバイスにダウンロードされる場合の警告 <p> 管理されていないデバイスへのこのラベル ("高度に分類された") を持つファイルのダウンロードをブロックする|
|||

## <a name="next-steps"></a>次の手順

Defender for Cloud Apps の使用の詳細については、「 [Microsoft Defender for Cloud Apps」のドキュメントを参照してください](//cloud-app-security/)。
