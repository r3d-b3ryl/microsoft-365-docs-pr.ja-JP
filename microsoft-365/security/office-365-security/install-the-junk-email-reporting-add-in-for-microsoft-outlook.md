---
title: Microsoft Outlook 用迷惑メール報告アドインのインストール
f1.keywords:
- NOCSH
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: この articleSupported LanguagesInstall the 迷惑メール報告アドインをアンインストールします。迷惑メール報告アドインをアンインストールする inFor 詳細情報
ms.openlocfilehash: 0f7a5a3cbaddf9aef5e518db38ffb36c397cd1f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599154"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook 用迷惑メール報告アドインのインストール

このトピックでは、Outlook 用 Microsoft 迷惑メール報告アドインを組織内のクライアント コンピューターにインストール (およびアンインストール) する方法を説明します。 現在のバージョンのアドイン (2016 年1月) には、Outlook 2016、Outlook 2013、および Outlook 2010 のサポートが含まれています。

この (サポートされているすべての言語の) アドインで、Outlook のリボンから直接、迷惑メールを報告できます。英語版アドインには、リボンから直接マイクロソフトにメールの問題を報告するための追加のオプションが含まれています。

- 受信したフィッシング詐欺メールを報告してください。

- 迷惑メールとして誤って識別されたメールを報告してください。

## <a name="supported-languages"></a>サポートされている言語
<a name="sectionSection0"> </a>

迷惑メール報告アドインは次の言語をサポートしています。

- 簡体字中国語

- 繁体字中国語

- オランダ語

- 英語

- フランス語

- ドイツ語

- イタリア語

- 日本語

- 韓国語

- ポルトガル語

- ポルトガル語 (ブラジル)

- スペイン語

## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをインストールする

次の手順で、迷惑メール報告アドインをインストールします。

- Windows インストーラーパッケージを他の .msi ファイルと同じように実行します。 アドインをインストールすると、GUI インターフェイスが開き、インストール画面が表示されます。 詳細については、「[セットアップウィザードを使用して迷惑メール報告アドインをインストール](#install-the-junk-email-reporting-add-in-using-the-setup-wizard)する」を参照してください。

または

- インストール ユーザー インターフェイスを表示しないサイレント インストールを実行する。インストール スクリプトを実行するコマンドライン オプションを指定します。アドインをインストールする際、GUI インターフェイスでは提供されない追加の構成オプションが使用できます。詳細については、「[サイレント モードで迷惑メール報告アドインをインストールする](#install-the-junk-email-reporting-add-in-using-silent-mode)」をご覧ください。

### <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- の迷惑メール報告アドインの**システム要件**を参照してください[https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275)。

> [!NOTE]
> このアドインをインストールするコンピューターの管理者特権が必要です。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップウィザードを使用して迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Microsoft [Outlook 用 Microsoft 迷惑メール報告アドイン](https://www.microsoft.com/download/details.aspx?id=18275)の**詳細**セクションで、使用しているバージョンの Office 用の適切な .msi ファイルをダウンロードします。

3. .msi ファイルをダブルクリックします。

4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。

5. 使用許諾契約書を確認し、インストール条件に同意する場合は、 **[使用許諾契約書の条件に同意する]** をクリックします (インストールを続行するには必須)。続行するには、 **[次へ]** をクリックします。

6. ウィザードが完了したら、 **[完了]** をクリックします。

7. Outlook を起動します。

8. Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。

9. Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>サイレント モードで迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. コマンド プロンプトを開きます。

3. オプション パラメーターを使用せずに、アドインを直接インストールしたい場合は、以下を指定します。

   - X86 Outlook を実行しているコンピューター:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`

   - X 64 Outlookを実行しているコンピューター: `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`

    オプションの MaxMessageSelection および BccEmailAddress パラメーターを指定することもできます。

   - MaxMessageSelection 管理者は、ユーザーが 1 回のクリックで送信する対象として選択できる最大メッセージ数を定義できます。範囲は 1 ～ 50 件で、既定値は 10 件です。

     Example: If you want to set the maximum number of messages that can be selected by users for submission in a single click to 16, use the following option as part of the installation command:  `MaxMessageSelection=16`

   - BccEmailAddress 管理者は、Bcc 電子メール アドレスを設定することで、ユーザーによるすべての送信のコピーを受信するようにメールボックスを設定できます。メールボックスを設定すると、送信されたすべての電子メールのコピーが BccEmailAddress に送信されます。この設定を行わない場合、既定の設定に Bcc 電子メール アドレスはありません。

     Example: If you want to use junkReports@contoso.com as the Bcc email address for all submissions, use the following command:  `BccEmailAddress="junkReports@contoso.com"`

     > [!NOTE]
     > セミコロンで区切って入力することで、複数の Bcc 電子メール アドレスを設定できます。例:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`

     前述の例に基づいてこれらのオプションのパラメーターを両方とも追加するには、x86 Outlook を実行しているコンピューターで次のコマンドを実行します。

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. インストールが完了したら、Outlook を起動します。

5. Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。

6. Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。

## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする

「迷惑メール報告アドインをアンインストールするには、次のいずれかのオプションを使用します。

- Windows コントロールパネルを使用してアドインを削除します。

- Windows インストーラー パッケージを実行し、アンインストール オプションを選択する。

- アンインストール オプションを使用して、サイレント インストールを実行する。

> [!NOTE]
> このアドインをアンインストールするコンピューターの管理者特権が必要です。

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>コントロール パネルから迷惑メール報告アドインをアンインストールする

1. お使いのコンピューターで Outlook を終了します。

2. コンピューターの [スタート] メニューから **[コントロール パネル]** を選択します。

3. **[プログラムと機能]** を選択します。

4. **[Microsoft Junk E-mail Reporting Add-In for Microsoft Office Outlook]** を選択します。

5. **[アンインストール]** を選択します。

6. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Windows インストーラー パッケージを実行して迷惑メール報告アドインをアンインストールする

1. お使いのコンピューターで Outlook を終了します。

   > [!NOTE]
   > アンインストール プロセス中に Outlook が稼働している場合は、アドインを完全にアンインストールするために、再起動する必要があります。

2. 以前にアドインをインストールするために実行した .msi ファイルを再度実行します

   (Microsoft [Outlook 用 Microsoft 迷惑メール報告アドイン](https://www.microsoft.com/download/details.aspx?id=18275)の**詳細**セクションで、使用している Office のバージョンに対応する .msi ファイルをダウンロードしてから、.msi ファイルをダブルクリックします)。

3. 表示されるメッセージに従って、アドインをアンインストールします。

4. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>サイレント モードで迷惑メール報告アドインをアンインストールする

1. お使いのコンピューターで Outlook を終了します。

   > [!NOTE]
   > アンインストール プロセス中に Outlook が稼働している場合は、アドインを完全にアンインストールするために、再起動する必要があります。

2. コマンド プロンプトを開きます。

3. 次のコマンド ライン パラメーターを指定します。

   Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

   Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

4. Outlook を再起動して、アドインが Outlook のリボンに表示されていないことを確認します。

## <a name="for-more-information"></a>関連情報

[迷惑メール メッセージを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)

[トラブルシューティングとサポート情報](troubleshooting-and-support-information.md)
