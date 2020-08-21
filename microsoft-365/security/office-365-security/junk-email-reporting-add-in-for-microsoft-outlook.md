---
title: Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 迷惑メール報告アドインをインストールして、スパム、非スパム、フィッシング メールを Microsoft に報告する方法について説明します。
ms.openlocfilehash: 42b38830b55ae3dbee4ec74a0e96531d920c24a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827101"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する

> [!NOTE]
> 迷惑メール報告アドインを使用している場合は、代わりに [、迷惑メール報告アドインをお勧](enable-the-report-message-add-in.md) めします。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

Microsoft Outlook 用迷惑メール報告アドインにより、ユーザーは誤検知 (優れたメールがスパムとしてマークされています)、漏えい (不適切なメールで許可される)、およびフィッシング メッセージを Microsoft に送信できます。 組織で Exchange Online Protection (たとえば、オンプレミスの Exchange、または Exchange Online 以外のメール サービス) を使用していない場合、迷惑メールの報告送信はスパム フィルタリングに影響しません。

このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 迷惑メール報告アドインをインストールする場合は、後述 [する「迷惑メール報告アドインをインストール](#install-the-junk-email-reporting-add-in) する」を参照してください。

- 迷惑メール報告アドインは、次のバージョンの Outlook で機能します。

  - Outlook 2013 以降
  - Microsoft 365 Apps for enterprise に含まれる Outlook

- Microsoft へのメッセージの報告の詳細については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>迷惑メール報告アドインを使用してスパム メッセージとフィッシング メッセージを報告する

1. 受信トレイ内のメッセージまたはその他の [迷惑メール] 以外の電子メール フォルダーに対しては、次のいずれかの方法を使用して、スパム メッセージとフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム** ] **または [メッセージ** ] タブで、[迷惑メールとして保存] **をクリックし**、[ **迷惑メールとして** レポート] または **[レポート] を選択します**。

     ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-ribbon.png)

   - メッセージを右クリックし、[迷惑メール **]** を選択して、[迷惑メールとして保存] または [ **フィッシ** ング **として報告] を選択します**。

     ![右クリックから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-right-click.png)

   - 複数のメッセージを選択して右クリックし、[迷惑メールとして報告] または [ **フィッシ** ング **として報告] を選択します**。

     ![右クリックして、複数の迷惑メール またはフィッシングメール メッセージを報告します](../../media/junk-email-reporting-right-click-multiple.png)

2. 表示されるダイアログで情報を読み、レポート をクリック **します**。 後で注意が必要な場合は、[ **レポートしない] をクリックします**。

   ![迷惑メールとして報告](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![フィッシング ダイアログとして報告する](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは、分析用に Microsoft に送信され、次の処理が行います。

   - スパムとして報告された場合、[迷惑メール] フォルダーに移動されました。
   - フィッシングとして報告された場合は削除されます。
   
   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>迷惑メール報告アドインを使用して、迷惑メール フォルダーから、スパムではないフィッシングやフィッシングのメッセージを報告する

1. 迷惑メール フォルダーで、次のいずれかの方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。

   - メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム** ] **または [メッセージ** ] タブで [迷惑メールしない] をクリック **し**、[迷惑メールしない] または [ **レポート** ] を **選択します**。

     ![[迷惑メール] フォルダーのリボンから、迷惑メールまたはフィッシングメールでないメールを報告します](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - メッセージを右クリックして [迷惑 **メール]** をクリックし、[迷惑メールとして保存] を選択するか、[ **フィ** ッ **シングとして報告] を選択します**。

     ![迷惑メール フォルダーで右クリックして、迷惑メールまたはフィッシング メールでないメールを報告します](../../media/junk-email-reporting-junk-folder-right-click.png)

   - 複数のメッセージを選択して右クリックし、次に [迷惑メールしないメールとしてレポート] または [ **フ** ィッ **シングとして報告] を選択します**。

     ![迷惑メール フォルダーで右クリックして、迷惑メール メッセージまたはフィッシングメール メッセージの複数を報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. 表示されるダイアログで情報を読み、レポート をクリック **します**。 後で注意が必要な場合は、[ **レポートしない] をクリックします**。

   ![迷惑メールでないことを報告するダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![フィッシング ダイアログとして報告する](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. 選択したメッセージは、分析用に Microsoft に送信され、次の処理が行います。

   - スパムとして報告された場合、[迷惑メール] フォルダーに移動されました。
   - フィッシングとして報告された場合は削除されます。

   メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="install-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをインストールする

- このアドインをインストールするコンピューターの管理者特権が必要です。

- お使 <https://www.microsoft.com/download/details.aspx?id=18275> いのバージョンに適した .msi ファイルに移動してOffice、簡単に見つけやすい場所にダウンロードします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Outlook 2013 以降では、前提条件は Microsoft .NET Framework 2.0 のみです。 Windows 10 では、ダウンロードからの .NET Framework 2.0 はインストールしていけない。

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、.NET Framework 2.0 が有効になっていることを確認します。 手順については、コントロール パネル [の [.NET Framework 3.5 を有効にする] を参照してください](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。

3. ダウンロードした .msi ファイルを見つけ、ダブルクリックします。

4. **[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。

5. 使用許諾契約書を確認し、 **使用許諾契約書** の条項に同意します。入力条件に同意する場合は、[次へ] をクリック **します**。

6. ウィザードが完了したら、 **[完了]** をクリックします。

Outlook を起動します。

Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。

Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>サイレント モードで迷惑メール報告アドインをインストールする

1. お使いのコンピューターで Outlook を終了します。

2. Windows 10 で、次のコマンドを実行して .NET Framework 2.0 をインストールします。

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. ユーザー入力を行わずにアドインをインストールするには、コマンド プロンプトを開いて次の構文を使用します。

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` 1 つの提出で選択できる最大メッセージ数を指定します。 有効な値は 1 ~ 50 です。 既定値は 15 です。

   - `BccEmailAddress` は、ユーザーのすべての申請のコピーを受信する追加の BCC 受信者を指定します。 既定値は空白です (追加の BCC 受信者はありません)。

   この例では、指定したパスから既定の設定で 64 ビット バージョンのアドインをインストールします。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   この例では、次の追加設定を指定したパスから 32 ビット バージョンのアドインをインストールします。

   - 1 つの送信で最大 20 のメッセージを選択できます。
   - junkreports@contoso.comはhollyd@treyresearch.net BCC コピーを受信または受信します。

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で以下のいずれかの手順を実行します。

- メッセージを選択するか、メッセージを開きます。 リボンの **[ホーム** ] **タブまたは [** メッセージ] タブで、[迷惑メール] **を**クリックして、次のオプションを使用できることを確認します。

  - **迷惑メールとして報告**
  - **レポートをフィッシングとして報告する**
  - **迷惑レポート オプション**
  - **迷惑メールの報告に役立つヘルプ**

  ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-ribbon.png)

- メッセージを右クリックし、[迷惑メール] **を選択して**、次のオプションが使用できることを確認します。

  - **迷惑メールとして報告**
  - **レポートをフィッシングとして報告する**
  - **迷惑レポート オプション**
  - **迷惑メールの報告に役立つヘルプ**

  ![右クリックから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-right-click.png)

- 複数のメッセージを選択し、右クリックして、次のオプションを使用できることを確認します。

  - **迷惑メールとして報告**
  - **レポートをフィッシングとして報告する**

  ![右クリックして、複数の迷惑メール またはフィッシングメール メッセージを報告します](../../media/junk-email-reporting-right-click-multiple.png)

- [迷惑メール] フォルダーで以前の **アクションを実行し** 、以前の迷惑メール報告 **オプションが** [迷惑メールでなけなけた] **になたびないことを確認します**。

  ![[迷惑メール] フォルダーのリボンから、迷惑メールまたはフィッシングメールでないメールを報告します](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダーで右クリックして、迷惑メールまたはフィッシング メールでないメールを報告します](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダーで右クリックして、迷惑メール メッセージまたはフィッシングメール メッセージの複数を報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインをアンインストールする

Outlook を終了した後、次のいずれかの手順を使用して迷惑メール報告アドインをアンインストールします。

- **[コントロール パネル]:** Windows キー + R キーを押します。開いた **[ファイル** 名を指定して実行] ダイアログ ボックスで `control appwiz.cpl` **、[OK] を入力してクリックします**。

  一覧から **Microsoft 迷惑メール報告アドインを検索して** 選択し、[アンインストール] をクリック **します**。

- **Windows インストーラ**ー パッケージ: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。

  - **32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  表示されるダイアログで **、[Outlook 用迷惑メール報告アドインを削除する** ] を選び、[次へ] をクリック **します**。

- **サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。 コマンド プロンプト ウィンドウで \<PathToFile\> 、.msi ファイルの場所を置き換え、次のいずれかのコマンドを実行します。

  - **32 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 ビット**:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

アンインストール後に Outlook を開くと、迷惑メール、迷惑メール、およびフィッシング レポート オプションがなけけないはなかもしれます。

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>迷惑メール報告アドインのトラブルシューティング

迷惑メール報告アドインの追加後に Outlook で問題が発生する場合があります。 このセクションでは、発生する可能性のある問題と、それらの問題を解決するためのヒントについて説明します。

### <a name="troubleshooting-for-users"></a>ユーザー向けのトラブルシューティング

次の 1 つ以上の問題が発生しています。

- **[迷惑メールの報告]** をクリックしても何も起こらない
- 電子メール メッセージを選択した後に Outlook が応答しなくなった
- "配信不能" と返され、報告された迷惑メールを配信できない

この問題を解決するには、次の手順を実行します。

1. Outlook を終了して再起動します。
2. テスト メッセージを作成して送信し、受信者がメッセージを受信したことを確認します。
3. それが解決しない場合は、管理者に問い合わせます。

メッセージをマイクロソフトに送信するために使用できるその他の方法については、「レポート メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

### <a name="troubleshooting-for-admins"></a>管理者向けのトラブルシューティング

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>問題: システム管理者への連絡をユーザーに連絡するようにユーザーに連絡をとるエラー メッセージが連続して表示される

1. レジストリ キーの `LoggingLevel` 値を "Verbose" に設定します。

   - **32 ビット Windows 上の 32 ビット Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32 ビット Outlook on 64 ビット Windows**:

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

2. Outlook を再起動し、エラー メッセージが表示されたら報告する必要があります。

3. 次の場所にあるログ情報を収集します。

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>問題: メッセージを報告するときに確認プロンプトが表示されないように選択したユーザーが、そのメッセージを返したい

1. 値 `ConfirmReportJunk` が "True" のレジストリ キーを作成します。

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Outlook を再起動します。
