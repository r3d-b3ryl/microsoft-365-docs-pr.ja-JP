---
title: ルールとカスタム フォームOutlook攻撃を検出して修復します。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: カスタム フォーム のルールとカスタム フォームOutlook攻撃を認識して修復する方法について説明Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 33fc889b2ddb42dcbbacb1e2b6030e3bf1b409fc07970927e99e06a2747bc21d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56807523"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>ルールとカスタム フォームOutlook攻撃を検出して修復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**概要** このページでは、フォーム ルールとカスタムフォームOutlook攻撃を認識して修復する方法についてOffice 365。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>ルールとカスタム フォームOutlook攻撃とは何ですか?

攻撃者が組織へのアクセス権を取得した後、攻撃者は、発見された後もその場所に滞在するか、または戻って行く足場を確立しようと試みる。 このアクティビティは、永続 *化メカニズムの確立と呼ばれる。* 攻撃者がデータベースを使用して、Outlookメカニズムを確立するには、次の 2 つの方法があります。

- ルールを悪用Outlook使用します。
- カスタム フォームをカスタム フォームに挿入Outlook。

ユーザー Outlook再インストールしたり、影響を受けるユーザーに新しいコンピューターを与えても、問題はありません。 サーバーの新しいインストールOutlookメールボックスに接続すると、すべてのルールとフォームがクラウドから同期されます。 通常、ルールまたはフォームは、リモート コードを実行し、ローカル コンピューターにマルウェアをインストールするように設計されています。 マルウェアは資格情報を盗んだり、他の不正なアクティビティを実行したりします。

良いニュースは、Outlook クライアントに最新バージョンへのパッチを適用し続ける場合、現在の Outlook クライアントの既定値が両方のメカニズムをブロックする脅威に対して脆弱ではありません。

通常、攻撃は次のパターンに従います。

**ルールの悪用**:

1. 攻撃者はユーザーの資格情報を盗む。

2. 攻撃者は、そのユーザーのメールボックス (ExchangeまたはExchange Online) にサインインExchange。

3. 攻撃者はメールボックスに転送受信トレイ ルールを作成します。 転送ルールは、メールボックスがルールの条件に一致する特定のメッセージを攻撃者から受信するとトリガーされます。 ルールの条件とメッセージ形式は、お互いに合わせてカスタマイズされます。

4. 攻撃者は侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーが通常通り使用しています。

5. メールボックスがルールの条件に一致するメッセージを受信すると、ルールのアクションが適用されます。 通常、ルールアクションは、リモート (WebDAV) サーバー上でアプリケーションを起動します。

6. 通常、アプリケーションはユーザーのコンピューター (PowerShell Empire など) に [マルウェアをインストールします](https://www.powershellempire.com/)。

7. このマルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから盗んだり、その他の悪意のあるアクティビティを実行したりすることができます。

**フォームエクスプロイト**:

1. 攻撃者はユーザーの資格情報を盗む。

2. 攻撃者は、そのユーザーのメールボックス (ExchangeまたはExchange Online) にサインインExchange。

3. 攻撃者はユーザーのメールボックスにカスタム メール フォーム テンプレートを挿入します。 カスタム フォームは、メールボックスがカスタム フォームを読み込む必要がある攻撃者から特定のメッセージを受信するとトリガーされます。 カスタム フォームとメッセージ形式は、お互いに合わせてカスタマイズされます。

4. 攻撃者は侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーが通常通り使用しています。

5. メールボックスがメッセージを受信すると、メールボックスは必要なフォームを読み込む。 フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。

6. 通常、アプリケーションはユーザーのコンピューター (PowerShell Empire など) に [マルウェアをインストールします](https://www.powershellempire.com/)。

7. このマルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから盗んだり、その他の悪意のあるアクティビティを実行したりすることができます。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>ルールとカスタム フォームインジェクション攻撃は、次のようなOffice 365?

これらの永続化メカニズムは、ユーザーが気付く可能性は低く、場合によってはユーザーに見えない場合もあります。 この記事では、以下に示す 7 つの兆候 (侵害の指標) を探す方法について説明します。 これらが見つけた場合は、修復手順を実行する必要があります。

- **ルールの侵害のインジケーター**:
  - ルール アクションは、アプリケーションを開始します。
  - ルール EXE、ZIP、または URL を参照します。
  - ローカル コンピューターで、PID から始まる新しいプロセスの開始Outlookします。

- **カスタム フォームの侵害のインジケーター**:
  - カスタム フォームは、独自のメッセージ クラスとして保存されます。
  - メッセージ クラスには、実行可能コードが含まれている。
  - 通常、悪意のあるフォームは個人用フォーム ライブラリまたは受信トレイ フォルダーに格納されます。
  - Form は IPM という名前です。注。[カスタム名]

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>この攻撃の兆候を見つけて確認するための手順

攻撃を確認するには、次のいずれかの方法を使用できます。

- クライアントを使用して、各メールボックスのルールとフォームを手動でOutlookします。 この方法は完全ですが、一度に確認できるメールボックスは 1 つのみです。 このメソッドは、多くのユーザーが確認する必要があり、使用しているコンピューターに感染する可能性がある場合、非常に時間がかかる場合があります。

- PowerShell スクリプト [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) 使用して、テナント内のすべてのユーザーに対してすべてのメール転送ルールとカスタム フォームを自動的にダンプします。 これは、オーバーヘッドの量が最も少ない最も高速で安全なメソッドです。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>クライアントを使用してルール攻撃をOutlookする

1. クライアントのユーザー Outlookユーザーとして開きます。 ユーザーが自分のメールボックスのルールを調べるのに役立つ場合があります。

2. ルール インターフェイス[を開く](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)方法については、「ルールを使用して電子メール メッセージを管理する」を参照Outlook。

3. ユーザーが作成しなかったルール、または不審な名前を持つ予期しないルールを探します。

4. ルールの説明を参照して、ルールアクションを開始および適用するか、.EXE、.ZIPを参照するか、URL を起動します。

5. プロセス ID の使用を開始する新しいOutlook探します。 「プロセス [ID の検索」を参照してください](/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>クライアントを使用して Forms 攻撃を確認Outlook手順

1. クライアントのユーザー Outlookユーザーとして開きます。

2. 「ユーザーのバージョンの [[開発者]](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)タブを表示する」の手順に従Outlook。

3. [フォーム] の [現在表示されている開発者] タブOutlookを開き、[フォーム **のデザイン] をクリックします**。

4. [参照 **先] リスト** から **受信トレイを選択** します。 カスタム フォームを探します。 カスタム フォームはまれであり、カスタム フォームが全くある場合は、より深い外観を見る価値があります。

5. カスタム フォーム、特に非表示としてマークされているフォームを調査します。

6. カスタム フォームを開き、[ **フォーム** ] グループで [コードの表示] **をクリック** して、フォームが読み込まれたときに実行される動作を確認します。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>PowerShell を使用してルールとフォーム攻撃を確認する手順

ルールまたはカスタム フォーム攻撃を確認する最も簡単な方法は、PowerShell [ スクリプト ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1)Get-AllTenantRulesAndForms.ps1実行します。 このスクリプトは、テナント内のすべてのメールボックスに接続し、すべてのルールとフォームを 2 つのファイルに.csvします。

#### <a name="pre-requisites"></a>前提条件

スクリプトはテナンシー内のすべてのメールボックスに接続してルールとフォームを読み取るので、スクリプトを実行するにはグローバル管理者権限が必要です。

1. ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。

2. スクリプトをダウンロードGet-AllTenantRulesAndForms.ps1からGitHub実行するフォルダーにコピーします。 このスクリプトは、このフォルダー、日付スタンプ付きファイル、および日付のMailboxFormsExport-yyyy-mm-dd.csv作成MailboxRulesExport-yyyy-mm-dd.csv。

3. PowerShell インスタンスを管理者として開き、スクリプトを保存したフォルダーを開きます。

4. 次のようにこの PowerShell コマンド ラインを `.\Get-AllTenantRulesAndForms.ps1` 実行.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>出力の解釈

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: アプリケーションまたは実行可能ファイルを含むアクション条件のルール (行ごとに 1 つ) を調べてください。

  - **ActionType (列 A)**: "ID_ACTION_CUSTOM" という値が表示された場合、ルールは悪意のある可能性があります。

  - **IsPotentiallyMalicious (列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。

  - **ActionCommand (列 G)**: この列に、.exe または .zip 拡張子を持つアプリケーションまたはファイル、または URL を参照する不明なエントリが一覧表示されている場合、ルールは悪意のある可能性があります。

- **MailboxFormsExport-*yyyy-mm-dd***.csv: 一般に、カスタム フォームの使用はまれです。 このブックに何か見つけた場合は、そのユーザーのメールボックスを開き、フォーム自体を調べてください。 組織が意図的にそこに置かなかった場合は、悪意のある可能性があります。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>ルールとフォームの攻撃を停止Outlook修復する方法

これらの攻撃の証拠が見当たっている場合、修復は簡単です。メールボックスからルールまたはフォームを削除してください。 これを行うには、クライアントまたはリモート powerShell Outlookルールを削除します。

### <a name="using-outlook"></a>データOutlook

1. ユーザーがユーザーと一緒に使用したデバイスをOutlook。 これらはすべて、潜在的なマルウェアをクリーンアップする必要があります。 すべてのデバイスがクリーンアップされるまで、ユーザーがサインオンして電子メールを使用することはできません。

2. 「デバイスごとにルール [を削除する」の手順](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) に従います。

3. 他のマルウェアの存在が不明な場合は、デバイス上のすべてのソフトウェアをフォーマットして再インストールできます。 モバイル デバイスの場合は、製造元の手順に従ってデバイスを工場出荷時のイメージにリセットできます。

4. 最新のバージョンのコンピューターをインストールOutlook。 既定では、現在のバージョンの Outlook両方の種類の攻撃がブロックされます。

5. メールボックスのすべてのオフライン コピーを削除したら、ユーザーのパスワードをリセットし (高品質のパスワードを使用する)、MFA が有効になっていない[](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)場合は、ユーザーの多要素認証をセットアップするの手順に従います。 これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再使用など) によって公開されません。

### <a name="using-powershell"></a>PowerShell の使用

危険なルールを削除または無効化するために使用できる 2 つのリモート PowerShell コマンドレットがあります。 手順に従ってください。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>サーバー上のメールボックスExchange手順

1. Connect PowerShell を使用Exchangeサーバーに接続します。 リモート PowerShell を使用してサーバー [ConnectをExchange手順に従います](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。

2. 1 つのルール、複数のルール、またはすべてのルールをメールボックスから完全に削除する場合は [、Remove-InboxRule コマンドレットを使用](/powershell/module/exchange/Remove-InboxRule) します。

3. 詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](/powershell/module/exchange/disable-inboxrule) します。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>サーバー内のメールボックスExchange Online

1. PowerShell を使用してConnect[をExchange Online手順に従います](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 1 つのルール、複数のルール、またはすべてのルールをメールボックスから完全に削除する場合は [、Remove-Inbox Rule コマンドレットを使用](/powershell/module/exchange/Remove-InboxRule) します。

3. 詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](/powershell/module/exchange/disable-inboxrule) します。

## <a name="how-to-minimize-future-attacks"></a>将来の攻撃を最小限に抑える方法

### <a name="first-protect-your-accounts"></a>まず、アカウントを保護する

ルールとフォームの悪用は、ユーザーのアカウントの 1 つを盗まれたり侵害したりした後にのみ、攻撃者によって使用されます。 そのため、組織に対するこれらの悪用の使用を防ぐための最初の手順は、ユーザー アカウントを積極的に保護する方法です。 アカウントが侵害される最も一般的な方法のいくつかは、フィッシング攻撃またはパスワード スプレー攻撃 [です](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。

ユーザー アカウント、特に管理者アカウントを保護する最善の方法は、ユーザーの多要素認証を [設定する方法です](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。 また、次の情報も必要です。

- ユーザー アカウントへのアクセス方法と使用 [方法を監視します](/azure/active-directory/active-directory-view-access-usage-reports)。 最初の違反を防ぐことはできない場合がありますが、違反を早く検出することで、違反の期間と影響を短くします。 以下のポリシーを使用[Office 365 Cloud App Security、](/cloud-app-security/what-is-cloud-app-security)アカウントを監視し、異常なアクティビティに関する警告を表示できます。

  - **複数の** 失敗したログイン試行: このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の失敗したログイン アクティビティを実行すると、環境をプロファイルし、アラートをトリガーします。これは、違反の試行を示している可能性があります。

  - **不可能** な移動: このポリシーは、環境をプロファイルし、2 つの場所間の予想される移動時間よりも短い時間内に異なる場所で同じユーザーからアクティビティが検出されると、アラートをトリガーします。 これは、別のユーザーが同じ資格情報を使用している可能性があります。 この異常な動作を検出するには、新しいユーザーのアクティビティ パターンを学習する最初の 7 日間の学習期間が必要です。

  - **異常な** 偽装アクティビティ (ユーザー別) : このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の偽装アクティビティを実行すると、環境をプロファイルし、アラートをトリガーします。違反の試行を示している可能性があります。

- Secure Score のようなツール[をOffice 365して](https://securescore.office.com/)、アカウントのセキュリティ構成と動作を管理します。

### <a name="second-keep-your-outlook-clients-current"></a>2 つ目: クライアントのOutlookを維持する

2013 年 2013 年および 2016 年の Outlook完全に更新および修正プログラムが適用されたバージョンでは、既定で "アプリケーションの開始" ルール/フォーム アクションが無効になります。 これにより、攻撃者がアカウントを侵害した場合でも、ルールとフォームのアクションがブロックされます。 「更新プログラムのインストール」の手順に従って、最新の更新プログラム[とセキュリティ パッチOfficeできます](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。

2013 および 2016 のクライアントOutlook更新プログラムのバージョンを次に示します。

- **Outlook 2016**: 16.0.4534.1001 以上。

- **Outlook 2013**: 15.0.4937.1000 以上。

個々のセキュリティ パッチの詳細については、以下を参照してください。

- [Outlook 2016セキュリティ パッチ](https://support.microsoft.com/help/3191883)

- [Outlook 2013 セキュリティ パッチ](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>3 つ目: クライアントOutlook監視する

パッチと更新プログラムがインストールされている場合でも、攻撃者がローカル コンピューターの構成を変更して"アプリケーションの起動" 動作を再び有効にできる可能性があります。 Advanced Group [Policy Management を使用して](/microsoft-desktop-optimization-pack/agpm/) 、クライアントにローカル コンピューター ポリシーを監視および適用できます。

「64 ビット バージョンの Windows を使用してシステム レジストリを表示する方法」の情報を使用して、レジストリ内のオーバーライドを通じて "アプリケーションの起動" が再び有効[になっているか確認できます](https://support.microsoft.com/help/305097)。 次のサブキーを確認します。

- **Outlook 2016:**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013:**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

EnableUnsafeClientMailRules キーを探します。 このセキュリティ 更新プログラムが 1 に設定されている場合、Outlook更新プログラムは上書きされ、コンピューターは Form/Rules 攻撃に対して脆弱です。 値が 0 の場合、[アプリケーションの開始] アクションは無効になります。 更新および修正プログラムが適用されたバージョンの Outlook がインストールされ、このレジストリ キーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。

オンプレミスのインストールを使用しているExchangeは、利用可能なパッチを持Outlook古いバージョンのデバイスをブロックする必要があります。 このプロセスの詳細については、「Configure [Outlook」を参照してください](/exchange/configure-outlook-client-blocking-exchange-2013-help)。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。 [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日間に実行するタスク。 これらは即座に影響を及ぼすので、ユーザーに与える影響は低いです。

- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:

- [ルール Outlookに](https://silentbreaksecurity.com/malicious-outlook-rules/)関する SilentBreak セキュリティ 投稿による悪意のあるセキュリティ ルールには、ルールの詳細なレビュー Outlookがあります。

- [Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)に関する Sensepost ブログの MAPI over HTTP と Mailrule Pwnage では、ルールを使用してメールボックスを悪用できる Ruler というツールについてOutlookしています。

- [Outlook脅威ベクトルに](https://sensepost.com/blog/2017/outlook-forms-and-shells/)関する Sensepost ブログでフォームとシェルを作成します。

- [Ruler Codebase](https://github.com/sensepost/ruler)

- [侵害のルーラーインジケーター](https://github.com/sensepost/notruler/blob/master/iocs.md)