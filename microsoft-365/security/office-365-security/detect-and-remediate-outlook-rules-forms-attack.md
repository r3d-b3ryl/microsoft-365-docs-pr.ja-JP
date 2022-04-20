---
title: Outlook規則とカスタム フォームインジェクション攻撃を検出して修復します。
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
ms.localizationpriority: medium
search.appverid:
- MET150
description: Office 365でOutlookルールとカスタム フォームインジェクション攻撃を認識して修復する方法について説明します
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c15046d43a1f2a48cf9f4ef4ccc79c060d18b156
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972807"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlookルールとカスタム フォームインジェクション攻撃の検出と修復

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**概要** Office 365でOutlookルールとカスタム フォームインジェクション攻撃を認識して修復する方法について説明します。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook ルールとカスタム フォームインジェクション攻撃とは何ですか?

攻撃者が組織にアクセスした後、攻撃者は検出された後に留まるか、戻るための足場を確立しようとします。 このアクティビティは、 *永続化メカニズムの確立* と呼ばれます。 攻撃者がOutlookを使用して永続化メカニズムを確立するには、次の 2 つの方法があります。

- Outlookルールを利用します。
- カスタム フォームをOutlookに挿入します。

Outlookを再インストールしたり、影響を受けるユーザーに新しいコンピューターを提供しても役に立ちません。 Outlookの新しいインストールがメールボックスに接続すると、すべてのルールとフォームがクラウドから同期されます。 通常、ルールまたはフォームは、リモート コードを実行し、ローカル コンピューターにマルウェアをインストールするように設計されています。 マルウェアによって資格情報が盗まれたり、他の不正なアクティビティが実行されたりします。

良いニュースは、Outlook クライアントに最新バージョンのパッチを適用したままにしておくと、現在のOutlookクライアントの既定値が両方のメカニズムをブロックするため、脅威に対して脆弱ではありません。

攻撃は通常、次のパターンに従います。

**ルールの悪用**:

1. 攻撃者はユーザーの資格情報を盗みます。

2. 攻撃者は、そのユーザーのExchangeメールボックス (Exchange OnlineまたはオンプレミスのExchange) にサインインします。

3. 攻撃者はメールボックスに転送受信トレイルールを作成します。 転送ルールは、メールボックスが規則の条件に一致する攻撃者から特定のメッセージを受信したときにトリガーされます。 ルールの条件とメッセージ形式は、互いに合わせて調整されます。

4. 攻撃者は、侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーによって引き続き通常どおりに使用されています。

5. メールボックスがルールの条件に一致するメッセージを受信すると、ルールのアクションが適用されます。 通常、ルールアクションは、リモート (WebDAV) サーバーでアプリケーションを起動することです。

6. 通常、アプリケーションはユーザーのコンピューター ( [PowerShellEmpire](https://www.powershellempire.com/) など) にマルウェアをインストールします。

7. マルウェアを使用すると、攻撃者はユーザーのユーザー名とパスワードまたはその他の資格情報をローカル コンピューターから盗む (または盗む) 他の悪意のあるアクティビティを実行できます。

**Forms Exploit**:

1. 攻撃者はユーザーの資格情報を盗みます。

2. 攻撃者は、そのユーザーのExchangeメールボックス (Exchange OnlineまたはオンプレミスのExchange) にサインインします。

3. 攻撃者は、ユーザーのメールボックスにカスタム メール フォーム テンプレートを挿入します。 カスタム フォームは、メールボックスがユーザー設定フォームを読み込む必要がある攻撃者から特定のメッセージを受信したときにトリガーされます。 カスタム フォームとメッセージ形式は、互いに合わせて調整されます。

4. 攻撃者は、侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーによって引き続き通常どおりに使用されています。

5. メールボックスがメッセージを受信すると、メールボックスは必要なフォームを読み込みます。 このフォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。

6. 通常、アプリケーションはユーザーのコンピューター ( [PowerShellEmpire](https://www.powershellempire.com/) など) にマルウェアをインストールします。

7. マルウェアを使用すると、攻撃者はユーザーのユーザー名とパスワードまたはその他の資格情報をローカル コンピューターから盗む (または盗む) 他の悪意のあるアクティビティを実行できます。

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>ルールとカスタム フォームインジェクション攻撃は、Office 365のように見えますか?

これらの永続化メカニズムは、ユーザーが気付く可能性が低く、場合によってはユーザーに表示されない場合もあります。 この記事では、次に示す 7 つの兆候 (侵害のインジケーター) のいずれかを検索する方法について説明します。 これらのいずれかが見つかる場合は、修復手順を実行する必要があります。

- **ルール侵害のインジケーター**:
  - ルール アクションは、アプリケーションを起動することです。
  - ルールは、EXE、ZIP、または URL を参照します。
  - ローカル コンピューターで、Outlook PID から開始された新しいプロセスの開始を探します。

- **カスタム フォームの侵害のインジケーター**:
  - 独自のメッセージ クラスとして保存されているカスタム フォーム。
  - メッセージ クラスには実行可能コードが含まれています。
  - 通常、悪意のあるフォームは個人用フォーム ライブラリまたは受信トレイ フォルダーに格納されます。
  - フォームは IPM という名前です。メモ。[カスタム名]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>この攻撃の兆候を見つけて確認する手順

次のいずれかの方法を使用して、攻撃を確認できます。

- Outlook クライアントを使用して、各メールボックスのルールとフォームを手動で調べます。 この方法は完全ですが、一度に確認できるメールボックスは 1 つだけです。 この方法は、確認するユーザーが多い場合に非常に時間がかかる場合があります。また、使用しているコンピューターにも感染する可能性があります。

- [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを使用して、テナント内のすべてのユーザーのすべてのメール転送ルールとカスタム フォームを自動的にダンプします。 これは、オーバーヘッドが最も少ない最も高速で安全な方法です。

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Outlook クライアントを使用してルール攻撃を確認する

1. ユーザーとしてクライアントOutlookユーザーを開きます。 ユーザーは、自分のメールボックスのルールを調べる際に支援が必要な場合があります。

2. Outlookでルール インターフェイスを開く方法については、「[ルールを使用した電子メール メッセージの管理](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)」の記事を参照してください。

3. ユーザーが作成しなかったルール、または疑わしい名前の予期しないルールまたはルールを探します。

4. .EXE、.ZIP ファイル、または URL の起動を開始または参照するルール アクションのルールの説明を確認します。

5. Outlookプロセス ID の使用を開始する新しいプロセスを探します。 [プロセス ID の検索に関するトピックを](/windows-hardware/drivers/debugger/finding-the-process-id)参照してください。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Outlook クライアントを使用してフォーム攻撃を確認する手順

1. ユーザー Outlookクライアントをユーザーとして開きます。

2. ユーザーのバージョンのOutlook[の [開発] タブ](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)の手順に従います。

3. Outlookで表示される開発者タブを開き、**フォームのデザインを** クリックします。

4. [**検索** 先] ボックスの一覧から **受信トレイ** を選択します。 カスタム フォームを探します。 カスタム フォームはごくまれであり、カスタム フォームがある場合は、より深く見る価値があります。

5. カスタム フォーム (特に非表示としてマークされたもの) を調査します。

6. カスタム フォームを開き、[ **フォーム** ] グループで [ **コードの表示** ] をクリックして、フォームが読み込まれたときに実行される内容を確認します。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>PowerShell を使用してルールとフォームの攻撃を確認する手順

ルールまたはカスタム フォーム攻撃を確認する最も簡単な方法は、 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを実行することです。 このスクリプトは、テナント内のすべてのメールボックスに接続し、すべてのルールとフォームを 2 つの.csv ファイルにダンプします。

#### <a name="pre-requisites"></a>前提条件

スクリプトはテナント内のすべてのメールボックスに接続してルールとフォームを読み取るため、スクリプトを実行するにはグローバル管理者権限が必要です。

1. ローカル管理者権限を使用して、スクリプトを実行するマシンにサインインします。

2. Get-AllTenantRulesAndForms.ps1 スクリプトをGitHubから実行元のフォルダーにダウンロードまたはコピーします。 このスクリプトでは、このフォルダーに 2 つの日付スタンプ ファイルが作成され、MailboxFormsExport-yyyy-mm-dd.csvとMailboxRulesExport-yyyy-mm-dd.csvされます。

3. 管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。

4. 次のように `.\Get-AllTenantRulesAndForms.ps1`、この PowerShell コマンド ラインを実行\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>出力の解釈

- ***MailboxRulesExport-yyyy-mm-dd*.csv**: アプリケーションまたは実行可能ファイルを含むアクション条件について、ルール (行ごとに 1 つずつ) を調べます。

  - **ActionType (列 A)**: 値 "ID_ACTION_CUSTOM" が表示された場合、ルールは悪意のある可能性があります。

  - **IsPotentiallyMalicious (列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。

  - **ActionCommand (列 G)**: この列に、アプリケーションまたは.exeまたは.zip拡張子を持つファイル、または URL を参照する不明なエントリが一覧表示されている場合、ルールは悪意のある可能性があります。

- ***MailboxFormsExport-yyyy-mm-dd*.csv**: 一般に、カスタム フォームの使用はまれです。 このブックで見つけた場合は、そのユーザーのメールボックスを開き、フォーム自体を調べます。 組織が意図的にそこに配置しなかった場合は、悪意のある可能性があります。

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Outlookルールとフォーム攻撃を停止して修復する方法

これらの攻撃のいずれかの証拠が見つかると、修復は簡単です。メールボックスからルールまたはフォームを削除するだけです。 これを行うには、Outlook クライアントを使用するか、リモート PowerShell を使用してルールを削除します。

### <a name="using-outlook"></a>Outlookの使用

1. ユーザーがOutlookで使用したすべてのデバイスを特定します。 これらはすべて、潜在的なマルウェアをクリーンアップする必要があります。 すべてのデバイスがクリーニングされるまで、ユーザーがサインオンして電子メールを使用することを許可しないでください。

2. 「デバイスごとに [ルールを削除する」](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) の手順に従います。

3. 他のマルウェアの存在が不明な場合は、すべてのソフトウェアをデバイスにフォーマットして再インストールできます。 モバイル デバイスの場合は、製造元の手順に従って、デバイスをファクトリ イメージにリセットできます。

4. 最新バージョンのOutlookをインストールします。 現在のバージョンのOutlookでは、この攻撃の両方の種類が既定でブロックされていることに注意してください。

5. メールボックスのすべてのオフライン コピーが削除されたら、ユーザーのパスワードをリセットし (高品質のものを使用)、MFA がまだ有効になっていない場合は、 [ユーザーの多要素認証を設定する](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) の手順に従います。 これにより、他の手段 (フィッシングやパスワードの再利用など) を介してユーザーの資格情報が公開されなくなります。

### <a name="using-powershell"></a>PowerShell の使用

危険なルールを削除または無効にするために使用できるリモート PowerShell コマンドレットは 2 つあります。 手順に従ってください。

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Exchange サーバー上にあるメールボックスの手順

1. リモート PowerShell を使用してExchange サーバーにConnectします。 Connectの手順に従って[、リモート PowerShell を使用してサーバーをExchange](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)します。

2. メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は、 [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) コマンドレットを使用します。

3. 詳細な調査のためにルールとその内容を保持する場合は、 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) コマンドレットを使用します。

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Exchange Onlineのメールボックスの手順

1. [PowerShell を使用してExchange Onlineするには、Connect](/powershell/exchange/connect-to-exchange-online-powershell)の手順に従います。

2. メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は、 [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) コマンドレットを使用します。

3. 詳細な調査のためにルールとその内容を保持する場合は、 [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) コマンドレットを使用します。

## <a name="how-to-minimize-future-attacks"></a>今後の攻撃を最小限に抑える方法

### <a name="first-protect-your-accounts"></a>まず、アカウントを保護する

ルールとフォームの悪用は、ユーザーのアカウントの 1 つを盗まれたり侵害したりした後にのみ、攻撃者によって使用されます。 そのため、組織に対してこれらの悪用を防止するための最初の手順は、ユーザー アカウントを積極的に保護することです。 アカウントが侵害される最も一般的な方法の一部は、フィッシング攻撃または [パスワード スプレー攻撃](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)です。

ユーザー アカウント (特に管理者アカウント) を保護する最善の方法は、 [ユーザーに多要素認証を設定することです](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。 また、次のことも行う必要があります。

- ユーザー アカウントに [アクセスして使用](/azure/active-directory/active-directory-view-access-usage-reports)する方法を監視します。 最初の違反を防ぐことはできないかもしれませんが、侵害を早期に検出することで、違反の期間と影響を短縮できます。 これらの[Office 365 Cloud App Security ポリシー](/cloud-app-security/what-is-cloud-app-security)を使用して、アカウントを監視し、異常なアクティビティに関するアラートを表示できます。

  - **複数の失敗したログイン試行**: このポリシーは、学習したベースラインに関してユーザーが 1 つのセッションで複数の失敗したログイン アクティビティを実行したときに、環境をプロファイリングし、アラートをトリガーします。これは侵害の試行を示している可能性があります。

  - **不可能な移動**: このポリシーは、環境をプロファイリングし、2 つの場所間の予想される移動時間よりも短い期間内に異なる場所の同じユーザーからアクティビティが検出されたときにアラートをトリガーします。 これは、別のユーザーが同じ資格情報を使用していることを示している可能性があります。 この異常な動作を検出するには、新しいユーザーのアクティビティ パターンを学習する 7 日間の最初の学習期間が必要です。

  - **異常な偽装アクティビティ (ユーザー別):** このポリシーは、環境をプロファイリングし、ユーザーが学習したベースラインに関して 1 つのセッションで複数の偽装アクティビティを実行するとアラートをトリガーします。これは侵害の試行を示している可能性があります。

- [セキュリティスコアOffice 365](https://securescore.office.com/)などのツールを使用して、アカウントのセキュリティの構成と動作を管理します。

### <a name="second-keep-your-outlook-clients-current"></a>2 番目: Outlook クライアントを最新の状態に保つ

Outlook 2013 および 2016 の完全に更新および修正プログラムが適用されたバージョンでは、既定で "アプリケーションの開始" ルール/フォーム アクションが無効になります。 これにより、攻撃者がアカウントに違反した場合でも、ルールとフォームのアクションがブロックされます。 更新プログラムのインストールに関するページの手順に従って、最新の[更新プログラムとセキュリティ パッチをインストールOffice](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。

Outlook 2013 および 2016 クライアントのパッチ バージョンを次に示します。

- **Outlook 2016**: 16.0.4534.1001 以降。

- **Outlook 2013**: 15.0.4937.1000 以上。

個々のセキュリティ パッチの詳細については、次を参照してください。

- [Outlook 2016 セキュリティ パッチ](https://support.microsoft.com/help/3191883)

- [Outlook 2013 セキュリティ パッチ](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>3 番目: Outlook クライアントを監視する

パッチと更新プログラムがインストールされていても、攻撃者はローカル コンピューターの構成を変更して、"アプリケーションの開始" 動作を再度有効にすることができます。 [Advanced グループ ポリシー Management を](/microsoft-desktop-optimization-pack/agpm/)使用して、クライアントに対してローカル コンピューター ポリシーを監視および適用できます。

[64 ビット バージョンのWindows](https://support.microsoft.com/help/305097)を使用してシステム レジストリを表示する方法に関するページの情報を使用して、レジストリのオーバーライドによって "アプリケーションの開始" が再度有効になっているかどうかを確認できます。 次のサブキーを確認します。

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Key EnableUnsafeClientMailRules を探します。 存在し、1 に設定されている場合は、Outlookセキュリティパッチがオーバーライドされ、コンピューターは Form/Rules 攻撃に対して脆弱です。 値が 0 の場合、"アプリケーションの開始" アクションは無効になります。 更新された修正プログラムが適用されたバージョンのOutlookがインストールされていて、このレジストリ キーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。

オンプレミスのExchangeインストールをお持ちのお客様は、利用可能なパッチがない古いバージョンのOutlookをブロックすることを検討する必要があります。 このプロセスの詳細については、「[クライアント ブロックの構成Outlook](/exchange/configure-outlook-client-blocking-exchange-2013-help)」を参照してください。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。 [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日間に実行するタスク。 これらは即座に影響を与え、ユーザーへの影響が低くなります。

- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:

- Rules Vector に関する SilentBreak セキュリティ ポストによる[悪意のあるOutlook](https://silentbreaksecurity.com/malicious-outlook-rules/)ルールは、Outlookルールの詳細なレビューを提供します。

- [Mailrule Pwnage に関する Sensepost ブログの HTTP と Mailrule Pwnage を介した MAPI](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) では、Outlookルールを使用してメールボックスを悪用できる Ruler というツールについて説明しています。

- Forms Threat Vector に関する Sensepost ブログで[フォームとシェルをOutlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/)します。

- [ルーラー コードベース](https://github.com/sensepost/ruler)

- [侵害のルーラー インジケーター](https://github.com/sensepost/notruler/blob/master/iocs.md)