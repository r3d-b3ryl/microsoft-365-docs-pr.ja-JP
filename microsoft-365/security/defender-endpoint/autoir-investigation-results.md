---
title: 自動調査の詳細と結果を表示する
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: bed61ca559ff6fe387d76e9f56842ae765e186fe
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170310"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果を表示する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint[](automated-investigations.md)では、自動調査が実行されると、その調査に関する詳細は、自動調査プロセスの間と後の両方で利用できます。 必要なアクセス許可を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。 調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。

## <a name="new-unified-investigation-page"></a>(NEW!)統合された調査ページ

調査ページが最近更新され、デバイス、電子メール、およびコラボレーション コンテンツ全体の情報が含まれます。 新しい統合された調査ページでは、共通言語を定義し[、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)および Microsoft Defender for Office 365 全体で自動調査を行う一元[的なエクスペリエンスを提供します](/microsoft-365/security/office-365-security/office-365-atp)。

> [!TIP]
> 変更の詳細については [、「(NEW!) 」を参照してください。統合された調査ページ](/microsoft-365/security/mtp/mtp-autoir-results)。

## <a name="open-the-investigation-details-view"></a>調査の詳細ビューを開く

調査の詳細ビューを開くには、次のいずれかの方法を使用できます。

- [アクション センターでアイテムを選択する](#select-an-item-in-the-action-center)
- [インシデントの詳細ページから調査を選択する](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>アクション センターでアイテムを選択する

改善された[アクション センターでは](auto-investigation-action-center.md)、デバイス[](manage-auto-investigation.md#remediation-actions)全体の修復アクション、電子メール、コラボレーション & ID がまとめされます。 リストされているアクションには、自動的または手動で実行された修復アクションが含まれます。 アクション センターでは、承認待ちのアクションと、既に承認または完了したアクションを表示できます。 調査ページなどの詳細に移動することもできます。

1. [ログイン] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>サインインします。
2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。
3. [**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。 そのフライアウト ウィンドウが開きます。
4. フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査ページを開く]** を選択して、調査の詳細を表示します。
   - [承認 **] を** 選択して保留中のアクションを開始します。
   - 保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。
   - [Go **hunt] を** 選択して高度な [ハンティングに入る](advanced-hunting-overview.md)。

### <a name="open-an-investigation-from-an-incident-details-page"></a>インシデントの詳細ページから調査を開く

インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。

1. [ログイン] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>サインインします。
2. ナビゲーション ウィンドウで、[インシデント] を選択 **し、[インシデント&通知** \> **します**。
3. リストでアイテムを選択し、[インシデント ページを開 **く] を選択します**。
4. [調査 **] タブを** 選択し、一覧で調査を選択します。 そのフライアウト ウィンドウが開きます。
5. [調査 **ページを開く] を選択します**。

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 調査の詳細ビューの画像は次のようになります。

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

> [!NOTE]
> 調査の詳細ページに表示される特定のタブは、サブスクリプションに含まれる内容によって異なります。 たとえば、サブスクリプションに Microsoft Defender for Office 365プラン 2 が含まれる場合、[メールボックス] タブ **は表示** されません。

|タブ|説明|
|---|---|
|**Investigation graph (調査グラフ)**|調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。 <p> グラフ上のアイテムを選択すると、詳細を表示できます。 たとえば、[証拠]**アイコンを** 選択すると、[証拠]タブに移動し、検出されたエンティティとその評決を確認できます。|
|**アラート**|調査に関連する警告を一覧表示します。 アラートは、ユーザーのデバイス、Office アプリ、Defender for Cloud Apps、その他のセキュリティ機能の脅威保護機能Microsoft 365 Defenderがあります。|
|**Devices**|調査に含まれるデバイスとその修復レベルを一覧表示します。 (修復レベルは、デバイス グループ [のオートメーション レベルに対応します](automation-levels.md)。)|
|**メールボックス**|検出された脅威の影響を受けたメールボックスを一覧表示します。|
|**ユーザー**|検出された脅威の影響を受けたユーザー アカウントを一覧表示します。|
|**証拠**|アラート/調査によって発生した証拠の一部を一覧表示します。 評決 (悪意のある、疑 *わしい、* または脅威が見 *つからない*) と修復の状態が含まれます。|
|**Entities**|各エンティティの種類 (悪意のある、疑わしい、または脅威が見つからない)の評決を含む、分析された各エンティティの詳細 *を提供します*。|
|**Log**|アラートがトリガーされた後に行ったすべての調査アクションの時系列的で詳細なビューを提供します。|
|**Pending actions (保留中のアクション)**|続けるには承認を必要とするアイテムを一覧表示します。 アクション センター ( ) に移動 <https://security.microsoft.com/action-center> して、保留中のアクションを承認します。|

## <a name="see-also"></a>関連項目

- [自動調査後の修復アクションの確認](manage-auto-investigation.md)
- [Microsoft Defender for Endpoint インシデント キューを表示して整理する](view-incidents-queue.md)
