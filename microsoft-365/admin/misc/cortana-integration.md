---
title: Microsoft 365のCortana
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
- Adm_NonTOC
ms.custom:
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 有効な職場または学校アカウントを持つユーザーは、エンタープライズ レベルのセキュリティの約束を満たすMicrosoft 365エクスペリエンスOffice 365 Cortanaを取得できます。
ms.openlocfilehash: 2f9bf926c2d72115e4c4723940b6a182684b79fb
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782173"
---
# <a name="cortana-in-microsoft-365"></a>Microsoft 365のCortana

個人の生産性アシスタントであるCortanaは、時間を節約し、最も重要な点に注目する AI を活用したエクスペリエンスを提供します。 Cortanaは、電子メール、ファイル、チャットなどのOffice 365データを安全かつ安全に処理し、理由を付ける機能を提供し、時間の節約、効率の向上、ユーザーの生産性の向上を目的として設計されています。

有効な職場または学校アカウントでサインインすると、ユーザーは、Office 365のエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束 ("Cortana エンタープライズ サービス") を満たすMicrosoft 365エクスペリエンスでCortanaを使用してクラウドベースのアシスタンス **サービスを** 利用できます。

- **Cortanaエンタープライズ サービスには**、Windows 10 (バージョン 2004 以降) のCortana、iOS と Android のOutlook、iOS および Android 用のモバイル アプリの [Microsoft Teams Microsoft Teams表示](/microsoftteams/devices/teams-displays)が含まれます。

- これらの異なるエクスペリエンスには、個別のライセンス条項が適用され、以下で説明する個別のオプトアウト手順があります。

- 他のOffice 365 サービスと一致するCortanaエンタープライズ サービスは、[Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products) に反映されるのと同じエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束を満たします。

- ブリーフィング メールや Play My Emails などの新しいMicrosoft 365 エクスペリエンスは、Cortanaエンタープライズ サービスを使用して有効になり、それらの約束に完全に準拠します。 これらの機能は現在、世界中で利用できます (標準のマルチテナント)。 使用場所の検索の詳細については、 [アカウントのその他のプロパティ値の表示に関するページを](../../enterprise/view-user-accounts-with-microsoft-365-powershell.md#view-additional-property-values-for-accounts)参照してください。

- Windows 10 (バージョン 1909 以前) のCortanaを含む既存のコンシューマー エクスペリエンスは[、Microsoft Services 契約](https://www.microsoft.com/licensing/product-licensing/products)と [Microsoft プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)に準拠しています (以下の「コンシューマー向けの既存のサービス」セクションを参照)。 これらの用語は、コンシューマー資格情報を使用してサインインしたときにユーザーに提供されるエンタープライズ サービスCortanaも管理します。

## <a name="what-data-is-processed-by-cortana-enterprise-services"></a>Cortanaエンタープライズ サービスによって処理されるデータは何ですか?

エンタープライズ サービスCortana、ユーザーからのクエリ、ユーザーの要求を満たすために必要なデータOffice、サービスを実行するために Microsoft システムによって生成されたその他のテレメトリが処理されます。 Cortanaエンタープライズ サービスによって収集されるデータには、ユーザーの音声クエリ (音声認識からの文字起こしなど) のテキスト表現が含まれます。 このテキスト データは顧客データであり、  [Online Services の使用条件](https://www.microsoft.com/licensing/product-licensing/products)に従って管理されます。 これは、Online Service Terms と一致する機械学習モデルの開発と改善にのみ使用されます。

## <a name="what-is-the-governance-model-for-customer-data-in-cortana-enterprise-services"></a>Cortanaエンタープライズ サービスにおける顧客データのガバナンス モデルは何ですか?

他のOffice 365 サービスと一致して、Cortanaエンタープライズ サービスはセキュリティで保護され、[Online Services の使用条件](https://www.microsoft.com/licensing/product-licensing/products)に従います。 これには、偶発的な損失、変更、不正な開示またはアクセス、または違法な破壊に対する顧客データの保護に関する一連の約束が含まれます。 顧客データには、厳密なアクセス制限も適用されます。 Microsoft は、合意されたサービスを提供し、それらのサービスと互換性のある目的でのみ、顧客データを使用します。 詳細については、次の表を参照してください。

## <a name="how-does-microsoft-store-retain-process-and-use-customer-data-in-cortana"></a>Microsoft では、Cortanaでの顧客データの保存、保持、処理、および使用はどのように行われますか?

次の表では、Cortana エンタープライズ サービスのデータ処理について説明します。

|名前|説明|
|---|---|
|**ストレージ**|顧客データは、Office 365 クラウド内の Microsoft サーバーに格納されます。 データはテナントの一部です。 <br/><br/>音声オーディオは保持されません。|
|**Geo に留まる**|顧客データは、Geo のOffice 365 クラウド内の Microsoft サーバーに格納されます。 データはテナントの一部です。|
|**Retention**|顧客データは、アカウントがテナント管理者によって終了されたとき、または GDPR データ主体の権利の削除要求が行われたときに削除されます。 <br/><br/>音声オーディオは保持されません。|
|**処理と機密性**|顧客データと個人データの処理に従事する担当者 (i) は、お客様からの指示に基づいてのみそのようなデータを処理し、(ii) 契約終了後もそのようなデータの機密性とセキュリティを維持する義務があります。|
|**使用状況**|Microsoft は、合意されたサービスを提供し、それらのサービスと互換性のある目的でのみ、顧客データを使用します。 モデルを開発および改善するための機械学習は、その目的の 1 つです。 機械学習はOffice 365 クラウド内で行われ、カスタマー データの人間の表示、レビュー、またはラベル付けは行われません。 <br/><br/>データは、広告のターゲット設定には使用されません。|

## <a name="cortana-enterprise-services-in-microsoft-365-experiences"></a>Microsoft 365 エクスペリエンスでエンタープライズ サービスをCortanaする

### <a name="cortana-in-windows-10-version-2004-and-later"></a>Windows 10のCortana (バージョン 2004 以降)

Windows 10のCortana アプリを使用すると、ユーザーはMicrosoft 365全体の情報をすばやく取得できます。入力または音声クエリを使用して、ユーザーとの接続、予定表の確認、リマインダーの設定などを行うことができます。

WindowsのCortanaは、ユーザーがスケジュールとタスクをより適切に管理するうえで役立ちます。 Microsoft To Doでリストに追加したり、ローカル情報を検索したり、定義を取得したり、Bing検索で最新のニュース、天気、財務情報を追跡したりすることができます。

Windows 10バージョン 2004 以降のCortanaは、[Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products) に示されているように、Cortanaエンタープライズ サービスに対する同じエンタープライズ レベルのプライバシー、セキュリティ、およびコンプライアンスの約束を満たしています。

### <a name="how-to-opt-out-of-cortana-in-windows-10"></a>Windows 10でCortanaをオプトアウトする方法

Windows 10でCortanaをオプトアウトしても、個別に制御される他のエクスペリエンスはオプトアウトされません。 管理者は、Experience\AllowCortana MDM ポリシーを使用するか、グループ ポリシー: Computer Configuration\Administrative Templates\Windows Components\Search\Allow Cortanaを使用して、組織のWindows 10でCortanaを構成できます。

Windows 10バージョン 2004 以降では、CortanaはWindowsがプレインストールされたユニバーサル Windows プラットフォーム (UWP) アプリであり、Microsoft Storeを通じて定期的に更新されます。 Cortanaに対する最新の更新プログラムを受け取るには、[Microsoft Storeを使用して更新プログラムを有効にする必要があります](/windows/configuration/stop-employees-from-using-microsoft-store)。

[Windows 10でCortanaの詳細を確認する](/windows/configuration/cortana-at-work/cortana-at-work-overview)

### <a name="cortana-voice-assistance-in-teams-mobile-and-teams-display"></a>TeamsモバイルディスプレイとTeamsディスプレイでの音声アシスタンスのCortana

> [!NOTE]
> Cortana音声アシスタンスは、iOS および Android 用のMicrosoft Teams モバイル アプリでサポートされており、[Microsoft Teams 米国](/microsoftteams/devices/teams-displays)、イギリス、カナダ、インド、オーストラリアのユーザー向けに英語で表示されます。  WindowsのMicrosoft Teams Roomsは、米国のユーザーにのみサポートされます。 Cortana音声アシスタンスは、現在、GCC、GCC-High、DoD、EDU テナントでは使用できません。 今後のリリースの一環として、追加の言語とリージョンへの拡張が行われ、管理者のお客様にはメッセージ センターと[Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=65346)を通じて通知されます。

Teams モバイル アプリやMicrosoft Teamsディスプレイ デバイスでの音声アシスタンスをCortanaすると、Microsoft 365 Enterpriseユーザーは音声自然言語を使用してコミュニケーション、コラボレーション、会議関連のタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ディスプレイで "Cortana" と言って、Cortanaに話しかけることができます。 ハンズフリーで、外出先でチームにすばやく接続するために、ユーザーは "Megan の呼び出し" や "次の会議にメッセージを送信する" などのクエリを言うことができます。 ユーザーは、"次の会議に参加する" と言って会議に参加したり、音声アシスタンスを使用してファイルを共有したり、予定表を確認したりすることもできます。 これらの音声アシスタンス エクスペリエンスは、Office 365のプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するエンタープライズ レベルのサービスCortanaを使用して提供されます[(Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products) に反映されます。

#### <a name="admin-control"></a>管理者コントロール

Cortana音声アシスタンスは、テナントに対して既定で有効になります。 管理者は、テナント内のユーザーがポリシー (TeamsCortanaPolicy) を介してTeamsでCortana音声アシスタンスを使用できるかを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortanaが無効になっているか、プッシュ ボタンの呼び出しでのみ有効になっているか、ウェイク ワード呼び出しで有効になっているかを判断することもできます (Microsoft Teams表示など、それをサポートするデバイスにも適用できます)。

#### <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、マイク ボタンCortanaクリックして、Teamsモバイル アプリで音声アシスタンスを試すことができます。 "Cortana" と言うだけで、ディスプレイ デバイスMicrosoft Teams音声アシスタンスCortana試すことができます。 また、ウェイク ワードの呼び出しCortana応答するかどうかを制御することもできます。

1. モバイルTeams開く
2. **設定** に移動する
3. **Cortana** を選択する
4. **音声アクティブ化** の切り替えを切り替える

[Teamsでの音声アシスタンスの使用の詳細](https://support.microsoft.com/office/274bb2f0-d962-4182-b45d-307435cea256)

### <a name="cortana-voice-assistance-in-teams-meeting-room"></a>Teams ミーティング ルームで音声アシスタンスをCortanaする

Teams会議室でのCortana音声アシスタンスは、パーソナル デバイスでTeamsで行うことができる機能を超えて、ワンタッチ参加などの独自の室内機能、インテリジェントな方法で会議に物理的なホワイトボードを共有するコンテンツ カメラ、自分の個人用デバイスから会議室をTeams会議にシームレスに転送するなどの近接機能を提供します。 ユーザーは、マイクを押して "会議を開始する" と言ってCortanaを開始することで、プッシュを使用して通話 (PTT) を行うことができます。 キーワード スポット (KWS) を有効にすると、ユーザーが "Cortana" と言ったときにCortanaリッスンが開始されます。

#### <a name="admin-control"></a>管理者コントロール

TeamsのCortana音声アシスタンスは、Office 365エンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠するサービスを使用して提供されます。 Cortana エンタープライズ サービスでのデータ処理の詳細については、Microsoft 365のCortanaを参照してください。 Cortanaは、テナント用のTeamsミーティング ルームで既定で有効になっています。 IT 管理者は、Microsoft 365 管理センターのTeams ミーティング ルームに対する音声アシスタンスをオプトアウトできます。

Teams会議室のすべてのCortana機能をオプトアウトする方法:

1. [Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?ref=Domains)にサインインする
2. **デバイスの** 選択
3. **Teams Rooms** を選択する
4. 変更する 1 つまたは複数のデバイスを選択する
5. [**編集] 設定** を選択する
6. **Cortana** に移動し、[既存の値を **オフ** に置き換える] を選択します
7. 適用を選択する

Teams会議室で音声アクティブ化をオプトアウトする方法:

1. [Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?ref=Domains)にサインインする
2. **デバイスの** 選択
3. **Teams Rooms** を選択する
4. 変更する 1 つまたは複数のデバイスを選択する
5. [**編集] 設定** を選択する
6. **ウェイク ワード検出** ボックスをオフにする
7. 適用を選択 **する**

#### <a name="configure-cortana-remotely-using-an-xml-configuration-file"></a>XML 構成ファイルを使用してリモートでCortanaを構成する

XML 構成ファイルを使用してMicrosoft Teams Rooms コンソール設定をリモートで管理する方法については、「[デバイス設定Microsoft Teams Roomsリモートで管理](/microsoftteams/rooms/xml-config-file)する」を参照してください。

[Teamsでの音声アシスタンスCortana詳細を確認する](/microsoftteams/cortana-in-teams)

### <a name="conversational-ai-in-outlook-for-ios-with-cortana"></a>Cortanaを使用した iOS 用Outlookの会話型 AI

iOS のOutlookでは、Cortanaの音声駆動型の会話型 AI エクスペリエンスを使用すると、ユーザーは生産性アシスタントに会議のスケジュール設定、メールの作成、予定表と受信トレイの管理、あらゆる種類の情報の検索を依頼できます。

Microsoft AI テクノロジに基づく自然言語、音声認識、機械学習、および言語学を使用して、Cortana、自分のコンテキストを把握し、組織化し、重要な人や物事につながり、1 日の管理に役立ちます。

マイク ボタンを使用して、会議の受信者を追加したり、日付、時刻、場所を変更したりするようにCortanaに依頼するだけです。 Cortanaに特定のイベントの検索を依頼することもできます。 最後に、クイック メールの作成、メッセージの転送、スレッドへの返信をCortanaに依頼できます。 Cortanaのマイクを使用すると、iOS 向けのOutlookでマイ メールの再生を開始し、受信トレイをハンズフリーで聞くこともできます。

当初、この新しい会話型 AI 機能とCortanaは、Microsoft 365仕事用アカウントを持つ iOS のOutlookを使用して、米国のお客様に英語で提供されます。 詳細については、Cortanaに関する[Outlookの個人用生産性アシスタントとの会話を開始](https://techcommunity.microsoft.com/t5/outlook-blog/start-a-conversation-with-your-personal-productivity-assistant/ba-p/2071416#:~:text=Conversational%20AI%20allows%20you%20to,time%2C%20all%20with%20your%20voice)する方法に関するページを参照してください。

### <a name="conversational-ai-with-cortana-in-outlook-with-ios-is-an-opt-in-experience"></a>iOS を使用したOutlookでのCortanaとの会話型 AI はオプトイン エクスペリエンスです

個々のユーザーは、iOS のOutlookで "音声を使用する" マイク ボタンを初めて選択したときに、会話型 AI エクスペリエンスにオプトインするように求められます。

### <a name="play-my-emails"></a>自分のメールを再生する

マイ メールを再生する (Outlook モバイル経由で接続されている) は、ユーザーがフォーカスされた受信トレイで新しいメッセージを聞き取り、電話、ヘッドフォン、または接続されたオーディオ デバイス上のスピーカーを介して 1 日に変更される音声ドリブンのハンズフリー エクスペリエンスです。 ユーザーは、Cortanaに最近のメールを読み上げるよう求め、フラグ、アーカイブ、削除、スキップメッセージなどのアクションを実行するようにCortanaに依頼できます。 この機能は、通学中、マルチタスク中、または外出先でメールに追いつくために特に役立ちます。 ユーザーが Play My Emails でCortanaと会話すると、音声オーディオ要求はエンタープライズ サービスCortana直接行われます。 ユーザーの電子メールのテキスト読み上げは、Office 365 クラウド内で処理されます。 このプロセス中、ユーザーのモバイル デバイスではOffice 365データは処理されません。電子メール データは保存されません。 読み上げられたコマンドのトランスクリプト ("読み取りとしてマークする"、"次へ"、"フラグ"など) は、Microsoft [Online Services 利用規約](https://www.microsoft.com/licensing/product-licensing/products)のデータ保護条項に従って保持される場合があります。

Cortanaは、メールが保護されたときに呼び出され、メッセージを読む前に一時停止して、ユーザーが再生を一時停止したり、次のメッセージにスキップしたりするのに十分な時間を与えます。 プライベート電話と同様に、機密情報が聞き取られる可能性がある場所で再生を開始する場合は、注意が必要です。 このような場合は、組織の従業員がモバイルで Play My Emails を使用する場合に、適切な環境でヘッドフォンOutlook装着することをお勧めします。

### <a name="how-to-opt-out-of-play-my-emails"></a>Play My Emails をオプトアウトする方法

個人は、次の手順を使用して、自分のメールの再生をオプトアウトできます。

1. モバイルOutlook開きます。

2. [**設定**] に移動します。

3. [ **自分のメールを再生]** を選択します。

4. 無効にするアカウントのトグルをオフに移動します。

[メールを再生する方法の詳細](https://support.microsoft.com/help/4558256)

### <a name="briefing-email"></a>ブリーフィングメール

Cortanaは、完了として **マークしたり、** フォーカス時間をスケジュールして完了できるように便利な方法で行ったタスクとコミットメントを含む、パーソナライズされたブリーフィングメールを送信します。 また、会議の概要と、1 日の関連ドキュメントも含まれます。 Cortanaは、ユーザーの電子メール メッセージから情報を抽出し、ブリーフィング メールに統合されるまでExchange Onlineメールボックスに格納します。 Exchange Online メールボックスの外部から個人データにアクセスできる場合はありません。 ユーザーは、Exchange Onlineサービス プランを含むライセンスがある場合にのみ、ブリーフィングメールにアクセスできます。

### <a name="how-to-opt-out-of-briefing-email"></a>ブリーフィングメールをオプトアウトする方法

管理者は、Exchange Onlineの [PowerShell](/briefing/be-admin) を使用して、組織のブリーフィングを構成できます。 個人は、メッセージのフッターで [**サブスクライブ解除]** を選択することで、Cortanaのブリーフィングメールからオプトアウトできます。

[ブリーフィングメールの詳細を確認する](https://support.microsoft.com/help/4558259)

組織の生産性を向上させるために、上記のようなより多くのエクスペリエンスを引き続き紹介します。

[Microsoft コンプライアンス オファリングの詳細を確認する](/compliance/regulatory/offering-home)

## <a name="how-is-the-delivery-of-cortana-enterprise-services-different-from-the-delivery-of-other-cortana-features-i-may-have-previously-experienced"></a>Cortanaエンタープライズ サービスの配信は、以前に経験した可能性のある他のCortana機能の配信とどのように異なりますか?

企業でのCortanaのしくみを考える 2 つの方法を次に示します。

**Cortanaエンタープライズ サービスを持つ組織の新しいエクスペリエンス**: Cortanaエンタープライズ サービスは、組織のセキュリティとコンプライアンスのニーズを満たすように設計されています。

1. これは新しいサービスであり、このドキュメントでここで説明します。

2. Online Services 利用規約に従うサービスの場合、Microsoft はデータ プロセッサです。Microsoft は、お客様から要求されたオンライン サービスを提供するため、およびお客様から指示された目的でのみ、顧客データを収集して使用します。 EU の一般データ保護規則 (GDPR) の下で、顧客はデータのデータ 管理者です。 [Online Services の使用条件](https://www.microsoft.com/licensing/product-licensing/products)と、[商用クラウドのお客様のプライバシーの透明性の強化に関するご紹介をご覧ください](https://blogs.microsoft.com/eupolicy/2019/11/18/introducing-privacy-transparency-commercial-cloud-customers/)。

3. たとえば、Play My Emails は、ユーザーが iOS のOutlook経由で接続でき、エンタープライズ サービスCortana利用できるCortana サービスです。

4. IT 管理者は、Office ProPlus アプリケーションの使用時のオプションの接続エクスペリエンスと同様に、Cortanaのオプションの接続エクスペリエンスを常に制御できます。

**コンシューマー向けの既存のサービス**: Cortanaオプションの接続済みサービスは、主にコンシューマー エクスペリエンス向けに設計されており、現在はWindows 10 (バージョン 1909 以前) と iOS および Android 上のCortana アプリで提供されています。

1. これらのエクスペリエンスにより、天気、ニュース、トラフィックなどの機能が有効になります。

2. テナント管理者は、Windows 10 (バージョン 1909 以前) のCortanaと、iOS および Android 上のCortana アプリがOffice 365テナント データへの接続をCortanaできるかどうかを制御できます。

組織の Microsoft ホステッド データへのアクセスCortana無効にする

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で設定 **Org 設定****を選択** > し、**Cortana** を選択します。

2. Windows 10 **(バージョン 1909 以前) の [Cortanaを許可する] チェック ボックスと、iOS と Android 上のCortana アプリのチェック ボックスをオフにして、組織内のユーザーに代わって Microsoft がホストするデータにアクセスして、** Cortana接続エクスペリエンスを無効にします。

3. **[変更の保存]** を選択します。

[Microsoft サービス契約](https://go.microsoft.com/fwlink/p/?LinkId=2109174)と [Microsoft プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)に準拠するサービスの場合、Microsoft はデータ コントローラーです。 データ コントローラーとして、Microsoft は、Microsoft [のプライバシーに](https://privacy.microsoft.com/privacystatement)関する声明に従って、データを使用して製品とサービスを改善します。

## <a name="related-content"></a>関連コンテンツ

[Teamsでの音声アシスタンスのCortana](/microsoftteams/cortana-in-teams) (記事)\
[Windows 10でCortanaを構成する](/windows/configuration/cortana-at-work/cortana-at-work-overview) (記事)\
[Cortanaから自分のメールを再生する方法](https://support.microsoft.com/help/4558256)
