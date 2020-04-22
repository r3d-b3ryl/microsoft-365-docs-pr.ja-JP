---
title: Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 迷惑メール報告アドインをインストールおよび使用して、スパム、非スパム、フィッシングメッセージを Microsoft に報告する方法について説明します。
ms.openlocfilehash: be087a15071114b2d1ec564cbb118dcd85e32429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638502"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a>Office 365 で Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する

> [!NOTE]
> 現在迷惑メール報告アドインを使用していない場合は、代わりに[レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用することをお勧めします。

Microsoft Outlook 用迷惑メール報告アドインを使用すると、ユーザーは誤検知 (スパムとしてマークされた良好な電子メール)、誤検知 (無効な電子メールが許可されている)、および Exchange Online Protection (EOP) へのフィッシングメッセージを送信することができます。 組織で EOP を使用していない場合、迷惑メールレポートの送信はスパムフィルタリングに影響しません。

このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 迷惑メール報告アドインをインストールするには、このトピックで後述する「[迷惑メール報告アドインをインストール](#install-the-junk-email-reporting-add-in)する」セクションを参照してください。

- 迷惑メール報告アドインは、次のバージョンの Outlook で動作します。

  - Outlook 2013 以降
  - Outlook は、Microsoft 365 Apps for enterprise に含まれています。

- Microsoft へのメッセージの報告の詳細については、「 [Office 365 でメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>迷惑メール報告アドインを使用してスパムおよびフィッシングメッセージを報告する

1. 受信トレイまたは迷惑メール以外のその他の電子メールフォルダー内のメッセージの場合、次のいずれかの方法を使用して、スパムメッセージとフィッシングメッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの [**ホーム**] タブまたは [**メッセージ**] タブで、[**迷惑メール**] をクリックし、[**迷惑メール**として報告] または [**フィッシングとして報告**] を選択します。

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-ribbon.png)

   - メッセージを右クリックし、[**迷惑メール**] を選択して、[**迷惑メールと**して報告] または [**フィッシングとして報告**] を選択します。

     ![右クリックで迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-right-click.png)

   - 複数のメッセージを選択して右クリックし、[**迷惑メールと**して報告] または [**フィッシングとして**報告] を選択します。

     ![右クリックで複数の迷惑メールまたはフィッシング詐欺メールメッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み、[**レポート**] をクリックします。 気が変わった場合は、[**レポートしない**] をクリックします。

   ![[迷惑メールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>迷惑メール報告アドインを使用して迷惑メールフォルダーからの非スパムメッセージとフィッシング詐欺メッセージを報告する

1. [迷惑メール] フォルダーで、次のいずれかの方法を使用してスパム誤検知またはフィッシングメッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの [**ホーム**] タブまたは [**メッセージ**] タブで、[**迷惑メール**ではない] をクリックし、[**迷惑メール**ではないと報告] または [**フィッシングとし**て報告する] を選択します。

     ![迷惑メールフォルダーのリボンから迷惑メールまたはフィッシング詐欺メールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - メッセージを右クリックし、[**迷惑メール**] をクリックして、[**迷惑メールではないメール**として報告] または [**フィッシングとして報告**] を選択します。

     ![迷惑メールフォルダーを右クリックして迷惑メールではないことを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 複数のメッセージを選択し、右クリックして、[**迷惑メール**ではないと報告] または [**フィッシングとし**て報告する] を選択します。

     ![迷惑メールフォルダー内の複数の迷惑メールまたはフィッシング詐欺メールメッセージを右クリックして報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み、[**レポート**] をクリックします。 気が変わった場合は、[**レポートしない**] をクリックします。

   ![[迷惑メールではないメールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをインストールする

- アドインをインストールするコンピューターで管理者特権を持っている必要があります。

- に<https://www.microsoft.com/download/details.aspx?id=18275>移動して、お使いの Office のバージョンに対応する .msi ファイルを、見つけやすい場所にダウンロードします。

  - **32 ビット**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 ビット**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 以降の場合、唯一の前提条件は、Microsoft .NET Framework 2.0 です。 Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールすることはありません。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップウィザードを使用して迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、.NET Framework 2.0 が有効になっていることを確認します。 手順については、「[コントロールパネルで .Net Framework 3.5 を有効にする](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)」を参照してください。

3. ダウンロードした .msi ファイルを見つけ、それをダブルクリックします。

4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。

5. 使用許諾契約書の内容を確認し、条項に同意する場合は [**使用許諾契約書の条項に同意**します] をクリックし、[**次へ**] をクリックします。

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

3. ユーザーの操作なしでアドインをインストールするには、コマンドプロンプトを開き、次の構文を使用します。

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection`1回の送信に対して選択できるメッセージの最大数を指定します。 有効な値は 1 ~ 50 です。 既定値は 15 です。

   - `BccEmailAddress`すべてのユーザー送信のコピーを受信する追加の Bcc 受信者を指定します。 既定値は空白です (追加の Bcc 受信者は含まれません)。

   この例では、既定の設定を使用して、指定されたパスから64ビット版のアドインをインストールします。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   この例では、次の追加設定を使用して、指定されたパスから32ビットバージョンのアドインをインストールします。

   - 1回の送信で最大20個のメッセージを選択できます。
   - junkreports@contoso.com および hollyd@treyresearch.net は、すべての送信の Bcc コピーを受信します。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で次のいずれかの手順を実行します。

- メッセージを選択するか、メッセージを開きます。 リボンの [**ホーム**] タブまたは [**メッセージ**] タブで、[**迷惑メール**] をクリックし、次のオプションが使用可能になっていることを確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メール報告オプション**
  - **迷惑メールを報告するオンラインヘルプ**

  ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-ribbon.png)

- メッセージを右クリックし、[**迷惑メール**] を選択して、次のオプションが使用可能であることを確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メール報告オプション**
  - **迷惑メールを報告するオンラインヘルプ**

  ![右クリックで迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-right-click.png)

- 複数のメッセージを選択し、右クリックして、次のオプションが使用可能であることを確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**

  ![右クリックで複数の迷惑メールまたはフィッシング詐欺メールメッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- **[迷惑メール**] フォルダー内の以前のアクションを実行し、以前の**迷惑**レポートオプションが迷惑メールでは**ない**ことを確認します。

  ![迷惑メールフォルダーのリボンから迷惑メールまたはフィッシング詐欺メールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メールフォルダーを右クリックして迷惑メールではないことを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メールフォルダー内の複数の迷惑メールまたはフィッシング詐欺メールメッセージを右クリックして報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする

Outlook を閉じた後、次のいずれかの手順を使用して、迷惑メール報告アドインをアンインストールします。

- **コントロールパネル**: Windows キー + R を押します。開いた [**実行**] ダイアログで、 `control appwiz.cpl` enter と入力し、[ **OK**] をクリックします。

  一覧で**Microsoft 迷惑メール報告アドイン**を見つけて選択し、[**アンインストール**] をクリックします。

- **Windows インストーラーパッケージ**: 該当する .msi ファイルを検索またはダウンロードし、それをダブルクリックします。

  - **32 ビット**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 ビット**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  表示されるダイアログで、[ **Outlook 用 Microsoft 迷惑メール報告アドインを削除**する] を選択し、[**次へ**] をクリックします。

- **サイレントモード**: 適切な .msi ファイルを検索またはダウンロードします。 コマンドプロンプトウィンドウで、PathToFile \<\>を .msi ファイルの場所に置き換えて、次のいずれかのコマンドを実行します。

  - **32 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

アンインストール後に Outlook を開くと、迷惑メール、迷惑メールではない迷惑メールの報告オプションは表示されなくなります。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインのトラブルシューティング

迷惑メール報告アドインを追加した後、Outlook で問題が発生することがあります。 このセクションでは、発生する可能性のある問題と、それらの問題を解決するためのヒントについて説明します。

### <a name="troubleshooting-for-users"></a>ユーザー向けのトラブルシューティング

次の1つまたは複数の問題が発生します。

- **[迷惑メールの報告]** をクリックしても何も起こらない
- 電子メール メッセージを選択した後に Outlook が応答しなくなった
- "配信不能" と返され、報告された迷惑メールを配信できない

この問題を解決するには、次の手順を実行します。

1. Outlook を閉じて、再起動します。
2. テストメッセージを作成して送信し、受信者がメッセージを受信したことを確認します。
3. 問題が解決しない場合は、管理者に問い合わせてください。

Microsoft にメッセージを送信するために使用できるその他の方法については、「Microsoft へのメッセージ[とファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。

### <a name="troubleshooting-for-admins"></a>管理者向けのトラブルシューティング

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>問題: ユーザーにシステム管理者に問い合わせるように求めるエラーメッセージが継続的に表示される

1. レジストリキーの`LoggingLevel`値を "Verbose" に設定していることを確認または設定します。

   - **32 ビット版32の Windows 上の Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32 ビット版64の Windows 上の Outlook**:

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

2. Outlook を再起動し、エラーメッセージが表示された場合にユーザーに報告するように依頼します。

3. 次の場所にあるログ情報を収集します。

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>問題: ユーザーがメッセージを報告するときに確認のメッセージを表示しないように選択したときに、プロンプトが戻る

1. レジストリキー `ConfirmReportJunk`wih を作成します。値は "True" です。

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook を再起動します。
