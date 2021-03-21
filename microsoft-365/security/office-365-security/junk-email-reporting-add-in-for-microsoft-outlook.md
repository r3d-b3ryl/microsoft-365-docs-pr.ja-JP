---
title: Microsoft Outlook の迷惑メール レポート アドインをインストールして使用する
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
description: Microsoft 迷惑メール レポート アドインをインストールして使用して、スパム、非スパム、フィッシング メッセージを Microsoft に報告する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a6386307b24d879cac9dd2390d9080cd2cb8b5b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920362"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook の迷惑メール レポート アドインをインストールして使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> 現在迷惑メール レポート アドインを使用していない場合は、代わりにレポート メッセージ アドイン[](enable-the-report-message-add-in.md)またはレポート フィッシング[アドインをお](enable-the-report-phish-add-in.md)勧めします。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

Microsoft Outlook の迷惑メール レポート アドインを使用すると、ユーザーは誤検知 (スパムとしてマークされた良いメール)、誤検知 (悪いメールが許可されている)、フィッシング メッセージを Microsoft に送信できます。 組織で Exchange Online Protection (たとえば、Exchange Online 以外のオンプレミス Exchange または電子メール サービス) を使用しない場合、迷惑メール レポートの送信はスパム フィルター処理に影響を与えかねない。

このトピックでは、迷惑メール レポート アドインをインストールして使用する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 迷惑メール レポート アドインをインストールするには、この記事の後半にある「迷惑 [メール](#install-the-junk-email-reporting-add-in) レポート アドインのインストール」セクションを参照してください。

- 迷惑メール レポート アドインは、次のバージョンの Outlook で動作します。

  - Outlook 2013 以降
  - エンタープライズ向け Microsoft 365 Apps に含まれる Outlook

- Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>迷惑メール レポート アドインを使用してスパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブ **または [メッセージ**] タブで、[迷惑 **メール]** をクリックし、[迷惑メールとして報告] または [フィッシングとしてレポート **] を選択します**。

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

   - メッセージを右クリックし、[迷惑メール **]** を選択し、[迷惑メールとして報告] または [フィッシング **として報告] を選択します**。

     ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

   - 複数のメッセージを選択し、右クリックし、[迷惑メールとして報告] または [フィッシング **として報告] を選択します**。

     ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み取り、[レポート] を **クリックします**。 気が変わる場合は、[ **レポートしない] をクリックします**。

   ![[迷惑メールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは、分析のために Microsoft に送信されます。

   - 迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。
   - フィッシングとして報告された場合に削除されます。

   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>迷惑メール レポート アドインを使用して迷惑メール フォルダーからスパム以外のメッセージとフィッシング メッセージを報告する

1. 迷惑メール フォルダーで、次の方法を使用してスパムの誤検知やフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブまたは **[メッセージ**] タブで、[迷惑メールではない] をクリックし、[迷惑メールとして報告] または [フィッシングとして報告]**を選択します**。 

     ![[迷惑メール] フォルダーのリボンから迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - メッセージを右クリックし、[迷惑メール **]** をクリックし、[迷惑メールではない] または [フィッシングとして報告する **] を選択します**。

     ![迷惑メール フォルダーで右クリックして迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 複数のメッセージを選択し、右クリックし、[迷惑メールとして報告する] または [フィッシング **として報告する] を選択します**。

     ![迷惑メール フォルダー内で右クリックして複数の迷惑メールメッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 表示されるダイアログで、情報を読み取り、[レポート] を **クリックします**。 気が変わる場合は、[ **レポートしない] をクリックします**。

   ![迷惑メールではないとして報告する](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは、分析のために Microsoft に送信されます。

   - 迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。
   - フィッシングとして報告された場合に削除されます。

   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール レポート アドインをインストールする

- アドインをインストールするコンピューターに管理者権限が必要です。

- ファイルのバージョンに適した .msi ファイルOffice簡単に <https://www.microsoft.com/download/details.aspx?id=18275> 見つけることができる場所に移動してダウンロードします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 以降の場合、唯一の前提条件は Microsoft .NET Framework 2.0 です。 Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールする必要があります。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップ ウィザードを使用して迷惑メール レポート アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、2.0 .NET Frameworkが有効になっているか確認します。 手順については、「コントロール パネル [で .NET Framework 3.5 を有効にする」を参照してください](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。

3. ダウンロードした .msi ファイルを見つけてダブルクリックします。

4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。

5. 使用許諾契約書を確認し、条項 **に** 同意する場合は[使用許諾契約書に同意する] をクリックし、[次へ] を **クリックします**。

6. ウィザードが完了したら、 **[完了]** をクリックします。

Outlook を起動します。

Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。

Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>サイレント モードで迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、次のコマンド.NET Framework 2.0 をインストールします。

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. ユーザー操作なしでアドインをインストールするには、コマンド プロンプトを開き、次の構文を使用します。

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 1 つの申請に対して選択できるメッセージの最大数を指定します。 有効な値は 1 ~ 50 です。 既定値は 15 です。

   - `BccEmailAddress` すべてのユーザー申請のコピーを受け取る追加の BCC 受信者を指定します。 既定値は空白です (追加の BCC 受信者はありません)。

   次の使用例は、指定したパスから 64 ビット バージョンのアドインを既定の設定でインストールします。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   この例では、指定したパスから 32 ビット バージョンのアドインをインストールし、次の追加設定を行います。

   - 1 回の申請で最大 20 件のメッセージを選択できます。
   - junkreports@contoso.com および hollyd@treyresearch.net、すべての申請の BCC コピーを受信します。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

迷惑メール レポート アドインが正常にインストールされたことを確認するには、Outlook で次の手順を実行します。

- メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム]** タブ **または [メッセージ** ] タブで、[迷惑 **メール]** をクリックし、次のオプションが使用できると確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メールレポートのオプション**
  - **迷惑メール のオンライン ヘルプを報告する**

  ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

- メッセージを右クリックし、[迷惑メール **]** を選択し、次のオプションが使用できると確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**
  - **迷惑メールレポートのオプション**
  - **迷惑メール のオンライン ヘルプを報告する**

  ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

- 複数のメッセージを選択し、右クリックして、次のオプションが使用できると確認します。

  - **迷惑メールとして報告する**
  - **フィッシングとして報告する**

  ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- [迷惑メール] フォルダーで前の **アクションを実行** し、以前の迷惑メール レポート オプションが [迷惑メールではない] に **なっていることを確認します**。

  ![[迷惑メール] フォルダーのリボンから迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダーで右クリックして迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダー内で右クリックして複数の迷惑メールメッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする

Outlook を閉じると、次の手順を使用して迷惑メール レポート アドインをアンインストールします。

- **コントロール パネル**: Windows キー + R キーを押します。開く **[ファイル名を指定** して実行] ダイアログで `control appwiz.cpl` 、[OK] を入力し **、[OK] をクリックします**。

  リストで **Microsoft 迷惑メール レポート アドイン** を検索して選択し、[アンインストール] を **クリックします**。

- **Windows インストーラー パッケージ**: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  表示されるダイアログで **、[Outlook** 用 Microsoft 迷惑メール レポート アドインの削除] を選択し、[次へ] を **クリックします**。

- **サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。 コマンド プロンプト ウィンドウで、.msi ファイルの場所に置き換え、 \<PathToFile\> 次のいずれかのコマンドを実行します。

  - **32 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

アンインストール後に Outlook を開いた場合は、迷惑メールではなく迷惑メールやフィッシング報告のオプションがなくなります。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>迷惑メール レポート アドインのトラブルシューティング

迷惑メール レポート アドインを追加した後で Outlook で問題が発生する場合があります。 このセクションでは、発生する可能性のある問題と、これらの問題を解決するためのヒントについて説明します。

### <a name="troubleshooting-for-users"></a>ユーザーのトラブルシューティング

次に示す問題が 1 つ以上発生します。

- **[迷惑メールの報告]** をクリックしても何も起こらない
- 電子メール メッセージを選択した後に Outlook が応答しなくなった
- "配信不能" と返され、報告された迷惑メールを配信できない

この問題を解決するには、次の手順を実行します。

1. Outlook を閉じて再起動します。
2. テスト メッセージを作成して送信し、受信者がメッセージを受信したと確認します。
3. 問題が解決しない場合は、管理者に問い合わせください。

Microsoft にメッセージを送信するために使用できるその他のメソッドについては、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

### <a name="troubleshooting-for-admins"></a>管理者向けトラブルシューティング

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>問題: システム管理者に連絡を求めるエラー メッセージが継続的に表示される

1. レジストリ キーを `LoggingLevel` "Verbose" という値に設定します。

   - **32 ビット Windows の 32 ビット Outlook:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64 ビット Windows の 32 ビット Outlook:**

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

2. Outlook を再起動し、エラー メッセージが表示されたユーザーに報告を求める。

3. 次の場所にあるログ情報を収集します。

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>問題: メッセージを報告するときに確認メッセージを受信しないユーザーを選択し、プロンプトを戻す

1. `ConfirmReportJunk`"True" という値のレジストリ キーを作成します。

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook を再起動します。