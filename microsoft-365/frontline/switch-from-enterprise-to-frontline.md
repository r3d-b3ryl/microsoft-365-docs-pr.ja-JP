---
title: Microsoft 365 E プランから Microsoft 365 F プランへの変更
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: 一部のユーザーを Microsoft 365 E プランから Microsoft 365 F プランに切り替える場合の考慮事項と準備方法について説明します。
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 81ebf6305ca4e60a33eb262fc277efe298d19c43
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331843"
---
# <a name="changing-from-a-microsoft-365-e-plan-to-a-microsoft-365-f-plan"></a>Microsoft 365 E プランから Microsoft 365 F プランへの変更

一部のユーザーを Microsoft 365 E プランから Microsoft 365 [F3](https://www.microsoft.com/microsoft-365/enterprise/f3) または [F1](https://www.microsoft.com/microsoft-365/enterprise/f1) プランに切り替える場合は、この記事では、変更に備えて組織を準備するためのガイダンスを提供します。 E プランから F プランに変更すると、ユーザーがアクセスできるサービスと機能に影響します。

E プランはインフォメーション ワーカー (通常はデスクで働く従業員) を対象としており、F プランは現場担当者 (外出先で、多くの場合、モバイル デバイスで、顧客や一般の人々と直接働く従業員) を対象としています。 各プランは、時間の経過とともに、インフォメーションワーカーと現場担当者それぞれに適したものに進化し続ける可能性があります。 詳細については、「[現場担当者のユーザーの種類とライセンスについて理解する](flw-licensing-options.md)」を参照してください。

ユーザーが F プランに切り替えられたときに予想される内容、変更の準備方法、および組織内の現場担当者を移行する計画を切り替えた後の対処方法の概要を説明します。

## <a name="understand-the-key-differences-between-e-and-f-plans"></a>E プランと F プランの主な違いを理解する

まず、プラン間のサービスと機能の違いに慣れ親しみましょう。

主な違いは次のとおりです:

- F プランには、Office デスクトップ アプリや Outlook デスクトップ アプリは含まれません。
- F プランは、Office モバイル アプリで 10.1 インチ未満の統合画面を備えたデバイスに限定されます。
- F プランでは、Microsoft Teams で、トランシーバー、Tasks、シフト、承認などの[現場担当者アプリを既定でピン留め](pin-teams-apps-based-on-license.md)する予定です。

このセクションでは、これらの主な違いに関する詳細情報を取り上げ、注意すべきその他の違いについて説明しました。 これは包括的なリストではありません。 詳細情報:

- E プランと F プランに含まれる内容の詳細な比較については、「[最新の作業計画の比較](https://go.microsoft.com/fwlink/p/?linkid=2139145)」を参照してください。
- E プランと F プランで利用可能なサービスや機能のリストは、[サービス利用可能性](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-availability-within-each-microsoft-365-and-office-365-plan)と[プラン間の機能利用可能性](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description#feature-availability-across-some-plans)をご覧ください。

### <a name="office-apps"></a>Office アプリ

Office デスクトップ アプリは F3 プランと F1 プランには含まれません。 現場担当者は、Office for the web と Office モバイル アプリを使用して作業を完了できます。 F3 ユーザーは Office for the web 内のドキュメントにフル アクセスでき、F1 ユーザーは読み取り専用アクセス権を持っていることに注意してください。

|サービスまたは機能|Microsoft 365 E3/E5  |Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Office デスクトップ アプリ (Word、Excel、OneNote、PowerPoint、Access、Publisher)|はい|不要|不要|
|Office for the web (Word、Excel、OneNote、PowerPoint)|はい|はい|読み取り専用|
|Office モバイル アプリ (Word、Excel、PowerPoint、Outlook、OneNote)|はい|はい&sup1;|読み取り専用|

&sup1;統合された画面が 10.1 インチ未満のデバイスでサポートされているファイルの編集。

#### <a name="office-for-the-web"></a>Web 用 Office

Office for the web を使用すると、現場担当者は Web ブラウザーを使用して Word、Excel、OneNote、および PowerPoint ファイルを開きます。

Office for the web を使用する場合に注意すべきいくつかの違いを次に示します。 Office for the web と Office デスクトップ アプリの詳細な機能比較については、「[Office for the web のサービスの説明](/office365/servicedescriptions/office-online-service-description/office-online-service-description)」を参照してください。

|サービスまたは機能|いくつかの違い |詳細情報|
|---------|---------|---------|
|**Word for the web**|<ul><li> マクロ対応ドキュメント (.docm) とテンプレート (.dotm) を開いて編集できますが、マクロは実行されません。</li><li>ユーザー定義アクセス許可 (UDP) Information Rights Management (IRM) で保護されたドキュメントを開けますが編集することはできません。</li></ul>|<ul><li>[Office for the web サービスの説明](/office365/servicedescriptions/office-online-service-description/word-online)</li><li>[ブラウザーと Word での文書の使用の相違点](https://support.microsoft.com//office/differences-between-using-a-document-in-the-browser-and-in-word-3e863ce3-e82c-4211-8f97-5b33c36c55f8)</li></ul>|
|**Excel for the web**|<ul><li>マクロ対応ブック (.xlsm) を開いて編集できますが、マクロは実行されません。</li><li>[ファイル サイズの制限](https://support.microsoft.com/office/file-size-limits-for-workbooks-in-sharepoint-9e5bc6f8-018f-415a-b890-5452687b325e)<ul><li>SharePoint Online に保存されているブックを表示または操作するには、ブックが 100 MB 未満である必要があります。 </li><li>Outlook on the web で電子メール メッセージに添付されているブックを開くには、ブックが 10 MB 未満である必要があります。</li></ul></ul>|<ul><li>[Excel for the web サービスの説明](/office365/servicedescriptions/office-online-service-description/excel-online)</li><li>[ブラウザーと Excel でのブックの使用の相違点](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6)</li><li>ほとんどの Excel 関数は、Excel と同じようにブラウザーで動作します。 例外の一覧については、「[Excel および Excel for the web の関数](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6#__functions)」を参照してください。</li></ul>|
|**OneNote for the web**|<ul><li>検索は現在のセクションに限定されます。</li><li>ズームインとズームアウトは使用できません。 代わりに、ユーザーはブラウザーのズーム機能を使用できます。</li></ul>|<ul><li>[OneNote for the web サービスの説明](/office365/servicedescriptions/office-online-service-description/onenote-online)</li><li>[ブラウザーと OneNote でのノートブックの使用の相違点](https://support.microsoft.com/office/differences-between-using-a-notebook-in-the-browser-and-in-onenote-a3d1fc13-ac74-456b-b391-b633a62aa83f)</li></ul>|
|**PowerPoint for the web**|<ul><li>最大 2 GB のファイルを開くことができます。</li><li>マクロ対応のプレゼンテーション (.pptm、.potm、.ppsm) を開いて編集できますが、マクロは実行されません。</li></ul>|<ul><li>[PowerPoint for the web サービスの説明](/office365/servicedescriptions/office-online-service-description/powerpoint-online)</li><li>[Web ベースの PowerPoint での特定の機能の動作](https://support.microsoft.com/office/how-certain-features-behave-in-web-based-powerpoint-a931f0c8-1305-4428-8f7c-9cfa00ef28c5)</li></ul>|

#### <a name="office-mobile"></a>Office Mobile

現場担当者は、次の 2 つの方法でモバイル デバイスで Office を入手できます。

- Word、Excel、PowerPoint を組み合わせた Office モバイル アプリをインストールします。
- Word、Excel、PowerPoint、OneNote 用の個々の Office モバイル アプリをインストールします。

詳細については、「[Android に Office をインストールしてセットアップする](https://support.microsoft.com/office/install-and-set-up-office-on-an-android-cafe9d6f-8b0c-4b03-b20a-12438a82a22d)」を参照し、「[iPhone または iPad で Office をインストールして設定する](https://support.microsoft.com/office/install-and-set-up-office-on-an-iphone-or-ipad-9df6d10c-7281-4671-8666-6ca8e339b628)」を参照してください。

Office モバイルで使用できる機能の詳細については、「[Microsoft 365 サブスクリプションを使用したモバイル デバイス上の Office アプリでできること](https://support.microsoft.com/office/what-you-can-do-in-the-office-apps-on-mobile-devices-with-a-microsoft-365-subscription-9ef8b63a-05fd-4f9c-bac5-29da046833ea)」を参照してください。

#### <a name="email"></a>メール

F3 ユーザーには、Outlook on the web 経由でアクセスできる 2 GB のメールボックスがあります。 Outlook on the web と Outlook デスクトップ アプリの機能の比較については、「[Outlook for PC、Outlook on the web および Outlook for iOS & Android の比較](https://support.microsoft.com/office/compare-outlook-for-pc-outlook-on-the-web-and-outlook-for-ios-android-b26a7bf5-0ac7-48ba-97af-984e0645dde5)」を参照してください。

F1 ユーザーにはメールボックスの権利がありません。 メールボックスは Exchange キオスク プランを通じてユーザーに対してプロビジョニングされますが、メールボックスを使用する権利はありません。 F1 ユーザーの [Outlook on the web を無効にする](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)ことをお勧めします。

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Exchange Online メールボックス|はい (100 GB メールボックス)|はい (2 GB メールボックス)|いいえ&sup1;|
|Outlook デスクトップ アプリケーション|はい|不要|不要|
|アーカイブ メールボックス|はい|不要|不要|
|代理人アクセス|はい|不要|不要|

&sup1;F1 には、Teams 予定表のみを有効にする Exchange キオスク プランが含まれており、メールボックスの権利は含まれません。

詳細については、「[Exchange Online サービスの説明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)」を参照してください。

#### <a name="teams"></a>Teams

F3 と F1 のプランには、現場担当者のコミュニケーションとコラボレーションのための Teams デスクトップ アプリ、モバイル アプリ、Web アプリが含まれます。 現場担当者は、会議、チャット、チャネル、コンテンツ、アプリなどの Teams 機能にアクセスできます。 ただし、ライブ イベントやウェビナーを作成したり、Teams Phone 機能を使用したりすることはできません。

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|ライブ イベント|はい|不要|不要|
|ウェビナー|はい|不要|不要|
|Teams 電話|はい|不要|不要|

#### <a name="sharepoint"></a>SharePoint

F3 および F1 ユーザーは、ドキュメントで共同作業を行い、SharePoint に保存されているトレーニング資料などの組織全体のリソースにアクセスできます。 F3 プランと F1 プランには、サイト メールボックスや個人用サイトは含まれていないことに注意してください。

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|サイト メールボックス|はい|不要|不要|
|個人用サイト|はい|不要|不要|

SharePoint の制限の詳細については、「[SharePoint の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)」を参照してください。

#### <a name="content-services"></a>コンテンツサービス

F3 と F1 のユーザーには、ファイルを格納および共有するための 2 GB の OneDrive ストレージがあります。 詳細については、「[OneDrive サービスの説明](/office365/servicedescriptions/onedrive-for-business-service-description)」を参照してください。

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|OneDrive|無制限のストレージ&sup1;|2 GB のストレージ|2 GB のストレージ|
|Microsoft Stream|はい|はい&sup2;|はい&sup2;|
|Sway|はい|はい|不要|
|Web 用 Visio|はい|はい|読み取り専用|
|Delve|はい|不要|不要|

&sup1;5 人以上のユーザーを持つサブスクリプションのテナントの[既定のクォータ](/onedrive/set-default-storage-space)に基づいて、ユーザーあたり最大 5 TB の初期 OneDrive ストレージ。 さらに多くのストレージを要求できます。</br>
&sup2;ユーザーは会議を記録し、Stream コンテンツを使用できますが、Stream で公開または共有することはできません。

#### <a name="insights-and-analytics"></a>インサイトと分析

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Viva インサイト|はい|不要|いいえ|
|Power BI|はい|不要|不要|

#### <a name="work-management-and-automation"></a>作業管理と自動化

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Power Apps|はい|はい|不要|
|Power Automate|はい|はい|不要|
|Power Virtual Agents|はい|はい|不要|
|Microsoft Dataverse for Teams|はい|はい|不要|
|Microsoft Forms|はい&sup1;|はい&sup1;|不要|
|Microsoft To Do|はい|はい|不要|

&sup1;ライセンスを持つユーザーは、フォームを作成、共有、管理できます。 フォームを完了したり、フォームに応答したりするためにライセンスは必要ありません。

#### <a name="windows"></a>Windows

|サービスまたは機能|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Windows 11 Enterprise|はい|はい&sup1;|不要|

&sup1;長期サービス チャネル (LTSC) または Microsoft Desktop Optimization Pack (MDOP) はありません。 仮想デスクトップ インフラストラクチャ (VDI) は、サービス品質 (QoS) を持つ共有デバイスのライセンスされたユーザーに対してのみ使用されます (Azure Virtual Desktop を除く)。

## <a name="what-to-expect"></a>想定される変化

次の表に、変更プロセス中に考慮すべき重要事項と推奨されるアクションを示します。 この情報は、切り替え前に実行する操作と、切り替え完了後に何を計画するかを特定するのに役立ちます。 

この表は、この記事の後半のセクションで参照します。

|サービスまたは機能 |切り替え前|切り替え後|
|---------|---------|---------|
|Office アプリ| <ul><li>ユーザーのローカル コンピューターに保存されているファイルを特定し、ユーザーが OneDrive に移動するのに役立ちます。</li><li>F プランに切り替えた後、Office デスクトップ アプリは機能低下モードになります。 切り替え後に Office デスクトップ アプリをアンインストールする準備をしてください。</li></ul>| ユーザー:</br> <ul><li>[office.com](https://www.office.com) にサインインして Office for the web にアクセスします。</li><li>[Office モバイル アプリをインストールして使用](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f) します (まだインストールしていない場合)。</li><li>ユーザーは、SharePoint ドキュメント ライブラリ、OneDrive、Teams、Yammer のドキュメントで直接共同作業することもできます。</li></ul>管理者:<ul><li>ユーザーのコンピューターから Office デスクトップ アプリをアンインストールします。</li></ul>      |
|メール、Exchange、Outlook|<ul><li>[Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps) Exchange PowerShell コマンドレットを使用して 2 GB を超えるユーザー メールボックスを識別し、必要に応じてメールボックス サイズを小さくします。 詳細については、「[Outlook on the web のメールボックスストレージの制限](https://support.microsoft.com/office/mailbox-storage-limits-in-outlook-on-the-web-f170fe90-b859-4034-bcda-e186fc6a26f5)」を参照してください。</li><li>ユーザーがアーカイブ メールボックスを持っている場合:</li><ul><li>アーカイブ メールボックスの内容をユーザーのメールボックスに戻します。</li><li>[Get-EXOMailbox](/powershell/module/exchange/get-exomailbox?view=exchange-ps) Exchange Online PowerShell コマンドレットを使用して、メッセージの古さに基づいて電子メールを自動的に移動する可能性があるアーカイブ ポリシーを確認します。</li></ul> <li>サイト メールボックスのアクセスと使用状況を特定します。</li><li>Outlook デスクトップ アプリ、データ、および構成:</li><ul><li>Outlook データ (.pst) ファイルを使用しているユーザーとコンピューターを識別します。</li><li>既存の Outlook クライアント専用ルールを特定して文書化します。</li><li>メール署名をエクスポートします。</li></ul></ul>|ユーザー:</br><ul><li>[office.com](https://www.office.com) にサインインして Outlook on the web にアクセスします。</li><li>[モバイル デバイスでメールを設定](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f)します (まだ設定していない場合)。</li><li>メール署名を確認して更新します。</li><li>メールボックス ルールを確認して更新します。</li></ul>管理者:<ul><li> F1 ユーザーの[Outlook on the web を無効](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)にし、他の方法でメールボックスにアクセスしないように求めます。</li></ul>|
|Teams | <ul><li>ライブ イベントとウェビナーの使用状況を特定します。</li><li>Teams 電話が有効になっているユーザーを特定します。 ユーザーがこの機能を使用している場合は、F プランに移行するための適切なユーザー セットではない可能性があります。</li></ul>      ||
|OneDrive | <ul><li>2 GB 以上または 2 GB に近いストレージを使用しているユーザーを特定します。 (OneDrive は、F プランへの切り替え後に 2 GB の制限を超えるユーザーの場合は読み取り専用になります)。</li><li>ユーザーが OneDrive に格納されているファイルの数と、使用されるストレージの全体的な量を減らすのに役立ちます。</li><li>すべてのファイルがユーザーのコンピューターから OneDrive に完全に同期されていることを確認します。</li></ul>| |

## <a name="prepare-to-switch-plans"></a>プラン切り替えの準備を行う

### <a name="create-a-change-management-strategy"></a>変更管理戦略の作成

最適な変更管理戦略には、F プランに切り替え前後のユーザーとのコミュニケーション、トレーニング、サポートの方法が含まれます。 たとえば、次のことを考慮する必要があります:

- ユーザーはどのように切り替えを意識しますか?
- ユーザーは、サービスと機能の違いをどのようにナビゲートできるようになりますか? Fプランへの切り替えは、行動の変更が必要なため、トレーニングに力を入れる必要があるかもしれません。
- ユーザーはどのようにヘルプとサポートを受けることができますか?

戦略を構築する場合は、コミュニケーションとトレーニングのユーザー設定を検討してください。 移行を確実に成功させるには、現場担当者と会社の文化の特定のニーズに合わせてメッセージング、トレーニング、サポートを調整します。

戦略の計画に役立ついくつかのアイデアを次に示します。

|コミュニケーション|トレーニング|サポート|
|---------|---------|---------|
|<ul><li>メール</li><li>部署またはストア マネージャー</li><li>チャンピオン</li><li>チームとチャネル</li><li>Yammer コミュニティ</li></ul> |<ul><li>Microsoft Online のヘルプ、トレーニング、ビデオ リソース</li><li>社内トレーニング</li></ul>|<ul><li>社内ヘルプデスク</li><li>セルフサービス イントラネット サイト</li><li>Microsoft Online のヘルプ、トレーニング、ビデオ リソース</li><li>現場監督と支持者</li></ul>         |

また、次の導入リソースを確認して、ユーザーのエンゲージメントとトレーニングに役立てることもできます:

- [Microsoft 365 – Microsoft 導入](https://adoption.microsoft.com/microsoft-365/)
- [現場担当者向けの Teams - Microsoft 導入](https://adoption.microsoft.com/microsoft-teams/frontline-workers/)

### <a name="back-up-or-prepare-data"></a>データのバックアップまたは配布準備

ユーザーが保持するデータを特定してバックアップまたは配布準備します。 この記事の前半の「[予想される内容](#what-to-expect)」セクションのガイダンスに従い、次の各コンポーネントについて、表の [**スイッチの前**] 列で推奨されるアクションを実行します:

- Office アプリ
- メール、Exchange、Outlook
- Teams
- OneDrive

詳細については、「[プランを切り替える前にデータをバックアップする](/microsoft-365/commerce/subscriptions/move-users-different-subscription)」を参照してください。

## <a name="switch-users-to-a-microsoft-365-f-plan"></a>ユーザーを Microsoft 365 F プランに切り替える

Microsoft 365 管理センターを使用して、PowerShell コマンドレットを使用して手動でプランまたはスクリプト化されたアプローチを変更できます。 どちらの方法を選択しても、1 回の操作でライセンス変更の割り当てを完了することが重要です。 つまり、既存の E ライセンスを削除し、同じ操作で F ライセンスを割り当てることで置き換えます。

ユーザーの既存のライセンスを削除し、後で新しいライセンスを再割り当てすることは避けてください。 これを行うと、ユーザーのデータに影響を与える可能性があります。 詳細については、「[ライセンスを削除するとユーザーのデータはどうなるか?](/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide#what-happens-to-a-users-data-when-you-remove-their-license)」を参照してください。

Microsoft 管理センターでプランを変更する方法の詳細なガイダンスについては、「[Microsoft プランを手動で変更する](/microsoft-365/commerce/subscriptions/change-plans-manually)」を参照してください。

## <a name="what-to-do-after-switching-plans"></a>プランを切り替えた後の操作

この記事の前半の「[予想される内容](#what-to-expect)」セクションのガイダンスに従い、次の各コンポーネントについて、テーブルの **[切り替え後**] 列で推奨されるアクションを完了します。

- Office アプリ
- メール、Exchange、Outlook
- Teams
- OneDrive

変更が完了したことをユーザーに伝え、変更管理戦略で定義されているヘルプを取得する方法をユーザーに知らせます。 切り替えでサポートするための[ヘルプとラーニング リソース](#user-setup-help-and-learning-resources)へのリンクを含めることができます。

## <a name="user-setup-help-and-learning-resources"></a>ユーザーのセットアップ、ヘルプ、ラーニング リソース

ここでは、トレーニングとサポートのために現場担当者と共有できるセットアップ、ヘルプ、ラーニング リソースへのリンクをいくつか示します。

|アプリ|リンク |
|---------|---------|
|Web 用 Office|<ul><li>[Office for the web のトレーニング](https://support.microsoft.com/office/office-for-the-web-training-e315b031-2bd5-40a1-99ca-264ebf2c8f96)</li><li>[Microsoft 365 での Office for the web の使用を開始する](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)</li></ul>|
|Outlook on the web|<ul><li>[Outlook on the web を知る](https://support.microsoft.com/office/get-to-know-outlook-on-the-web-3f1a229b-0d60-438f-b515-dd7a28026bc1)</li><li>[Outlook on the web に関するヘルプを得る](https://support.microsoft.com/office/get-help-with-outlook-on-the-web-cf659288-35cc-4c6c-8c75-e8e4317fda11)</li><li>[Outlook on the web のビデオ](https://support.microsoft.com/office/learn-more-about-outlook-on-the-web-adbacbab-fe59-4259-a550-6cb7f85f19ec)</li></ul>|
|Office Mobile|セットアップ:</br><ul><li>[Android で Office アプリとメールをセットアップする](https://support.microsoft.com/office/set-up-office-apps-and-email-on-android-6ef2ebf2-fc2d-474a-be4a-5a801365c87f)</li><li>[iOS デバイスで Office アプリとメールをセットアップする](https://support.microsoft.com/office/set-up-the-office-app-and-outlook-on-ios-devices-0402b37e-49c4-4419-a030-f34c2013041f)</li></ul>Office モバイル アプリのヘルプ:<ul><li>[Android 用 Office モバイル アプリのヘルプ](https://support.microsoft.com/office/microsoft-office-app-for-android-0383d031-a1c6-46c9-b734-53cd1d22765b)</li><li>[iOS 用 Office アプリのヘルプ](https://support.microsoft.com/office/microsoft-office-app-for-ios-c8880c05-883a-46b6-ad32-9bffa31228d0)</li></ul>個々の Office モバイル アプリのヘルプ:<ul><li>[Word for Android Phone](https://support.microsoft.com/office/word-for-android-phones-help-764afb31-ad50-4645-8f51-820ecf731d8f), [Word for Android タブレット](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8), [Word for iPhone](https://support.microsoft.com/office/word-for-iphone-help-d41a5299-f6fa-4cca-b529-46a8069c5796), [Word for iPad](https://support.microsoft.com/office/word-for-ipad-help-6567cf2a-c949-4213-912d-f7a14f6264c5)</li><li>[Excel for Android Phone](https://support.microsoft.com/office/excel-for-android-phones-help-f818cb37-bfac-485d-8480-363b3da40596), [Excel for Android タブレット](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8), [Excel for iPhone](https://support.microsoft.com/office/excel-for-iphone-help-b367819b-05b4-4a56-ab1c-678da62e1fd3), [Excel for iPad](https://support.microsoft.com/office/excel-for-ipad-help-6b5dc2e1-a8e4-48e6-bb69-cb9a3964bc91)</li><li>[PowerPoint for Android Phone](https://support.microsoft.com/office/powerpoint-for-android-phones-help-f6714e00-0ee2-48d1-bd3d-e1997565861f), [PowerPoint for Android タブレット](https://support.microsoft.com/office/powerpoint-for-android-tablets-help-2ada1d22-3784-4943-bc47-9d1ede42875c), [PowerPoint for iPhone](https://support.microsoft.com/office/powerpoint-for-iphone-help-754fcb37-783b-4e8a-afca-edb900221b8b), [PowerPoint for iPad](https://support.microsoft.com/office/powerpoint-for-ipad-help-b75ce3bb-03e3-46df-a792-647573fef84a)</li><li>[OneNote for Android](https://support.microsoft.com/office/microsoft-onenote-for-android-46b4b49d-2bef-4746-9c30-6abb5e20b688), [OneNote for iPhone](https://support.microsoft.com/office/microsoft-onenote-for-iphone-b93a0ea8-1285-4d31-a7c5-86a849731902), [OneNote for iPad](https://support.microsoft.com/office/microsoft-onenote-help-ipad-f44e5bcd-5203-4553-9de4-0c56e6500825)</li></ul>
|Teams|<ul><li>[Teams ビデオ トレーニング](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)</li><li>[Teams ヘルプとラーニング](https://support.microsoft.com/teams)</li></ul>|

