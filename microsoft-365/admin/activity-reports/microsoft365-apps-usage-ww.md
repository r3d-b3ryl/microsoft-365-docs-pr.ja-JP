---
title: アプリ使用状況レポートをMicrosoft 365 管理センターする
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Microsoft 365 Apps使用状況レポートを取得して、アプリ全体のライセンスユーザー アクティビティと、プラットフォーム間でのアプリの使用方法を確認する方法について説明します。
ms.openlocfilehash: 0a3545c71627c666249b91f2080603ea32ae30f0
ms.sourcegitcommit: 5014666778b2d48912c68c2e06992cdb43cfaee3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66662726"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>管理センターの Microsoft 365 レポート - Microsoft 365 Apps使用状況

Microsoft 365 の [レポート] ダッシュボードには、組織内での製品全体に関するアクティビティが表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。

たとえば、Microsoft 365 Apps アプリを使用するライセンスを持つ各ユーザーのアクティビティを理解するには、アプリ全体のアクティビティと、プラットフォーム間での利用状況を確認します。

> [!NOTE]
> このレポートには、共有コンピューターのライセンス認証は含まれません。

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps使用状況レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
2. ダッシュボードのホームページで、アクティブユーザー - Microsoft 365 Apps カードの **[その他の表示**] ボタンをクリックします。

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Microsoft 365 Apps使用状況レポートを解釈する

ユーザー **と****プラットフォーム** のグラフを見ると、ユーザーのMicrosoft 365 Appsアクティビティを確認できます。

> [!div class="mx-imgBorder"]
> ![使用状況レポートをMicrosoft 365 Appsします。](../../media/0bcf67e6-a6e4-4109-a215-369f9f20ad84.png)

**Microsoft 365 Apps使用状況** レポートは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。

各レポートのデータは、通常、過去 2 日間まで対象となります。 6 日ごとに、データ品質を確保するために、レポートをマイナー更新で更新します。

**[ユーザー]** ビューには、Outlook、Word、Excel、PowerPoint、OneNote、Teams の各アプリのアクティブ ユーザー数の傾向が表示されます。 "アクティブ ユーザー" とは、これらのアプリ内で意図的な操作を実行するユーザーのことです。

**[プラットフォーム]** ビューには、Windows、Mac、Web、Mobile の各プラットフォームのすべてのアプリにわたるアクティブ ユーザーの傾向が表示されます。

[ユーザー] グラフの Y 軸は、それぞれのアプリの一意のアクティブなユーザーの数です。 プラットフォーム グラフの Y 軸は、それぞれのプラットフォームの一意のユーザーの数です。 両方のグラフの X 軸は、特定のプラットフォームでアプリが使用された日付です。

凡例の項目を選択して、グラフに表示する系列をフィルター処理できます。 たとえば、[ユーザー] グラフで Outlook、Word、Excel、PowerPoint、OneDrive、または Teams を選択すると、それぞれに関連する情報のみが表示されます。 この選択を変更しても、その下にあるグリッド テーブルの情報は変更されません。

テーブルには、ユーザー レベルでのデータの内訳が表示されます。 テーブルの列は追加または削除できます。


|アイテム|説明|
|---|---|
|Username|Microsoft Appsでアクティビティを実行したユーザーの電子メール アドレス。|
|最終アクティブ化日 (UTC)|ユーザーがコンピューターでMicrosoft 365 Appsサブスクリプションをアクティブ化した最新の日付、または共有コンピューターにログオンし、自分のアカウントでアプリを起動します。|
|最終アクティビティ日 (UTC)|意図的なアクティビティがユーザーによって実行された最新の日付。 特定の日付に発生したアクティビティを表示するには、直接グラフ内の日付を選択します。|


他の列では、選択した期間内に (Microsoft 365 Apps 内で) そのアプリのそのプラットフォームでユーザーがアクティブであったかどうかを識別します。

[ **列の選択]** アイコンを選択して、レポートの列を追加または削除します。

また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、簡単な集計、並べ替え、フィルター処理を実行して詳細な分析を行うことができます。 