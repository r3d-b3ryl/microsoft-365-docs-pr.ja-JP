---
title: SaaS アプリの推奨Microsoft Defender for Cloud Apps ポリシー - Microsoft 365 Enterprise |Microsoft Docs
description: Microsoft Defender for Cloud Appsとの統合に推奨されるポリシーについて説明します。
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
ms.openlocfilehash: a53666c58c8a9cc5793d160c428bc96ea322b274
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64945541"
---
# <a name="recommended-microsoft-defender-for-cloud-apps-policies-for-saas-apps"></a>推奨される SaaS アプリ用 Microsoft Defender for Cloud Apps ポリシー

Microsoft Defender for Cloud Apps Azure AD条件付きアクセス ポリシーに基づいて構築され、ダウンロードのブロック、アップロード、コピーと貼り付け、印刷など、SaaS アプリできめ細かなアクションをリアルタイムで監視および制御できます。 この機能により、企業リソースにアンマネージド デバイスやゲスト ユーザーからアクセスされる場合など、固有のリスクを伴うセッションにセキュリティが追加されます。

Defender for Cloud Apps は Microsoft Purview Information Protectionともネイティブに統合され、機密情報の種類と秘密度ラベルに基づいて機密データを検索し、適切なアクションを実行するためのリアルタイムコンテンツ検査を提供します。

このガイダンスには、次のシナリオに関する推奨事項が含まれています。

- SaaS アプリを IT 管理に取り込む
- 特定の SaaS アプリの保護を調整する
- データ保護規則に準拠できるように Microsoft Purview データ損失防止 (DLP) を構成する

## <a name="bring-saas-apps-into-it-management"></a>SaaS アプリを IT 管理に取り込む

Defender for Cloud Apps を使用して SaaS アプリを管理する最初の手順は、これらを検出してAzure AD テナントに追加することです。 検出に関するヘルプが必要な場合は、 [ネットワーク内の SaaS アプリの検出と管理に関するページを参照してください](/cloud-app-security/tutorial-shadow-it)。 アプリを検出したら、[これらをAzure AD テナントに追加します](/azure/active-directory/manage-apps/add-application-portal)。

これらの管理を開始するには、次の手順を実行します。

1. まず、Azure ADで、新しい条件付きアクセス ポリシーを作成し、"条件付きアクセス アプリ制御の使用" に構成します。 これにより、要求が Defender for Cloud Apps にリダイレクトされます。 1 つのポリシーを作成し、すべての SaaS アプリをこのポリシーに追加できます。
1. 次に、Defender for Cloud Apps でセッション ポリシーを作成します。 適用するコントロールごとに 1 つのポリシーを作成します。

通常、SaaS アプリに対するアクセス許可は、アプリへのアクセスに必要なビジネスニーズに基づいています。 これらのアクセス許可は非常に動的な場合があります。 Defender for Cloud Apps ポリシーを使用すると、ユーザーが開始点、エンタープライズ、または特殊なセキュリティ保護に関連付けられているAzure AD グループに割り当てられているかどうかに関係なく、アプリ データの保護が保証されます。

SaaS アプリのコレクション全体でデータを保護するために、次の図は、Defender for Cloud Apps で作成できる必要なAzure AD条件付きアクセス ポリシーと推奨されるポリシーを示しています。 この例では、Defender for Cloud Apps で作成されたポリシーは、管理しているすべての SaaS アプリに適用されます。 これらは、既にファイルに適用されている機密ラベルだけでなく、デバイスが管理されているかどうかに基づいて適切な制御を適用するように設計されています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png" alt-text="Defender for Cloud Apps で SaaS アプリを管理するためのポリシー" lightbox="../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png":::

次の表に、Azure ADで作成する必要がある新しい条件付きアクセス ポリシーを示します。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|すべての保護レベル|[Defender for Cloud アプリで条件付きアクセス アプリ制御を使用する](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|これにより、Defender for Cloud Apps を操作するように IdP (Azure AD) が構成されます。|
||||

次の表に、すべての SaaS アプリを保護するために作成できる上記のポリシーの例を示します。 自分のビジネス、セキュリティ、コンプライアンスの目標を必ず評価し、環境に最も適切な保護を提供するポリシーを作成してください。

|保護レベル|ポリシー|
|---|---|
|開始点|管理されていないデバイスからのトラフィックを監視する <p> 非管理対象デバイスからのファイルダウンロードに保護を追加する|
|Enterprise|非管理対象デバイスから機密または分類されたラベルが付けられたファイルのダウンロードをブロックする (これにより、ブラウザーのみのアクセスが提供されます)|
|特殊なセキュリティ|すべてのデバイスから分類されたラベルが付いたファイルのダウンロードをブロックします (これにより、ブラウザーのみのアクセスが提供されます)|
|||

条件付きアクセス アプリ制御を設定するためのエンドツーエンドの手順については、「注目のアプリに [条件付きアクセス アプリコントロールをデプロイする](/cloud-app-security/proxy-deployment-aad)」を参照してください。 この記事では、Azure ADで必要な条件付きアクセス ポリシーを作成し、SaaS アプリをテストするプロセスについて説明します。

詳細については、「[条件付きアクセス アプリ制御を使用してアプリを保護Microsoft Defender for Cloud Apps」を](/cloud-app-security/proxy-intro-aad)参照してください。

## <a name="tune-protection-for-specific-saas-apps"></a>特定の SaaS アプリの保護を調整する

環境内の特定の SaaS アプリに、追加の監視と制御を適用できます。 Defender for Cloud アプリを使用すると、これを実現できます。 たとえば、Box のようなアプリが環境で頻繁に使用されている場合は、追加のコントロールを適用するのが理にかなっています。 または、法務部門または財務部門が機密ビジネス データに特定の SaaS アプリを使用している場合は、これらのアプリに対して追加の保護をターゲットにすることができます。

たとえば、次の種類の組み込みの異常検出ポリシー テンプレートを使用して Box 環境を保護できます。

- 匿名 IP アドレスからのアクティビティ
- ほとんどアクセスがない国からのアクティビティ
- 疑わしい IP アドレスからのアクティビティ
- 不可能な移動
- 終了したユーザーによって実行されるアクティビティ (IdP としてAADが必要)
- マルウェアの検出
- 複数回のログイン試行の失敗
- ランサムウェアのアクティビティ
- 危険な Oauth アプリ
- 通常と異なるファイル共有アクティビティ

これらは例です。 追加のポリシー テンプレートは定期的に追加されます。 特定のアプリに追加の保護を適用する方法の例については、「 [接続されているアプリの保護](/cloud-app-security/protect-connected-apps)」を参照してください。

[Defender for Cloud アプリを使用して Box 環境を保護する方法](/cloud-app-security/protect-box)は、Box やその他のアプリのビジネス データを機密データで保護するのに役立つコントロールの種類を示しています。

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>データ保護規制に準拠できるようにデータ損失防止 (DLP) を構成する

Defender for Cloud アプリは、コンプライアンス規制の保護を構成するための貴重なツールです。 この場合、規制が適用される特定のデータを検索する特定のポリシーを作成し、適切なアクションを実行するように各ポリシーを構成します。

次の図と表に、一般データ保護規則 (GDPR) に準拠するように構成できるポリシーの例をいくつか示します。 これらの例では、ポリシーは特定のデータを検索します。 データの機密性に基づいて、各ポリシーは適切なアクションを実行するように構成されます。

:::image type="content" source="../../media/microsoft-365-policies-configurations/mcas-dlp.png" alt-text="データ損失防止の [Defender for Cloud アプリ ポリシー] ページ" lightbox="../../media/microsoft-365-policies-configurations/mcas-dlp.png":::

|保護レベル|ポリシーの例|
|---|---|
|開始点|この機密情報の種類を含むファイル ("クレジット カード番号") が組織外で共有されたときにアラートを送信する <p> >この機密情報の種類 ("クレジット カード番号") を含むファイルの非管理対象デバイスへのダウンロードをブロックする|
|Enterprise|この機密情報の種類 ("クレジット カード番号") を含むファイルのダウンロードをマネージド デバイスに保護する <p> この機密情報の種類 ("クレジット カード番号") を含むファイルの非管理対象デバイスへのダウンロードをブロックする <p> これらのラベルが付いたファイルがOneDrive for Businessまたは Box (顧客データ、人事: 給与データ、人事、従業員データ) にアップロードされたときにアラートを送信する|
|特殊なセキュリティ|このラベルを持つファイル ("高度に分類された") が管理対象デバイスにダウンロードされたときにアラートを送信する <p> このラベルを持つファイル ("高度に分類") を含むファイルの非管理対象デバイスへのダウンロードをブロックする|
|||

## <a name="next-steps"></a>次の手順

Defender for Cloud アプリの使用の詳細については、[Microsoft Defender for Cloud Appsドキュメントを参照してください](//cloud-app-security/)。
