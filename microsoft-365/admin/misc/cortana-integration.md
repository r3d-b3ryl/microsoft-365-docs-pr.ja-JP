---
title: CortanaのMicrosoft 365
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
description: 有効な仕事用アカウントまたは学校アカウントを持つCortana、Microsoft 365レベルのセキュリティOffice 365を満たすエクスペリエンスを利用できます。
ms.openlocfilehash: ddf2eaffff528051e3d7268bfb92618d614439fc
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553822"
---
# <a name="cortana-in-microsoft-365"></a>CortanaのMicrosoft 365

Cortana生産性アシスタントは、AI を活用したエクスペリエンスを提供し、時間を節約し、最も重要な点に注目します。 Cortanaは、電子メール、ファイル、チャットなどの Office 365 データを安全かつ安全に処理し、理由付ける機能を提供し、時間を節約し、効率を高め、ユーザーの生産性を向上するように設計されています。

有効な仕事用アカウントまたは学校アカウントでサインインすると、Office 365 のエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束 **("** Cortana エンタープライズ サービス ") を満たす Microsoft 365 エクスペリエンスで、Cortana を使用してクラウドベースのアシスタンス サービスを取得できます。

- **Cortanaエンタープライズ** サービスには、Windows 10 (バージョン 2004 以降) の Cortana、iOS および Android 用 Outlook、iOS および Android および Microsoft Teams ディスプレイ用の Microsoft Teams モバイル アプリが [含](/microsoftteams/devices/teams-displays)まれます。

- これらの異なるエクスペリエンスには、個別のライセンス条項が適用され、以下で説明する個別のオプトアウト手順があります。

- 他の Office 365 サービスと一致する Cortana エンタープライズ サービスは、Online Services Terms [(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されているのと同じエンタープライズ レベルのプライバシー、セキュリティ、およびコンプライアンスの約束を満たしています。

- ブリー Microsoft 365メールや Play My Emails などの新しいエクスペリエンスは、Cortanaエンタープライズ サービスを使用して有効にされ、それらの約束に完全に準拠します。 これらの機能は現在、世界中で利用できます (標準のマルチテナント)。 使用状況の場所の検索の詳細については、「アカウントの追加のプロパティ値を表示 [する」を参照してください](../../enterprise/view-user-accounts-with-microsoft-365-powershell.md#view-additional-property-values-for-accounts)。

- Windows 10 (バージョン 1909 以前) の Cortana を含む既存のコンシューマー エクスペリエンスは[、Microsoft Services](https://www.microsoft.com/licensing/product-licensing/products) Agreement および[Microsoft Privacy](https://privacy.microsoft.com/privacystatement) Statement (以下の「コンシューマー向け既存のサービス」セクションを参照) によって管理されます。 また、これらの用語は、Cortana資格情報でサインインするときにユーザーに提供されるエンタープライズ サービスの管理も行います。

## <a name="what-data-is-processed-by-cortana-enterprise-services"></a>エンタープライズ サービスによって処理Cortanaデータは何ですか? 

Cortanaは、ユーザーからのクエリ、ユーザーの要求を満たすために必要な Office データ、およびサービスを実行するために Microsoft システムによって生成されたその他のテレメトリを処理します。 エンタープライズ サービスによってCortanaデータには、ユーザーの音声クエリ (音声認識からの文字起こし) のテキスト表現が含まれます。 このテキスト データは顧客データであり、オンライン サービス規約に従  [って管理されます](https://www.microsoft.com/licensing/product-licensing/products)。 これは、Online Service Terms と一致する機械学習モデルの開発と改善にのみ使用されます。

## <a name="what-is-the-governance-model-for-customer-data-in-cortana-enterprise-services"></a>エンタープライズ サービスの顧客データのガバナンス モデルCortana。

他のサービスOffice 365一Cortanaエンタープライズ サービスはセキュリティで保護され[、Online Services の条件に従います](https://www.microsoft.com/licensing/product-licensing/products)。 これには、偶発的な損失、改ざん、不正な開示またはアクセス、または違法な破壊に対する顧客データの保護に関する一連の約束が含まれます。 顧客データは、厳密なアクセス制限の対象にもなっています。 Microsoft は、お客様データを使用して、合意されたサービスを提供する目的と、それらのサービスと互換性のある目的でのみ使用します。 詳細については、以下の表を参照してください。

## <a name="how-does-microsoft-store-retain-process-and-use-customer-data-in-cortana"></a>Microsoft では、顧客データを保存、保持、処理、および使用する方法をCortana。

次の表に、エンタープライズ サービスのデータ処理Cortana示します。

| 名前 | 説明 |
|:-----|:-----|
|**ストレージ**  <br/> |顧客データは、クラウド内の Microsoft サーバー Office 365されます。 データはテナントの一部です。 <br/><br/>音声音声は保持されません。  <br/> |
|**Geo に滞在する**  <br/> |顧客データは、Geo のクラウド内の Microsoft Office 365に格納されます。 データはテナントの一部です。  <br/> |
|**Retention**  <br/> |顧客データは、テナント管理者がアカウントを閉じた場合、または GDPR データ主体の権利削除要求が行われたときに削除されます。 <br/><br/>音声音声は保持されません。  <br/> |
|**処理と機密性**  <br/> |顧客データおよび個人データの処理に従事する担当者 (i) は、お客様からの指示に従って、そのようなデータを処理し、(ii) 契約終了後も、そのようなデータの機密性とセキュリティを維持する義務があります。  <br/> |
|**使用状況**  <br/> |Microsoft は、お客様データを使用して、合意されたサービスを提供する目的と、それらのサービスと互換性のある目的でのみ使用します。 モデルの開発と改善を行う機械学習は、その目的の 1 つです。 機械学習はクラウド内でOffice 365され、顧客データの人間による閲覧、レビュー、またはラベル付けはありません。 <br/><br/>データは広告のターゲットに使用されません。  <br/> |

## <a name="cortana-enterprise-services-in-microsoft-365-experiences"></a>Cortanaエクスペリエンスでのエンタープライズ サービスMicrosoft 365する

### <a name="cortana-in-windows-10-version-2004-and-later"></a>Cortana (Windows 10 2004 以降)

Windows 10 Cortana の Cortana アプリは、入力または音声クエリを使用してユーザーと接続したり、予定表を確認したり、リマインダーを設定したりして、Microsoft 365 全体で情報をすばやく取得するのに役立ちます。

CortanaのWindows、ユーザーのスケジュールとタスクの管理を支援できます。 Microsoft To Do でリストに追加し、ローカル情報を検索し、定義を取得し、最新のニュース、天気予報、財務情報をBingできます。

Cortana バージョン 2004 以降の Windows 10 では、オンライン サービス条項[(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されている Cortana エンタープライズ サービスと同じエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束を満たしています。

### <a name="how-to-opt-out-of-cortana-in-windows-10"></a>CortanaのWindows 10

このサービスでCortana Windows 10、個別に制御される他のエクスペリエンスをオプトアウトする必要があります。 管理者は、Cortana\AllowCortana MDM ポリシーを使用するか、またはグループ ポリシー : コンピューター構成\管理用テンプレート\Windows Components\Search\Allow Cortana を使用して、組織の Cortana で Windows 10 を構成できます。

Windows 10 バージョン 2004 から、Cortana は Windows でプレインストールされたユニバーサル Windows プラットフォーム (UWP) アプリであり、Microsoft Store を通じて定期的に更新されます。 最新の更新プログラムを受信するには、Cortana を使用して更新[プログラムを有効にするMicrosoft Store。](/windows/configuration/stop-employees-from-using-microsoft-store)

[詳細については、「Cortana」を参照Windows 10](/windows/configuration/cortana-at-work/cortana-at-work-overview)

### <a name="cortana-voice-assistance-in-teams-mobile-and-teams-display"></a>Cortanaディスプレイでの音声TeamsサポートTeamsする

> [!NOTE]
> Cortanaは、米国、英国、カナダ、インド、オーストラリアのユーザー向け英語の iOS および Android および Microsoft Teams ディスプレイ用の[Microsoft Teams](/microsoftteams/devices/teams-displays)モバイル アプリでサポートされています。  Microsoft TeamsWindowsは、米国のユーザーに対してのみサポートされます。 Cortanaサポートは、現在、GCC-High、DoD、EDU テナントGCC使用できません。 追加の言語と地域への拡張は、今後のリリースの一環として行い、管理者のお客様にはメッセージ センターと新しいロードマップを通[Microsoft 365されます](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=65346)。

Cortana Teams モバイル アプリおよび Microsoft Teams ディスプレイ デバイスでの音声サポートを使用すると、Microsoft 365 Enterprise ユーザーは話し声の自然言語を使用して、コミュニケーション、コラボレーション、会議関連のタスクを合理化できます。 ユーザーは Cortana、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ディスプレイで &#8220;Cortana&#8221; とMicrosoft Teamsします。 チームにハンズフリーで素早く接続し、移動中に、ユーザーは &#8220;から Megan&#8221; または &#8220;に電話などのクエリを言って、次の会議&#8221; にメッセージを送信できます。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使用してファイルを共有し、予定表を確認する、などと言って会議に参加することもできます。 これらの音声支援エクスペリエンスは、Office 365 のプライバシー、セキュリティ、およびコンプライアンスの約束を完全に遵守する Cortana エンタープライズ レベルのサービスを使用して提供されます。これは、オンライン サービス規約[(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されています。

#### <a name="admin-control"></a>管理コントロール

Cortanaは、テナントに対して既定で有効になります。 管理者は、ポリシー (TeamsCortanaPolicy) を使用して、CortanaでTeamsを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。 管理者は、このポリシー コントロール内の CortanaVoiceInvocationMode フィールドを使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているか、ウェイク ワード呼び出しで有効になっているのかを判断することもできます (Microsoft Teams ディスプレイなど、それをサポートするデバイスにも適用されます)。 

#### <a name="user-control"></a>ユーザー コントロール

個々のユーザーは、マイク Cortanaをクリックして、Teamsアプリで音声サポートを試してみてください。 &#8220;Cortana.&#8221; &#8220;Cortana.&#8221; と言うだけで、Microsoft Teams ディスプレイ デバイスで音声アシスタンスを試し、Cortana がウェイク ワードの呼び出しに応答するかどうかを制御することもできます。 Cortana 

1. モバイルTeams開く
2. [ファイル] に **移動設定**
3. [選択 **Cortana**
4. [音声の **アクティブ化] トグルを切り替** える

[音声サポートを使用する方法の詳細については、Teams](https://support.microsoft.com/office/274bb2f0-d962-4182-b45d-307435cea256)

### <a name="cortana-voice-assistance-in-teams-meeting-room"></a>Cortanaでの音声サポートのTeams ミーティング ルーム

Cortana Teams ミーティング ルームでの音声サポートは、ワンタッチ参加、インテリジェントな方法で会議に物理的なホワイトボードを共有するコンテンツ カメラ、自分の個人用デバイスから会議室を Teams 会議にシームレスに転送する近接機能など、独自の会議室機能を提供することで、個人用デバイス上の Teams で行える機能を超えます。 ユーザーは、マイクを押して 「会議を開始する」とCortanaプッシュして話す (PTT) を使用できます。 キーワード スポット (KWS) を有効にすると、ユーザー Cortanaが 「メッセージ」と表示された場合にCortana。 

#### <a name="admin-control"></a>管理コントロール

Cortanaの音声サポートTeams Office 365、企業レベルのプライバシー、セキュリティ、およびコンプライアンスの約束に完全に準拠するサービスを使用して配信されます。 エンタープライズ サービスでのデータ処理のCortanaについては、「Cortana」をMicrosoft 365。 Cortanaは、テナントの会議室Teams既定で有効になっています。 IT 管理者は、音声サポートをオプトアウトして、Teams ミーティング ルームのMicrosoft 365 管理センター。 
 
会議室のすべての機能をCortanaするTeams方法:
1.  アカウントにサインイン[Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?ref=Domains)
2.  デバイスの **選択**
3.  [会議室 **Teams選択]**
4.  変更するデバイスを 1 つ以上選択する
5.  [編集 **] を選択設定**
6.  [既存の値を **Cortana** に移動し、[既存の値を Off に置き換える] を **選択します。**
7.  [適用] を選択します。

会議室で音声のアクティブ化をTeamsする方法:
1.  アカウントにサインイン[Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?ref=Domains)
2.  デバイスの **選択**
3.  [会議室 **Teams選択]**
4.  変更するデバイスを 1 つ以上選択する
5.  [編集 **] を選択設定**
6.  [ウェイク ワード **検出] ボックスのチェックを外** す
7.  [適用] **を選択します。**

#### <a name="configure-cortana-remotely-using-an-xml-configuration-file"></a>XML 構成Cortanaを使用してリモートで構成する
XML 構成ファイルを使用してリモートで Microsoft Teams Rooms コンソール設定を管理する方法については、「会議室のデバイス設定をリモートMicrosoft Teamsする」を[参照してください](/microsoftteams/rooms/xml-config-file)。


[音声サポートの詳細Cortana詳細については、Teams](/microsoftteams/cortana-in-teams)

### <a name="conversational-ai-in-outlook-for-ios-with-cortana"></a>iOS 向けOutlook会話型 AI と Cortana

iOS Outlook では、Cortana の音声駆動型会話型 AI エクスペリエンスを使用すると、ユーザーは生産性アシスタントに会議のスケジュール設定、メールの作成、予定表と受信トレイの管理、あらゆる種類の情報の検索を求めることができます。

Microsoft AI テクノロジに基づく自然言語、音声認識、機械学習、言語学を使用して、Cortana は、組織化を行い、自分にとって重要な人や物事に接続し、一日を制御するのに役立つコンテキストを知る。

マイク ボタンを使用して、会議のCortanaを追加したり、日付、時刻、場所を変更したりします。 また、特定のイベントをCortanaを求めすることもできます。 最後に、クイック メールの作成Cortanaメッセージの転送、スレッドへの返信を求めるメッセージを送信できます。 Cortanaのマイクは、iOS 用の Outlook でマイ メールの再生を開始する場合にも役立ちます。受信トレイをハンズフリーで聞く方法があります。

当初、Cortana を使用したこの新しい会話型 AI 機能は、Outlook for iOS を使用して、Microsoft 365 ワーク アカウントを使用している米国のお客様向け英語で利用できます。 詳細については、「個人の生産性アシスタントと会話を開始する」を参照[OutlookをCortana。](https://techcommunity.microsoft.com/t5/outlook-blog/start-a-conversation-with-your-personal-productivity-assistant/ba-p/2071416#:~:text=Conversational%20AI%20allows%20you%20to,time%2C%20all%20with%20your%20voice)

### <a name="conversational-ai-with-cortana-in-outlook-with-ios-is-an-opt-in-experience"></a>iOS を使用Cortana Outlook会話型 AI は、オプトイン エクスペリエンスです。

個々のユーザーは、iOS の [音声の使用] マイク ボタンを初めて選択した場合に、会話型 AI エクスペリエンスにオプトインOutlookされます。

### <a name="play-my-emails"></a>自分のメールを再生する

[マイ メールの再生] (Outlook モバイル経由で接続されている場合) は、電話、ヘッドホン、または接続されたオーディオ デバイスのスピーカーを介して、ユーザーがフォーカス受信トレイで新しいメッセージを聞き、その日の変更を聞く音声駆動型のハンズフリーエクスペリエンスです。 ユーザーは、Cortanaメールを声に出して読み上げ、Cortana にフラグ、アーカイブ、削除、スキップなどのアクションを実行してもらいます。 この機能は、通勤中、マルチタスク中、または移動中にメールをキャッチアップする場合に特に役立ちます。 ユーザーが Play My Emails でCortanaすると、音声音声要求はエンタープライズ サービスのCortanaされます。 ユーザーの電子メールの読み取りテキストは、クラウド内でOffice 365されます。 このプロセスの間Office 365のモバイル デバイスでデータが処理され、電子メール データは保存されません。 音声コマンドのトランスクリプト (つまり、"読み取りとしてマーク"、"next"、"flag"など) は、Microsoft [Online Services](https://www.microsoft.com/licensing/product-licensing/products)Terms のデータ保護条件に従って保持される場合があります。

Cortanaメールが保護されているときに呼び出し、メッセージを読む前に簡単に一時停止して、ユーザーが再生を一時停止したり、次のメッセージにスキップしたりするのに十分な時間を与える必要があります。 プライベート電話と同様に、機密情報が聞き取り過ぎになる可能性がある場所で再生を開始する場合は注意が必要です。 このような場合、組織の従業員がモバイルで Play My Emails を使用する場合は、適切な環境でヘッドホンを装着Outlook勧めします。

### <a name="how-to-opt-out-of-play-my-emails"></a>Play My Emails をオプトアウトする方法

個人は、次の手順を使用して、自分のメールの再生をオプトアウトできます。

1. モバイルOutlook開きます。

2. に移動 **設定。**
  
3. [マイ **メールの再生] を選択します**。

4. 無効にするアカウントでトグルをオフに移動します。

[Play My Emails の詳細](https://support.microsoft.com/help/4558256)

### <a name="briefing-email"></a>ブリーフィングメール

Cortanaは、タスクとコミットメントを含む個別のブリーフィング メールを送信し、タスクを完了としてマークしたり、フォーカス時間をスケジュールして完了したりします。 また、会議の概要と、その日の関連ドキュメントも含まれます。 Cortanaユーザーの電子メール メッセージから情報を抽出し、ブリーフィング 電子メールに統合されるまで、Exchange Online メールボックスに保存します。 ユーザーのメールボックスの外部で個人データにアクセスExchange Onlineはありません。 ユーザーがブリーフィング メールにアクセスできるのは、ユーザーがサービス プランを含むライセンスExchange Online場合のみです。

### <a name="how-to-opt-out-of-briefing-email"></a>ブリーフィングメールをオプトアウトする方法

管理者は[、PowerShell](/briefing/be-admin)を使用して組織のブリーフィングを構成Exchange Online。 個人は、メッセージのフッター Cortanaで [登録解除] を選択して、ユーザーのブリーフィング メールをオプトアウトできます。

[ブリーフィングメールの詳細](https://support.microsoft.com/help/4558259)

引き続き、組織の生産性を高めるのに役立つ、上記のようなエクスペリエンスを引き続き紹介します。

[Microsoft コンプライアンス サービスの詳細](/compliance/regulatory/offering-home)

## <a name="how-is-the-delivery-of-cortana-enterprise-services-different-from-the-delivery-of-other-cortana-features-i-may-have-previously-experienced"></a>エンタープライズ サービスの配信Cortana、以前に経験した可能性がある他Cortanaの配信とどのように異なりますか?

エンタープライズでの機能を考える 2 つのCortana次に示します。

**エンタープライズ サービスを使用する** 組織Cortana新しいエクスペリエンス: Cortanaエンタープライズ サービスは、組織のセキュリティとコンプライアンスのニーズを満たするように設計されています。 

1. これは新しいサービスであり、このドキュメントで説明します。

2. オンライン サービス条項に従うサービスの場合、Microsoft はデータ 処理者です。Microsoft は顧客から顧客データを収集して使用し、お客様から要求されたオンライン サービスを提供する目的と、お客様が指示した目的でのみ使用します。 EU の一般データ保護規則 (GDPR) では、顧客はデータのデータ管理者です。 「Online [Services の利用規約」および](https://www.microsoft.com/licensing/product-licensing/products) 「商用クラウドのお客様向けプライバシーの透明性の向上 [」をご覧ください](https://blogs.microsoft.com/eupolicy/2019/11/18/introducing-privacy-transparency-commercial-cloud-customers/)。

3. たとえば、Play My Email Cortana s は、ユーザーが iOS 用の Outlook 経由で接続し、エンタープライズ サービスCortana利用できる Cortana サービスです。 

4. IT 管理者は、ProPlus アプリケーションの使用中に、オプションの接続エクスペリエンスと同様に、Cortana接続エクスペリエンスのオプションのOfficeがあります。  

コンシューマー向け既存の **サービス:** Cortana オプションの接続サービスは、主にコンシューマー エクスペリエンス用に設計され、現在は Windows 10 (バージョン 1909 以前) および iOS および Android 上の Cortana アプリで配信されています。

1. これらのエクスペリエンスは、天気、ニュース、トラフィックなどの機能を有効にしています。

2. テナント管理者は、Windows 10 (バージョン 1909 以前) の Cortana と iOS および Android 上の Cortana アプリが Cortana が Office 365 テナント データに接続できるかどうかを制御できます。

組織のCortanaデータへのアクセスをオフにする

1. [組織の <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター]</a>で、[組織  >  **設定]** 設定を選択Cortana。 

2. Windows 10 (バージョン **1909** 以前) の Cortana と iOS と Android の Cortana アプリのチェック ボックスをオフにして、組織内のユーザーに代わって Microsoft ホスト型データにアクセスして Cortana 接続エクスペリエンスを無効にします。

3. **[変更の保存]** を選択します。

Microsoft Services Agreement および [Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174)  [Privacy Statement](https://privacy.microsoft.com/privacystatement)に準拠するサービスの場合、Microsoft はデータ 管理者です。 データ管理者として、Microsoft はデータを使用して、Microsoft プライバシーに関する声明に従って製品および [サービスを改善します](https://privacy.microsoft.com/privacystatement)。

## <a name="related-content"></a>関連コンテンツ
 
[Cortanaの音声サポートのTeams](/microsoftteams/cortana-in-teams) (記事)\
[[CortanaのWindows 10](/windows/configuration/cortana-at-work/cortana-at-work-overview)構成 (記事)\
[[メールを再生する] を使用して、Cortana?](https://support.microsoft.com/help/4558256)

