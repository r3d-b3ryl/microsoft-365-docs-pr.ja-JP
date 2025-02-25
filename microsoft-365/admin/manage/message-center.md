---
title: Microsoft 365 管理センターのメッセージ センター
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: Microsoft 365 メッセージ センターの概要と、新機能や変更された機能やその他の重要なお知らせを追跡する役割について説明します。
ms.openlocfilehash: 8368e86e0ab4431aeb07c387daf0a57f89ea1827
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67322917"
---
# <a name="track-new-and-changed-features-in-the-microsoft-365-message-center"></a>Microsoft 365 メッセージ センターで新機能と変更された機能を追跡する

新機能や変更された機能、計画済みメンテナンス、その他の重要なお知らせなどの今後の変更を管理するには、「<a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">メッセージ センター</a>」に移動します。
  
メッセージ センターを開く方法:

::: moniker range="o365-worldwide"

- 管理センターで、「**正常性** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">メッセージ センター</a>」へ移動します。

::: moniker-end

::: moniker range="o365-21vianet"

- <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で「**正常性** > **メッセージ センター**」へ移動します。

::: moniker-end

モバイル デバイスで [Microsoft 365 管理者アプリ](https://go.microsoft.com/fwlink/p/?linkid=627216) を使用してメッセージ センターを表示することもできます。これはプッシュ通知により、常に最新情報を入手する優れた手段です。

メッセージ センターのメールの登録を解除するには、この記事の [「メッセージ センターの電子メールのサブスクライブ解除](#unsubscribe-from-message-center-emails) 」を参照してください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

<br>

****

|質問|答え|
|---|---|
|メッセージ センターの投稿を表示できるのは誰ですか?|Microsoft 365 で何らかの管理者の役割が割り当てられているほとんどのユーザーは、メッセージ センターの投稿を表示できます。 [次に、メッセージ センターへのアクセス権を持たない管理者の役割の一覧](#admin-roles-that-dont-have-access-to-the-message-center)を示します。 また、何も管理者特権を持っていないユーザーに対して、メッセージ センターの投稿を読み共有できるメッセージ センター リーダーの役割をユーザーに割り当てすることもできます。|
|これは、Microsoft が Microsoft 365 についての変更を伝える唯一の方法ですか?|そうではありませんが、メッセージ センターは、Microsoft 365の個別の変更のタイミングを伝える主要な手段です。 その他のリソースについては、「[Microsoft 365 の変更に関する最新情報を得る](stay-on-top-of-updates.md)」をご覧ください。|
|自分の言語で投稿を表示するにはどうしたらよいですか?|メッセージ センターの投稿は英語でのみ書き込まれますが、投稿を既定通り英語で表示するか、または指定した言語に自動的に機械翻訳するかどうかを制御できます。 また、サポートされている任意の言語へ投稿を機械翻訳にかけることもできます。 詳細については、「[メッセージ センターの投稿の言語の翻訳](language-translation-for-message-center-posts.md)」を参照してください。|
|変更や機能を組織に展開する前に、プレビューできますか?|変更や新機能の中には、初回リリース プログラムにオプトインすることで、プレビューできるものもあります。 参加するには、管理センターで **[設定]** > **[組織の設定]** > **[組織のプロフィール]** > **[ユーザー設定のリリース]** へ移動します。 (管理センターでは、左側のナビゲーション ウィンドウの下部にある **[すべてのオプションを表示]** を選び、[**設定**] タブを表示必要があります)。組織全体を対象とする指定リリースか、選択したユーザーに対してのリリースかを選択します。 プログラムの詳細については、「[Microsoft 365 の標準またはターゲット リリース オプション](release-options-in-office-365.md)」を参照してください。|
|変更が組織で利用可能になる正確な日付がわかりますか?|残念ながら、変更が組織に対して行われる正確な日付を伝えることはできません。 メッセージ センターの投稿では、信頼レベルに基づいて、リリースのタイミングについてできる限り多くの情報を提供します。 現在、その詳細レベルでの改善に取り組っています。|
|これらのメッセージは組織に固有のものですか?|所属の組織に影響するメッセージ センターの投稿のみが表示されるように最善を尽くしています。 Office 365 ロードマップには、現在 Microsoft が取り組み中および展開中のすべての機能が含まれていますが、これらのすべての機能が各組織に適用されるわけではありません。|
|メッセージ センターの投稿を電子メールで受け取ることはできますか?|はい。 ユーザーと最大でその他 2 つの電子メール アドレス宛てに週刊ダイジェストを受信する選択ができます。 週刊ダイジェストの電子メール送付は既定でオンになっています。 週刊ダイジェストが届かない場合、迷惑メール フォルダーを確認してください。 週刊ダイジェストの設定方法については、この記事の「[ユーザー設定](#preferences) 」を参照してください。|
|メッセージ センターのダイジェストの取得を停止するにはどうしたら良いですか?|管理センターのメッセージ センターに移動し、[**ユーザー設定**] を選択します。 [**メール**] タブで、[**メッセージ センターからメールを送信する**] オプションをオフにします。|
|組織内の適切な連絡先がデータ プライバシーに関する通知を確実に受け取れるようにするにはどうすれば良いですか?|グローバル管理者は、組織のデータのプライバシーに関するメッセージを受信します。 さらに、データ プライバシー メッセージを表示する必要があるユーザーに、メッセージ センター プライバシー リーダーの役割を割り当てすることができます。 メッセージ センターにアクセスできる他の管理者の役割では、データ プライバシー メッセージを表示できません。   <br/><br/>詳細については、この記事の[[ユーザー設定](#preferences)] を参照してください。|
|以前あったメッセージが表示できない理由はなぜでしょうか?|メッセージ センター内のメッセージ数を管理するには、各メッセージが一定の期間で期限切れになり削除されるように設定します。 一般に、メッセージは、メッセージ本文に示されている期間の 30 日後に期限切れになります。|
|

## <a name="filter-messages"></a>メッセージをフィルター処理する

メッセージ センターでは、アクティブなすべてのメッセージが表形式で表示されます。 既定では、最新のメッセージがリストの上部に表示されます。 **[サービス]** を選択して、Microsoft 365 アプリ、SharePoint Online などのさまざまなサービスのメッセージを表示できます。 **タグ** の下で [**管理者への影響**]、 [**データ のプライバシー**]、 [**機能更新プログラム**]、 [**主な更新プログラム**]、 [**新機能**]、 [**サポート**]、または [**ユーザーへの影響**] の中からメッセージを選択できます。 [**メッセージの状態**] の下で、[**お気に入り**]、 [**未読**],または [**最新**] のメッセージから選択できます。

[アーカイブ] タブには、アーカイブしたメッセージが表示されます。 メッセージをアーカイブするには、メッセージ ウィンドウで [**アーカイブ**] を選択します。

::: moniker range="o365-worldwide"

[**サービス**]、[**タグ**]、および [**メッセージの状態**] のドロップダウン メニューを使用して、メッセージのフィルタリングされたビューを選択します。  たとえばこの図では、メッセージは [**管理者への影響**] タグでタグ付けされています。

[**サービス**] と [**タグ**] を除いた任意の列見出しをクリックすると、メッセージを昇順または降順で並べ替えることができます。

:::image type="content" source="../../media/message-center-admin-impact1.png" alt-text="管理影響で並べ替えられたメッセージ センター ビュー。":::

::: moniker-end

::: moniker range="o365-21vianet"

[**サービス**]、[**タグ**]、および [**メッセージの状態**] のドロップダウン メニューを使用して、メッセージのフィルタリングされたビューを選択します。  たとえばこの図では、メッセージは [**管理者への影響**] でタグ付けされています。

[**サービス**] と [**タグ**] を除いた任意の列見出しをクリックすると、メッセージを昇順または降順で並べ替えることができます。

::: moniker-end

### <a name="major-updates"></a>メジャー更新プログラム

[**タグ**] ドロップダウンから [**主要な更新プログラム**] を選択して、主要な更新プログラムを確認できます。

以下のユーザーの対応が必要になるような、メジャー更新プログラムは少なくとも 30 日前に通知されます。

- 受信トレイ、会議、会議の委任、共有、アクセスなど、毎日の業務に関わる変更。
- テーマ、Web パーツ、カスタマイズされた機能に影響を与える可能性があるその他のコンポーネントに対する変更
- 記憶域、ルールの数、アイテム、期間など、確認できる容量の増減。
- 製品ブランドの変更。
  - エンド ユーザーの混乱を引き起こす、
  - その結果、ヘルプ デスク プロセスや参考資料に変更が加わります。
  - URL を変更する
- 新しいサービスやアプリケーション
- 管理者による対応が必要となる変更 (問題の予防または修正を除く)
- データの保存場所の変更
  
### <a name="preferences"></a>ユーザー設定

管理が組織全体に分散している場合は、Office 365 サービスのすべての  投稿を表示する必要がない場合があります。 各管理者は次の方法で行います。

- メッセージ センターで表示されるメッセージを制御するユーザー設定を行います。
- メッセージをフィルター処理する
- すべてのメッセージの週刊ダイジェスト、大きな更新のみを知るメール、データ プライバシー メッセージ用のメールを受信するために、メールのユーザー設定を行います。  

::: moniker range="o365-worldwide"

1. メッセージ センターの一番上で [**ユーザー設定**] を選択します。

2. [**カスタム ビュー**] タブで、監視する各サービスのチェックボックスをオンにしていることを確認します。 メッセージ センターのビューからフィルター処理するサービスのチェック ボックスをオフにします。

3. ダイジェスト メールは既定でオンになっており、プライマリの電子メール アドレスに届きます。 週刊ダイジェストの受信を停止するには、[**電子メール**] タブにある [**メッセージ センターから電子メール通知を送信する**] チェック ボックスをオフにします。 

   また、最大 2 つのメール アドレスをセミコロンで区切って入力することもできます。

   また、選択した週刊ダイジェストのサービスの種類の数と同じだけ、メールを選択することもできます。

4. [**保存**] をクリックし、変更を保存します。
  
::: moniker-end

::: moniker range="o365-21vianet"

1. メッセージ センターの一番上で [**ユーザー設定**] を選択します。

2. [**カスタム ビュー**] タブで、監視する各サービスのチェックボックスをオンにしていることを確認します。 メッセージ センターのビューからフィルター処理するサービスのチェック ボックスをオフにします。

3. ダイジェスト メールは既定でオンになっており、プライマリの電子メール アドレスに届きます。 週刊ダイジェストの受信を停止するには、[**電子メール**] タブにある [**メッセージ センターから電子メール通知を送信する**] チェック ボックスをオフにします。

   また、最大 2 つのメール アドレスをセミコロンで区切って入力することもできます。

   また、選択した週刊ダイジェストのサービスの種類の数と同じだけ、メールを選択することもできます。

4. [**保存**] をクリックし、変更を保存します。

::: moniker-end

### <a name="display-messages-in-your-preferred-language"></a>指定した言語でメッセージを表示する
  
機械翻訳を利用し、ユーザーの優先言語でメッセージを自動表示しています。言語の設定方法については、「[メッセージ センターの投稿の言語の翻訳](language-translation-for-message-center-posts.md)」を参照してください。
  
> [!NOTE]
> 週刊ダイジェストやメールで送信されるその他の投稿は英語でのみ提供されます。受信後、[Outlook 用翻訳ツール](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa)を利用してメッセージを自分の優先言語で読むことができます。

## <a name="monthly-active-users"></a>毎月アクティブなユーザー

メッセージ センターの投稿を開くと、その Microsoft 365 アプリまたはサービスをサービス & **月間アクティブ ユーザー** セクションで使用しているユーザーの数が表示されます。 数値は過去 28 日間です。 この情報は、作業する必要がある変更に優先順位を付けるのに役立ちます。

:::image type="content" source="../../media/msgctr-mau-teams.png" alt-text="スクリーンショット: 毎月アクティブなユーザー データを含むメッセージ センター投稿の Microsoft Teams チャット密度ページを表示する":::

月次ユーザーの数は、任意のデバイスでその Microsoft 365 アプリまたはサービスを使用したすべてのユーザーに適用されます。

> [!NOTE]
> この機能は、まだすべての Microsoft 365 アプリとサービスでは使用できません。 機能が利用できない場合は、お知らせします。

## <a name="choose-columns"></a>列を選択する

列を選択するには、**メッセージ センター** ページで、最も右にある [ **列の選択**] を選択し、[ **列の選択** ] ウィンドウで、表示する列を選択します。

各列に表示される情報の概要を示します。

### <a name="column-information"></a>列情報

<br>

****

|列|説明|
|---|---|
|チェック マーク|列見出し行でチェック マークを選択すると、現在表示されているメッセージすべてが選択されます。 1 つ以上のメッセージの横にあるチェック マークを選択すると、それらのメッセージに対してアクションを実行できます。|
|メッセージのタイトル|メッセージのタイトルは、予定されている変更の簡単な説明です。 完全なタイトルが表示されない場合は、タイトルの上にカーソルを置くと、ポップアップ ボックスにタイトルの全体が表示されます。|
|サービス|アイコンは、メッセージが適用されるアプリケーションを示します。|
|その他のオプション|その他のオプションを使用すると、メッセージを閉じ、既読または未読としてマークしたり、別の管理者と共有することができます。アーカイブ したメッセージを復元するには、[**アーカイブ**] タブを選択して、次にメッセージの横にあるチェック マークで、[**アーカイブの復元**] を選択します。|
|タグ| メッセージをフィルター処理するには、[タグ] のドロップダウンから選択できます。 <br> <p> **データプライバシー**: データプライバシー通知 (グローバル管理者とメッセージ センターのプライバシー 閲覧者ロールに限定)。 <p> **メジャー 更新プログラム**: 少なくとも 30 日前に伝達された変更 ([メジャー 更新プログラム](#major-updates))。 <p> **廃止**: サービスまたは機能の廃止。 <p> **新機能**: 新機能またはサービス。 <p> **機能の更新**: 既存の機能に更新します。 <p> **管理影響**: UI の変更、ワークフローの変更、使用可能な制御、および特定/潜在的なアクションなど、変更が管理者に明確に影響を与える場合。 <p> **ユーザーの影響**: サービスへの変更がユーザーに明らかに影響する場合 - UI の変更とワークフローの変更。 <p> **更新されたメッセージ**: メッセージが更新されたとき。|
|カテゴリ| 既定では表示されませんが、[**列の選択**] パネルで指定できます。 メッセージは、次の 3 つのカテゴリのいずれかで識別されます。 <p> **問題の予防または修正**:組織に影響する既知の問題を知らせます。サービスの中断を回避するため、ユーザーに対応を求める場合があります。 問題の予防または修正は、問題を回避するために積極的な対応を促すため、サービスの正常性メッセージとは異なります。 <p> **変更の計画**: サービスの中断を回避するためにユーザーの対応が必要になる場合がある Microsoft 365 への変更を通知します。 たとえば、システム要件の変更や削除される機能についてお知らせします。 サービスの正常な実行を維持するために管理者が対応する必要があるすべての変更については、30 日以上前に通知するようにしています。 <p> **最新の情報を得る**: 組織内でオンにしている新機能または更新された機能について通知します。 機能は通常、「[Microsoft 365 ロードマップ](https://go.microsoft.com/fwlink/?linkid=2070821)」で最初に通知されます。 <p> サービス レベル契約に従った計画済みメンテナンスについても通知する場合があります。 計画済みメンテナンスにより、ダウンタイムが発生する場合があります。ダウンタイムが発生すると、ユーザーは Office 365 や、特定の機能、メールまたは OneDrive for Business などのサービスにアクセスできなくなります。|
|対応期限|特定の期限までにユーザーの対応を必要とする変更を行った場合にのみここに日付を記入します。 [**対応期限**] 列を使うことは滅多にないため、ここに何かが表示されている場合は、特に注意を払う必要があります。|
|最終更新日時|メッセージが公開または最終更新された日付。|
|メッセージ ID|Microsoft は、メッセージ ID でメッセージ センターの投稿を追跡します。 特定のメッセージについてフィードバックを送信する場合、またはサポートに連絡する場合は、この ID を参照することができます。|
|

### <a name="admin-roles-that-dont-have-access-to-the-message-center"></a>メッセージ センターにアクセスできない管理者役割

- コンプライアンス管理者
- 条件付きアクセス管理者
- カスタマー ロックボックス アクセス承認者
- デバイス管理者
- ディレクトリ閲覧者
- ディレクトリ同期アカウント
- ディレクトリ製作者
- Intune サービス管理者
- 特権的役割管理者
- レポート閲覧者

## <a name="give-feedback-on-a-post"></a>投稿にフィードバックを送信する

メッセージ センターでは、メッセージを選択して詳細を表示できます。

メッセージに関するフィードバックを提供する場合、詳細ウィンドウで、メッセージ詳細ウィンドウの下部にある [**いいね!**] または [**嫌い**] アイコンを選択し、表示されるテキスト ボックスにオプションのフィードバックを入力します。 どんな個人情報も提供しないでください。 オプションで、**[このフィードバックについて私に連絡しても問題ありません]** を選択し、**[送信]** を選択できます。

> [!NOTE]
> 政府機関向け Microsoft 365 -GCC、政府機関向け Microsoft 365 - GCC High および Office 365 Government - DoD を使用している場合、投稿に関するフィードバックを提供することはできません。

## <a name="share-a-message"></a>メッセージの共有

他のユーザーの対応が必要なメッセージについては、 メールを使って、そのメッセージの内容を任意のユーザーと共有できます。
  
1. メッセージを選択して開き、**[共有]** を選択します。
  
2. メッセージを共有するには、最大 2 つのメール アドレスをコロンで区切って入力します。 個人およびグループの電子メール アドレスに送信できます。 オプションで、メッセージのコピーをメールで受信するか (メッセージはメインのメール アドレスに送信されます)、個人のメッセージを追加して受信者により多くのコンテキストを提供するかを選択できます。
  
3. **[共有]** を選択して、メールを送信します。

## <a name="get-a-link"></a>リンクを取得

別の管理者をフォローアップして、変更と操作の実行について確実に知らせる必要がある場合は、メールまたはインスタント メッセージで共有リンクを作成し、たとえば、ユーザーがメッセージに直接接続されるようにします。 リンクの共有先のユーザーは、組織の Office 365 の管理者である必要があります。 リンクを共有する対象は、メッセージ センターにアクセスできるユーザーである必要があります。 詳細については、「[メッセージ センター にアクセスできない管理者ロール](message-center.md#admin-roles-that-dont-have-access-to-the-message-center)」を参照してください。

1. 受信したメッセージを選択して開きます。

2. [**リンクのコピー**] を選択します。

3. Ctrl + V を押すか、右クリックして **[貼り付け]** を選択して、任意のドキュメントにリンクを挿入します。

## <a name="read-and-unread-states"></a>開封状態と未開封状態

メッセージ センター内の未開封メッセージは太字で表示されます。 メッセージを開くと、既読になります。 メッセージを未読としてマークすることができます。

メッセージ センターのメイン ページで、メッセージの横にある、[**その他のオプション**] の省略記号を選択し、[**未読としてマークする**] を選択します。

メッセージを開いて、詳細パネルで未読としてマークすることもできます。
  
## <a name="archive-and-restore"></a>アーカイブと復元

関係のないメッセージが表示されている場合、またはそのメッセージが既に対処済みの場合は、メッセージをアーカイブして、受信トレイから削除することができます。 メッセージ センターに表示されるビューは、ユーザー アカウントに固有です。したがって、ビューからアーカイブしても、他の管理者には影響しません。 メッセージをアーカイブするには、2 つの方法があります。

- メッセージセンターのメインページで、メッセージを選択し、メッセージのリストの上にある **[アーカイブ]** を選択します。
- メッセージを開き、メッセージ ウィンドウの上部にある **[アーカイブ]** を選択します。

アーカイブしたメッセージが再度必要ですか? 問題ありません。
  
1. メッセージ センターの上部にある **[アーカイブ]** タブを選択してください。 アーカイブしたメッセージの一覧が表示されます。

1. メッセージを選択し、**[復元]** を選択すると、メッセージは受信トレイに復元されます。

## <a name="favorite-messages"></a>お気に入りのメッセージ

メッセージをお気に入りとしてマークするには、メッセージのタイトルにマウス ポインターを置くと、[**その他のオプション**] の省略記号の直後に、選択できる **お気に入り** の:::image type="icon" source="../../media/favorite-star.png" border="false":::星マークが表示されます。 メッセージをお気に入りとしてマークすると、並べ替えやフィルター処理を行うことができます。

## <a name="scroll-messages-in-the-message-pane"></a>メッセージ ウィンドウでメッセージをスクロールする

閲覧ウィンドウでメッセージを開くと、ウィンドウの上部にある 「**上**」または 「**下**」:::image type="icon" source="../../media/updownarrows.png" border="false":::の矢印キーを使用して、リスト内の次のメッセージまたは前のメッセージに移動できます。

## <a name="track-your-message-center-tasks-in-planner"></a>Planner でメッセージ センターのタスクを追跡する

Microsoft 365 サービスの変更に関する実践的な情報の多くは、Microsoft 365 メッセージ センターに届きます。 各タスクのどの変更がいつ、誰によって実行されるかを、完了まで追跡するのは難しい場合があります。 また、何かをメモして、後で確認するためにタグを付けておきたいと思うかも知れません。 これらのすべては、Microsoft 365 管理センターから Microsoft Planner にメッセージを同期することで行えます。 詳細については、「[Planner でメッセージ センターのタスクを追跡する](/office365/planner/track-message-center-tasks-planner)」をご覧ください。

メッセージ センターの概要については、「[Microsoft 365 のメッセージ センター](message-center.md)」を参照してください。 また、メッセージ センターの投稿の機械翻訳を有効にするために言語設定を設定する方法については、「[メッセージ センターの投稿の言語の翻訳を有効にする](language-translation-for-message-center-posts.md)」を参照してください。 リアルタイムのサービス正常性情報とメッセージ センターの通信を取得する別の方法をプログラムする場合は、 [Microsoft Graph のサービス通信 API の操作に関する](/graph/api/resources/service-communications-api-overview)ページを参照してください。

## <a name="unsubscribe-from-message-center-emails"></a>メッセージ センターのメール登録を解除する

1. ダイジェスト メールは既定でオンになっており、プライマリの電子メール アドレスに届きます。 週刊ダイジェストの受信を停止するには、[**ユーザー 設定**] を選択して、次に [**電子メール**] をします。
    - [**メッセージの週刊ダイジェストを送信する**] チェック ボックスを 解除します。
    - 主要な更新プログラムの電子メール通知は別に制御されます。 主要な更新プログラムに関するメール通知を受信したくない場合は、[**主要な更新プログラムのメールを送信する**] チェック ボックスがオフになっていることを確認します。
    - データ プライバシー メッセージに関するメール通知の受信を停止するには、[**データ プライバシー メッセージのメールを送信する**] チェック ボックスがオフになっていることを確認します。  (データプライバシー に関するメッセージは、週刊ダイジェストには含まれません)。

2. [**保存**] をクリックし、変更を保存します。

## <a name="related-content"></a>関連コンテンツ

[標準または対象指定リリース オプションを設定する](../manage/release-options-in-office-365.md) (article)\
[ビジネス サブスクリプションと課金ドキュメント](../../commerce/index.yml) (リンク ページ)
