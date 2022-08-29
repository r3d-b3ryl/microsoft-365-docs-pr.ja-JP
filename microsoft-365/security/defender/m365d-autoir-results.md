---
title: 自動調査の詳細と結果
description: Microsoft 365 Defenderで自動調査の結果と主な結果を表示する
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 08/11/2022
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: 591c7a8aca882c0674eaa3ba4b3eacc89817e859
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388619"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defenderでは、自動調査が実行されると、[その調査](m365d-autoir.md)に関する詳細は、自動調査プロセス中と自動調査後の両方で利用できます。 [必要なアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks)がある場合は、調査の詳細ビューでそれらの詳細を表示できます。これにより、最新の状態と保留中のアクションを承認できます。 

## <a name="new-unified-investigation-page"></a>(NEW)統合調査ページ

調査ページが最近更新され、デバイス、電子メール、コラボレーション コンテンツ全体の情報が含まれています。 新しい統合調査ページでは、共通言語が定義され、[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)と[Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md)全体で自動調査を行うための統合エクスペリエンスが提供されます。 統合調査ページにアクセスするには、表示される黄色のバナーでリンクを選択します。

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Microsoft Purview コンプライアンス ポータル</a>の任意の調査ページ
- Microsoft 365 Defender ポータルの任意の調査ページ ([https://security.microsoft.com](https://security.microsoft.com))
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>でのインシデントまたはアクション センターのエクスペリエンス

## <a name="open-the-investigation-details-view"></a>調査の詳細ビューを開く

調査の詳細ビューを開くには、次のいずれかの方法を使用できます。

- [アクション センターでアイテムを選択する](#select-an-item-in-the-action-center)
- [インシデントの詳細ページから調査を選択する](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>アクション センターでアイテムを選択する

改善された [アクション センター](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) には、デバイス間の [修復アクション](m365d-remediation-actions.md) 、電子メール&コラボレーション コンテンツ、ID がまとめられます。 一覧表示されるアクションには、自動的または手動で実行された修復アクションが含まれます。 アクション センターでは、承認待ちのアクションと、既に承認または完了したアクションを表示できます。 調査ページなど、詳細に移動することもできます。

> [!TIP]
> アクションを承認、拒否、または元に戻すための [特定のアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks) が必要です。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. [**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。 ポップアップ ウィンドウが開きます。

4. ポップアップ ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査を開く] ページ** を選択して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中のアクションが実行されないようにするには、[ **拒否] を** 選択します。
   - [ **Go hunt** ] を選択して [高度なハンティング](advanced-hunting-overview.md)に移動します。

### <a name="open-an-investigation-from-an-incident-details-page"></a>インシデントの詳細ページから調査を開く

インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[インシデント& **アラート** > **インシデント**] を選択します。 

3. 一覧で項目を選択し、[ **インシデント ページを開く**] を選択します。

4. [調査] タブ **を** 選択し、一覧で調査を選択します。 ポップアップ ウィンドウが開きます。

5. [ **調査ページを開く]** を選択します。 

次に例を示します。

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Microsoft 365 Defender ポータルの調査ページ" lightbox="../../media/mtp-incidentdetails-tabs.png":::

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 次に例を示します。

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Microsoft 365 Defender ポータルの調査の詳細ページ" lightbox="../../media/mtp-air-investdetails.png":::

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

> [!NOTE]
> 調査の詳細ページに表示される特定のタブは、サブスクリプションに含まれる内容によって異なります。 たとえば、サブスクリプションにプラン 2 Microsoft Defender for Office 365含まれていない場合、[**メールボックス]** タブは表示されません。

| タブ | 説明 |
|:--------|:--------|
| **Investigation graph (調査グラフ)** | 調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。<br/>グラフ上の項目を選択すると、詳細を表示できます。 たとえば、[ **証拠** ] アイコンを選択すると、[ **証拠** ] タブに移動し、検出されたエンティティとその評決を確認できます。 |
| **アラート** | 調査に関連する警告を一覧表示します。 アラートは、ユーザーのデバイス、Office アプリ、Microsoft Defender for Cloud Apps、その他のMicrosoft 365 Defender機能の脅威保護機能から取得できます。 <br> <br> *サポートされていないアラートの種類* が表示された場合は、自動調査機能ではそのアラートを取得して自動調査を実行できないことを意味します。 ただし、 [これらのアラートは手動で調査](investigate-incidents.md#alerts)できます。
| **Devices** | 調査に含まれるデバイスとその修復レベルを一覧表示します。 (修復レベルは [、デバイス グループの自動化レベルに](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)対応します)。 |
| **メールボックス** |検出された脅威の影響を受けるメールボックスを一覧表示します。  |
| **Users**  | 検出された脅威の影響を受けるユーザー アカウントを一覧表示します。 |
| **証拠** | アラートまたは調査によって発生した証拠の一部を一覧表示します。 判定 (*悪意のある*、 *疑わしい*、 *不明*、または *脅威が見つかりません*) と修復状態が含まれます。 |
| **Entities** | 各エンティティの種類 (*悪意のある*、 *疑わしい*、または *脅威が見つかりません*) の判定など、分析された各エンティティの詳細を提供します。|
|**Log** | アラートがトリガーされた後に実行されたすべての調査アクションの時系列的で詳細なビューを提供します。|
| **保留中のアクション履歴** | 続けるには承認を必要とするアイテムを一覧表示します。 アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) に移動して、保留中のアクションを承認します。 |


## <a name="investigation-states"></a>調査の状態

次の表に、調査の状態とそれらが示す内容を示します。


|調査の状態  |定義  |
|---------|---------|
|良性   | アーティファクトが調査され、脅威が見つからなかったという判断が下されました。|
|PendingResource     | 修復アクションが承認待ちであるか、アーティファクトが見つかったデバイスが一時的に使用できないため、自動調査は一時停止されます。|
|UnsupportedAlertType     | この種類のアラートでは、自動調査を利用できません。 詳細な調査は、高度な捜索を使用して手動で行うことができます。 |
|失敗     | 少なくとも 1 つの調査アナライザーで、調査を完了できない問題が発生しました。 修復アクションが承認された後に調査が失敗した場合でも、修復アクションは成功している可能性があります。|
|正常に修復されました| 自動調査が完了し、すべての修復アクションが完了または承認されました。|

調査状態の表示方法に関するより詳細なコンテキストを提供するために、次の表にアラートとそれに対応する自動調査の状態を示します。 この表は、セキュリティ運用チームがMicrosoft 365 Defender ポータルに表示する可能性のある内容の例として含まれています。

|アラート名 | 重要度 | 調査の状態 | 状態 | カテゴリ |
|-----------|----------|---------------------|--------|----------|
|wim ディスク イメージ ファイルでマルウェアが検出されました|情報|良性|Resolved|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|PendingResource|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|UnsupportedAlertType|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|UnsupportedAlertType|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|UnsupportedAlertType|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|Wpakill hacktool が防止されました|低|失敗|新規|マルウェア|
|GendowsBatch hacktool が禁止されました|低|失敗|新規|マルウェア|
|Keygen hacktool が防止されました|低|失敗|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|PendingResource|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|PendingResource|新規|マルウェア|
|zip アーカイブ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|PendingResource|新規|マルウェア|
|マルウェアがrarアーカイブ ファイルで検出されました|情報|PendingResource|新規|マルウェア|
|iso ディスク イメージ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|iso ディスク イメージ ファイルでマルウェアが検出されました|情報|PendingResource|新規|マルウェア|
|pst outlook データ ファイルでマルウェアが検出されました|情報|UnsupportedAlertType|新規|マルウェア|
|pst outlook データ ファイルでマルウェアが検出されました|情報|UnsupportedAlertType|新規|マルウェア|
|MediaGet が検出されました|中|PartiallyInvestigated|新規|マルウェア|
|TrojanEmailFile|中|正常に修復されました|Resolved|マルウェア|
|CustomEnterpriseBlock マルウェアが防止されました|情報|正常に修復されました|Resolved|マルウェア|
|アクティブな CustomEnterpriseBlock マルウェアがブロックされました|低|正常に修復されました|Resolved|マルウェア|
|アクティブな CustomEnterpriseBlock マルウェアがブロックされました|低|正常に修復されました|Resolved|マルウェア|
|アクティブな CustomEnterpriseBlock マルウェアがブロックされました|低|正常に修復されました|Resolved|マルウェア|
|TrojanEmailFile|中|良性|Resolved|マルウェア|
|CustomEnterpriseBlock マルウェアが防止されました|情報|UnsupportedAlertType|新規|マルウェア|
|CustomEnterpriseBlock マルウェアが防止されました|情報|正常に修復されました|Resolved|マルウェア|
|TrojanEmailFile|中|正常に修復されました|Resolved|マルウェア|
|TrojanEmailFile|中|良性|Resolved|マルウェア|
|アクティブな CustomEnterpriseBlock マルウェアがブロックされました|低|PendingResource|新規|マルウェア|

## <a name="next-steps"></a>次の手順

- [修復アクションを表示および管理する](m365d-autoir-actions.md)
- [修復アクションの詳細を確認する](m365d-remediation-actions.md)
