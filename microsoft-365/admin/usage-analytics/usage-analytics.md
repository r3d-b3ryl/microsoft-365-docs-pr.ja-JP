---
title: Microsoft 365 利用状況分析
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: コミュニケーションとコラボレーションのために、組織がMicrosoft 365サービスをどのように採用しているかを概説します。
ms.openlocfilehash: f641e2b99e2d61881eb86506a1770f4401cb98bc
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572335"
---
# <a name="microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析

Power BI内Microsoft 365利用分析を使用して、組織がMicrosoft 365内のさまざまなサービスをどのように採用しているかについての洞察を得ます。 Microsoft 365利用データを視覚化および分析し、カスタム レポートを作成し、組織内でインサイトを共有できます。 また、特定の地域や部門がどのようにMicrosoft 365を使用しているかを把握することもできます。
  
Microsoft 365使用状況分析では、過去 12 か月間の製品間ビューを提供し、多数の事前作成済みレポートを含む、事前構築済みのダッシュボードにアクセスできます。 各レポートからは、特定の利用状況に関する洞察が得られます。 ユーザー固有の情報は、最後の完全な暦月に使用できます。
  
テンプレート アプリを有効にする [データ モデル](usage-analytics-data-model.md) には、Active Directory のユーザー属性が含まれており、特定のレポートでピボットを実行できます。 Active Directory 属性には、場所、部門、および組織が含まれます。 
  
データ収集を開始する方法については、[Microsoft 365 利用状況分析の有効化](enable-usage-analytics.md)に関するページを参照してください。 
  
Microsoft 365使用状況分析には、次のセクションで詳しく説明する多数のレポートが含まれています。 

データ テーブルを選択すると、各領域の詳細レポートにアクセスできます。 サイトの下部にあるタブを選択すると、事前に作成されたすべてのレポートを表示できます。 詳細な手順については、「 [レポートの移動と利用](navigate-and-utilize-reports.md) 」および [「レポートのカスタマイズ」を](customize-reports.md)参照してください。

## <a name="executive-summary"></a>エグゼクティブサマリー

エグゼクティブ サマリーは、ビジネスの導入、利用、モビリティ、コミュニケーション、コラボレーション、ストレージに関するレポートに関するMicrosoft 365の概要を一目で把握し、ビジネスの意思決定者を対象としています。 有効にされたすべてのユーザーとアクティブなユーザーに基づいて、個々のサービスがどのように使用されているかを確認できます。 レポートに表示される月のすべての値は、最新の完全な月を参照します。 

この概要を使用すると、Officeの使用パターンと、従業員が共同作業を行っている方法と場所を簡単に把握できます。

![Microsoft 365の使用状況エグゼクティブ サマリーのイメージ。](../../media/office365usage-exec-summary.png)

## <a name="overview"></a>概要

Microsoft 365概要レポートには、次のレポートが含まれています。 レポート ページの上部にあるタブを選択すると、表示できます。 レポートの上部に表示される月のすべての値は、最新の完全な月を参照します。

- **採用** &ndash; 導入傾向の概要を示します。 このセクションのレポートを使用して、ユーザーがMicrosoft 365をどのように採用したか、また各サービスの全体的な使用状況が月ごとにどのように変化したかを確認します。 ユーザーが有効になる方法、組織内でMicrosoft 365をアクティブに使用しているユーザーの数、ユーザーを返すユーザー数、および製品を初めて使用するユーザー数を確認できます。

- **使用法** &ndash; 過去 12 か月間のアクティブ ユーザーのボリュームと各製品の主要な活動をドリルダウン表示できます。 このセクションのレポートを使用して、組織内のユーザーがMicrosoft 365をどのように使用しているかを確認します。

- **コミュニケーション** &ndash;組織内のユーザーが、Teams、Yammer、電子メール、またはSkype通話を使用して連絡を取り合うことを好むかどうかを一目で確認できます。 コミュニケーションツールの使用パターンが従業員間で変化しているかどうかが確認できます。 

- **コラボレーション** &ndash;組織内のユーザーがOneDriveとSharePointを使用してドキュメントを保存し、互いに共同作業を行う方法、およびこれらの傾向が月々にどのように進化していくのかを確認します。 また、内部または外部で共有されているドキュメントの数や、所有者や他の共同作業者が、アクティブに使用されているSharePointサイトまたはOneDriveアカウントの数を確認することもできます。

- **Storage** &ndash;このレポートを使用して、メールボックス、OneDrive、およびSharePoint サイトのクラウド ストレージを追跡します。

- **モビリティ** &ndash;電子メール、Teams、Skype、またはYammerへの接続に使用するクライアントとデバイスを追跡します。

## <a name="activation-and-licensing"></a>ライセンス認証とライセンス

アクティベーションとライセンスページでは、Microsoft 365アクティベーションに関するレポートが提供されます。つまり、Officeアプリをダウンロードしてアクティブにしたユーザーの数、および組織によって割り当てられたライセンスの数です。 トップに向かう月の値は現在の月を表し、メトリックは月の初めから現在の日付までの集計値を反映します。

- **アクティベーション** &ndash;組織内のサービス計画 (Microsoft 365 Apps for enterprise、Project、Visioなど) のアクティブ化を追跡します。 Office のライセンスを持つ各ユーザーは、最大 5 つのデバイスに製品をインストールできます。 また、このセクションのレポートを使用して、ユーザーがOfficeアプリをインストールしたデバイスを確認することもできます。 プランをアクティブ化するには、ユーザーがアプリをインストールし、アカウントでサインインする必要があります。

- **ライセンス** &ndash; このレポートには、ライセンスタイプの概要、各ライセンスタイプに割り当てられたユーザー数、および各月のライセンス割り当て配布が含まれます。 トップに向かう月の値は現在の月を表し、メトリックは月の初めから現在の日付までの集計値を反映します。

## <a name="product-usage"></a>製品の使用

このレポートには、Exchange、Microsoft 365 グループ、OneDrive、SharePoint、Skype、Teams、Yammerなど、各Microsoft 365 サービスに対する個別のレポートが含まれます。 各レポートには、有効なユーザー レポートとアクティブなユーザーレポートの合計数、メールボックス、サイト、グループ、アカウントなどのエンティティの数、および必要に応じてアクティビティタイプレポートが含まれます。 レポートの上部に表示される月のすべての値は、最新の完全な月を参照します。

## <a name="user-activity"></a>ユーザー アクティビティ

ユーザー アクティビティ レポートは、特定のサービスに対して使用できます。 これらのレポートは、Active Directory 属性と結合されたユーザー レベルの詳細使用状況データを提供します。 さらに、部門導入レポートでは、Active Directory 属性ごとにスライスできるため、個々のサービス全体でアクティブなユーザーを表示できます。 すべてのメトリックは、最新の完全な月に集計されます。

## <a name="faq"></a>FAQ

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a>このテンプレートアプリは購入を通じて利用可能になるのですか、それとも無料ですか?

それは無料ではありません、あなたはPower BI Proライセンスが必要になります。 詳細については、テンプレート アプリのインストール、カスタマイズ、および配布の [前提条件](/power-bi/service-template-apps-install-distribute#prerequisites) を参照してください。

ダッシュボードを他のユーザーと共有するには、「 [ダッシュボードとレポートの共有](/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports)」を参照してください。
### <a name="is-the-usage-summary-reports-reader-role-enough-to-view-the-usage-analytics"></a>利用状況の概要レポート閲覧者ロールは、利用状況分析を表示するのに十分ですか。

使用状況の概要レポート閲覧者ロールでは、使用状況分析でのテナント レベルの集計にのみアクセスMicrosoft 365許可されます。  変更管理と導入を担当するが、必ずしも IT 管理者ではないすべてのユーザーに対しては、レポート閲覧者または使用状況の概要レポート閲覧者ロールをお勧めします。

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a>誰が Microsoft 365 利用状況分析に接続できますか。

テンプレート アプリへの接続を確立するには、**グローバル管理者****、Exchange管理者****、Skype for Business管理者****、SharePoint管理者**、**グローバル リーダー** 、または **レポート リーダー** のいずれかである必要があります。 詳細については、「 [管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。

### <a name="who-can-customize-the-usage-analytics-reports"></a>使用状況分析レポートをカスタマイズWho。

テンプレート アプリに最初に接続したユーザーのみが、レポートをカスタマイズしたり、Power BI Web インターフェイスで新しいレポートを作成したりできます。 詳しくは[、Microsoft 365利用状況分析のレポートのカスタマイズ](customize-reports.md)を参照してください。

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a>Power BI Web インターフェイスからのみレポートをカスタマイズできますか。

Power BI Web インターフェイスからレポートをカスタマイズするだけでなく、Power BI Desktopを使用してMicrosoft 365レポート サービスに直接接続して独自のレポートを作成することもできます。

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a>このダッシュボードに関連付けられている pbit ファイルはどのような方法で取得できますか。

この pbit ファイルは [、Microsoft ダウンロード センター](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)からアクセスできます。

### <a name="who-can-view-the-dashboards-and-reports"></a>Whoダッシュボードとレポートを表示できますか。

テンプレート アプリに接続している場合は、 [共有機能](/power-bi/collaborate-share/service-share-dashboards)を使用して、誰とでも共有できます。 Power BIライセンスでは、ダッシュボードを共有するユーザーとユーザーの両方がPower BI ProまたはPower BI Premiumされている必要があります。

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a>ダッシュボードは誰でも共有できますか。または、ダッシュボードに接続したユーザーに限られますか。

ダッシュボードを共有する場合、ユーザーがダッシュボードを他のユーザーと再共有できるように設定できます。 このオプションは共有時に設定できます。

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a>同じテンプレート アプリをグループの人たちと一緒に操作したりカスタマイズしたりすることは可能ですか?

はい。 管理者グループが同じテンプレート アプリで共同作業を行えるようにするには、Power BIのアプリ ワークスペース機能を活用して、詳細については、「[ダッシュボードとレポートの共同作業と共有方法](/power-bi/collaborate-share/service-how-to-collaborate-distribute-dashboards-reports)」をご覧ください。 

### <a name="for-which-timeframe-is-data-available"></a>データはどの時間枠で利用できますか。

レポートの大半は、過去 12 か月のデータを表示します。 ただし、異なる製品やレポートのデータ収集が異なる時間に開始され、12 か月間のデータが利用できない可能性があるため、グラフの一部のグラフでは、履歴が少なくなることがあります。 すべてのレポートは、最終的に最大12ヶ月の歴史を構築します。 ユーザー レベルの詳細を表示するレポートには、前の完全な月のデータが表示されます。

### <a name="what-data-is-included-in-the-template-app"></a>テンプレート アプリにはどのようなデータが含まれていますか?

テンプレート アプリのデータは、現在、 [アクティビティ レポート](../activity-reports/activity-reports.md)で使用できるアクティビティ メトリックと同じセットをカバーしています。 アクティビティ レポートにレポートが追加されると、今後のリリースでテンプレート アプリに追加されます。

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a>テンプレート アプリのデータと使用状況レポートのデータの違い

テンプレート アプリに表示される基になるデータは、Microsoft 365管理センターのアクティビティ レポートに表示されるデータと一致します。 主な違いは、管理センターのデータは過去 7/30/90/180 日間利用可能であり、テンプレート アプリは月単位で最大 12 か月間データを表示することです。

さらに、テンプレート アプリのユーザー レベルの詳細は、製品ライセンスを割り当てられ、アクティビティを実行したユーザーの最後の月にだけ利用できます。

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a>テンプレート アプリを使用するタイミングと使用状況レポートをいつ使用する必要がありますか。

[アクティビティ レポート](../activity-reports/activity-reports.md)は、Microsoft 365の使用と採用を理解するための出発点として適しています。 テンプレート アプリは、Microsoft 365の使用状況データと組織の Active Directory 情報を組み合わせて使用し、管理者がPower BIのビジュアル分析機能を使用してデータ セットを分析できるようにします。 これにより、管理者はMicrosoft 365利用状況データを視覚化して分析するだけでなく、部門や場所などの Active Directory プロパティでスライスすることもできます。また、カスタム レポートを作成し、組織内でインサイトを共有することもできます。 

### <a name="how-often-is-the-data-refreshed"></a>データはどのくらいの頻度で更新されますか。 

初めてテンプレート アプリに接続すると、前の 12 か月間のデータが自動的に入力されます。 その後、テンプレート アプリのデータは毎週更新されます。 お客様は、このデータの使用が異なる更新リズムを必要とする場合に、更新スケジュールを変更することを選択できます。

バックエンド Microsoft 365 サービスは、毎日データを更新し、現在の日付から 5 ~ 8 日間の間にデータを提供します。

各データセットの **[コンテンツの日付** ] 列は、テンプレート アプリのデータの更新日を表します。

### <a name="how-is-an-active-user-defined"></a>アクティブなユーザーはどのように定義されますか?

アクティブユーザーの定義は、アクティビティレポートの [アクティブユーザー](../activity-reports/active-users.md) の定義と同じです。

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a>SharePoint レポートにはどのような SharePoint サイト コレクションが含まれていますか。

テンプレート アプリの現在のバージョンには、チーム サイトSharePoint、グループ サイトSharePointファイル アクティビティが含まれています。

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a>Microsoft 365 グループ使用状況レポートに含まれるグループ

テンプレート アプリの現在のバージョンには、Outlook グループ、Yammer グループ、およびSharePoint グループからの使用状況が含まれています。 Microsoft Teamsまたはプランナーに関連するグループは含まれません。

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a>テンプレート アプリの更新バージョンが利用可能になるのはいつですか?

テンプレート アプリの大幅な変更は年に 2 回リリースされ、新しいレポートや新しいデータが含まれる可能性があります。 レポートに対するマイナーな変更は、より頻繁にリリースされる可能性があります。

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a>テンプレート アプリのデータを既存のソリューションに統合することは可能ですか。 

テンプレート アプリのデータは、Microsoft 365 API を使用して取得できます (プレビュー)。 実稼働に出荷されると[、Microsoft Graphレポート API](https://go.microsoft.com/fwlink/p/?linkid=848843)内にマージされます。 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a>テンプレート アプリを拡張して、他の Microsoft 製品の使用状況データを表示する予定はありますか。

これは、将来の改善のために考慮されます。 [Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)で更新を確認してください。

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a>Active Directory で会社情報をピボットする方法はありますか。

会社情報は、テンプレート アプリの Active Directory フィールドの 1 つが含まれており、 **製品ユーザー アクティビティ** レポートで事前に作成されたフィルターとして表示できます。 これは、 **ユーザー状態** テーブルの列として使用できます。

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a>Active Directory からその他のフィールドを持ち込むことはできますか。

このデータに対する追加のカスタマイズは[、Microsoft Graph レポート API](https://go.microsoft.com/fwlink/p/?linkid=848843)に接続して、Azure Active Directoryから追加のフィールドを取得し、データセットに結合することで可能です。 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a>テンプレート アプリの情報を複数のサブスクリプションに集約することはできますか。

この時点では、テンプレート アプリは、最初に接続するために使用された資格情報に関連付けられているため、1 つのサブスクリプション用です。

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a>プラン(E1、E3)での使用状況を確認できますか?

テンプレート アプリでは、使用量は製品単位で表されます。 ユーザーに割り当てられたさまざまなサブスクリプションに関するデータが提供されていますが、ユーザーのアクティビティをユーザーに割り当てられたサブスクリプションに関連付けすることはできません。

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a>他のデータセットをテンプレートアプリに統合することは可能ですか?

Power BI Desktopを使用して Microsoft 365 API に接続 (プレビュー表示) して、テンプレート アプリ データと組み合わせる追加のデータ ソースを作成できます。

詳細については、 [カスタマイズ 文書](customize-reports.md)を参照してください。

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a>特定の期間の"トップユーザー"レポートを見ることは可能ですか?

すべてのユーザー レベル レポートには、前月の集計データが表示されます。

### <a name="will-the-template-app-be-localized"></a>テンプレート アプリはローカライズされますか? 

これは現在、ロードマップにはありません。

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a>自分の組織に関して表示されるデータについてわからない点があります。誰に質問すればよいですか。

管理センターのアクティビティ概要ページの [フィードバック] ボタンを使用するか、サポート [ケース](../../business-video/get-help-support.md) を開いてテンプレート アプリのヘルプを表示できます。 

### <a name="how-can-partners-access-the-data"></a>パートナーはどのような方法でデータにアクセスできますか。

パートナーが管理者権限を委任している場合、パートナーは顧客の代わりにテンプレート アプリに接続できます。

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a>ユーザー、グループ、レポート内のサイト名など、身元を特定できる情報を非表示にできますか。

はい、 [収集されたデータを匿名にする](enable-usage-analytics.md#make-the-collected-data-anonymous)を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 利用状況分析を有効にする](enable-usage-analytics.md) (記事)

[使用状況分析でレポートを移動して利用Microsoft 365](navigate-and-utilize-reports.md) (記事)

[Microsoft 365で使用状況レポートを確認](../../business-video/act-on-report.md)する (ビデオ)