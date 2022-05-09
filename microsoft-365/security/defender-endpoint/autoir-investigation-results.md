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
author: dansimp
ms.author: dansimp
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
ms.openlocfilehash: 294722f3f79172e06752c5318bfef21dfc640eed
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327631"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>自動調査の詳細と結果を表示する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpointでは、自動調査が実行されると、[その調査](automated-investigations.md)に関する詳細は、自動調査プロセス中と自動調査後の両方で利用できます。 必要なアクセス許可を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。 調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。

## <a name="new-unified-investigation-page"></a>(NEW!)統合調査ページ

調査ページが最近更新され、デバイス、電子メール、コラボレーション コンテンツ全体の情報が含まれています。 新しい統合調査ページでは、共通言語が定義され、[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)と[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)全体で自動調査を行うための統合エクスペリエンスが提供されます。

> [!TIP]
> 変更点の詳細については、 [(NEW!) を参照してください。統合調査ページ](/microsoft-365/security/mtp/mtp-autoir-results)。

## <a name="open-the-investigation-details-view"></a>調査の詳細ビューを開く

調査の詳細ビューを開くには、次のいずれかの方法を使用できます。

- [アクション センターでアイテムを選択する](#select-an-item-in-the-action-center)
- [インシデントの詳細ページから調査を選択する](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>アクション センターでアイテムを選択する

改善された [アクション センター](auto-investigation-action-center.md) では、デバイス間の [修復アクション](manage-auto-investigation.md#remediation-actions) 、電子メール&コラボレーション コンテンツ、ID がまとめられます。 一覧表示されるアクションには、自動的または手動で実行された修復アクションが含まれます。 アクション センターでは、承認待ちのアクションと、既に承認または完了したアクションを表示できます。 調査ページなど、詳細に移動することもできます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> に移動してサインインします。
2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。
3. [**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。 ポップアップ ウィンドウが開きます。
4. ポップアップ ウィンドウで情報を確認し、次のいずれかの手順を実行します。
   - [ **調査を開く] ページ** を選択して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中のアクションが実行されないようにするには、[ **拒否] を** 選択します。
   - [ **Go hunt** ] を選択して [高度なハンティング](advanced-hunting-overview.md)に移動します。

### <a name="open-an-investigation-from-an-incident-details-page"></a>インシデントの詳細ページから調査を開く

インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> に移動してサインインします。
2. ナビゲーション ウィンドウで、[インシデント& **アラート** \> **インシデント**] を選択します。
3. 一覧で項目を選択し、[ **インシデント ページを開く**] を選択します。
4. [調査] タブ **を** 選択し、一覧で調査を選択します。 ポップアップ ウィンドウが開きます。
5. [ **調査ページを開く]** を選択します。

## <a name="investigation-details"></a>調査の詳細

調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。 調査の詳細ビューの画像は次のようになります。

調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。

> [!NOTE]
> 調査の詳細ページに表示される特定のタブは、サブスクリプションに含まれる内容によって異なります。 たとえば、サブスクリプションにプラン 2 Microsoft Defender for Office 365含まれていない場合、[**メールボックス]** タブは表示されません。

|タブ|説明|
|---|---|
|**Investigation graph (調査グラフ)**|調査を視覚的に表します。 エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。 <p> グラフ上の項目を選択すると、詳細を表示できます。 たとえば、[ **証拠** ] アイコンを選択すると、[ **証拠** ] タブに移動し、検出されたエンティティとその評決を確認できます。|
|**アラート**|調査に関連する警告を一覧表示します。 アラートは、ユーザーのデバイス上または Office アプリ内の脅威対策機能、Defender for Cloud Apps、その他の Microsoft 365 Defender 機能により出されます。|
|**Devices**|調査に含まれるデバイスとその修復レベルを一覧表示します。 (修復レベルは [、デバイス グループの自動化レベルに](automation-levels.md)対応します)。|
|**メールボックス**|検出された脅威の影響を受けるメールボックスを一覧表示します。|
|**Users**|検出された脅威の影響を受けるユーザー アカウントを一覧表示します。|
|**証拠**|アラート/調査によって発生した証拠の一部を一覧表示します。 判定 (*悪意のある*、 *疑わしい*、または *脅威が見つかりません*) と修復状態が含まれます。|
|**Entities**|各エンティティの種類 (*悪意のある*、 *疑わしい*、または *脅威が見つかりません*) の判定など、分析された各エンティティの詳細を提供します。|
|**Log**|アラートがトリガーされた後に実行されたすべての調査アクションの時系列的で詳細なビューを提供します。|
|**Pending actions (保留中のアクション)**|続けるには承認を必要とするアイテムを一覧表示します。 アクション センター (<https://security.microsoft.com/action-center>) に移動して、保留中のアクションを承認します。|

## <a name="see-also"></a>関連項目

- [自動調査後の修復アクションを確認する](manage-auto-investigation.md)
- [Microsoft Defender for Endpoint インシデント キューを表示して整理する](view-incidents-queue.md)
