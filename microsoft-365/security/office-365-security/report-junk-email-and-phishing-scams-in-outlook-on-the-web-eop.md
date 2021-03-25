---
title: Outlook on the web で迷惑メールとフィッシングメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online の Outlook on the Web (Outlook Web App) の組み込みの迷惑メール、迷惑メール、フィッシングメールレポートオプション、およびユーザーに対してこれらのレポートオプションを無効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1233b85ad213091ac84ac6f7e8eb93d9145af
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205727"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Exchange Online で Outlook on the web で迷惑メールとフィッシングメールを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを持つ Microsoft 365 組織では、Outlook on the web (以前は Outlook Web App と呼ばれる) の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪いメールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange Online メールボックスを使用している組織の管理者の場合は、セキュリティ コンプライアンス センターの申請ポータルを使用&勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 管理者は、Outlook on the web でユーザーが Microsoft にメッセージを報告する機能を無効または有効にできます。 詳細については、この記事の後半の [「Outlook on the Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) での迷惑メールレポートを無効または有効にする」セクションを参照してください。

- 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。

- Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Outlook on the web でスパムメッセージとフィッシング メッセージを報告する

1. 迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次のいずれかの方法を使用してスパムメッセージとフィッシング メッセージを報告します。

   - メッセージを選択し、ツールバー **の [迷惑** メール] をクリックし、[迷惑メール] または **[フィッシング]** **を選択します**。

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/owa-report-junk.png)

   - 1 つ以上のメッセージを選択し、右クリックし、[迷惑メールとして **マーク] を選択します**。

2. 表示されるダイアログで、[レポート] を **クリックします**。 気が変わる場合は、[ **レポートしない] をクリックします**。

   |迷惑メール|フィッシング|
   |:---:|:---:|
   |![[迷惑メールとして報告] ダイアログ](../../media/owa-report-as-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. 選択したメッセージは、分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Web 上の Outlook の迷惑メール フォルダーからスパム以外のメッセージとフィッシング メッセージを報告する

1. [迷惑メール] フォルダーで、次のいずれかの方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。

   - メッセージを選択し、ツールバーの **[迷惑メールではない** ] をクリックし、[迷惑メールや **フィッシング** ではない] **を選択します**。

     ![リボンから迷惑メールやフィッシングメールを報告しない](../../media/owa-report-not-junk.png)

   - 1 つ以上のメッセージを選択し、右クリックし、[迷惑メールではない **としてマークする] を選択します**。

2. 表示されるダイアログで、情報を読み取り、[レポート] を **クリックします**。 気が変わる場合は、[ **レポートしない] をクリックします**。

   |迷惑メールではないメール|フィッシング詐欺|
   |:---:|:---:|
   |![迷惑メールではないとして報告する](../../media/owa-report-as-not-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. 選択したメッセージは、分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Outlook on the web で迷惑メールレポートを無効または有効にする

既定では、ユーザーは、Outlook on the web で分析のために、スパムの誤検知、誤検知、フィッシング メッセージを Microsoft に報告できます。 管理者は、Exchange Online PowerShell で Outlook on the Web メールボックス ポリシーを構成して、ユーザーがスパムの誤検知やスパムの誤検知を Microsoft に報告するのを防ぐことが可能です。 ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。

### <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、既定で **組織の管理** 役割グループと受信者管理役割グループに割り当てられている受信者ポリシーまたはメール受信者の役割が必要です。  Exchange Online の役割グループの詳細については、「Exchange Online のアクセス許可」および [「Exchange Online](/exchange/permissions-exo/permissions-exo) の役割グループの [変更」を参照してください](/Exchange/permissions-exo/role-groups#modify-role-groups)。

- すべての組織に OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前にスコープ付きユーザーに適用されます。 Outlook on the Web メールボックス ポリシーの詳細については、「Outlook on the Web Mailbox [Policies in Exchange Online」を参照してください](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。

- 迷惑メールレポートを無効にしても、Outlook on the web でメッセージを迷惑メールとしてマークしたり、迷惑メールとしてマークしたりする機能は削除されません。 迷惑メール フォルダーでメッセージを選択し、[迷惑メールではない] をクリックすると、メッセージは受信トレイ \> に戻ります。 他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール \> ] フォルダーに移動されます。 使用できなくなったのは、Microsoft にメッセージを報告するオプションです。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Exchange Online PowerShell を使用して Outlook on the web で迷惑メールレポートを無効または有効にする

1. Web メールボックス ポリシー上の既存の Outlook と迷惑メールレポートの状態を確認するには、次のコマンドを実行します。

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Outlook on the web で迷惑メール レポートを無効または有効にするには、次の構文を使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   この例では、既定のポリシーで迷惑メールレポートを無効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール レポートを有効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

構文とパラメーターの詳細については [、「Get-OwaMailboxPolicy」](/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

Outlook on the web で迷惑メールレポートが正常に有効または無効にされたことを確認するには、次の手順を実行します。

- Exchange Online PowerShell で、次のコマンドを実行し **、ReportJunkEmailEnabled プロパティ** の値を確認します。

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 影響を受けるユーザーのメールボックスを Outlook on the web で開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します \> 。<sup>\*</sup>

- 影響を受けるユーザーのメールボックスを Outlook on the web で開き、[迷惑メール]フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup>

<sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。 Outlook on the web でこの設定を確認するには、次の方法を実行します。

1. [Web **設定]** ![ アイコンの [Outlook の設定] アイコン [ ](../../media/owa-settings-icon.png) \> **すべての Outlook 設定の迷惑メールを** \> **表示する] をクリックします**。
2. [レポート **] セクションで** 、値を確認します。 **レポートを送信する前に確認してください**。

   ![Outlook on the web Junk Email Reporting settings](../../media/owa-junk-email-reporting-options.png)