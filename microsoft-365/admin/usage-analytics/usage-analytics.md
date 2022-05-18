---
title: 使用状況分析Microsoft 365について
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 77ff780d-ab19-4553-adea-09cb65ad0f1f
description: 組織がMicrosoft 365サービスを採用してコミュニケーションと共同作業を行う方法の概要を確認します。
ms.openlocfilehash: 92a6b1437fa092b54df5e10a6593d130e0808164
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467956"
---
# <a name="microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析

Power BI内でMicrosoft 365使用状況分析を使用して、組織がMicrosoft 365内のさまざまなサービスをどのように採用しているかについての洞察を得ます。 Microsoft 365使用状況データの視覚化と分析、カスタム レポートの作成、組織内の分析情報の共有を行うことができます。 また、特定のリージョンや部署がMicrosoft 365を使用している方法に関する分析情報を得ることもできます。
  
Microsoft 365使用状況分析を使用すると、過去 12 か月間の製品間ビューを提供する事前構築済みダッシュボードにアクセスでき、事前に作成された多数のレポートが含まれています。 各レポートからは、特定の利用状況に関する洞察が得られます。 ユーザー固有の情報は、最後の完全な予定表の月に使用できます。
  
テンプレート アプリを使用する [データ モデル](usage-analytics-data-model.md) には、Active Directory のユーザー属性が含まれ、特定のレポートでピボットできます。 次の Active Directory 属性が含まれます:場所、部署、および組織。 
  
データ収集を開始する方法については、[Microsoft 365 利用状況分析の有効化](enable-usage-analytics.md)に関するページを参照してください。 
  
Microsoft 365利用状況分析には、次のセクションで詳しく説明するレポートが多数含まれています。 

データ テーブルを選択すると、各領域の詳細なレポートにアクセスできます。 サイトの下部にあるタブを選択すると、すべての事前構築済みレポートを表示できます。 詳細な手順については、「[レポートのナビゲートと利用」と「レポートの](navigate-and-utilize-reports.md)[カスタマイズ](customize-reports.md)」を参照してください。

## <a name="executive-summary"></a>エグゼクティブサマリー

経営幹部の概要は、ビジネスの導入、使用状況、モビリティ、コミュニケーション、コラボレーション、ストレージのレポートのMicrosoft 365を一目で確認できる概要であり、ビジネス意思決定者向けです。 有効になっているすべてのユーザーとアクティブなユーザーに基づいて、一部の個々のサービスがどのように使用されているかを確認できます。 レポートに表示される月のすべての値は、最新の完了月を参照します。 

この概要を使用すると、Officeの使用パターンと、従業員が共同作業を行う方法と場所をすばやく理解できます。

![Microsoft 365使用状況の概要の画像。](../../media/office365usage-exec-summary.png)

## <a name="overview"></a>概要

Microsoft 365概要レポートには、次のレポートが含まれています。 レポート ページの上部にあるタブを選択すると、それらを表示できます。 レポートの上部セクションに表示される月のすべての値は、最新の完了月を参照します。

- **採用** &ndash; 導入傾向の概要を提供します。 このセクションのレポートを使用して、ユーザーがMicrosoft 365を採用した方法と、個々のサービスの全体的な使用状況が月単位でどのように変化したかを確認します。 ユーザーを有効にする方法、組織内でアクティブにMicrosoft 365を使用しているユーザーの数、ユーザーを返しているユーザーの数、および製品を初めて使用しているユーザーの数を確認できます。

- **使用** &ndash; アクティブなユーザーの量と、過去 12 か月間の各製品の主要なアクティビティのドリルダウン ビューを提供します。 このセクションのレポートを使用して、組織内のユーザーがどのようにMicrosoft 365を使用しているかを確認します。

- **通信** &ndash;組織内のユーザーが、Teams、Yammer、電子メール、またはSkypeの通話を使用して連絡を取り合うかどうかを一目で確認できます。 従業員間でコミュニケーション ツールを使用するパターンが変化しているかどうかを確認できます。 

- **コラボレーション** &ndash;組織内のユーザーがOneDriveとSharePointを使用してドキュメントを保存し、相互に共同作業する方法と、これらの傾向が月単位でどのように進化しているかを確認します。 また、内部または外部でドキュメントを共有したユーザーの数や、所有者や他のコラボレーターによって分割されたサイトまたはOneDrive アカウントSharePoint使用したユーザーの数も確認できます。

-  &ndash; Storage このレポートを使用して、メールボックス、OneDrive、SharePoint サイトのクラウド ストレージを追跡します。

- **モビリティ** &ndash;ユーザーが電子メール、Teams、Skype、またはYammerに接続するために使用するクライアントとデバイスを追跡します。

## <a name="activation-and-licensing"></a>アクティブ化とライセンス

アクティブ化とライセンスのページには、Microsoft 365ライセンス認証に関するレポートが表示されます。つまり、アプリOfficeダウンロードしてアクティブ化したユーザーの数と、組織によって割り当てられているライセンスの数です。 上部の月の値は現在の月を参照し、メトリックには月の始まりから現在の日付に集計された値が反映されます。

- **活性 化** &ndash;組織内のサービス プラン (Microsoft 365 Apps for enterprise、Project、Visioなど) のアクティブ化を追跡します。 Office のライセンスを持つ各ユーザーは、最大 5 つのデバイスに製品をインストールできます。 このセクションのレポートを使用して、ユーザーがOffice アプリをインストールしたデバイスを確認することもできます。 プランをアクティブ化するには、ユーザーがアプリをインストールし、自分のアカウントでサインインする必要があることに注意してください。

- **ライセンス** &ndash; このレポートには、ライセンスの種類の概要、各ライセンスの種類が割り当てられたユーザーの数、および各月のライセンス割り当て配布が含まれています。 上部の月の値は現在の月を参照し、メトリックには月の始まりから現在の日付に集計された値が反映されます。

## <a name="product-usage"></a>製品の使用状況

このレポートには、Exchange、Microsoft 365 グループ、OneDrive、SharePoint、Skype、Teams、Yammerなど、Microsoft 365 サービスごとに個別のレポートが含まれています。 各レポートには、有効な合計レポートとアクティブなユーザー レポートの合計数、メールボックス、サイト、グループ、アカウントなどのエンティティの数、必要に応じてアクティビティの種類レポートが含まれます。 レポートの上部セクションに表示される月のすべての値は、最新の完了月を参照します。

## <a name="user-activity"></a>ユーザー アクティビティ

ユーザー アクティビティ レポートは、特定の個々のサービスで使用できます。 これらのレポートは、Active Directory 属性と結合されたユーザー レベルの詳細使用状況データを提供します。 さらに、部門導入レポートを使用すると、Active Directory 属性をスライスして、すべての個々のサービスでアクティブなユーザーを表示できます。 すべてのメトリックは、最新の完了月に集計されます。 コンテンツの日付を表示するには、テーブル ページに移動し、TimeFrame の値がレポート期間を提供する UserActivity テーブルを選択します。 

> [!NOTE]
> グローバル リーダーと使用状況の概要レポート閲覧者には、ユーザー アクティビティ レポートを表示するアクセス許可がありません。 

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="is-this-template-app-going-to-be-available-through-purchase-or-will-it-be-free"></a>このテンプレート アプリは購入を通じて利用できますか、それとも無料ですか?

無料ではありません。Power BI Proライセンスが必要です。 詳細については、テンプレート アプリをインストール、カスタマイズ、配布するための [前提条件](/power-bi/service-template-apps-install-distribute#prerequisites) を参照してください。

ダッシュボードを他のユーザーと共有するには、 [ダッシュボードとレポートの共有に関する](/power-bi/service-how-to-collaborate-distribute-dashboards-reports#share-dashboards-and-reports)ページを参照してください。

### <a name="who-can-connect-to-microsoft-365-usage-analytics"></a>誰が Microsoft 365 利用状況分析に接続できますか。

テンプレート アプリへの接続を確立するには、**グローバル管理者**、**Exchange管理者**、**Skype for Business管理者**、**SharePoint管理者**、**グローバル リーダー**、**レポート リーダー**、**使用状況サマリー レポート リーダー** のいずれかである必要があります。 詳細については、「 [管理者ロールについて](../add-users/about-admin-roles.md) 」を参照してください。 **注:** **グローバル 閲覧者** と **使用状況の概要レポート閲覧者** は、Microsoft 365利用状況分析のテナント レベルの集計へのアクセスのみを許可し、ユーザー アクティビティ レポートを表示する権限がありません。 

### <a name="who-can-customize-the-usage-analytics-reports"></a>利用状況分析レポートWhoカスタマイズできますか?

テンプレート アプリへの初期接続を行ったユーザーのみが、Power BI Web インターフェイスでレポートをカスタマイズしたり、新しいレポートを作成したりできます。 手順については、[Microsoft 365利用状況分析のレポートのカスタマイズ](customize-reports.md)に関するページを参照してください。

### <a name="can-i-only-customize-the-reports-from-the-power-bi-web-interface"></a>Power BI Web インターフェイスからのみレポートをカスタマイズできますか?

ユーザーは、Power BI Web インターフェイスからレポートをカスタマイズするだけでなく、Power BI Desktopを使用してMicrosoft 365レポート サービスに直接接続して独自のレポートを作成することもできます。

### <a name="how-can-i-get-the-pbit-file-that-this-dashboard-is-associated-with"></a>このダッシュボードに関連付けられている pbit ファイルはどのような方法で取得できますか。

[Microsoft ダウンロード センター](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)から pbit ファイルにアクセスできます。 

### <a name="who-can-view-the-dashboards-and-reports"></a>ダッシュボードとレポートWho表示できますか?

テンプレート アプリに接続している場合は、共有機能を使用して誰とでも [共有](/power-bi/collaborate-share/service-share-dashboards)できます。 Power BI ライセンスでは、ユーザー共有とダッシュボードが共有されているユーザーの両方にPower BI ProまたはPower BI Premiumが必要です。

### <a name="can-anyone-share-the-dashboard-or-does-it-have-to-be-the-person-who-connected-to-the-dashboard"></a>ダッシュボードは誰でも共有できますか。または、ダッシュボードに接続したユーザーに限られますか。

ダッシュボードを共有する場合は、ユーザーが他のユーザーとダッシュボードを再共有することを許可するか、共有しないようにすることができます。 このオプションは、共有時に設定できます。

### <a name="is-it-possible-to-work-on-and-customize-the-same-template-app-with-a-group-of-people"></a>ユーザーのグループで同じテンプレート アプリを操作してカスタマイズすることは可能ですか?

はい。 管理者のグループが同じテンプレート アプリで連携できるようにするには、Power BIのアプリ ワークスペース機能を利用できます。詳細については、「[ダッシュボードとレポートを共同作業して共有する方法](/power-bi/collaborate-share/service-how-to-collaborate-distribute-dashboards-reports)」を参照してください。 

### <a name="for-which-timeframe-is-data-available"></a>データはどの時間枠で利用できますか。

レポートの大部分には、過去 12 か月間のデータが表示されます。 ただし、一部のグラフでは、異なる製品とレポートのデータ収集が異なる時期に開始され、12 か月間のデータが利用できない可能性があるため、履歴が少なくなる場合があります。 すべてのレポートは最終的に最大 12 か月間の履歴を作成します。 ユーザー レベルの詳細を表示するレポートには、前の完了月のデータが表示されます。

### <a name="what-data-is-included-in-the-template-app"></a>テンプレート アプリに含まれるデータは何ですか?

テンプレート アプリのデータは、現在、アクティビティ レポートで使用できるのと同じアクティビティ メトリックのセットを対象 [とします](../activity-reports/activity-reports.md)。 レポートがアクティビティ レポートに追加されると、今後のリリースでテンプレート アプリに追加されます。

### <a name="how-does-the-data-in-the-template-app-differ-from-the-data-in-the-usage-reports"></a>テンプレート アプリのデータと使用状況レポートのデータの違いは何ですか?

テンプレート アプリに表示される基になるデータは、Microsoft 365 管理センターのアクティビティ レポートに表示されるデータと一致します。 主な違いは、管理センターのデータは過去 7/30/90/180 日間使用可能であり、テンプレート アプリは最大 12 か月間月単位でデータを表示することです。

さらに、テンプレート アプリのユーザー レベルの詳細は、製品ライセンスを割り当て、アクティビティを実行したユーザーが最後の 1 か月間のみ使用できます。

### <a name="when-should-i-use-the-template-app-and-when-the-usage-reports"></a>テンプレート アプリをいつ使用し、使用状況レポートをいつ使用すればよいですか?

[アクティビティ レポート](../activity-reports/activity-reports.md)は、Microsoft 365の使用状況と導入を理解するのに適した出発点です。 テンプレート アプリは、Microsoft 365使用状況データと組織の Active Directory 情報を結合し、管理者がPower BIのビジュアル分析機能を使用してデータ セットを分析できるようにします。 これにより、管理者は、Microsoft 365使用状況データを視覚化して分析するだけでなく、部門、場所などの Active Directory プロパティによってスライスすることもできます。また、カスタム レポートを作成し、組織内で分析情報を共有することもできます。 

### <a name="how-often-is-the-data-refreshed"></a>データはどのくらいの頻度で更新されますか。 

テンプレート アプリに初めて接続すると、過去 12 か月間のデータが自動的に入力されます。 その後、テンプレート アプリのデータは毎週更新されます。 このデータの使用に別の更新のリズムが必要な場合は、更新スケジュールを変更することを選択できます。

バックエンド Microsoft 365 サービスは毎日データを更新し、現在の日付から 5 ~ 8 日間のデータを提供します。

各データセットの **[コンテンツの日付** ] 列は、テンプレート アプリ内のデータの鮮度の日付を表します。

### <a name="how-is-an-active-user-defined"></a>アクティブなユーザーはどのように定義されていますか?

アクティブ ユーザーの定義は、アクティビティ レポートの [アクティブ ユーザー](../activity-reports/active-users.md) の定義と同じです。

### <a name="what-sharepoint-site-collections-are-included-in-the-sharepoint-reports"></a>SharePoint レポートにはどのような SharePoint サイト コレクションが含まれていますか。

テンプレート アプリの現在のバージョンには、SharePoint チーム サイトとSharePoint グループ サイトからのファイル アクティビティが含まれています。

### <a name="which-groups-are-included-in-the-microsoft-365-groups-usage-report"></a>Microsoft 365 グループ使用状況レポートに含まれるグループはどれですか?

テンプレート アプリの現在のバージョンには、Outlook グループ、Yammer グループ、SharePoint グループからの使用状況が含まれます。 Microsoft Teamsまたは Planner に関連するグループは含まれません。

### <a name="when-will-an-updated-version-of-the-template-app-become-available"></a>更新されたバージョンのテンプレート アプリは、いつ利用可能になりますか?

テンプレート アプリの主な変更は年に 2 回リリースされます。これには、新しいレポートや新しいデータが含まれる場合があります。 レポートの軽微な変更は、より頻繁にリリースされる可能性があります。

### <a name="is-it-possible-to-integrate-the-data-from-the-template-app-into-existing-solutions"></a>テンプレート アプリのデータを既存のソリューションに統合することは可能ですか? 

テンプレート アプリ内のデータは、Microsoft 365 API (プレビュー段階) を使用して取得できます。 運用環境に出荷すると、[Microsoft Graph レポート API](https://go.microsoft.com/fwlink/p/?linkid=848843) 内でマージされます。 

### <a name="are-there-plans-to-expand-the-template-app-to-show-usage-data-from-other-microsoft-products"></a>他の Microsoft 製品の使用状況データを表示するようにテンプレート アプリを拡張する予定はありますか?

これは、今後の改善のために考慮されます。 更新プログラムの[Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を確認してください。

### <a name="how-can-i-pivot-by-company-information-in-active-directory"></a>Active Directory で会社情報をピボットする方法はありますか。

会社の情報は、テンプレート アプリの Active Directory フィールドの 1 つに含まれており、 **製品ユーザー アクティビティ** レポートで事前に構築されたフィルターとして表示できます。 **UserState** テーブルの列として使用できます。

### <a name="is-it-possible-to-bring-in-additional-fields-from-active-directory"></a>Active Directory からその他のフィールドを持ち込むことはできますか。

このデータに対する追加のカスタマイズは、[Microsoft Graph レポート API に](https://go.microsoft.com/fwlink/p/?linkid=848843)接続して、追加のフィールドをAzure Active Directoryから取得してデータセットに結合することで可能です。 

### <a name="is-it-possible-to-aggregate-the-information-in-the-template-app-across-multiple-subscriptions"></a>テンプレート アプリ内の情報を複数のサブスクリプションにわたって集計することは可能ですか?

現時点では、テンプレート アプリは、最初に接続するために使用された資格情報に関連付けられているため、1 つのサブスクリプション用です。

### <a name="is-it-possible-to-see-usage-by-plan-ie-e1-e3"></a>プラン別の使用状況 (E1、E3 など) を確認できますか?

テンプレート アプリでは、使用状況は製品レベルごとに表されます。 ユーザーに割り当てられているさまざまなサブスクリプションに関するデータが提供されていますが、ユーザーアクティビティをユーザーに割り当てられたサブスクリプションに関連付けすることはできません。

### <a name="is-it-possible-to-integrate-other-data-sets-into-the-template-app"></a>他のデータ セットをテンプレート アプリに統合することは可能ですか?

Power BI Desktopを使用してMicrosoft 365 API に接続できます (プレビュー段階)、追加のデータ ソースをテンプレート アプリ データと組み合わせることができます。

詳細については、「カスタマイズ」 [ドキュメント](customize-reports.md)を参照してください。

### <a name="is-it-possible-to-see-the-top-users-reports-for-a-specific-timeframe"></a>特定の期間の "上位ユーザー" レポートを表示することは可能ですか?

すべてのユーザー レベルのレポートには、前月の集計データが表示されます。

### <a name="will-the-template-app-be-localized"></a>テンプレート アプリはローカライズされますか? 

これは現在、ロードマップには含まれていません。

### <a name="i-have-a-specific-question-about-the-data-im-seeing-for-my-organization-who-can-i-reach-out-to"></a>自分の組織に関して表示されるデータについてわからない点があります。誰に質問すればよいですか。

管理センターのアクティビティの概要ページの [フィードバック] ボタンを使用するか、サポート ケースを開くことができます ([サポートを受けて](../get-help-support.md) テンプレート アプリのヘルプを受けることができます。 

### <a name="how-can-partners-access-the-data"></a>パートナーはどのような方法でデータにアクセスできますか。

パートナーが管理者権限を委任している場合は、顧客に代わってテンプレート アプリに接続できます。

### <a name="can-i-hide-identifiable-information-such-as-user-group-and-site-names-in-reports"></a>ユーザー、グループ、レポート内のサイト名など、身元を特定できる情報を非表示にできますか。

はい。 [「収集されたデータを匿名にする](enable-usage-analytics.md#make-the-collected-data-anonymous)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 利用状況分析を有効にする](enable-usage-analytics.md) (記事)\
[利用状況分析のMicrosoft 365レポートを移動して利用](navigate-and-utilize-reports.md)する (記事)\
[管理センターでレポートをMicrosoft 365する](../activity-reports/activity-reports.md) (ビデオ)
