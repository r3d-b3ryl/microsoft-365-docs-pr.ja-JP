---
title: GDPR および CCPA に関する Visual Studio ファミリ データ主体要求
description: GDPR および CCPA に関する Visual Studio ファミリ データ主体要求
keywords: Visual Studio、Visual Studio Code、Visual Studio for Mac、Visual Studio ドキュメント、プライバシー、GDPR、CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 81dfd4b0c0724e2ab40113c1d134e0932c215c8f
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557987"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA に関する Visual Studio ファミリ データ主体要求

EU の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、ユーザー (規則では_データ主体_と呼ばれる) に対して個人データを管理する権利を与えています。個人データは、GDPR の下で特定されたまたは特定可能な自然人に関するあらゆるデータとして広く定義されています。GDPR は、個人データに対するデータ主体固有の権利を与えています。これらの権利には、個人データのコピーの取得、その修正の要求、その処理の制限、その削除、またはその電子形式での受信が含まれます。データ主体からデータ コントローラー (個人データを制御する雇用主、その他の種類の代理人、または組織) にデータ主体の個人データに対するアクションの実行を求める正式な要求は、_データ主体要求_ (DSR) と呼ばれます。

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、それらの個人情報の削除、アクセスおよび受信 (移植性) の権利などの GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。  また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、“売上“ として分類された特定のデータ転送の “オプトアウト/オプトイン“ 要件を規定します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。

## <a name="products-covered-by-this-guide"></a>このガイドの対象製品

このガイドでは、Microsoft のツールを使用して、認証済みの (サインイン済みの) Visual Studio、Visual Studio for Mac、Microsoft 拡張機能のセッション使用中に収集された個人データを、Visual Studio Code にエクスポートまたは削除する方法について説明します。 また、このガイドでは Visual Studio 開発者コミュニティ、NuGet.org、および ASP.NET Web サイトの使用中に収集された個人データのデータ主体要求を作成する方法についても説明します。 これらの製品は、Microsoft 以外のツールや拡張機能を有効にできる場合があります。また、Microsoft はこれらのツールや拡張機能に対応するデータ プロセッサまたはコントローラーではありません。 ユーザーは、ツールや拡張機能に関する個人データとコレクション ポリシーを理解するために、ツールや拡張機能のプロバイダーに問い合わせる必要があります。

## <a name="additional-privacy-information"></a>その他のプライバシー情報

製品に付属しているマイクロソフト ソフトウェア ライセンス条項、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkId=660726)、および [Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)にデータ処理慣行が記載されています。

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio、Visual Studio for Mac、および Visual Studio Code

### <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

GDPR に基づくデータ プロセッサとして、Microsoft は、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能に対するエクスペリエンスを提供し、これらを改善するために必要なデータをユーザーから収集します。データは、顧客データとシステム生成ログという 2 つのカテゴリに分けられます。顧客データには、これらの製品が提供しているサービスを実行するために必要なユーザーを特定できるトランザクション データと相互作用データが含まれます。たとえば、ユーザーにローミング設定などの個人的なエクスペリエンスを提供するには、ユーザー アカウント情報と設定データを収集する必要があります。システム生成ログは、問題を特定してトラブルシューティングし、弊社の製品やサービスを向上させるために使用される、利用状況データまたは診断データで、ユーザー名などのエンドユーザーに関する特定可能な情報が含まれている場合もあります。システム生成ログは、少なくとも 18 か月間保持されます。例として、システム生成ログは、次のサンプルで示すように、製品使用の日ごとに集計され、使用日、使用された製品 ("Visual Studio 2017" など)、実行されたアクション ("vs/core/packagecostsummary/solutionload" など)、およびアクションの実行回数が記録されます。

```Log
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

- Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなどの Azure テナントにより裏付けられるアカウントを使用して、Visual Studio ファミリ製品を登録したユーザーは、「[GDPR のための Azure データ主体要求](gdpr-dsr-azure.md)」の手順に従うことができます。
- Microsoft アカウント (MSA) を使用した複数のアカウントなど、Azure テナントによって裏付けられたアカウントを使用せずに Visual Studio ファミリ製品を登録したユーザーは、Microsoft アカウント経由で [Ｗeb ベースの Microsoft Privacy Response Center](https://aka.ms/userprivacysite) を使用して、複数の Microsoft サービスで Microsoft アカウントに紐づけられたアクティビティ データを表示、管理、および削除できます。 このシナリオでは、ユーザーは個人データのコントローラーです。

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

1. [開発者コミュニティ](https://developercommunity.visualstudio.com) にサインインします。 右上のプロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。
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

## <a name="xamarin-forums"></a>Xamarin フォーラム

### <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

Microsoft は、[Xamarin フォーラム](https://forums.xamarin.com/) ユーザー コミュニティを通して、Microsoft 製品とサービスに関する問題を再現してトラブルシューティングするためにユーザーが提供するデータを 収集します。 このデータには、個人データと公的フィードバックが含まれます。 収集する個人データは、ユーザー アカウント データ (Xamarin フォーラムに関連付けられているユーザー名とメールアドレスなど) で、収集する公的フィードバックは、ユーザーが Xamarin フォーラムで提供するバグ、問題、コメント、解決方法を含みます。

### <a name="how-you-can-control-your-data"></a>データの管理方法

#### <a name="xamarin-forums"></a>Xamarin フォーラム

##### <a name="view"></a>表示

アクティブな Xamarin フォーラム アカウントを持っているユーザーは、Xamarin フォーラム アカウント ページから個人データとパブリック フィードバック (投稿済みのスレッドと投稿のすべてなど) を表示できます。ユーザーは、アカウント ページ経由で個人データを編集することもできます。

##### <a name="export"></a>エクスポート

Xamarin フォーラムは、サードパーティの Vanilla フォーラムでホストされます。公開データのエクスポートを要求するには、ユーザーが forums@xamarin.com (Xamarin チームによって監視される) に問い合わせる必要があります。その後で、Vanilla フォーラムを直接操作してこの要求を処理します。

##### <a name="delete"></a>削除する

Xamarin Forumは、サードパーティの Vanilla Forums によりホストされています。個人データと公開データの削除を依頼するには、forums@xamarin.com (Xamarin チームによってモニターされています) にお問い合わせください。その後に、ユーザーからの個人データ削除依頼を手動で処理いたします。

> [!NOTE]
> Xamarin の Bugzilla は、新しい問題を受け付けていません。 以前の Xamarin Bugzilla アカウントを持っているユーザーは、ユーザーが報告したすべてのバグのアーカイブおよびユーザーがバグに追加したすべてのコメントを [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/) で見ることができます。 アーカイブに含まれる個人データの削除を要求するには、ユーザーは [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose) で問題を提出できます。 削除要求の受理後、ユーザーが Xamarin Bugzilla に投稿したパブリック フィードバック (バグ、問題、コメント、解決策など) は削除されません。 その代わり、削除要求の送信者によって作成されたパブリック フィードバックに関連付けられている名前とメール アドレスを削除することによりパブリック フィードバックは匿名化されます。

## <a name="nuget"></a>NuGet

NuGet.org の DSR の詳細については、「[NuGet ユーザー データ要求](https://docs.microsoft.com/nuget/policies/data-requests)」を参照してください。

## <a name="aspnet"></a>ASP.NET

ASP.NET Web サイトの DSR については、「[ASP.NET Web サイトと GDPR データ主体要求の処理](https://www.asp.net/gdpr)」を参照してください。

## <a name="iisnet"></a>IIS.NET

IIS.NET Web サイトの DSR については、「[IIS.NET Web サイトと GDPR データ主体要求の処理](https://www.iis.net/gdpr)」を参照してください。

## <a name="other-visual-studio-family-services"></a>その他の Visual Studio ファミリ サービス

### <a name="surveymonkey"></a>SurveyMonkey

SurveyMonkey 経由でこれらの製品に関するフィードバックの提供をお願いすることがあります。このデータは 28 日以内に削除されます。これらの製品に関するデータ主体要求を処理するときに、アンケートの回答が認証されていれば、それらをエクスポートに含め、データ主体要求を削除します。

## <a name="learn-more"></a>詳細情報

- [一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)
- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft プライバシー ダッシュボード](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)
