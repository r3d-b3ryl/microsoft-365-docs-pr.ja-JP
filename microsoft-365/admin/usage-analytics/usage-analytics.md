---
title: Microsoft 365 利用状況分析
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: 組織が Microsoft 365 サービスを採用して通信および共同作業を行う方法の概要について説明します。
ms.openlocfilehash: 783b2c599a5f3a31446855450029859e6dfd9f65
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626936"
---
# <a name="microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析
---
Microsoft 365 usage analytics は、Microsoft 365 US Government Community ではまだ利用できません。
 
## <a name="overview-of-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析の概要

Power BI 内の Microsoft 365 usage analytics を使用して、組織が Microsoft 365 内で通信および共同作業を行うさまざまなサービスをどのように採用しているかを把握します。 Microsoft 365 使用状況データの視覚化と分析、カスタムレポートの作成、組織内での insights の共有、および特定の地域または部署がどのように Microsoft 365 を利用しているかを把握することができます。
  
Microsoft 365 usage analytics は、過去12か月間のクロス積ビューを提供し、多数の事前に作成されたレポートを含む、作成済みのダッシュボードへのアクセスを提供するテンプレートアプリです。 各レポートからは、特定の利用状況に関する洞察が得られます。 ユーザー固有情報は最後の暦月全体に対して利用できます。
  
テンプレートアプリを構成する[データモデル](usage-analytics-data-model.md)には、Active Directory からのユーザー属性が含まれているため、特定のレポートでピボットすることができます。 Active Directory 属性の場所、部署、組織が含まれます。 
  
データ収集を開始する方法については、[Microsoft 365 利用状況分析の有効化](enable-usage-analytics.md)に関するページを参照してください。 
  
Microsoft 365 usage analytics には、以下のセクションで説明するいくつかのレポートが含まれています。 

データテーブルを選択すると、各エリアの詳細なレポートにアクセスできます。 レポートを表示した後、サイトの下部にあるタブを選択することで、事前に作成されたすべてのレポートを表示できます。 詳細な手順については、「 [microsoft 365 usage analytics」の「レポートへの移動と利用](navigate-and-utilize-reports.md)」、および「 [microsoft 365 usage analytics でのレポートのカスタマイズ](customize-reports.md)」を参照してください。

## <a name="executive-summary"></a>エグゼクティブの概要

エグゼクティブサマリーは、Microsoft 365 のビジネス導入、使用状況、モビリティ、コミュニケーション、コラボレーション、およびストレージレポートの概要を示した概要であり、ビジネス意思決定者を対象としています。 これにより、有効になっているすべてのユーザーと、アクティブなユーザーに基づいて、いくつかの個別のサービスがどのように使用されているかを確認できます。 レポートに表示される月のすべての値は、最後の完全な月を表します。 

この要約により、Office の使用パターンと、従業員が共同作業する方法と場所をすばやく理解できます。

![Microsoft 365 利用状況の概要の画像。](../../media/office365usage-exec-summary.png)

## <a name="overview"></a>概要

Microsoft 365 の概要レポートには、次のレポートが含まれています。 [レポート] ページの上部にあるタブを選択すると、それらを表示できます。 レポートの上部セクションに表示されている月のすべての値は、最後の完全な月を表します。

- **導入** &ndash;は、導入傾向の概要を提供します。 このセクションのレポートを使用して、ユーザーが Microsoft 365 を採用した方法と、個々のサービスの全体的な使用状況が月ごとにどのように変更されたかについて説明します。 ユーザーがどのように有効になっているか、組織内で Microsoft 365 を使用しているユーザー数、ユーザーが初めて何を使用しているか、何人がその製品を初めて使用しているかを確認することができます。

- [**使用状況]** &ndash;過去12か月間に、アクティブなユーザーの数と各製品の主要なアクティビティについてのドリルダウンビューを提供します。 このセクションのレポートを使用して、組織内のユーザーが Microsoft 365 をどのように使用しているかについて説明します。

- 組織内のユーザーが Teams、Yammer、電子メール、または Skype 呼び出しを使用して連絡を取り続けることを希望しているかどうかを一目で確認できる**コミュニケーション** &ndash; 。 従業員の間で通信ツールを使用すると、パターンに変化があるかどうかを観察できます。 

- **コラボレーション** &ndash; [組織内のユーザーが OneDrive と SharePoint を使用してドキュメントを保存し、互いに共同作業する方法と、これらの傾向が月にわたってどのように変化するかを確認します。 また、内部または外部で共有されているドキュメント数、および現在使用されている SharePoint サイトまたは OneDrive アカウントの数を、所有者や他のコラボレーターによって分類することもできます。

- **ストレージ** &ndash;このレポートを使用して、メールボックス、OneDrive、および SharePoint サイトのクラウドストレージを追跡します。

- **Mobility** &ndash;は、ユーザーがメール、Teams、Skype、Yammer への接続に使用するクライアントとデバイスを追跡します。

## <a name="activation-and-licensing"></a>ライセンス認証とライセンス

[アクティブ化とライセンス] ページでは、Microsoft 365 ライセンス認証に関するレポートが提供されます。つまり、Office アプリをダウンロードしてアクティブ化したユーザーの数と、組織によって割り当てられたライセンスの数を示します。 上方向の月の値は現在の月を参照し、指標には月の最初から現在の日付まで集計された値が反映されます。

- **ライセンス認証** &ndash;トラックサービスプラン (たとえば、Microsoft 365 ProPlus、Project、Visio) が組織内でアクティブ化されています。 Office のライセンスを持つ各ユーザーは、最大 5 つのデバイスに製品をインストールできます。 このセクションのレポートを使用して、ユーザーが Office アプリをインストールしたデバイスを確認することもできます。 プランをアクティブにするには、ユーザーがアプリをインストールし、アカウントを使用してサインインする必要があることに注意してください。

- **Licensing** &ndash;このレポートには、ライセンスの種類の概要、各ライセンスの種類が割り当てられているユーザーの数、各月のライセンス割り当ての配分が含まれています。 上方向の月の値は現在の月を参照し、指標には月の最初から現在の日付まで集計された値が反映されます。

## <a name="product-usage"></a>製品の使用状況

このレポートには、Exchange、Microsoft 365 グループ、OneDrive、SharePoint、Skype、Teams、Yammer など、Microsoft 365 サービスごとに個別のレポートが含まれています。 各レポートには、アクティブなユーザーレポート数、メールボックス、サイト、グループ、アカウントなどのエンティティ数、および必要に応じたアクティビティの種類のレポートが含まれます。 レポートの上部セクションに表示されている月のすべての値は、最後の完全な月を表します。

## <a name="user-activity"></a>ユーザー アクティビティ

ユーザーアクティビティレポートは、特定の個別のサービスで使用できます。 これらのレポートは、Active Directory 属性で結合されたユーザーレベルの詳細な利用状況データを提供します。 また、部署導入レポートを使用すると、Active Directory の属性によってスライスすることができます。これにより、すべての個別のサービスにわたってアクティブなユーザーが表示されます。 すべての指標は、最新の完全な月を集計しています。

## <a name="faq"></a>FAQ

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a>このテンプレートアプリは購入によって利用できるようになりますか。または無料ですか。

無料ではないので、Power BI Pro ライセンスが必要になります。 詳細については、「テンプレートアプリをインストール、カスタマイズ、および配布するための[前提条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute#prerequisites)」を参照してください。

ダッシュボードを他のユーザーと共有するには、「[共有ダッシュボードとレポート](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports)」を参照してください。

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a>誰が Microsoft 365 利用状況分析に接続できますか。

テンプレートアプリへの接続を確立するには、**グローバル管理者**、 **Exchange 管理**者、 **Skype for business 管理者**、 **SharePoint 管理者**、**グローバルリーダー** 、または**レポートリーダー**のいずれかである必要があります。 詳細については、「[管理者ロールについ](../add-users/about-admin-roles.md)て」を参照してください。

### <a name="who-can-customize-the-usage-analytics-reports"></a>利用状況分析レポートをカスタマイズできるユーザー

Power BI web インターフェイスでレポートをカスタマイズするか、新しいレポートを作成することができるのは、テンプレートアプリに最初に接続したユーザーのみです。 手順について[は、「Microsoft 365 usage analytics でレポートをカスタマイズする](customize-reports.md)」を参照してください。

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a>Power BI web インターフェイスからのみレポートをカスタマイズできますか。

Power BI web インターフェイスからレポートをカスタマイズするだけでなく、Power BI Desktop を使用して直接 Microsoft 365 reporting service に接続し、独自のレポートを作成することもできます。

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a>このダッシュボードに関連付けられている pbit ファイルはどのような方法で取得できますか。

[Microsoft ダウンロードセンター](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)から pbit ファイルにアクセスできます。

### <a name="who-can-view-the-dashboards-and-reports"></a>ダッシュボードとレポートを表示できるユーザー

テンプレートアプリに接続した場合は、[共有機能](https://go.microsoft.com/fwlink/p/?linkid=845494)を使用して他のユーザーと共有できます。 Power BI のライセンスでは、ユーザーの共有とダッシュボードを共有しているユーザーの両方が Power BI Pro または Power BI Premium を持っている必要があります。

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a>ダッシュボードは誰でも共有できますか。または、ダッシュボードに接続したユーザーに限られますか。

ダッシュボードを共有する場合は、ユーザーが他のユーザーとダッシュボードを共有できるようにすることができます。 このオプションは、共有時に設定できます。

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a>同じテンプレートアプリを共同作業し、ユーザーのグループとカスタマイズすることはできますか。

はい。 管理者のグループが同じテンプレートアプリで共同作業できるようにするには、Power BI のアプリワークスペース機能を利用できます。詳細については、「[ダッシュボードとレポートをどのように連携して共有する必要がありますか?](https://go.microsoft.com/fwlink/p/?linkid=851070) 」を参照してください。 

### <a name="for-which-timeframe-is-data-available"></a>データはどの時間枠で利用できますか。

レポートの大部分は、過去12か月間のデータを表示します。 ただし、グラフの中には、さまざまな製品とレポートのデータ収集が異なる時間に開始されたために、履歴が少なくなる場合があるため、12か月分のデータを使用できない場合があります。 すべてのレポートは、最終的に12か月の履歴を作成します。 ユーザーレベルの詳細を表示するレポートには、過去の全月のデータが表示されます。

### <a name="what-data-is-included-in-the-template-app"></a>テンプレートアプリにはどのようなデータが含まれていますか。

現在、テンプレートアプリのデータは、[アクティビティレポート](../activity-reports/activity-reports.md)で使用できるものと同じアクティビティ指標のセットをカバーしています。 レポートがアクティビティレポートに追加されると、今後のリリースでテンプレートアプリに追加されます。

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a>テンプレートアプリのデータと利用状況レポートのデータはどのような違いがありますか?

テンプレートアプリに表示される基になるデータは、Microsoft 365 管理センターのアクティビティレポートに表示されるデータと一致します。 主な違いは、管理センターのデータは過去7/30/90/180 日間で利用可能であるのに対して、テンプレートアプリは、最大12か月間、月単位でデータを表示していることです。

さらに、テンプレートアプリのユーザーレベルの詳細は、製品ライセンスを割り当てられ、アクティビティを実行したユーザーの最後の完全な月に対してのみ使用できます。

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a>テンプレートアプリと利用状況レポートをいつ使用するか

[アクティビティレポート](../activity-reports/activity-reports.md)は、Microsoft 365 の使用と導入を理解するための開始点として適しています。 テンプレートアプリは、Microsoft 365 使用状況データと組織の Active Directory 情報を組み合わせて、Power BI の visual analytics 機能を使用して、管理者がデータセットを分析できるようにします。 これにより、管理者は、Microsoft 365 利用状況データを視覚化および分析するだけでなく、部署や場所などの Active Directory プロパティによってスライスすることもできます。また、カスタムレポートを作成し、組織内でその分析情報を共有することもできます。 

### <a name="how-often-is-the-data-refreshed"></a>データはどのくらいの頻度で更新されますか。 

テンプレートアプリに初めて接続すると、過去12か月間のデータが自動的に設定されます。 その後、テンプレートアプリのデータは毎週更新されます。 このデータを使用すると、更新のリズムが異なる場合は、更新スケジュールの変更を選択できます。

バックエンドの Microsoft 365 サービスは、毎日データを更新し、現在の日付から5-8 日以内のデータを提供します。

各データセットの [**コンテンツ日付**] 列は、テンプレートアプリのデータの鮮度の日付を表します。

### <a name="how-is-an-active-user-defined"></a>アクティブなユーザーがどのように定義されていますか?

アクティブユーザーの定義は、アクティビティレポートの[アクティブユーザー](../activity-reports/active-users.md)の定義と同じです。

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a>SharePoint レポートにはどのような SharePoint サイト コレクションが含まれていますか。

テンプレートアプリの現在のバージョンには、SharePoint チームサイトおよび SharePoint グループサイトのファイルアクティビティが含まれています。

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a>Microsoft 365 グループの使用状況レポートに含まれるグループ

テンプレートアプリの現在のバージョンには、Outlook グループ、Yammer グループ、および SharePoint グループからの使用法が含まれています。 Microsoft Teams や Planner に関連するグループは含まれません。

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a>更新されたバージョンのテンプレートアプリが利用可能になるのはいつですか?

テンプレートアプリに対する大きな変更は、新しいレポートまたは新しいデータを含む年に2回リリースされます。 レポートに対する小さな変更は、より頻繁にリリースされる場合があります。

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a>テンプレートアプリのデータを既存のソリューションに統合することはできますか? 

テンプレートアプリのデータは、Microsoft 365 Api (プレビュー) を使用して取得できます。 これらの製品が運用環境に出荷されると、 [Microsoft Graph レポート api](https://go.microsoft.com/fwlink/p/?linkid=848843)内にマージされます。 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a>他の Microsoft 製品の利用状況データを表示するために、テンプレートアプリを拡張する予定はありますか。

今後の改善のために考慮されます。 更新プログラムについては、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を確認してください。

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a>Active Directory で会社情報をピボットする方法はありますか。

会社情報は、テンプレートアプリの Active Directory フィールドの1つを含んでおり、**製品ユーザーアクティビティ**レポートで事前に作成されたフィルターとして表示できます。 これは、 **UserState**テーブルの列として使用できます。

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a>Active Directory からその他のフィールドを持ち込むことはできますか。

[Microsoft Graph レポート api](https://go.microsoft.com/fwlink/p/?linkid=848843)に接続することにより、Azure Active Directory から追加のフィールドを取得し、データセットに結合することで、このデータに対する追加のカスタマイズを行うことができます。 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a>複数のサブスクリプション間でテンプレートアプリの情報を集約することはできますか。

現時点では、テンプレートアプリは、最初に接続したときに使用された資格情報に関連付けられているので、1つのサブスクリプションに対して使用されます。

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a>プランの使用状況を確認することはできますか (つまり、E1, E3)?

テンプレートアプリでは、使用状況は製品レベルごとに表示されます。 ユーザーに割り当てられているさまざまなサブスクリプションに関するデータが提供されますが、ユーザーのアクティビティをユーザーに割り当てられたサブスクリプションに関連付けることはできません。

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a>他のデータセットをテンプレートアプリに統合することはできますか。

Power BI Desktop を使用して Microsoft 365 Api (プレビュー) に接続すると、追加のデータソースをテンプレートアプリのデータと組み合わせることができます。

詳細については、「[カスタマイズドキュメント](customize-reports.md)」を参照してください。

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a>特定の期間について "上位ユーザー" レポートを表示することはできますか?

すべてのユーザーレベルレポートには、前月の集計データが表示されます。

### <a name="will-the-template-app-be-localized"></a>テンプレートアプリはローカライズされますか。 

これは現在、ロードマップに含まれていません。

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a>自分の組織で表示されているデータについて特定の質問があります。 どこにアクセスできますか?

[管理センターアクティビティの概要] ページの [フィードバック] ボタンを使用するか、[サポートケース](../contact-support-for-business-products.md)を開いてテンプレートアプリのヘルプを表示することができます。 

### <a name="how-can-partners-access-the-data"></a>パートナーはどのような方法でデータにアクセスできますか。

パートナーが管理者権限を委任されている場合は、ユーザーの代わりにテンプレートアプリに接続することができます。

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a>ユーザー、グループ、レポート内のサイト名など、身元を特定できる情報を非表示にできますか。

はい。「[収集したデータを匿名で作成する](enable-usage-analytics.md#make-the-collected-data-anonymous)」を参照してください。
