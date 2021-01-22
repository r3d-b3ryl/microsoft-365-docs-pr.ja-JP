---
title: 自動調査の詳細と結果
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930368"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender で自動調査が行われると、その調査に関する詳細は、自動調査プロセス中および自動調査後に確認できます。 [必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。 調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。 

![調査の詳細](../../media/mtp-air-investdetails.png)

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

3. リスト内のアイテムを選択してインシデントの詳細ビューを開きます。<br/>![インシデントの詳細](../../media/mtp-incidentdetails-tabs.png)

4. [**調査**] タブで、一覧から調査を選択します。

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 調査の詳細ビューの画像は次のようになります。

![調査の詳細](../../media/mtp-air-investdetails.png)

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

| タブ | 説明 |
|--------|--------|
| **Investigation graph (調査グラフ)**   | 調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。<br/>グラフ上のアイテムをクリックすると、詳細が表示されます。 たとえば、[**Threats found (見つかった脅威)**] アイコンをクリックすると、[**Key findings (主な検出事項)**] タブに移動します。 |
| **Alerts**    | 調査に関連する警告を一覧表示します。 アラートは、ユーザーのコンピューター、Office アプリ、Cloud App Security、その他の Microsoft 365 Defender 機能の脅威保護機能から発生する可能性があります。|
| **デバイス** | 調査に含まれるコンピューターと修復レベルを一覧表示します。|
| **Key findings (主な検出事項)**  | 調査の結果と共に、状態と実行または保留されているアクションを一覧表示します。 このタブでは、デバイスおよび ID に対する保留中のアクションを承認できます。|
| **Entities**  | 調査に関連付けられているユーザー アクティビティ、ファイル、プロセス、サービス、ドライバー、IP アドレス、および永続化の方法と共に、状態と実行されたアクションが一覧表示されます。|
|**Log**    | 調査中に実行されたすべてのステップの詳細および状態を表示します。|
| **Pending actions (保留中のアクション)** | 続けるには承認を必要とするアイテムを一覧表示します。|

## <a name="next-steps"></a>次のステップ

- [自動調査と対応に関連するアクションを承認または拒否する](mtp-autoir-actions.md)
- [修復アクションを確認する](mtp-remediation-actions.md)
