---
title: Outlook ルールとカスタム フォーム インジェクション攻撃を検出して修復します。
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
description: Office 365 で Outlook ルールとカスタム フォーム インジェクション攻撃を認識して修復する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286395"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlook ルールとカスタム フォーム インジェクション攻撃を検出して修復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**概要** Office 365 で Outlook ルールとカスタム フォーム インジェクション攻撃を認識して修復する方法について説明します。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook ルールとユーザー設定フォーム挿入攻撃とは

攻撃者がテナンシーのアカウントを侵害してログインした後、攻撃者が発見および削除された後に、その中に残る方法や戻る方法を確立する必要があります。 これは、永続化メカニズムの確立と呼ばれる方法です。 これを行う 2 つの方法は、Outlook ルールを悪用するか、カスタム フォームを Outlook に挿入する方法です。
どちらの場合も、ルールまたはフォームはクラウド サービスからデスクトップ クライアントに同期されます。そのため、クライアント ソフトウェアの完全な形式と再インストールによって、インジェクション メカニズムは排除されません。 これは、Outlook クライアント ソフトウェアがクラウド内のメールボックスに再接続すると、ルールとフォームがクラウドから再ダウンロードされるためです。 ルールとフォームが設定された後、攻撃者はそれらを使用してリモート コードまたはカスタム コードを実行し、通常はローカル コンピューターにマルウェアをインストールします。 マルウェアはその後、資格情報を再盗みするか、他の不正なアクティビティを実行します。
ここでの良いニュースは、クライアントに最新バージョンのパッチを適用し続ける場合、現在の Outlook クライアントの既定値によって両方のメカニズムがブロックされるので、脅威に対して脆弱ではありません。

通常、攻撃は次のパターンに従います。

**ルールの悪用**:

1. 攻撃者は、ユーザーの 1 人のユーザー名とパスワードを盗んだ。

2. その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。 メールボックスは、Exchange Online または Exchange オンプレミスのどちらかにできます。

3. その後、攻撃者は、メールボックスがルールの条件に一致する電子メールを受信するとトリガーされる転送ルールをメールボックスに作成します。 ルールの条件とトリガー メールの内容は、お互いに合わせて調整されます。

4. 攻撃者は、通常はメールボックスを使用しているユーザーにトリガー メールを送信します。

5. 電子メールを受信すると、ルールがトリガーされます。 通常、ルールのアクションは、リモート (WebDAV) サーバー上でアプリケーションを起動します。

6. アプリケーションは、通常 [、Powershell The"](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。

7. マルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから再び盗み、その他の悪意のあるアクティビティを実行できます。

**Forms Exploit**:

1. 攻撃者は、ユーザーの 1 人のユーザー名とパスワードを盗んだ。

2. その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。 メールボックスは、Exchange Online または Exchange オンプレミスのどちらかにできます。

3. その後、攻撃者はカスタム メール フォーム テンプレートを作成し、ユーザーのメールボックスに挿入します。 カスタム フォームは、メールボックスがカスタム フォームを読み込む必要がある電子メールを受信するとトリガーされます。 カスタム フォームと電子メールの形式は、お互いに合わせて調整されます。
4. 攻撃者は、通常はメールボックスを使用しているユーザーにトリガー メールを送信します。

5. 電子メールを受信すると、フォームが読み込まれます。 フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。

6. アプリケーションは、通常 [、Powershell The"](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。

7. マルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから再び盗み、その他の悪意のあるアクティビティを実行できます。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>ルールとカスタム フォーム 挿入攻撃は 365 Officeしますか?

これらの永続化メカニズムは、ユーザーが気付く可能性が低く、場合によってはユーザーに見えない場合もあります。 この記事では、以下に示す 7 つの兆候 (侵害インジケーター) を探す方法について説明します。 これらが見つけた場合は、修復手順を実行する必要があります。

- ルールの侵害を示すインジケーター:

  - ルールの処理として、アプリケーションを起動します。

  - ルールは、EXE、ZIP、または URL を参照します。

  - ローカル コンピューターで、Outlook PID から始まる新しいプロセスの開始を探します。

- ユーザー設定フォームの侵害を示すインジケーター:

  - 独自のメッセージ クラスとして保存されたカスタム フォーム。

  - メッセージ クラスには実行可能コードが含まれている。

  - 通常、個人用フォーム ライブラリまたは受信トレイ フォルダーに格納されます。

  - フォームの名前は IPM です。注:[custom name].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>この攻撃の兆候を見つけて確認するための手順

攻撃を確認するには、次の 2 つの方法のいずれかを使用できます。

- Outlook クライアントを使用して、各メールボックスのルールとフォームを手動で確認します。 この方法は徹底的ですが、メールボックス ユーザーを確認できるのは一度にしか行えなくが、確認するユーザーが多い場合は非常に時間がかかる場合があります。 また、チェックを実行しているコンピューターが侵害される可能性があります。

- PowerShell [ スクリプトGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) 使用して、テナンシー内のすべてのユーザーのすべてのメール転送ルールとカスタム フォームを自動的にダンプします。 これは、オーバーヘッドが最も少ない最も速く安全な方法です。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Outlook クライアントを使用してルール攻撃を確認する

1. ユーザーとして Outlook クライアントを開きます。 ユーザーは、自分のメールボックスのルールを調べる上でヘルプが必要な場合があります。

2. Outlook で [ルール インターフェイスを開](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) く方法の手順については、「ルールを使用して電子メール メッセージを管理する」を参照してください。

3. ユーザーが作成しなかったルール、または予期しないルールや不審な名前のルールを探します。

4. ルールの説明で、ルールの処理を開始し、適用または参照するルールの説明を確認します。EXE, .ZIP ファイルまたは URL の起動。

5. Outlook プロセス ID の使用を開始する新しいプロセスを探します。 「プロセス [ID の検索」を参照してください](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Outlook クライアントを使用してフォーム攻撃を確認する手順

1. ユーザーとして Outlook クライアントを開きます。

2. Outlook のユーザー バージョンの [開発] [タブ](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) の手順に従います。

3. Outlook で表示されている [開発] タブを開き、フォーム **のデザインをクリックします**。

4. [参照 **先]** ボックスの一 **覧から受信トレイを選択** します。 ユーザー設定フォームを探します。 ユーザー設定フォームはまれであり、ユーザー設定フォームがある場合は、より深く見る価値があります。

5. カスタム フォーム (特に非表示としてマークされているフォーム) を調査します。

6. ユーザー設定フォームを開き、フォーム グループで [コードの表示] をクリックして、フォームが読み込まれたときに実行される動作を確認します。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>PowerShell を使用してルールとフォーム攻撃を確認する手順

ルールまたはカスタム フォーム攻撃を確認する最も簡単な方法は、PowerShell [ スクリプトGet-AllTenantRulesAndForms.ps1実行 ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) する方法です。 このスクリプトはテナント内のすべてのメールボックスに接続し、すべてのルールとフォームを 2 つの .csv ファイルにダンプします。

#### <a name="pre-requisites"></a>前提条件

スクリプトはテナント内のすべてのメールボックスに接続してルールとフォームを読み取るので、スクリプトを実行するにはグローバル管理者権限が必要です。

1. ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。

2. GitHub からGet-AllTenantRulesAndForms.ps1スクリプトを、実行するフォルダーにダウンロードまたはコピーします。 このスクリプトは、このフォルダーに 2 つの日付スタンプ付きファイルを作成し、MailboxFormsExport-yyyy-mm-dd.csv、MailboxRulesExport-yyyy-mm-dd.csv。

3. 管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。

4. 次のコマンドを使用して、この PowerShell コマンド `.\Get-AllTenantRulesAndForms.ps1` ラインを.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>出力の解釈

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: アプリケーションまたは実行可能ファイルを含むアクション条件のルール (1 行に 1 つ) を調べてください。

  - **ActionType (列 A)**: 値 "ID_ACTION_CUSTOM" が表示される場合、ルールは悪意のある可能性があります。

  - **IsPotentiallyMalicious (列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。

  - **ActionCommand (列 G)**: .exe、.zip 拡張子、または URL を参照するエントリを持つアプリケーションまたはファイルの一覧が表示される場合、その URL とは見なされない場合、ルールは悪意のある可能性があります。

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: 一般に、ユーザー設定フォームの使用は非常にまれです。 このブックに何か見つけた場合は、そのユーザーのメールボックスを開き、フォーム自体を調べてください。 組織が意図的にそこに置かなかった場合は、悪意のある可能性があります。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Outlook のルールとフォームの攻撃を停止して修復する方法

これらの攻撃のどちらかの証拠が見つかった場合、修復は簡単で、メールボックスからルールまたはフォームを削除します。 これを行うには、Outlook クライアントまたはリモート PowerShell を使用してルールを削除します。

### <a name="using-outlook"></a>Outlook の使用

1. ユーザーが Outlook で使用したデバイスを識別します。 これらはすべて、潜在的なマルウェアを除去する必要があります。 すべてのデバイスがクリーンアップされるまで、ユーザーがサインオンしてメールを使用することはできません。

2. 「デバイスごとにルールを [削除する」の](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 手順に従います。

3. 他のマルウェアの存在が不明な場合は、デバイス上のすべてのソフトウェアのフォーマットと再インストールを行います。 モバイル デバイスの場合は、製造元の手順に従って、デバイスを出荷時のイメージにリセットできます。

4. 最新バージョンの Outlook をインストールします。 現在のバージョンの Outlook では、既定でこの両方の種類の攻撃がブロックされます。

5. メールボックスのすべてのオフライン コピーが削除された後、ユーザーのパスワードをリセットし (高品質のパスワードを使用)、MFA が有効になっていない場合[](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)は、ユーザーの多要素認証をセットアップする手順に従います。 これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再使用など) によって公開されません。

### <a name="using-powershell"></a>PowerShell の使用

危険なルールを削除または無効化するには、2 つのリモート PowerShell コマンドレットを使用できます。 手順に従ってください。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Exchange サーバー上のメールボックスの手順

1. リモート PowerShell を使用して Exchange サーバーに接続します。 リモート PowerShell を使用 [して Exchange サーバーに接続する手順に従います](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。

2. メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は [、Remove-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) します。

3. 詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) します。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Exchange Online のメールボックスの手順

1. PowerShell を使用して [Exchange Online に接続する手順に従います](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は [、Remove-Inbox Rule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) します。

3. 詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) します。

## <a name="how-to-minimize-future-attacks"></a>今後の攻撃を最小限にする方法

### <a name="first-protect-your-accounts"></a>最初に:アカウントを保護する

ルールとフォームの悪用は、攻撃者がユーザーのアカウントの 1 つを盗難または侵害した後にのみ使用されます。 そのため、これらの悪用を組織に対して使用することを防ぐための最初の手順は、ユーザー アカウントを積極的に保護する方法です。 アカウントが侵害される最も一般的な方法のいくつかは、フィッシング攻撃またはパスワード スプレー [攻撃](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) です。

ユーザー アカウント、特に管理者アカウントを保護する最善の方法は、ユーザーの多要素認証 [を設定する方法です](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。 また、以下も行う必要があります。

- ユーザー アカウントのアクセス方法と使用 [方法を監視します](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)。 最初の違反を防ぐことはできない場合がありますが、違反を早く検出することで、その期間と影響を短縮できます。 これらの [365 Cloud App Security Officeを](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 使用して、アカウントを監視し、異常なアクティビティについて警告することができます。

  - 複数 **の** ログイン試行の失敗 : このポリシーは、環境のプロファイルを作成し、ユーザーが 1 つのセッションで複数の失敗したログイン アクティビティを実行するときにアラートをトリガーします。このアクティビティは、侵害の試行を示している可能性がある、学習済みベースラインに関して実行されます。

  - **移動** 不可能 : このポリシーは環境のプロファイルを作成し、2 つの場所間の予想される移動時間よりも短い期間に、同じユーザーから異なる場所でアクティビティが検出されるとアラートをトリガーします。 これは、別のユーザーが同じ資格情報を使用している可能性があります。 この異常な動作を検出するには、新しいユーザーのアクティビティ パターンを学習する最初の学習期間が 7 日間必要です。

  - **(** ユーザーによる) 異常な偽装アクティビティ: このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の偽装アクティビティを実行すると、環境をプロファイルし、アラートをトリガーします。これは、侵害の試行を示している可能性があります。

- 365 セキュア スコアOffice [ツールを利用](https://securescore.office.com/) して、アカウントのセキュリティ構成と動作を管理します。

### <a name="second-keep-your-outlook-clients-current"></a>2 番目: Outlook クライアントを最新の状態に保つ

Outlook 2013 および 2016 の完全に更新および修正されたバージョンでは、"アプリケーションの開始" ルール/フォーム アクションが既定で無効になっています。 これにより、攻撃者がアカウントを侵害した場合でも、ルールとフォームのアクションがブロックされます。 「更新プログラムのインストール」の手順に従って、最新の更新プログラムとセキュリティ 修正 [プログラムOfficeできます](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。

Outlook 2013 および 2016 クライアントの修正プログラムのバージョンを次に示します。

- **Outlook 2016**: 16.0.4534.1001 以上。

- **Outlook 2013**: 15.0.4937.1000 以上。

個々のセキュリティ 修正プログラムの詳細については、以下を参照してください。

- [Outlook 2016 セキュリティ更新プログラム](https://support.microsoft.com/help/3191883)

- [Outlook 2013 セキュリティ更新プログラム](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>3 番目: Outlook クライアントを監視する

修正プログラムと更新プログラムがインストールされている場合でも、攻撃者はローカル コンピューターの構成を変更して "アプリケーションの起動" 動作を再び有効にできる点に注意してください。 Advanced [Group Policy Management を使用すると](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) 、クライアントでローカル コンピューター ポリシーを監視および適用できます。

[「64](https://support.microsoft.com/help/305097)ビット バージョンの Windows を使用してシステム レジストリを表示する方法」の情報を使用して、レジストリ内のオーバーライドによって "アプリケーションの起動" が再び有効になっているか確認できます。 次のサブキーを確認します。

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

EnableUnsafeClientMailRules キーを探します。 この更新プログラムがインストールされ、1 に設定されている場合、Outlook セキュリティ更新プログラムは上書きされ、コンピューターはフォーム/ルール攻撃に対して脆弱です。 値が 0 の場合、"アプリケーションの開始" アクションは無効になります。 更新および修正プログラムが適用されたバージョンの Outlook がインストールされ、このレジストリ キーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。

オンプレミスの Exchange インストールを使用しているお客様は、利用可能な修正プログラムを含めずに古いバージョンの Outlook をブロックする必要があります。 このプロセスの詳細については、「Outlook クライアントのブロックを構成する」 [を参照してください](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。 [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日以内に実行するタスク。 これらはすぐに影響を受け、ユーザーへの影響は低い。

- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:

- [Rules Vector に関](https://silentbreaksecurity.com/malicious-outlook-rules/) する SilentBreak セキュリティ投稿による悪意のある Outlook ルールは、Outlook ルールの詳細なレビューを提供します。

- Mailrule Pwnage に関する Sensepost ブログの MAPI over HTTP および[Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)では、Outlook ルールを使用してメールボックスを悪用できる Ruler というツールについて説明しています。

- Forms Threat Vector[に関する](https://sensepost.com/blog/2017/outlook-forms-and-shells/)Sensepost ブログの Outlook フォームとシェル。

- [Ruler Codebase](https://github.com/sensepost/ruler)

- [侵害のルーラー インジケーター](https://github.com/sensepost/notruler/blob/master/iocs.md)
