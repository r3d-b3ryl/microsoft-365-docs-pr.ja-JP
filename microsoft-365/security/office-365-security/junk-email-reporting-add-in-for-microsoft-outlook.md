---
title: Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 迷惑メール報告アドインをインストールして使用して、スパム、非スパム、フィッシング メッセージを Microsoft に報告する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 171bdc43e565a0890cddcd1e48208b49774a5315
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167349"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> 迷惑メール報告アドインを現在使用していない場合は、代わりに迷惑メール報告アドインまたは Report [](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)アドインをお勧めします。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

Microsoft Outlook 用迷惑メール報告アドインを使用すると、ユーザーは誤検知 (スパムとしてマークされた良いメール)、偽陰性 (迷惑メールが許可された)、フィッシング メッセージを Microsoft に送信できます。 組織で Exchange Online Protection を使用していない場合 (たとえば、オンプレミスの Exchange または Exchange Online 以外のメール サービス)、迷惑メール レポートの送信はスパム フィルター処理に影響を与える可能性があります。

このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 迷惑メール報告アドインをインストールするには、この記事の後半[](#install-the-junk-email-reporting-add-in)にある「迷惑メール報告アドインのインストール」セクションを参照してください。

- 迷惑メール報告アドインは、次のバージョンの Outlook で動作します。

  - Outlook 2013 以降
  - Microsoft 365 Apps for enterprise に含まれる Outlook

- メッセージを Microsoft に報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>迷惑メール報告アドインを使用してスパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール以外の受信トレイまたは他の電子メール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブまたは **[メッセージ**] タブで[迷惑メール] をクリックし、[迷惑メールとして報告] または [フィッシングとして報告] を **選択します**。 

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

   - メッセージを右クリックし、[迷惑メール]**を選択** して、[迷惑メールとして報告] または [フィッシングとして報告]**を選択します**。

     ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

   - 複数のメッセージを選択し、右クリックして、[迷惑メールとして報告 **]** または [フィッシングとして **報告] を選択します**。

     ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。 If you change your mind, click **Don't Report**.

   ![迷惑メールとして報告するダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは分析のために Microsoft に送信され、次の処理が行されます。

   - 迷惑メールとして報告された場合は、[迷惑メール] フォルダーに移動されました。
   - フィッシングとして報告された場合に削除されます。

   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>迷惑メール報告アドインを使用して、[迷惑メール] フォルダーから非スパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール フォルダーで、次の方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブまたは [**メッセージ**] タブで、[迷惑メールではないメール] をクリックし、[迷惑メールではないメールとして報告] または [フィッシングとして報告] を **選択します**。

     ![[迷惑メール] フォルダーのリボンから迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - メッセージを右クリックし、[迷惑メール]**をクリック** して、[迷惑メールではないメールとして報告] または [フィッシングとして報告]**を選択します**。

     ![迷惑メール フォルダー内の右クリックからの迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 複数のメッセージを選択し、右クリックして、[迷惑メールではないメールとして報告] または [フィッシングとして報告]**を選択します**。

     ![迷惑メール フォルダー内で右クリックした複数の迷惑メール メッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。 If you change your mind, click **Don't Report**.

   ![迷惑メールではないとして報告するダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは分析のために Microsoft に送信され、次の処理が行されます。

   - 迷惑メールとして報告された場合は、[迷惑メール] フォルダーに移動されました。
   - フィッシングとして報告された場合に削除されます。

   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをインストールする

- アドインをインストールするコンピューターに管理者特権が必要です。

- ご使用のバージョンのファイルに適した .msi ファイルOffice見つけやすい場所 <https://www.microsoft.com/download/details.aspx?id=18275> に移動してダウンロードします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 以降の場合、前提条件は Microsoft .NET Framework 2.0 のみです。 Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールする必要があります。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、.NET Framework 2.0 が有効になっているか確認します。 手順については、「コントロール パネル [で .NET Framework 3.5 を有効にする」を参照してください](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。

3. ダウンロードした .msi ファイルを見つけてダブルクリックします。

4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。

5. 使用許諾契約書を確認し、条項に同意する場合は[使用許諾契約書に同意します] をクリックし、[次へ] をクリック **します**。

6. ウィザードが完了したら、 **[完了]** をクリックします。

Outlook を起動します。

Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。

Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>サイレント モードで迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 では、次のコマンドを実行して .NET Framework 2.0 をインストールします。

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. ユーザーの操作なしでアドインをインストールするには、コマンド プロンプトを開き、次の構文を使用します。

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 1 回の申請に対して選択できるメッセージの最大数を指定します。 有効な値は 1 ~ 50 です。 既定値は 15 です。

   - `BccEmailAddress` すべてのユーザー提出のコピーを受け取る追加の BCC 受信者を指定します。 既定値は空白です (BCC 受信者は追加されません)。

   この例では、既定の設定を使用して、指定したパスから 64 ビット バージョンのアドインをインストールします。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   この例では、次の追加設定を使用して、指定したパスから 32 ビット バージョンのアドインをインストールします。

   - 1 回の申請で最大 20 件のメッセージを選択できます。
   - junkreports@contoso.comとhollyd@treyresearch.netすべての提出の BCC コピーを受け取る。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で次の手順を実行します。

- メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブまたは [**メッセージ**] タブで [迷惑メール] をクリックし、次のオプションが使用可能な場合を確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メール報告オプション**
  - **迷惑メール のヘルプを報告する**

  ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

- メッセージを右クリックし、[迷惑メール] **を選択して**、次のオプションが使用可能な場合を確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メール報告オプション**
  - **迷惑メール のヘルプを報告する**

  ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

- 複数のメッセージを選択し、右クリックして、次のオプションが使用可能なか確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**

  ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- [迷惑メール] フォルダーで **以前の操作** を行い、以前の迷惑メール **報告オプションが** [迷惑メールではない] に **なことを確認します**。

  ![[迷惑メール] フォルダーのリボンから迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダー内の右クリックからの迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダー内で右クリックした複数の迷惑メール メッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする

Outlook を終了した後、次の手順を使用して迷惑メール報告アドインをアンインストールします。

- **コントロール パネル**: Windows キー + R キーを押します。[ファイル名 **を指定** して実行] ダイアログボックスが開いたら `control appwiz.cpl` **、「OK」** と入力してクリックします。

  一覧で **Microsoft 迷惑メール報告アドインを** 見つけて選択し、[アンインストール] をクリック **します**。

- **Windows インストーラー パッケージ**: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  表示されるダイアログで **、[Outlook** 用 Microsoft 迷惑メール報告アドインの削除] を選択し、[次へ] をクリック **します**。

- **サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。 コマンド プロンプト ウィンドウで、.msi ファイルの場所に置き換え、次 \<PathToFile\> のいずれかのコマンドを実行します。

  - **32 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

アンインストール後に Outlook を開いた場合、迷惑メール、迷惑メール、フィッシング報告のオプションがなくなります。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインのトラブルシューティング

迷惑メール報告アドインを追加した後、Outlook で問題が発生する場合があります。 このセクションでは、発生する可能性のある問題と、これらの問題を解決するためのヒントについて説明します。

### <a name="troubleshooting-for-users"></a>ユーザーのトラブルシューティング

次の 1 つ以上の問題が発生します。

- **[迷惑メールの報告]** をクリックしても何も起こらない
- 電子メール メッセージを選択した後に Outlook が応答しなくなった
- "配信不能" と返され、報告された迷惑メールを配信できない

この問題を解決するには、次の手順を実行します。

1. Outlook を閉じて再起動します。
2. テスト メッセージを作成して送信し、受信者がメッセージを受信したのを確認します。
3. 問題が解決しない場合は、管理者にお問い合わせください。

Microsoft にメッセージを送信するために使用できる他のメソッドについては、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。

### <a name="troubleshooting-for-admins"></a>管理者向けトラブルシューティング

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>問題: システム管理者に連絡を求めるエラー メッセージが継続的に表示される

1. レジストリ キーの値 `LoggingLevel` を "Verbose" に設定します。

   - **32 ビット Windows 上の 32 ビット Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 ビット Windows 上の 32 ビット Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 ビット Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Outlook を再起動し、エラー メッセージが表示された場合にユーザーに報告を求める。

3. 次の場所にあるログ情報を収集します。

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>問題: ユーザーがメッセージを報告するときに確認プロンプトを受信しない選択をしたが、プロンプトを戻す

1. 値 `ConfirmReportJunk` が "True" のレジストリ キーを作成します。

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook を再起動します。
