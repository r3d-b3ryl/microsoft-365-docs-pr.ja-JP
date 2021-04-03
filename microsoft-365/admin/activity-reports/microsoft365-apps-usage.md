---
title: 管理センターの Microsoft 365 レポート - Microsoft 365 Apps の使用状況
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Microsoft 365 管理センターの Microsoft 365 レポート ダッシュボードを使用して、使用状況レポート用の Microsoft 365 アプリを取得する方法について説明します。
ms.openlocfilehash: 362697ba8dd40a12107e1b2d9ad6ef1bededda7d
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579580"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>管理センターの Microsoft 365 レポート - Microsoft 365 Apps の使用状況

Microsoft 365 の [**レポート**] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。

 たとえば、Microsoft 365 Apps アプリを使用するライセンスを受け取った各ユーザーのアクティビティを理解するには、アプリ全体でのアクティビティと、プラットフォーム間での利用方法を確認します。


 > [!NOTE]
 > レポートを表示するには、Microsoft 365 または Exchange、SharePoint、または Skype for Business 管理者のグローバル管理者、グローバル リーダー、またはレポート リーダーである必要があります。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps 利用状況レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

 2. [レポート **の選択] ドロップダウンから****、[365 Microsoft 365** Apps Office使用]   \>  **を選択します**。

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps 利用状況レポートの解釈

ユーザーとプラットフォームのグラフを見て、ユーザーの Microsoft 365 Apps アクティビティ **のビューを****取得** できます。

![Microsoft 365 Apps 利用状況レポート](../../media/proplususagenumbers.png)

|アイテム|説明|
 |:-----|:-----|
 |1. <br/> |**Microsoft 365 Apps** 利用状況レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。 <br/> |
 |2. <br/> |各レポートのデータは、通常、過去 7 日間までカバーされます。 <br/> |
 |3。 <br/> |[ **ユーザー]** ビューには、Outlook、Word、Excel、PowerPoint、OneNote、Teams の各アプリのアクティブ ユーザー数の傾向が表示されます。 "アクティブ ユーザー" は、これらのアプリ内で意図的なアクションを実行するユーザーです。 <br/> |
 |4. <br/> |[ **プラットフォーム] ビュー** には、Windows、Mac、Web、およびモバイルの各プラットフォームのすべてのアプリでアクティブ ユーザーの傾向が表示されます。 <br/> |
 |5.<br/>|[ユーザー **] グラフ** の Y 軸は、それぞれのアプリの一意のアクティブ ユーザーの数です。 [プラットフォーム **] グラフ**   の Y 軸は、それぞれのプラットフォームの一意のユーザー数です。 両方のグラフの X 軸は、特定のプラットフォームでアプリが使用された日付です。<br/>|
 6.<br/>|凡例の項目を選択して、グラフに表示する系列をフィルター処理できます。 たとえば、[ユーザー] グラフ **で** 、[Outlook]、Word、Excel、PowerPoint、OneDrive、または Teams を選択して、それぞれに関連する情報のみを表示します。 この選択を変更しても、下のグリッド テーブルの情報は変更されません。|
 |7.<br/>|テーブルには、ユーザー レベルでのデータの内訳が表示されます。 テーブルの列は追加または削除できます。 <br/><br/>**ユーザー** 名は、Microsoft Apps でアクティビティを実行したユーザーの電子メール アドレスです。<br><br/>**最後のライセンス認証日 (UTC)** は、ユーザーが Microsoft 365 Apps サブスクリプションをアクティブ化した最新の日付です。<br/><br/>**最後のアクティビティ日付 (UTC)** は、ユーザーが意図的なアクティビティを実行した最新の日付です。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。<br/><br/>次の列は、選択した期間にユーザーがアプリでアクティブだった場合を識別する各アプリに対応します。<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> 次の列は、選択した期間にユーザーが任意のアプリ (Microsoft 365 Apps 内) のプラットフォームでアクティブだった場合を識別する各プラットフォームに対応しています。<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (Web)** <br>**Outlook (Mobile)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Web)**<br> **Word (Mobile)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (Web)**<br> **Excel (Mobile)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Web)**<br> **PowerPoint (Mobile)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (Web)**<br>**OneNote (Mobile)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (Web)**<br>**Teams (Mobile)** |
 |8.<br/>|[列の **管理] アイコンを** 選択して、レポートの列を追加または削除します。|
 |9.<br/>|また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、およびフィルター処理を実行して、さらに分析できます。 ユーザー数が 100 人未満の場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行えます。 ユーザーが 100 人を超える場合は、フィルター処理と並べ替えを行う場合は、データをエクスポートする必要があります。|
