---
title: 自動調査の詳細と結果
description: 自動調査の結果と主要な結果を確認Microsoft 365 Defender
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
ms.openlocfilehash: 05e16a32fb21f682a756c32201a69c192d398184
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321809"
---
# <a name="details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

このMicrosoft 365 Defender、自動調査が実行されると[](m365d-autoir.md)、その調査に関する詳細は、自動調査プロセスの間と後の両方で利用できます。 必要な [アクセス許可がある](m365d-action-center.md#required-permissions-for-action-center-tasks)場合は、最新の状態と保留中のアクションを承認する機能を提供する調査の詳細ビューでこれらの詳細を表示できます。 

## <a name="new-unified-investigation-page"></a>(NEW)統合された調査ページ

調査ページが最近更新され、デバイス、電子メール、およびコラボレーション コンテンツ全体の情報が含まれます。 新しい統合された調査ページでは、共通言語が定義され、[Microsoft Defender for Endpoint および Microsoft Defender for microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) for Office 365 の間で自動調査を行う一元[的なエクスペリエンスが提供されます](../office-365-security/defender-for-office-365.md)。 統合調査ページにアクセスするには、次の黄色のバナーにあるリンクを選択します。

- コンプライアンス センターの [セキュリティOffice 365<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">&] ページ</a>
- ポータル内の調査Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))
- Microsoft 365 Defender ポータルでのインシデント<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">またはアクション センターのエクスペリエンス</a>

## <a name="open-the-investigation-details-view"></a>調査の詳細ビューを開く

調査の詳細ビューを開くには、次のいずれかの方法を使用できます。

- [アクション センターでアイテムを選択する](#select-an-item-in-the-action-center)
- [インシデントの詳細ページから調査を選択する](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>アクション センターでアイテムを選択する

改善された[アクション センター](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) では、デバイス全体[](m365d-remediation-actions.md)の修復アクション、電子メール、コラボレーション & ID がまとめされます。 リストされているアクションには、自動的または手動で実行された修復アクションが含まれます。 アクション センターでは、承認待ちのアクションと、既に承認または完了したアクションを表示できます。 調査ページなどの詳細に移動することもできます。

> [!TIP]
> アクションを承認 [、拒否、または](m365d-action-center.md#required-permissions-for-action-center-tasks) 元に戻すには、特定のアクセス許可が必要です。

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderに移動し</a>、サインインします。 

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。 

3. [**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。 そのフライアウト ウィンドウが開きます。

4. フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査ページを開く]** を選択して、調査の詳細を表示します。
   - [承認 **] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。
   - [Go **hunt] を** 選択して高度な [ハンティングに入る](advanced-hunting-overview.md)。

### <a name="open-an-investigation-from-an-incident-details-page"></a>インシデントの詳細ページから調査を開く

インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderに移動し</a>、サインインします。 

2. ナビゲーション ウィンドウで、[インシデント] **を選択し、[&** >  **Incidents] を選択します**。 

3. 一覧でアイテムを選択し、[インシデント ページを開 **く] を選択します**。

4. [調査 **] タブを** 選択し、一覧で調査を選択します。 そのフライアウト ウィンドウが開きます。

5. [調査 **ページを開く] を選択します**。 

次に例を示します。

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="調査ページの例。" lightbox="../../media/mtp-incidentdetails-tabs.png":::

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 次に例を示します。

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="調査の詳細の例。" lightbox="../../media/mtp-air-investdetails.png":::

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

> [!NOTE]
> 調査の詳細ページに表示される特定のタブは、サブスクリプションに含まれる内容によって異なります。 たとえば、サブスクリプションにプラン 2 の Microsoft Defender がOffice 365場合、[メールボックス] タブ **は表示** されません。

| タブ | 説明 |
|:--------|:--------|
| **Investigation graph (調査グラフ)** | 調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。<br/>グラフ上のアイテムを選択すると、詳細を表示できます。 たとえば、[証拠 **] アイコンを** 選択すると、[証拠] タブに移動し、検出されたエンティティとその評決を確認できます。 |
| **アラート** | 調査に関連する警告を一覧表示します。 アラートは、ユーザーのデバイス、Office アプリ、Microsoft Defender for Cloud Apps、その他のセキュリティ機能の脅威保護機能Microsoft 365 Defenderがあります。|
| **Devices** | 調査に含まれるデバイスとその修復レベルを一覧表示します。 (修復レベルは、 [デバイス グループのオートメーション レベルに対応](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)します)。 |
| **メールボックス** |検出された脅威の影響を受けたメールボックスを一覧表示します。  |
| **ユーザー**  | 検出された脅威の影響を受けたユーザー アカウントを一覧表示します。 |
| **証拠** | アラートまたは調査によって発生した証拠の一部を一覧表示します。 評決 (悪意のある、疑 *わしい**、**不明* な、または脅威が見 *つからない) と* 修復の状態が含まれます。 |
| **Entities** | 各エンティティの種類 (悪意のある、疑わしい、または検出された脅威なし) の評決を含む、分析された各エンティティに関する詳細 *を提供します*。|
|**Log** | アラートがトリガーされた後に行ったすべての調査アクションの時系列的で詳細なビューを提供します。|
| **保留中のアクションの履歴** | 続けるには承認を必要とするアイテムを一覧表示します。 アクション センター () に移動して[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)、保留中のアクションを承認します。 |

## <a name="next-steps"></a>次の手順

- [修復アクションを表示および管理する](m365d-autoir-actions.md)
- [修復アクションの詳細](m365d-remediation-actions.md)
