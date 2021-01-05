---
title: Microsoft 365 の Cortana
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 有効な仕事用アカウントまたは学校アカウントでサインインすると、ユーザーは Office 365 のエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束を満たす Microsoft 365 エクスペリエンスで Cortana を使用してクラウドベースのアシスタンス サービスを利用できます。
ms.openlocfilehash: bd296b19d0e21abb39fe39e2a0bb92d0d84d9034
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751337"
---
# <a name="cortana-in-microsoft-365"></a>Microsoft 365 の Cortana

個人の生産性アシスタントである Cortana は、AI を活用したエクスペリエンスを提供し、時間を節約し、最も重要な事柄に集中します。 Cortana は、ユーザーが仕事と生活の両方で 1 日の個人の生産性を向上させるのに役立ちます。 有効な仕事用アカウントまたは学校アカウントでサインインすると、ユーザーは Office 365 のエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束 ("Cortana enterprise services") を満たす Microsoft 365 エクスペリエンスで、Cortana を使用してクラウドベースのアシスタンス サービスを利用できます。 

個人生産性アシスタントとして、Cortana は、時間の節約、効率性の向上、ユーザーの生産性の向上を目的として、Office 365 データ (メール、ファイル、チャットなど) を安全かつ安全に処理および理由付ける機能を提供するように設計されています。

今後は、企業の生産性に Cortana を重点的に取り入えています。

- Cortana エンタープライズ サービスは、他の Office 365 サービスと一貫性があり、オンライン サービスの使用条件 [(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されているのと同じエンタープライズ レベルのプライバシー、セキュリティ、コンプライアンスの約束を満たします。

- 新しい Microsoft 365 エクスペリエンス ([説明] メールや [自分のメールの再生] など) は、Cortana エンタープライズ サービスを使用して有効にされ、それらの約束に完全に準拠します。 これらの機能は現在、世界中で利用可能です (標準のマルチテナント)。 使用場所の検索の詳細については、「アカウントの追加のプロパティ値を表示する」を [参照してください](https://docs.microsoft.com/microsoft-365/enterprise/view-user-accounts-with-microsoft-365-powershell?view=o365-worldwide#view-additional-property-values-for-accounts)。

- ユーザーは、Windows 10 (バージョン 2004 以降) の Cortana や、iOS および Android 用の Outlook などのクライアント アプリケーションを通じて、ここで説明する Cortana エンタープライズ サービスに個別のライセンス条項に従って接続できます。 

- Windows 10 (バージョン 1909 以前) の Cortana や iOS および Android の Cortana アプリを含む既存のコンシューマー エクスペリエンスは [、Microsoft サービス](https://www.microsoft.com/licensing/product-licensing/products) 規約と [Microsoft](https://privacy.microsoft.com/privacystatement) プライバシーに関する声明 (下記の「コンシューマー向け既存のサービス」セクションを参照) によって管理されます。 これらの条件は、ユーザーの資格情報でサインインするときにユーザーに提供される Cortana エンタープライズ サービスも管理します。

## <a name="what-data-is-processed-by-cortana-enterprise-services"></a>Cortana エンタープライズ サービスによってどのようなデータが処理されますか? 

Cortana エンタープライズ サービスは、ユーザーからのクエリ、Office要求を満たすために必要なデータ、およびサービスを実行するために Microsoft システムによって生成されたその他の利用統計情報を処理します。 Cortana エンタープライズ サービスによって収集されるデータには、ユーザーの音声クエリ (音声認識によるトランスクリプション) のテキスト表現が含まれます。 このテキスト データは顧客データであり、オンライン サービスの使用条件に従  [って管理されます](https://www.microsoft.com/licensing/product-licensing/products)。 オンライン サービスの使用条件と一致する機械学習モデルを開発および改善するためにのみ使用されます。

## <a name="what-is-the-governance-model-for-customer-data-in-cortana-enterprise-services"></a>Cortana エンタープライズ サービスの顧客データのガバナンス モデルは何ですか?

Cortana エンタープライズ サービスは、Office 365 サービスと一貫性があり、オンライン サービスの使用条件 [の対象になります](https://www.microsoft.com/licensing/product-licensing/products)。 これには、偶発的な損失、改変、不正な開示またはアクセス、または不法な破壊に対する顧客データの保護に関する一連の約束が含まれます。 顧客データは、厳密なアクセス制限の対象にもなっています。 Microsoft は、お客様データを使用して、合意されたサービスおよびそれらのサービスと互換性のある目的でのみ提供します。 詳細については、次の表を参照してください。

## <a name="how-does-microsoft-store-retain-process-and-use-customer-data-in-cortana"></a>Microsoft では、Cortana で顧客データを保存、保持、処理、使用する方法について説明します。

次の表では、Cortana エンタープライズ サービスのデータ処理について説明します。

| 名前 | 説明 |
|:-----|:-----|
|**ストレージ**  <br/> |顧客データは、Office 365 クラウド内の Microsoft サーバーに保存されます。 データはテナントの一部です。 <br/><br/>音声オーディオは保持されません。  <br/> |
|**Geo に残る**  <br/> |顧客データは、Geo の Office 365 クラウド内の Microsoft サーバーに保存されます。 データはテナントの一部です。  <br/> |
|**Retention**  <br/> |顧客データは、テナント管理者によってアカウントが閉鎖された場合、または GDPR データ主体の権利削除要求が行われたときに削除されます。 <br/><br/>音声オーディオは保持されません。  <br/> |
|**処理と機密性**  <br/> |顧客データおよび個人データの取り扱いを行う担当者 (i) は、お客様からの指示に基でのみそのようなデータを処理し、(ii) 契約終了後も、そのようなデータの機密性とセキュリティを維持する義務があります。  <br/> |
|**使用法**  <br/> |Microsoft は、お客様データを使用して、合意されたサービスおよびそれらのサービスと互換性のある目的でのみ提供します。 モデルの開発と改善のための機械学習は、その目的の 1 つです。 機械学習は Office 365 クラウド内で行われ、顧客データの人間による表示、レビュー、ラベル付けはありません。 <br/><br/>データは広告のターゲット設定には使用されません。  <br/> |

## <a name="cortana-enterprise-services-in-microsoft-365-experiences"></a>Microsoft 365 エクスペリエンスの Cortana エンタープライズ サービス

### <a name="cortana-in-windows-10-version-2004-and-later"></a>Windows 10 の Cortana (バージョン 2004 以降)

Windows 10 の Cortana アプリは、ユーザーが Microsoft 365 全体で情報をすばやく取得し、入力クエリや音声クエリを使用してユーザーとの接続、予定表の確認、リマインダーの設定を行うのに役立ちます。

Windows の Cortana は、ユーザーが自分のスケジュールとタスクをより良く管理できるよう支援します。 Bing 検索を使用して、Microsoft To Do のリストに追加し、ローカル情報を検索し、定義を取得し、最新のニュース、天気、財務情報を追跡できます。

Windows 10 バージョン 2004 以降の Cortana は、オンライン サービスの使用条件 [(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されているのと同じエンタープライズ レベルのプライバシー、セキュリティ、および Cortana エンタープライズ サービスのコンプライアンスの約束を満たします。

### <a name="how-to-opt-out-of-cortana-in-windows-10"></a>Windows 10 で Cortana をオプトアウトする方法

管理者は、Experience\AllowCortana MDM ポリシーを使って、またはグループ ポリシー (コンピューターの構成\管理用テンプレート\Windows コンポーネント\検索\Cortana を許可する) を使って、組織の Windows 10 で Cortana を構成できます。

Windows 10 バージョン 2004 から、Cortana は Windows がプレインストールされたユニバーサル Windows プラットフォーム (UWP) アプリであり、Microsoft Store を通じて定期的に更新されます。 Cortana の最新の更新プログラムを受信するには、Microsoft Store から更新プログラム [を有効にする必要があります](https://docs.microsoft.com/windows/configuration/stop-employees-from-using-microsoft-store)。

[Windows 10 の Cortana の詳細](https://docs.microsoft.com/windows/configuration/cortana-at-work/cortana-at-work-overview)

### <a name="cortana-voice-assistance-in-teams"></a>Teams での Cortana 音声アシスタンス

Teams モバイル アプリと Microsoft Teams 表示デバイスでの Cortana 音声アシスタンスを使用すると、Microsoft 365 Enterprise ユーザーは自然言語で音声を使用して、コミュニケーション、コラボレーション、会議に関連するタスクを効率化できます。 ユーザーは、Teams モバイル アプリの右上にあるマイク ボタンを選択するか、Microsoft Teams ディスプレイで &#8220;Cortana&#8221; と言って Cortana と話し合います。 チームのハンズフリーで簡単に接続し、移動中に、ユーザーは &#8220;通話 Megan&#8221; や &#8220;などのクエリを言って、次の会議にメッセージを送信&#8221;。 ユーザーは、次の会議に参加&#8220;、音声&#8221;を使用してファイルの共有、予定表の確認など、会議に参加することもできます。 これらの音声アシスタンス エクスペリエンスは、オンライン サービスの使用条件 [(OST)](https://www.microsoft.com/licensing/product-licensing/products)に反映されている Office 365 のプライバシー、セキュリティ、コンプライアンスの約束に完全に準拠する Cortana エンタープライズ レベルのサービスを使用して提供されます。

**管理者の制御**

Cortana 音声アシスタンスは、テナントに対して既定で有効になります。 管理者は、ポリシー (TeamsCortanaPolicy) を使用して、テナント内で Teams で Cortana 音声アシスタンスを使用できるユーザーを制御できます。 このポリシーは、ユーザー アカウント レベルまたはテナント レベルで設定できます。 管理者は、CortanaVoiceInvocationMode フィールドをこのポリシー コントロール内で使用して、Cortana が無効になっているか、プッシュ ボタン呼び出しでのみ有効になっているのか、スリープ解除時の呼び出しでのみ有効になっているのかを判断することもできます (Microsoft Teams ディスプレイなど、Cortana をサポートするデバイスに適用されます)。 英語の米国の Microsoft 365 Enterprise ユーザー向け最初のリリースの時点では、Teams モバイル アプリはスリープ解除ワードのアクティブ化をサポートしない予定ですが、今後サポートされる予定です。

**ユーザー コントロール**

個々のユーザーは、マイク ボタンをクリックして、Teams モバイル アプリで Cortana の音声アシスタンスを試用できます。 &#8220;Cortana.&#8221; と言うだけで、Microsoft Teams ディスプレイ デバイスで Cortana の音声アシスタンスを試し、Teams の Cortana が Teams モバイル アプリまたは Microsoft Teams ディスプレイの設定を介してデバイスに対して有効になっているかどうかを制御することもできます。 

1. Teams モバイル アプリを開く、または Microsoft Teams ディスプレイの環境 (ホーム) 画面に移動します。

2. Teams モバイル アプリで、[設定] に移動 **します**。 Microsoft Teams の表示で、ユーザーアバターを選択し、[設定] を選択します。 Cortana が有効になっている場合は、Cortana &#8220;、[設定] に移動します&#8221;

3. Cortana **を選択します**。

4. デバイスで Cortanaの **音声** サポートが必要かどうかに応じて、トグルを [オン] または [オフ] に移動します。

[Teams での Cortana 音声アシスタンスについて詳しくは、次をご覧ください。](https://docs.microsoft.com/microsoftteams/cortana-in-teams)

### <a name="play-my-emails"></a>自分のメールを再生する

[自分のメールの再生] (Outlook モバイル経由で接続) は、ユーザーが自分の [集中受信トレイ] で新しいメッセージを聞き、電話、ヘッドホン、または接続されたオーディオ デバイスのスピーカーを介して 1 日に変更を加える音声駆動型のハンズフリー エクスペリエンスです。 ユーザーは、Cortana に最近のメールを読み上げさせるか、Cortana にメッセージのフラグ、アーカイブ、削除、スキップなどのアクションを実行してもらいます。 この機能は、特に、通学中、マルチタスク中、または移動中にメールをキャッチアップする場合に役立ちます。 ユーザーが [マイ メールの再生] で Cortana と話し合う場合、音声オーディオ要求は Cortana エンタープライズ サービスに直接送信されます。 ユーザーの電子メールの音声読み取りテキストは、Office 365 クラウド内で処理されます。 このプロセス中、ユーザー Office 365 データは処理されません。また、電子メール データは保存されません。 音声コマンドのトランスクリプト ("読み取りとしてマークする"、"次へ"、"フラグ"など) は、Microsoft [Online Services](https://www.microsoft.com/licensing/product-licensing/products)の使用条件のデータ保護条件に従って保持できます。

Cortana は、メールが保護されているときに呼び出しを行い、メッセージを読む前に少し一時停止して、再生を一時停止したり、次のメッセージにスキップしたりするのに十分な時間をユーザーに提供します。 プライベート電話と同様に、機密情報が聞き取り過ぎる可能性がある場所で再生を開始する場合は、注意が必要です。 このような場合は、Outlook モバイルで [マイ メールの再生] を使用する場合、組織の従業員が適切な環境でヘッドホンを装着する方法をお勧めします。

### <a name="opt-out-of-play-my-emails"></a>メールの再生をオプトアウトする

個人は、次の手順を使用してメールの再生をオプトアウトできます。

1. Outlook モバイルを開きます。

2. [設定] に **移動します**。
  
3. Select **Play My Emails**.

4. 無効にするアカウントのトグルをオフにします。

[メールの再生について詳しくは、次のリンクを参照してください。](https://support.microsoft.com/help/4558256)

### <a name="briefing-email"></a>説明用メール

Cortana は、タスクとコミットメントを含む個別の説明メールを送信し、完了としてマークしたり、フォーカス時間をスケジュールして作業を完了したりするための便利な方法で行いました。 また、会議の概要と、1 日の関連ドキュメントも含まれます。 Cortana は、ユーザーの電子メール メッセージから情報を抽出し、その情報をその Exchange Online メールボックスに格納します。このメールボックスは、その情報が [待ち時間] メールに統合されるまで保存されます。 Exchange Online メールボックスの外部から個人データにアクセスすることはできません。

### <a name="how-to-opt-out-of-briefing-email"></a>説明用メールをオプトアウトする方法

管理者は、Exchange Online の PowerShell を使用して、 [自分の組織の説明](https://docs.microsoft.com/briefing/be-admin) を構成できます。 個人は、メッセージのフッターで [登録解除] を選択することで、Cortana の [の説明] メールをオプトアウトできます。

[に関する詳しい情報](https://support.microsoft.com/help/4558259)

組織の生産性を向上するために、上記のようなより多くのエクスペリエンスを引き続き導入します。

[Microsoft コンプライアンス サービスの詳細](https://docs.microsoft.com/microsoft-365/compliance/offering-home)

## <a name="how-is-the-delivery-of-cortana-enterprise-services-different-from-the-delivery-of-other-cortana-features-i-may-have-previously-experienced"></a>Cortana エンタープライズ サービスの配信は、以前に経験した Cortana の他の機能の配信とどのように異なりますか?

企業での Cortana の動作を考える 2 つの方法を次に示します。

**Cortana エンタープライズ サービスを使用する** 組織向け新しいエクスペリエンス: Cortana エンタープライズ サービスは、組織のセキュリティとコンプライアンスのニーズを満たするように設計されています。 

1. これは新しいサービスであり、このドキュメントで説明します。

2. オンライン サービス使用条件の対象となるサービスの場合、Microsoft はデータ処理者です。Microsoft は、お客様から要求されたオンライン サービスを提供する目的、およびお客様から指示された目的のためにのみ、お客様から顧客データを収集および使用します。 EU の一般データ保護規則 (GDPR) の下で、お客様はデータのデータ管理者です。 オンライン サービス [の使用条件と](https://www.microsoft.com/licensing/product-licensing/products) 、商用クラウドのお客様向けプライバシーの透明性 [の向上をご覧ください](https://blogs.microsoft.com/eupolicy/2019/11/18/introducing-privacy-transparency-commercial-cloud-customers/)。

3. たとえば、メールの再生は、ユーザーが Outlook for iOS を通じて接続し、Cortana エンタープライズ サービスを利用できる Cortana サービスです。 

4. IT 管理者は、Office ProPlus アプリケーションを使用する場合のオプションの接続エクスペリエンスと同様に、Cortana のオプションの接続エクスペリエンスを制御します。  

コンシューマー向け既存のサービス **:** Cortana のオプション接続サービスは、主にコンシューマー エクスペリエンスを目的として設計され、現在 Windows 10 (バージョン 1909 以前) と iOS および Android の Cortana アプリで提供されています。

1. これらのエクスペリエンスにより、天気、ニュース、トラフィックなどの機能を利用できます。

2. テナント管理者は、Windows 10 (バージョン 1909 以前) の Cortana と iOS および Android 上の Cortana アプリで、Cortana が Office 365 テナント データに接続できるかどうかを制御できます。

組織の Microsoft がホストするデータへの Cortana アクセスをオフにする

1. Microsoft 365 管理センターで、[**設定** 組織の設定] を選択し  >  **、Cortana を選択します**。

2. **Windows 10 (バージョン 1909** 以前) の Cortana と iOS および Android の Cortana アプリで、組織内のユーザーに代わって Microsoft がホストするデータにアクセスして Cortana の接続エクスペリエンスを無効にするチェック ボックスをオフにします。

3. [**変更の保存**] を選択します。

Microsoft サービス規約および[Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174)プライバシーに [](https://privacy.microsoft.com/privacystatement)関する声明に準拠するサービスの場合、Microsoft はデータ管理者です。 データ管理者として、Microsoft はデータを使用して、Microsoft のプライバシーに関する声明に従って製品とサービス [を改善します](https://privacy.microsoft.com/privacystatement)。
