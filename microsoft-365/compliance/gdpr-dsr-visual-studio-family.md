---
title: GDPR に関する Visual Studio ファミリ データ主体要求
description: GDPR に関する Visual Studio ファミリ データ主体要求
keywords: Visual Studio、Visual Studio Code、Visual Studio for Mac、Visual Studio ドキュメント、プライバシー、GDPR
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 744935cb41e1521970e6fac05493129eaaf7910d
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431548"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a>GDPR に関する Visual Studio ファミリ データ主体要求

EU の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、ユーザー (規則では_データ主体_と呼ばれる) に対して個人データを管理する権利を与えています。個人データは、GDPR の下で特定されたまたは特定可能な自然人に関するあらゆるデータとして広く定義されています。GDPR は、個人データに対するデータ主体固有の権利を与えています。これらの権利には、個人データのコピーの取得、その修正の要求、その処理の制限、その削除、またはその電子形式での受信が含まれます。データ主体からデータ コントローラー (個人データを制御する雇用主、その他の種類の代理人、または組織) にデータ主体の個人データに対するアクションの実行を求める正式な要求は、_データ主体要求_ (DSR) と呼ばれます。GDPR に関する一般情報については、「[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)」を参照してください。

## <a name="products-covered-by-this-guide"></a>このガイドの対象製品

このガイドでは、Microsoft ツールを使用して、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能の認証済み (サインイン済み) セッション使用時に収集された個人データをエクスポートまたは削除する方法について説明します。また、Visual Studio 開発者コミュニティ、NuGet.org、および ASP.NET Web サイトの使用時に収集された個人データに対するデータ主体要求の発行方法についても説明します。これらの製品を使用すれば、Microsoft 以外のツールと拡張機能の使用が可能になりますが、Microsoft はこれらのツールと拡張機能のデータ プロセッサまたはコントローラーではありません。これらのツールまたは拡張機能については、それぞれのプロバイダーに問い合わせて個人データと収集に関するポリシーを確認する必要があります。

## <a name="additional-privacy-information"></a>その他のプライバシー情報

製品に付属しているマイクロソフト ソフトウェア ライセンス条項、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkId=660726)、および [Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)にデータ処理慣行が記載されています。

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio、Visual Studio for Mac、および Visual Studio Code

### <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

GDPR に基づくデータ プロセッサとして、Microsoft は、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能に対するエクスペリエンスを提供し、これらを改善するために必要なデータをユーザーから収集します。データは、顧客データとシステム生成ログという 2 つのカテゴリに分けられます。顧客データには、これらの製品が提供しているサービスを実行するために必要なユーザーを特定できるトランザクション データと相互作用データが含まれます。たとえば、ユーザーにローミング設定などの個人的なエクスペリエンスを提供するには、ユーザー アカウント情報と設定データを収集する必要があります。システム生成ログは、問題を特定してトラブルシューティングし、弊社の製品やサービスを向上させるために使用される、利用状況データまたは診断データで、ユーザー名などのエンドユーザーに関する特定可能な情報が含まれている場合もあります。システム生成ログは、少なくとも 18 か月間保持されます。例として、システム生成ログは、次のサンプルで示すように、製品使用の日ごとに集計され、使用日、使用された製品 ("Visual Studio 2017" など)、実行されたアクション ("vs/core/packagecostsummary/solutionload" など)、およびアクションの実行回数が記録されます。

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

詳細については、「[Visual Studio によって収集されるシステム生成ログ](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection)」を参照してください。

認証済みの ID に関連付けられた個人データのみが DSR で処理されます。そのため、たとえば、Visual Studio Code はサインインをサポートしていないため、そこからのシステム生成ログは認証済みの ID に関連付けられず、処理されません。ただし、Visual Studio Code に対する一部の Microsoft 拡張機能が認証済みのデータを提供するため、このデータは DSR で処理されます。詳細については、「[GDPR と Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)」を参照してください。一般に、Visual Studio 2013 以前のデータは保存されませんが、後述するように、特定の拡張機能とコンポーネントが、認証済みの ID に関連付けられたデータを提供する場合があるため、DSR で処理されます。

### <a name="how-users-can-control-personal-data"></a>ユーザーによる個人データの管理方法

Visual Studio 2015 以降、Visual Studio for Mac、および Visual Studio Code は、ユーザーがデータ収集を停止したり、コントローラーが既に収集されたデータをエクスポートまたは削除したりするための以下の手段を提供します。

#### <a name="in-app-settings"></a>アプリ内設定

ユーザーは、これらの製品のプライバシー設定を管理できます。詳細については、以下を参照してください。

- [Visual Studio でプライバシー設定を管理する方法](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program)
- [Visual Studio for Mac でプライバシー設定を管理する方法](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program)
- [Visual Studio Code でテレメトリ レポート機能を無効にする方法](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)

#### <a name="exporting-or-deleting-data"></a>データのエクスポートまたは削除

コントローラーは、Visual Studio ファミリ製品または Microsoft 拡張機能が登録された方法に応じて、2 つの方法のどちらかでデータ主体から収集された顧客データとシステム生成ログを管理できます。両方の方法を使用しなければならない場合もあります。両方の方法を使用すれば、コントローラーは、その方法によって管理されているアクティビティ履歴のコピーをダウンロードすることができます。AAD または MSA アカウントを閉鎖すると、関連する Visual Studio 顧客データが削除され、これらの製品に関するシステム生成ログ内の個人を特定できるデータが匿名化されます。匿名化されたシステム生成ログは少なくとも 18 か月間保持されます。

- Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなどの Azure テナントにより裏付けられるアカウントを使用して、Visual Studio ファミリ製品を登録したユーザーは、「[GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)」の手順に従うことができます。
- Microsoft アカウント (MSA) を使用した複数のアカウントなどの Azure テナントによって裏付けられたアカウントを使用せずに Visual Studio ファミリ製品を登録したユーザーは、Microsoft アカウント経由で使用可能な [Ｗeb ベースの Microsoft Privacy Response Center](https://aka.ms/userprivacysite) を使用して、複数の Microsoft サービス 全体で Microsoft アカウントに紐づけられたアクティビティ データを表示、管理、および削除できます。このシナリオでは、ユーザーは自分の個人データのコントローラーです。

> [!NOTE]
> MSA アカウント所有者がアカウントを削除すると、アカウントが Azure テナントによって裏付けされているかどうかに関係なく、これらの製品に関するすべての個人を特定できるデータが削除され、システム生成ログが匿名化されます。

Visual Studio 2013 では、収集されたデータが匿名化されます。Visual Studio 2012 以前のリリースでは、データが受信時に即座に削除されます。どちらの場合も、後で表示、エクスポート、または削除するものはありません。

## <a name="visual-studio-developer-community"></a>Visual Studio 開発者コミュニティ

[開発者コミュニティ](https://developercommunity.visualstudio.com) Web サイト経由の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 要求がサポートされています。フィードバック データを表示、エクスポート、または削除できます。

### <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

Microsoft は、Visual Studio ファミリ製品を使用して報告された問題を再現してトラブルシューティングするためのデータを収集します。このデータには、個人データとパブリック フィードバックが含まれます。個人データには、以下が含まれます。

- [開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報
- ユーザー設定と通知
- [Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイルとシステム生成ログ
- 投票

パブリック フィードバックには、問題、コメント、および解決策が含まれます。

### <a name="how-users-can-control-personal-data"></a>ユーザーによる個人データの管理方法

#### <a name="view"></a>表示

フィードバック関連データを表示するには、次の手順に従います。

1. [開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。 右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。
2. **[プロファイル]**、**[通知]**、**[アクティビティ]**、および **[添付ファイル]** タブのいずれかをクリックして、フィードバック システムに送信されたデータを表示します。
   1. **プロファイル**は、[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイルを意味し、ユーザー名、電子メール アドレス、自己紹介などが含まれます。
   2. **通知は、受信する電子メール通知の管理方法です。
   3. **アクティビティ**は、アクティブだったフィードバック項目 (投稿済み、コメント済みなど) と実行されたアクティビティを表示します。
   4. **添付ファイル**は、`FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM` のような形式の添付ファイル履歴のリストです。

#### <a name="export"></a>エクスポート

DSR の一部として、フィードバック データをエクスポートすることができます。次のデータを含む 1 つ以上の .zip アーカイブが作成されます。

- [開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報
- ユーザー設定と通知設定
- [Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル

> [!NOTE]
> 入力されたパブリック フィードバック (コメント、解決策、および報告済みの問題) がアーカイブから除外されます。

エクスポートを開始するには、次の手順に従います。

1. [開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。 右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。
2. **[プライバシー]** タブをクリックしてから、**[アーカイブの作成]** をクリックし、データのエクスポートを要求します。
3. **[アーカイブ状態]** が、データの準備中であることを示すように更新されます。データが使用可能になるまでの時間の長さは、エクスポートする必要があるデータ量に依存します。
4. データの準備ができると、電子メールが送信されます。
5. 電子メール内の **[アーカイブのダウンロード]** をクリックするか、[プライバシー] タブに戻ってデータをダウンロードします。

> [!NOTE]
> - [通知] タブで通知を受信しないように選択した場合は、電子メールが送信されません。
> - 再度エクスポートを要求すると、古いアーカイブが削除され、新しいアーカイブが作成されます。

#### <a name="delete"></a>削除

削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)から次の情報が削除されます。

- プロファイル情報
- ユーザー設定と通知設定
- [Visual Studio で問題を報告する](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル
- 投票

> [!NOTE]
> 公開情報 (コメント、解決策、報告済みの問題) は削除されずに、匿名化されます。
>
> [!IMPORTANT]
> AAD または MSA アカウントを削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)の削除プロセスがトリガーされます。

削除を開始するには、次の手順に従います。

1. [開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。
2. **[プライバシー]** タブをクリックしてから、**[データとアカウントの削除]** をクリックし、データの削除を開始します。
3. 確認画面が表示されます。
4. ボックスに "delete" と入力してから、**[マイ アカウントの削除]** をクリックします。

**[マイ アカウントの削除]** をクリックすると:

- サインアウトされます。
- [開発者コミュニティ](https://developercommunity.visualstudio.com) アカウント、個人データ、および添付ファイルが削除されます。
- パブリック フィードバックが匿名化されます。パブリック フィードバックは、開発者コミュニティでは使用可能なままで、匿名ユーザーから報告されたかのように表示されます。
- アカウントを削除しても、電子メールは送信されません。これは、システム内に存在しなくなるためです。
- 新しい問題を報告するか、[開発者コミュニティ](https://developercommunity.visualstudio.com)にログインすると、新しいユーザーとして識別されます。
- [開発者コミュニティ](https://developercommunity.visualstudio.com)からアカウントを削除しても、他の Microsoft サービスからは削除されません。

## <a name="xamarin-forums-and-bugzilla"></a>Xamarin フォーラムと Bugzilla

### <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

[Xamarin フォーラム](https://forums.xamarin.com) ユーザー コミュニティと [Xamarin Bugzilla](https://bugzilla.xamarin.com/) バグ報告 Web サイト経由で、Microsoft は、Microsoft の製品とサービスで発生した可能性のある問題の再現とトラブルシューティングを支援するために提供されたデータを収集します。このデータには、個人データとパブリック フィードバックが含まれます。Microsoft が収集する個人データは、ユーザー アカウント データ (Xamarin フォーラムまたは Bugzilla アカウントに関連付けられたユーザー名や電子メール アドレスなど) で、収集するパブリック フィードバックには、Xamarin フォーラムや Xamarin Bugzilla バグ報告 Web サイト経由で提供されたバグ、問題、コメント、および解決策が含まれます。

### <a name="how-you-can-control-your-data"></a>データの管理方法

#### <a name="xamarin-forums"></a>Xamarin フォーラム

##### <a name="view"></a>表示

アクティブな Xamarin フォーラム アカウントを持っているユーザーは、Xamarin フォーラム アカウント ページから個人データとパブリック フィードバック (投稿済みのスレッドと投稿のすべてなど) を表示できます。ユーザーは、アカウント ページ経由で個人データを編集することもできます。

##### <a name="export"></a>エクスポート

Xamarin フォーラムは、サードパーティの Vanilla フォーラムでホストされます。公開データのエクスポートを要求するには、ユーザーが forums@xamarin.com (Xamarin チームによって監視される) に問い合わせる必要があります。その後で、Vanilla フォーラムを直接操作してこの要求を処理します。

##### <a name="delete"></a>削除する

Xamarin Forumは、サードパーティの Vanilla Forums によりホストされています。個人データと公開データの削除を依頼するには、forums@xamarin.com (Xamarin チームによってモニターされています) にお問い合わせください。その後に、ユーザーからの個人データ削除依頼を手動で処理いたします。

#### <a name="bugzilla-for-xamarin"></a>Xamarin 用の Bugzilla

##### <a name="view"></a>表示

アクティブな Xamarin Bugzilla アカウントを持っているユーザーは、Xamarin Bugzilla ホーム ページ上の適切なリンクをクリックすることにより、報告されたすべてのバグとバグに追加されたすべてのコメントを表示できます。

##### <a name="export"></a>エクスポート

個人データのエクスポートはサポートされていません。

##### <a name="delete"></a>削除

Xamarin の Bugzilla バグ報告 Web サイトとの接続に使用される個人データの削除を要求するには、[[ユーザー設定] ページ](https://bugzilla.xamarin.com/userprefs.cgi)に移動して、**[アカウントの削除] タブ**を選択することにより、Xamarin Bugzilla アカウントを閉鎖できます。Bugzilla パスワードを入力して、自分のアカウントが完全に削除されることの認識を確認するボックスをオンにします。ユーザーが Xamarin Bugzilla に投稿したパブリック フィードバック (バグ、問題、コメント、解決策など) は、削除要求が受信されても削除されません。代わりに、パブリック フィードバックは、削除要求の送信者によって作成されたパブリック フィードバックに関連付けられた名前と電子メール アドレスを削除することにより、匿名化されます。

## <a name="nuget"></a>NuGet

NuGet.org の DSR の詳細については、「[NuGet ユーザー データ要求](https://docs.microsoft.com/nuget/policies/data-requests)」を参照してください。

## <a name="aspnet"></a>ASP.NET

ASP.NET Web サイトの DSR については、「[ASP.NET Web サイトと GDPR データ主体要求の処理](https://www.asp.net/gdpr)」を参照してください。

## <a name="iisnet"></a>IIS.NET

IIS.NET Web サイトの DSR については、「[IIS.NET Web サイトと GDPR データ主体要求の処理](https://www.iis.net/gdpr)」を参照してください。

## <a name="other-visual-studio-family-services"></a>その他の Visual Studio ファミリ サービス

### <a name="surveymonkey"></a>SurveyMonkey

SurveyMonkey 経由でこれらの製品に関するフィードバックの提供をお願いすることがあります。このデータは 28 日以内に削除されます。これらの製品に関するデータ主体要求を処理するときに、アンケートの回答が認証されていれば、それらをエクスポートに含め、データ主体要求を削除します。

### <a name="uservoice"></a>UserVoice

これらの製品の UserVoice.com サイトで製品に関する提案の提供をお願いしています。これらのサイトは UserVoice によって個別に運営されており、データ主体要求は UserVoice によって管理されています。

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

このデータに対するデータ主体要求については、「[データをエクスポートする方法](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data)」または「[データを削除する方法](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information)」を参照してください。

## <a name="learn-more"></a>詳細情報

- [一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)
- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft プライバシー ダッシュボード](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)
