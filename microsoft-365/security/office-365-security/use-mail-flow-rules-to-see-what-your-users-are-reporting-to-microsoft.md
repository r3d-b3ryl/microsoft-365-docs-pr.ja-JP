---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、ユーザーが Microsoft に報告するメッセージのコピーを受信する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206099"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、「メッセージと[](report-junk-email-messages-to-microsoft.md)ファイルを Microsoft に報告する」で説明したように、ユーザーが分析のために Microsoft にメッセージを報告する方法は複数あります。

ユーザーが Microsoft に報告するメッセージを探すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、これらの報告されたメッセージのコピーを受信する BCC 受信者を構成できます。

メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) に作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事の手順を実行するには、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定では、組織の管理、コンプライアンス管理 **(グローバル** 管理者)、レコード管理の役割グループに割り当てられているトランスポート ルールの役割が必要です。 

  詳細については、次のトピックをご覧ください。

  - [Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)
  - [スタンドアロン EOP のアクセス許可](feature-permissions-in-eop.md)
  - [役割グループ内のメンバーの一覧を変更する EAC を使用する](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online で EAC を開く方法については、「Exchange Online [の Exchange 管理センター」を参照してください](/Exchange/exchange-admin-center)。 スタンドアロン EOP で EAC を開く方法については、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメール フロー ルールの詳細については、次のトピックを参照してください。
  - [Exchange Online のメール フロー ルール (トランスポート ルール)](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Exchange Online のメール フロー ルールでの条件と例外 (述語)](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Exchange Online でのメール フロー ルールの処理](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルール **の作成] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: ルールの一意でわかりやすい名前を入力します。 たとえば、BCC メッセージが Microsoft に報告されました。

   - [**その他のオプション**] をクリックします。

   - [受信者アドレスに次のいずれかの単語が含まれる] を選択する場合は、次のルールを適用します。表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[アイコンの追加] をクリックし、すべての値を入力するまで繰り返します。 \>    ![ ](../../media/ITPro-EAC-AddIcon.png)

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完了したら、 **[OK]** をクリックします。

   - **[Bcc] ボックス** に **[受信者を追加** \> **する] を選択します**。 表示されるダイアログで、追加する受信者を見つけて選択します。 完了したら、 **[OK]** をクリックします。

4. 追加の選択を行って、ルールの監査、ルールのテスト、特定の期間中のルールのアクティブ化、その他の設定を行います。 ルールを適用する前に、ルールをテストすることをお勧めします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

この例では、この記事で説明するメソッドを使用して Microsoft に報告される電子メール メッセージを確認し、ユーザー laura@contoso.com および julia@contoso.com を BCC 受信者として追加する、Bcc Messages Reported to Microsoft という名前の新しいメール フロー ルールを作成します。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。

- EAC で、[メールフロールール] に移動し、[編集] アイコンをクリックして、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- レポート電子メール アドレスの 1 つにテスト メッセージを送信し、結果を確認します。