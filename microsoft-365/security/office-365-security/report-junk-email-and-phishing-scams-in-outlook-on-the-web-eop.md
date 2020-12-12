---
title: Outlook on the web で迷惑メールとフィッシングメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online の Outlook on the web (Outlook Web App) の組み込みの迷惑メール、迷惑メールではないメール、フィッシングメール報告オプション、およびユーザーに対してこれらのレポート オプションを無効にする方法について説明します。
ms.openlocfilehash: 0032e807961aed60128d6863899ae0de32d1a627
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659317"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Exchange Online の Outlook on the web で迷惑メールとフィッシングメールを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online にメールボックスを持つ Microsoft 365 組織では、Outlook on the web (旧称 Outlook Web App) の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。 詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 管理者は、ユーザーが Outlook on the web で Microsoft にメッセージを報告する機能を無効または有効にできます。 詳細については、この記事の後半 [の「Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) で迷惑メール報告を無効または有効にする」を参照してください。

- 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。

- メッセージを Microsoft に報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Outlook on the web でスパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール以外の受信トレイまたは他の電子メール フォルダー内のメッセージの場合は、次のいずれかの方法を使用してスパム メッセージとフィッシング メッセージを報告します。

   - メッセージを選択し、ツール バーの **[迷惑メール** ] をクリックして、[迷惑メール] または [フィッシング **]** **を選択します**。

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/owa-report-junk.png)

   - 1 つ以上のメッセージを選択し、右クリックして、[迷惑メール **としてマーク] を選択します**。

2. 表示されるダイアログで、[レポート] を **クリックします**。 If you change your mind, click **Don't Report**.

   |迷惑メール|フィッシング|
   |:---:|:---:|
   |![迷惑メールとして報告するダイアログ](../../media/owa-report-as-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. 選択したメッセージは分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Outlook on the web の [迷惑メール] フォルダーから非スパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール フォルダーで、次のいずれかの方法を使用して、スパム誤検知またはフィッシング メッセージを報告します。

   - メッセージを選択し、ツール バー **の [迷惑メール** ではない] をクリックして、[迷惑メールやフィッシング **ではない]** **を選択します**。

     ![リボンからの迷惑メールまたはフィッシングメールではないメールを報告する](../../media/owa-report-not-junk.png)

   - 1 つ以上のメッセージを選択し、右クリックして、[迷惑メール **ではないメールとしてマークする] を選択します**。

2. 表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。 If you change your mind, click **Don't Report**.

   |迷惑メールではないメール|フィッシング詐欺|
   |:---:|:---:|
   |![迷惑メールではないとして報告するダイアログ](../../media/owa-report-as-not-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. 選択したメッセージは分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Outlook on the web で迷惑メール報告を無効または有効にする

既定では、ユーザーはスパムの誤検知、偽陰性、フィッシング メッセージを Outlook on the web で分析するために Microsoft に報告できます。 管理者は、Exchange Online PowerShell で Outlook on the web メールボックス ポリシーを構成して、ユーザーがスパムの誤検知やスパムの検出検出を Microsoft に報告するのを防ぐことが可能です。 ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。

### <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理役割グループと受信者管理役割グループに割り当てられる受信者ポリシーまたはメール受信者の役割が必要です。 Exchange Online の役割グループの詳細については、「Exchange Online のアクセス許可」および [「Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) の役割グループの変更」を [参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。

- すべての組織には OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前にスコープ設定されたユーザーに適用されます。 Outlook on the web メールボックス ポリシーの詳細については、Exchange Online の Outlook on the web メールボックス [ポリシーを参照してください](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 迷惑メール報告を無効にしても、Outlook on the web でメッセージを迷惑メールとしてマークする機能や迷惑メールではないメッセージとしてマークする機能は削除されません。 [迷惑メール] フォルダーでメッセージを選択し、[迷惑メールではないメッセージ] をクリックすると、メッセージは受信トレイ \> に戻ります。 他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール] \> フォルダーに移動されます。 利用できなくなったのは、メッセージを Microsoft に報告するオプションです。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell を使用して Outlook on the web で迷惑メール報告を無効または有効にする

1. 既存の Outlook on the web メールボックス ポリシーと迷惑メール報告の状態を確認するには、次のコマンドを実行します。

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Outlook on the web で迷惑メール報告を無効または有効にするには、次の構文を使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   この例では、既定のポリシーで迷惑メール報告を無効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール報告を有効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

構文およびパラメーターの詳細については [、「Get-OwaMailboxPolicy」](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

Outlook on the web で迷惑メール報告が正常に有効または無効にされたことを確認するには、次の手順を使用します。

- Exchange Online PowerShell で次のコマンドを実行し **、ReportJunkEmailEnabled** プロパティの値を確認します。

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 影響を受けるユーザーのメールボックスを Outlook on the web で開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示しないか確認します。 \> <sup>\*</sup>

- 影響を受けるユーザーのメールボックスを Outlook on the web で開き、[迷惑メール]フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示しないか確認します。 \> <sup>\*</sup>

<sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。 Outlook on the web でこの設定を確認するには:

1. Click **Settings** ![ Outlook on the web settings icon View all ](../../media/owa-settings-icon.png) \> **Outlook settings** \> **Junk email**.
2. [レポート **] セクションで** 、次の値を確認します。 **レポートを送信する前に確認してください**。

   ![Outlook on the web の迷惑メール報告の設定](../../media/owa-junk-email-reporting-options.png)
