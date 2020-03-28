---
title: 'Outlook on the web で迷惑メールとフィッシング詐欺を報告する '
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
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Office 365 Exchange Online メールボックスを使用しているユーザーは、web 上の Outlook (Outlook Web App) を使用して、スパム、非スパム、フィッシングメッセージを分析のために Microsoft に送信できます。
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033706"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a>Office 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する

Exchange Online メールボックスを使用している Office 365 のお客様の場合は、web 上の Outlook (旧称 Outlook Web App) の組み込みのレポート作成オプションを使用して誤検知 (スパムとしてマークされた良好な電子メール)、誤検知 (無効な電子メールを許可)、Exchange Online Protection (EOP) へのフィッシングメッセージ

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Office 365 組織の管理者が Exchange Online メールボックスを使用している場合は、Office 365 セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。 詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。

- 管理者は、ユーザーが Outlook on the web でメッセージを Microsoft に報告する機能を無効または有効にすることができます。 詳細については、このトピックで後述する「 [web 上の Outlook で迷惑メール報告を無効または有効](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)にする」を参照してください。

- Microsoft へのメッセージの報告の詳細については、「 [Office 365 でメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Outlook on the web でスパムメッセージとフィッシングメッセージを報告する

1. 受信トレイまたは迷惑メール以外の他の電子メールフォルダー内のメッセージの場合は、次のいずれかの方法を使用して、スパムメッセージとフィッシングメッセージを報告します。

   - メッセージを選択し、ツールバーの [**迷惑メール**] をクリックして、[**迷惑メール**または**フィッシング詐欺**] を選択します。

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/owa-report-junk.png)

   - 1つ以上のメッセージを選択し、右クリックして、[**迷惑メールにマーク**] を選択します。

2. 表示されるダイアログで、[**レポート**] をクリックします。 気が変わった場合は、[**レポートしない**] をクリックします。

   ![[迷惑メールとして報告] ダイアログ](../../media/owa-report-as-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/owa-report-as-phishing-dialog.png)

3. 選択したメッセージが分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Outlook on the web で迷惑メールフォルダーから非スパムメッセージとフィッシングメッセージを報告する

1. [迷惑メール] フォルダーで、次のいずれかの方法を使用して、スパム誤検知またはフィッシングメッセージを報告します。

   - メッセージを選択し、ツールバーの [**迷惑メール**ではない] をクリックし、[**迷惑メール**ではない] または [**フィッシング詐欺**] を選択します。

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/owa-report-not-junk.png)

   - 1つ以上のメッセージを選択して右クリックし、[**迷惑メールではないメールとしてマーク**] を選択します。

2. 表示されるダイアログで、情報を読み、[**レポート**] をクリックします。 気が変わった場合は、[**レポートしない**] をクリックします。

   ![[迷惑メールではないメールとして報告] ダイアログ](../../media/owa-report-as-not-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/owa-report-as-phishing-dialog.png)

3. 選択したメッセージが分析のために Microsoft に送信されます。 メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Outlook on the web で迷惑メール報告を無効または有効にする

既定では、ユーザーは、web 上の Outlook で分析するために、スパム誤検知、誤ネガ、フィッシングメッセージを Microsoft に報告できます。 管理者は、Exchange Online の web メールボックスポリシーで Outlook を使用して、この機能を有効または無効にできますが、Exchange Online の PowerShell でのみ使用できます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

- これらの手順を実行する前に、アクセス許可を割り当てる必要があります。 具体的には、**組織の管理**役割グループおよび**受信者管理**役割グループに既定で割り当てられる Exchange Online の**受信者ポリシー**または**メール受信者**の役割が必要です。 Exchange Online の役割グループの詳細については、「 [Exchange online で役割グループを変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)する」を参照してください。

- すべての組織には、Owam社内 Boxpolicy-Default という名前の既定のポリシーがありますが、カスタムポリシーを作成することができます。 カスタムポリシーは、既定のポリシーよりも前に、スコープを指定したユーザーに適用されます。 Outlook on the web メールボックスポリシーの詳細については、「 [outlook on the web mailbox policies In Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)」を参照してください。

1. 既存の Outlook on the web メールボックスポリシーと、迷惑メール報告の状態を確認するには、次のコマンドを実行します。

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

   この例では、Contoso Managers という名前のカスタムポリシーで迷惑メール報告を有効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

構文およびパラメーターの詳細については、「[収集](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)」を[参照してください。](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

Outlook on the web で迷惑メール報告が正常に有効または無効にされたことを確認するには、次のいずれかの手順を使用します。

- Exchange Online PowerShell で次のコマンドを実行し、 **ReportJunkEmailEnabled**プロパティの値を確認します。

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- 影響を受けるユーザーのメールボックスを web 上の Outlook で開き、迷惑メールではなく迷惑メールを報告するオプションを確認します。または使用できないことを確認します。 なお、ユーザーはメッセージを迷惑メールとしてマークし、迷惑メールとしてマークすることはできませんが、ユーザーは Microsoft に報告することはできません。
