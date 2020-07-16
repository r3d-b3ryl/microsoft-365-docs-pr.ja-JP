---
title: グループのガバナンスを計画する
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
- BCS160
- MET150
- MOE150
- BSA160
description: Microsoft 365 グループガバナンスを計画する方法について説明します。
ms.openlocfilehash: 37d243b56de363985ecb9463dfe5eb182d9e40b1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780495"
---
# <a name="plan-for-governance-in-groups"></a>グループでのガバナンスを計画する

Microsoft 365 グループには、組織で必要となる可能性があるすべてのガバナンス機能を実装するための豊富なツールセットがあります。この記事では、IT プロフェッショナルが適切な質問をして、ガバナンスの要件を確認する方法と、組織のプロファイルに基づいてそれらを満たす方法について説明します。

## <a name="why-microsoft-365-groups"></a>Microsoft 365 グループの理由
![画像の説明](../../media/01.png)

今日、組織は多様なツールセットを使用していることがわかっています。開発者は、チームチャット、メールを送信する役員、およびエンタープライズソーシャルを介して接続する組織全体を使用しています。グループはそれぞれ一意であり、独自の機能上のニーズとワークスタイルがあるため、複数のコラボレーションツールが使用されています。一部のユーザーはメールのみを使用し、他のユーザーは主にチャットに住んでいます。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は "シャドウ IT" と呼ばれ、組織にとって重大なリスクを持ちます。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Microsoft 365 グループは、ユーザーを支援し、共同作業に必要なツールの多くが1つのステップで提供されるため、IT をシャドウイングするリスクを軽減します。 Microsoft 365 グループでは、共同作業を希望するユーザーのセットを選択し、それらのユーザーが共有するリソースのコレクションを簡単にセットアップすることができます。 リソースに対するアクセス許可を手動で割り当てることは、グループにメンバーを追加することによって、グループが提供するすべての資産に対して必要なアクセス許可を自動的に付与することです。

## <a name="technical-architecture"></a>テクニカル アーキテクチャ

Microsoft 365 グループでサポートされている3つの主要な通信方法があります。これらのエクスペリエンス内でグループを作成し、Microsoft 365 の間で使用することができます。
- Outlook: グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- Microsoft Teams: 特定のサブグループによって開催される、さまざまなトピックに関する非公式でリアルタイム会話を可能にする常設チャットベースのワークスペース。
- Yammer: 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

> [!NOTE]
> 他のチームワークアプリケーションを使用して新しいグループを作成します。たとえば、SharePoint、Planner、Stream などのグループは、Outlook の受信トレイと Microsoft Teams への接続機能を備えています。

グループの作成場所に応じて、次のような特定のリソースが自動的にプロビジョニングされます。
- [受信トレイ](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)-グループメンバー間の電子メールスレッドの場合。この受信トレイにはメールアドレスが設定されており、従来の配布リストのように、グループ外のユーザーや組織外からのメッセージを受け付けるように設定できます。
 - [予定表](https://support.microsoft.com/office/0cf1ad68-1034-4306-b367-d75e9818376a): グループに関連したスケジュール済みイベント用
- [SharePoint チームサイト](https://support.microsoft.com/office/75545757-36c3-46a7-beed-0aaa74f0401e)–グループに関連する情報、リンク、およびコンテンツの中央リポジトリ
- [SharePoint ドキュメントライブラリ](https://support.microsoft.com/office/749bc73b-90c9-4760-9b6f-9aa1cf01b403)–グループがファイルを保存および共有するための一元的な場所
- [OneNote ノートブック](https://support.microsoft.com/office/e768fafa-8f9b-4eac-8600-65aa10b2fe97)–アイデア、研究、情報を収集するためのものです。
- [Planner](https://support.microsoft.com/office/4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc): グループのメンバーへのプロジェクト タスクの割り当ておよび管理用
- [Yammer グループ](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)–会話を行い、情報を共有するための共通の場所
- Microsoft Teams – Microsoft 365 のチャットベースのワークスペース

各グループに対して作成されるリソースの詳細については、「 [Microsoft 365 グループについて](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)」を参照してください。

> [!NOTE]
> Yammer または Teams を使用して新しい Microsoft 365 グループを作成すると、それらのユーザー間のプライマリ通信はそれぞれのクライアントで行われるため、Outlook またはアドレス帳にグループが表示されません。 Yammer グループを Microsoft Teams に接続することはできません。

## <a name="where-to-start-a-conversation"></a>会話を開始する場所
Microsoft 365 で会話を行う場所が複数あります。 会話を開始する場所を理解することは、組織がコミュニケーションの戦略を定義するのに役立ちます。

![画像の説明](../../media/03.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
   - 日常的に作業するメンバーとの共同作業のために作成されています
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - Live chat、音声ビデオ会議、レコーディングされた会議

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 共通の利息や専門知識を共有しているが、必ずしも日常的に共同作業するわけではないユーザーの、社内で働くグループのコミュニティ。
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- Outlook グループ: モダン DL (電子メールベースのコラボレーション)
  - 対象とするコミュニケーションにとってユビキタス
  - Dl を Microsoft 365 グループにアップグレードする-[アップグレードが必要な理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint –すべての Microsoft 365 グループの主要なコンテンツコラボレーション環境
  - すべてのグループが接続された SharePoint チームサイトを取得する
  - コンテンツの共有、カスタマイズしたページの作成およびニュースの執筆
  - 既存の SharePoint チームサイトを新しい Microsoft 365 グループに[接続](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)する

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Microsoft 365 をスケールおよび管理する

Microsoft 365 グループには、組織で必要となる可能性があるすべてのガバナンス機能を実装するための豊富なツールセットがあります。 次のセクションでは、機能について説明し、ベストプラクティスを推奨し、ガバナンスの要件を決定するための適切な質問とそれらを満たす方法についてのガイダンスを提供します。

**このセクションの内容**:
- [Microsoft 365 グループを作成できるユーザーを制御する](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [グループの論理的な削除と復元](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [グループの名前付けポリシー](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [グループの有効期限ポリシー](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [グループのゲスト アクセス](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [グループのポリシーと情報保護](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [従来の共同作業ツールをアップグレードする](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [グループのレポート](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Microsoft 365 グループを作成できるユーザーを制御する
エンドユーザーは、Outlook、SharePoint、Teams、その他の環境を含む複数のエンドポイントからグループを作成できます。

![画像の説明](../../media/04.png)
> [!Tip]
>- グループの所有者に裁量を委ねるセルフサービスについて特に考慮に入れます。
>- グループの要求方法を文書化して伝えます。
>- クラウドへの移行過程でグループを作成できるユーザーについて再考します。
>- 動的メンバーシップを使用して、グループの作成を制御するセキュリティグループのメンバーを構成することを検討してください。
>- 動的メンバーシップを介して管理できるグループシナリオを評価し、rest に対してセルフサービスを許可します。

グループでのプロビジョニングには、オープン、IT 主導、および制御の3つの主要なモデルがあります。 次の表では、各モデルの利点について説明します。

| モデル          | 長所                                                   |
| -------------- | ------------------------------------------------------------ |
| オープン (既定) | ユーザーは必要に応じて独自のグループを作成できます。IT 部門の対応を待機したり依頼する必要はありません。 |
| IT 主導         | ユーザーは IT 部門にグループを要求します。IT 部門は、ユーザーのニーズに応じた最適な共同作業ツールを選択するように指導できます。 |
| 制御     | グループの作成は特定の人、チーム、またはサービスに制限されています。 詳細については、「 [Microsoft 365 グループを作成できるユーザーを管理](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)する」を参照してください。 |

組織には、グループを作成できるユーザーの厳格な管理を実施するための固有の要件がある場合があります。次の表を利用して、それぞれの組織に適したプロビジョニング モデルについて判断してください。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>組織の要件に適したプロビジョニング モデルは何か?</li><li>組織はグループの作成を管理者に限定する必要があるか?</li><li>組織はグループの作成をセキュリティ グループのメンバーに限定する必要があるか?</li><li>組織はユーザーの属性 (所属部署など) に基づいて一部のグループを動的に作成する必要があるか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>グループとチームの作成に関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部として実装する計画を立てます。</li><li>ユーザーにポリシーについて通達および公開して、ユーザーが要求できる行動を知らせます</li><li>該当する場合は動的メンバーシップを実装する計画を立てます。</li></ul>|

> [!Important]
> グループとチームの作成を制限すると、多くの Microsoft 365 サービスでは、サービスを機能させるためにグループを作成する必要があるため、ユーザーの生産性が低下する可能性があります。 詳細については、「 [Microsoft 365 グループを作成したユーザーを制御する理由](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)」を参照してください。

#### <a name="resources"></a>*リソース*
- [Microsoft 365 グループを作成できるユーザーを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [オブジェクトの属性に基づいて動的にグループを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Outlook 用の Microsoft 365 グループの既定の設定をパブリックまたはプライベートに変更する方法](https://support.microsoft.com/office/36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [セキュリティ グループとチーム メンバーシップを同期する](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>グループの論理的な削除と復元
Microsoft 365 グループを削除した場合は、既定では30日間保持されます。 グループを引き続き復元できるため、この 30 日の期間は "論理的な削除" と呼ばれます。 30 日後、グループおよび関連付けられているコンテンツは完全に削除され、復元することはできません。

> [!Tip]
>- ユーザーに復元処理について通達します。
>- ヘルプデスク チームをトレーニングします。
>- PowerShell スクリプトを使用して削除予定のグループの追跡を実行します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>特定の資産を長期保存のためにアーカイブする必要がありますか?</li><li>組織には保持に関する特定の要件がありますか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>ユーザーに削除および復元のポリシーについて通達および公開して、ユーザーが要求できる行動を知らせます </li><li> 削除したグループの監視に関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li></ul>|

> [!Important]
>"論理的な削除" 期間中にユーザーがサイトにアクセスしようとすると、403 アクセス不可メッセージが表示されます。 この期間が経過した後、ユーザーがサイトにアクセスしようとすると、404 見つかりませんのメッセージが表示されます。

#### <a name="resources"></a>*リソース*
- [削除された Microsoft 365 グループを復元する](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Azure Active Directory で削除された Microsoft 365 グループを復元する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Remove-UnifiedGroup コマンドレットを使用してグループを削除する](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>グループの名前付けポリシー
名前付けポリシーにより、管理者やユーザーはグループの機能、メンバーシップ、地域、グループの作成者を特定しやすくなります。名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。ポリシーを使用すると、グループの名前やエイリアスに特定の単語が使用されないようにブロックできます。

> [!Tip]
> - 短い文字列をサフィックスとして使用します。
> - 値が指定された属性を使用します。
> - 創造的なので、名前の長さの合計は264文字までです。
> - 使用制限する組織固有の禁止単語をアップロードします。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>組織はグループに対する特定の命名規則を必要としていますか?</li><li>組織はすべてのワークロードに通用する命名規則を必要としていますか?</li><li>組織にはユーザーが使用できないようにする特定の単語がありますか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>組織の名前付けグループの要件を文書化します。 </li><li> 該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li><li> 名前付けのポリシーと標準を通達および公開して、ユーザーに知らせます。</li></ul>|

> [!Important]
>名前付けポリシーは、すべてのグループのワークロード (Outlook、Microsoft Teams、SharePoint、Planner、Yammer など) で作成されたグループに適用されます。グループ名とグループのエイリアスのどちらにも適用されます。名前付けポリシーは、ユーザーによるグループの作成時、または既存のグループのグループ名やエイリアスの編集時に適用されます。

#### <a name="resources"></a>*リソース*
- [Microsoft 365 グループの名前付けポリシー](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Microsoft 365 グループの名前付けポリシーを Azure Active Directory に適用する](https://go.microsoft.com/fwlink/?linkid=868340)
- [グループ設定を構成するための Azure Active Directory コマンドレット](https://go.microsoft.com/fwlink/?linkid=868341)
- [グループの名前付けのプレビュー機能](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>グループの有効期限ポリシー
管理者は、有効期限を指定し、その期間の最後に到達して更新されていないすべてのグループを削除することができます。 有効期限は、グループが作成された時点、または最後に更新された日付から始まります。 グループの所有者は、有効期限が切れる前に、別の有効期限が切れるまでグループを更新できるように、メールを自動的に送信します。 アクティブなグループが自動的に更新されます。

グループを有効期限切れに設定した場合:
- 有効期限が近づくと、グループの所有者にグループを更新するための通知が送られます
- 更新されないグループは削除されます
- 削除されたグループは、30 日以内であれば、グループ所有者または管理者によって復元することできます

> [!Tip]
> - 最初に特定のグループでパイロット運用します。
> - Microsoft 365 管理センターのアクティビティ レポートに基づいてアクティブでないグループを選択します。
> - グループの所有者に更新処理について伝えます。
> - ヘルプ デスクチームを参加させます。
> - グループには複数の所有者がいるようにして、孤立したグループに関する電子メールを構成します。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断ポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>孤立グループを処理する戦略を決定します。</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>グループの有効期限、データの保持、アーカイブに関する組織の要件を文書化します。</li><li>該当する要件をグループのロールアウトの一部に実装する計画を立てます。</li><li>所有者が単独または所有者が存在しないグループについてレポートするカスタム ジョブを実装する計画を立てます。 </li></ul>|

> [!Important]
>有効期限ポリシーを変更すると、サービスによって各グループの有効期限が再計算されます。常にグループの作成日からカウントされます。その後で新しい有効期限ポリシーが適用されます。

#### <a name="resources"></a>*リソース*
- [Microsoft 365 グループの有効期限ポリシー](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)
- [Microsoft 365 グループの有効期限ポリシーを構成する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>グループのゲスト アクセス
管理者は、組織全体または個別の Microsoft 365 グループに対して Microsoft 365 グループへのゲストアクセスを許可するかどうかを制御できます。 また、グループへのゲストの追加を許可するユーザーを制御することもできます。
>[!Tip]
>- ゲスト アクセスはテナント レベルで有効化します。必要に応じて、特定のグループへのゲスト アクセスをブロックします。
>- ゲストの許可/禁止ドメイン、ゲスト招待元ロール、アクセス レビュー、利用規約の使用を管理します。
>- 監査ログでゲスト ユーザーのアクティビティを追跡します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>チームにゲストを追加する機能をグループごとに制限する必要がありますか?</li><li> 組織は法的要件やコンプライアンス要件に関連する免責事項を提示する必要がありますか?</li><li>組織はユーザーの追加と削除にかかわる管理の負担を減らす必要がありますか?</li><li>組織はゲスト アクセス/外部アクセスに関する監査制御を期待していますか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次のステップ|<ul><li>特定の分類されたグループに対するゲスト/外部アクセスの要件 (保持期間や発生回数などを含む) を文書化します。</li><li>使用条件とアクセスレビューを必要とするグループについて、組織の要件を文書化します。 </li><li>レビューを実行して、内部ユーザーとゲスト ユーザーの両方のグループ メンバーシップを効率的に管理します。</li></ul>|


#### <a name="resources"></a>*資料*
- [組織外のユーザーとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Microsoft 365 グループでゲストアクセスを管理する](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [ゲストを Microsoft 365 グループに追加する](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Azure Active Directory Terms of Use 機能](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google フェデレーション](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>グループのポリシーと情報保護
Microsoft 365 グループは、Microsoft 365 の高度なセキュリティおよびコンプライアンス機能に基づいて構築されており、分類、監査とレポート、コンプライアンスコンテンツ検索、電子情報開示、法律ホールド、およびアイテム保持ポリシーをサポートしています。
>[!Tip]
>- 組織のニーズに合わせて、分類、使用上のガイドライン、およびラベルを構成します。
>- 保持ポリシーは、ラベルとは別に定義できます。
>- 監査グループのアクティビティ: 作成や削除など。
>- 分類に基づいてグループのプライバシーとゲスト アクセスを管理します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>組織には、すべてのユーザーに通達する必要のある特定の使用に関する要件がありますか?</li><li>組織はすべてのコンテンツの分類を必要としていますか?</li><li>組織はコンテンツを一定期間保持することを必要としていますか?</li><li>組織で特定のデータ保持ポリシーをグループに適用する必要があるかどうか。</li><li>組織は、コンテンツを保持するためにアクティブでないグループをアーカイブする機能を必要としますか?</li><li>グループ作成者は、チームに組織固有の分類を割り当てる機能を必要としますか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>グループの組織の使用ガイドラインを文書化する</li><li>組織の分類の要件を文書化します。</li><li>機密保持、保存、ゲストアクセスなどの分類に基づいて、適用するポリシーを決定します。</li><li>組織の秘密度のラベルと、それに割り当てる保護設定を定義します。</li><li>ユーザーとグループが確認できるラベルを制御するためのラベル ポリシーを定義します。</li><li>[グループの機密度ラベルのプレビュー](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を設定し、組織内のグループの分類を開始します。</li><li>該当する要件をグループのロールアウトの一部として実装する計画を立てます。</li></ul>|


#### <a name="resources"></a>*資料*
- [Microsoft 365 グループの使用ガイドラインへのリンク](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [組織の Office グループに対する分類を作成する](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [グループ設定を構成する](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [アイテム保持ポリシーの概要](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [機密ラベルの概要](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [ラベルの概要](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [監査ログを検索する](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [インプレース訴訟ホールドを作成または削除する](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [保持ポリシーを作成する](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [セキュリティ & コンプライアンスセンターでコンテンツ検索を実行する](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [PowerShell を使用して保持ラベルを一括で作成および発行する](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>従来の共同作業ツールをアップグレードする
数年の組織は、社内内外のユーザーグループとの通信と共同作業を行うために、配布グループに依存しています。 しかし現時点では、Outlook の Microsoft 365 グループはコラボレーションのためのより強力なソリューションを提供しています。 さらに、そのサイトをモダン化する場合は、Microsoft 365 グループを既存の SharePoint サイトに接続できることが重要です。

>[!Tip]
>- Exchange 管理センターを介すか、 PowerShell コマンドレットを使用して、すべての対象となる配布リストを数秒で簡単にアップグレードできます。
>- 既存の SharePoint チームサイトを新しい Microsoft 365 グループに接続します。

|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>組織にはアップグレードの[対象にならない](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade)配布リストがありますか?<li>移行先の配布リストとなるグループの種類を決定します。</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>Microsoft 365 グループにアップグレードする候補となる配布リストを特定します。</li><li>既存の SharePoint チーム サイトを分析して、グループへの接続準備が整っているサイトを確かめます。</li><li>社内の別のチームに配布グループをアップグレードしたことと、そのアップグレードを成功に導いた手順について知らせます。</li></ul>|


#### <a name="resources"></a>*資料*
- [配布リスト (DL) を Outlook のグループにアップグレードする](https://aka.ms/whyupgradedls)
- 1 回のクリックでアップグレードする方法 (Exchange 管理センターまたは [PowerShell スクリプト](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)を使用)
- [配布リストを Microsoft 365 グループに移行する-管理者ヘルプ](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [既存の SharePoint サイトを Microsoft 365 グループに接続する:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [スキャナー データの分析と使用](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint Modernization Scanner](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (GitHub にあるツール)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>グループのレポート
Microsoft 365 Reports dashboard には、組織内の Microsoft 製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。
> [!TIP]
>- グループレポートを使用すると、組織内の Microsoft 365 グループのアクティビティに関する洞察を得ることができ、作成されて使用されているグループの数を確認できます。
>-過去7日間、30 90 日間、30日間、または180日の傾向を確認するには、Microsoft 365 Groups レポートを表示します。
>- グループ メールボックスの会話のすべてにわたるアクティビティ、グループ サイト/ファイルのアクティビティ、グループ メンバーシップに関する詳細 (外部メンバーの数を含む) を監視します。
>- 定期的な監視によってアクティブなグループの所有者を支援し、ユース ケースを調べて、そのユース ケースを内部に広めます。
>- 追加の所見を得るために Power BI コンテンツ パックを活用します。


|         |         |         |
|---------|---------|---------|
|![画像の説明](../../media/decision_point.png)|判断のポイント|<ul><li>組織では、Microsoft 365 グループの使用を理解するために正規のレポートが必要ですか。<li>組織は外部メンバーが参加しているすべてのグループに関するレポートの作成を必要としていますか?</li></ul>|
|![画像の説明](../../media/next_steps.png)|次の手順|<ul><li>定期的にグループアクティビティレポートをレビューするための組織の要件を文書化します。</li></ul>|


#### <a name="resources"></a>*リソース*
- [管理センターの Microsoft 365 レポート](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Office 365 の導入コンテンツ パック](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD コンテンツ パック](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Microsoft Graph グループ アクティビティ API](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 グループレポート (統合グループ)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Azure Active Directory ポータルの監査アクティビティ レポート](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph: デルタ クエリを使用して変更を追跡する](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>クラウド導入行程の開始

Microsoft 365 グループには、組織で必要となる可能性がある、豊富なガバナンス機能のセットが用意されています。 次の組織プロファイルをガイダンスとして検討して、ベストプラクティスを理解し、適切な質問を行ってガバナンスの要件と、それらを満たす方法を決定します。

**次の組織プロファイルについて検討してください。**
- Small Business
- 中規模企業
- 規制またはエンタープライズ

### <a name="small-business"></a>Small Business
少なくとも Exchange Online と SharePoint Online のライセンスを使用して Microsoft 365 を展開している組織で、ビジネスエッセンシャルプランとビジネスプレミアムプランが含まれていること、および Azure Active クタプレミアムライセンスを持たないエンタープライズ E1、E3、E5 プランがあることを検討してください。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li>セルフサービスのプロビジョニングモデルを検討します。</li><li> Outlook および SharePoint サイトのグループは、[既定でプライベート](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395)になります。</li><li> グループを作成するには、既存の配布リスト (Dl) を1つずつ、または一括で PowerShell を介してアップグレードします。 「 [Upgrade distribution lists To Microsoft 365 Groups」を](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)参照してください。</li><li> ゲスト アクセスは有効にしますが、ゲストの許可/禁止ドメインを使用して管理します。</li><li> グループのレポートを使用して、ユーザーによるグループの使用方法に関する所見を得ます。</li><li> すべてのユーザーが共同作業のために1つのチームの一員になるように、組織全体のチーム Microsoft Teams チームを作成することを検討してください。 </li></ul>|
| 次のステップ      |<ul><li>[JSON スキーマ リファレンス](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)で定義されているアクションを使用するコントロールに、既定のデザインを定義するために [サイト デザインとサイト スクリプト](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview)の使用を検討します。</li><li>[グループレポート](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)を確認します。</li><li>グループ合計および非アクティブ/アクティブグループを追跡します。</li><li>使用されている Exchange と SharePoint の両方の記憶域を追跡します。</li><li>グループ メールボックスの会話のすべてにわたるアクティビティ、グループのサイト/ファイルのアクティビティなどを表示します。</li></ul> |

### <a name="medium-sized-business"></a>中規模ビジネス
上記の推奨事項に加えて、Azure Active Directory Premium P1 ライセンスを使用して、少なくとも Enterprise E3/E5 を使用して Microsoft 365 を展開した中規模企業の場合は、次のことを考慮してください。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li>Open または IT 主導のプロビジョニング モデルを決定します。</li><li> 部署などの Azure AD 属性に基づいて、[動的メンバーシップの規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)に関連付けられた特定のグループを作成することを検討します</li><li> 高機密、社外秘 (既定)、一般など、組織内の分類を定義します。</li><li>  保持や機密性などの分類に基づいてポリシーを定義します。</li><li> SharePoint は、すべての Microsoft 365 グループのコンテンツサービスです。 3層の保護 (ベースライン、機密、高機密)[に対して SharePoint Online サイトを設計および展開することを](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection)検討してください。 この 3 層の保護の詳細については、「[SharePoint Online サイトとファイルをセキュリティで保護する](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)」を参照してください。</li><li> 既定では、パブリック グループとプライベート グループの両方が GAL にリストされます。 GAL に表示するグループ、特に Microsoft Teams の外部で作成されたグループを決定します。  特定のグループを非表示にするには、 [set-unifiedgroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx)コマンドレットの "HiddenFromAddressListsEnabled" または "HidefromExchangeClients" を使用します。</li></ul> |
| 次のステップ      |<ul><li>[使用方法のガイドライン](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) を定義して、グループを効果的に維持するために役立つベスト プラクティスや、内部コンテンツのポリシーについてユーザーを教育します。たとえば、分類、ポリシー、手順を理解させることなどです。</li><li>グループのライフサイクル期間 (有効期限ポリシー) を定義します。この期間でグループは更新される必要があり、そうでない場合は削除されます。</li><li>分類に基づいてポリシーを実装するために、次に示すカスタム ジョブの作成を検討します。</li><li>プライバシーをプライベートに設定します。</li><li>外部のメンバーシップ/共有を無効にします。 </li><li>電子メールを送信して、[所有者のいない](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)グループのグループ メンバーに通知します。</li><li>所有権ポリシーを強制します (最低 2 人の所有者)。</li><li> 分類に基づいて、グループのアイテム保持ポリシーを定義します。 </li><li>アイテム保持ポリシーの概要。</li><li>PowerShell を使用して、分類と [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps) でグループを識別します。</li><li>[JSON スキーマ リファレンス](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema)で定義されているアクションを使ったコントロールを定義するために、サイト デザインとサイト スクリプトの使用を検討します。</li><li>[サイト デザインと Microsoft Flow を使用して簡単なサイト ディレクトリを作成する](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial)ことを検討してください。 このサイト デザインを使用してサイトが作成されると、サイトの詳細情報が取り込まれ、リストに書き込まれます。 </li></ul>|

### <a name="regulated-or-enterprise"></a>規制またはエンタープライズ
上記の推奨事項に加えて、Azure Active Directory Premium P1/P2 ライセンスを使用して、少なくとも Enterprise E3/E5 を使用して Office 365 を展開した政府機関、金融サービス、医療機関のような、厳しく規制された、または大規模な企業の場合は、次のことを考慮してください。

| ステージ | 説明 |
| --------------- | ------------------------------------------------------------ |
| ガイダンス |<ul><li> 分類に基づいたグループに関連付けられている SharePoint サイトのデータ ガバナンスのポリシーを定義します。</li><li>[ラベルと DLP で SharePoint Online のファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)します。</li><li>[Azure Information Protection を使用して SharePoint Online ファイルを保護します](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)。</li><li> ユーザーの優先するデータの場所 ([複数地域](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)) に関連付けられた、地域でプロビジョニングされたグループサイト。</li><li> 外部メンバーを含むグループのメンバーシップをレビューします ([アクセス レビュー](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview))。</li><li>アクセスする前に、従業員またはゲスト ユーザーは関連する法的要件またはコンプライアンス要件の免責事項を確認している必要があります。([利用規約](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou))。</li><li>[外部ユーザーを](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561)含む特定の分類を使用して、Microsoft 365 グループを特定して報告します。</li><li>メンバーシップを非表示にする必要がある秘密のグループは、グループ作成時に [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) コマンドレット (HiddenGroup-MembershipEnabled スイッチを使用) を使用して作成する必要があります。</li><li>[暗号化を使用してコンテンツへのアクセスを制限](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)し、特定の Microsoft 365 グループに発行することによって、組織の[機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を定義します。</li><li>[Windows 情報保護と機密ラベル](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)を使用して、機密性の高いコンテンツが Windows を実行している組織のデバイス上に放置されないようにします。 |
| 次のステップ      | <ul><li> サイト デザインとサイト スクリプトを使用して、新しいサイトの作成時に実行される既定の[アクション](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/)を定義します。たとえば、ネイティブでサポートされていない構成を適用するために、[外部共有設定を構成](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting)したり、[Microsoft Flow を起動して Azure 関数を呼び出す](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function)ようにします。</li><li> ラベルおよび DLP を使用して、Microsoft 365 グループに関連付けられているサイトに対して[SharePoint Online ファイルを保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)するための要件を文書化します。</li><li>Microsoft 365 グループに接続されている[SharePoint Online サイトとファイルをセキュリティで保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files)するための組織の要件を文書化します。 </li><li>コンテンツを保護するために[機密ラベル](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を特定のユーザーまたはグループに発行するための組織の要件を文書化します。</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>グループの管理機能の計画チェックリスト

Azure Active Directory を使用して、さまざまなグループに関連するコントロールを管理できます。グループ設定の構成に関する詳細については、「[グループの設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)」を参照してください。

次の表を使用して、組織の要件を展開するために必要な機能を決定できます。これは、計画を進めるために必要なライセンスの決定に役立ちます。

| **機能**      | **詳細**                                    | **Azure AD Premium ライセンスが必要** | **決定事項** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| グループの名前付けポリシー | プレフィックス サフィックスに基づくカスタム ブロックの単語を使用します。 | P1                                    |      TBD     |
| グループの分類 | チームに分類を割り当てます。 | P1                                    |   TBD        |
| グループのゲスト アクセス | ゲストがグループに追加されることを許可または禁止します。 | いいえ                                    |  TBD        |
| グループの作成 | チームの作成を管理者に限定します。 | 不要                                    |   TBD        |
| グループの作成 | チームの作成をセキュリティ グループのメンバーに限定します。 | P1                                    |     TBD      |
| グループの使用方法のガイドライン | すべてのグループ作成のエンドポイントに表示される、「グループの使用方法のガイドライン」にリンクを設定します。 | P1                                    |   TBD        |
| 非表示のメンバーシップ | グループのメンバーではないユーザーから Microsoft 365 グループのメンバーを非表示にする | いいえ                                    |   TBD        |
| 有効期限ポリシー | 有効期限ポリシーを設定して、Microsoft 365 グループのライフサイクルを管理します。 | P1                                    |  TBD        |
| グループのアクティビティ レポート | 組織内の Microsoft 365 グループのアクティビティに関する洞察を得て、作成され、使用されている Microsoft 365 グループの数を確認します。 | いいえ                                    |    TBD       |
| アイテム保持ポリシー | セキュリティ & コンプライアンスセンターで Microsoft 365 グループのアイテム保持ポリシーを設定して、特定の期間のデータを保持または削除します。 **注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。 | 不要                                    |    TBD       |
| データ損失防止ポリシー | Microsoft 365 グループに接続されたサイトで機密情報を識別し、偶発的な共有を防止します。 **注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。 | 不要                                    |     TBD      |
| アーカイブと復元 | アクティブでなくなったチームをアーカイブしますが、参照のために保持したり、今後再アクティブ化したりする必要があります。 | 不要                                    |   TBD        |
| アクセス レビュー | レビューを実行して、内部ユーザーとゲスト ユーザーの両方のグループ メンバーシップを効率的に管理します | P2                                    |   TBD       |
| 利用規約 | エンド ユーザーに情報を提示するために組織が使用できる簡単な方法。このプレゼンテーションにより、ユーザーは法的要件またはコンプライアンス要件に関連する免責事項を確認できます。 | P1                                    |         TBD  |

