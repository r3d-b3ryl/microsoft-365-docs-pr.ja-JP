---
title: 自動調査の詳細と結果を表示する
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 7d3923a3032653f9bfc4a59dc98fe06953975bac
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967920"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果を表示する

**適用対象:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

自動調査が Microsoft Threat Protection で実行された際は、自動調査プロセスの実行中および実行後に調査の詳細を確認できます。 [必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。 調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。 

![調査の詳細](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>調査の詳細ビューを開く

調査の詳細ビューを開くには、次のいずれかの方法を使用できます。
- [アクション センターでアイテムを選択する](#select-an-item-in-the-action-center)
- [インシデントの詳細ページから調査を選択する](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>アクション センターでアイテムを選択する

アクション センターを使用して、承認が保留中のアクション ([**保留中**] タブで) または既に承認されているアクション ([**履歴**] タブで) を表示します。 

1. [https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. [**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。 [必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、保留中のアクションを承認 (または拒否) できます。

### <a name="open-an-investigation-from-an-incident-details-page"></a>インシデントの詳細ページから調査を開く

インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。

1. [https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。 

2. ナビゲーション ウィンドウで、[**インシデント**] を選択します。 

3. リスト内のアイテムを選択してインシデントの詳細ビューを開きます。<br/>![インシデントの詳細](../images/mtp-incidentdetails-tabs.png)

4. [**調査**] タブで、一覧から調査を選択します。

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 調査の詳細ビューの画像は次のようになります。

![調査の詳細](../images/mtp-air-investdetails.png)

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

|タブ    |説明 |
|--------|--------|
|Investigation graph (調査グラフ)    |調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。<br/>グラフ上のアイテムをクリックすると、詳細が表示されます。 たとえば、[**Threats found (見つかった脅威)**] アイコンをクリックすると、[**Key findings (主な検出事項)**] タブに移動します。 |
|Alerts (警告) |調査に関連する警告を一覧表示します。 警告は、ユーザーのコンピューター上または Office アプリ内の脅威対策機能、Cloud App Security、その他の Microsoft 365 Threat Protection 機能により出されます。|
|Devices (デバイス)|調査に含まれるコンピューターと修復レベルを一覧表示します。|
|Key findings (主な検出事項)   |調査の結果と共に、状態と実行または保留されているアクションを一覧表示します。 このタブでは、デバイスおよび ID に対する保留中のアクションを承認できます。|
|Entities (エンティティ)   |調査に関連付けられているユーザー アクティビティ、ファイル、プロセス、サービス、ドライバー、IP アドレス、および永続化の方法と共に、状態と実行されたアクションが一覧表示されます。|
|Log (ログ)    |調査中に実行されたすべてのステップの詳細および状態を表示します。|
|Pending actions (保留中のアクション)    |続けるには承認を必要とするアイテムを一覧表示します。|

## <a name="remediation-actions-following-automated-investigation"></a>自動調査後の修復アクション

自動調査が完了すると、関係するすべての証拠について判定が行われ、修復アクションが特定されます。 修復アクションが自動的に実行される場合もあれば、修復アクションが承認を待機する場合もあります。 考えられる判定と結果を次の表に示します。

|判定    |分野   |結果|
|------|------|------|
|Malicious (悪意のある)  |デバイス (エンドポイント)    |修復アクションが自動的に実行されます|
|Malicious (悪意のある)  |メールのコンテンツ (URL または添付ファイル) | 推奨される修復アクションが承認待ちになります|
|Suspicious (不審) |デバイスまたはメールのコンテンツ |推奨される修復アクションが承認待ちになります|
|Clean (クリーン)  |デバイスまたはメールのコンテンツ   |必要な修復アクションはありません|

[保留中のアクションをアクション センターで確認する](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

## <a name="next-steps"></a>次のステップ

- [アクション センターのアクセス許可の概要を確認する](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [自動調査と応答に関連するアクションを承認または拒否する](mtp-autoir-actions.md)

