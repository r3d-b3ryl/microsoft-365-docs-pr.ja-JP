---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (別名トランスポート ルール) を使用して、ユーザーが Microsoft に報告するメッセージのコピーを受信する方法について学習できます。
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827387"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、メッセージの報告とファイルについての説明の説明のとおりに、ユーザーが分析のため Microsoft [にメッセージを報告する方法が複数あります](report-junk-email-messages-to-microsoft.md)。

ユーザーが Microsoft に報告するメッセージを検索するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、報告されたメッセージのコピーを受信するように BCC 受信者を構成できます。

メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online にメールボックスが置かれており、Exchange Online メールボックスを持つ組織用のスタンドアロン EOP PowerShell) で作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、Exchange Online または EOP でアクセス許可が割り当てられている必要があります。 特に、組織管理、コンプライアンス管理、**およびレコード**管理の各役割に既定で**Organization Management**割り当てられる **、** トランスポート ルールの**役割を割り**当てる必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- EAC を開くには[、「Exchange Online の Exchange 管理センター」または](https://docs.microsoft.com/Exchange/exchange-admin-center)[「スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online でのメール フロー ルールとスタンドアロン EOP のメール フロー ルールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメール フロー ルールでの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: わかりやすい一意のルールの名前を入力します。 たとえば、Bcc メッセージは Microsoft に報告されます。

   - [**その他のオプション**] をクリックします。

   - **受信者のアドレスに次**のいずれかの単語**が**含まれている場合に、このルール \> **を適用します**。表示**される単語**または語句を指定します。ダイアログで、次の値のいずれかを**Add**入力して [ ![ 追加] アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返します。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完了したら、 **[OK]** をクリックします。

   - **次の手順に**従います。[ **受信者を** \> **BCC ボックスに追加する] を選います**。 表示されるダイアログで、追加する受信者を見つけ、選択します。 完了したら、 **[OK]** をクリックします。

4. ルールを監査する、ルールをテストする、一定期間内にルールをアクティブ化する、その他の設定など、追加を行うことができます。 ルールを適用する前に、ルールをテストしてみることをお勧めします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

この例では、Bcc Messages Reported という名前の新しいメール フロー ルールを作成して、このトピックで説明した方法を使用して Microsoft に報告されたメール メッセージを検索し、ユーザー laura@contoso.com および julia@contoso.com を BCC 受信者として追加します。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、[メール フロー ルール]**に移動し** \> **Rules** \> 、[編集] アイコン \> をクリック**Edit** ![ して ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- テスト メッセージをレポートのメール アドレスのいずれかに送信し、結果を確認します。
