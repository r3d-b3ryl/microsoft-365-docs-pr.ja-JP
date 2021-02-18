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
ms.openlocfilehash: 40e87fec3bfd8ed4402713ca7ec45499bb50c68e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287607"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、「メッセージとファイルを [Microsoft](report-junk-email-messages-to-microsoft.md)に報告する」の説明に従って、ユーザーが分析のためにメッセージを Microsoft に報告する方法は複数あります。

ユーザーが Microsoft に報告するメッセージを探すメール フロー ルール (トランスポート ルールとも呼ばれる) を作成し、報告されたメッセージのコピーを受信する BCC 受信者を構成できます。

メール フロー ルールは、Exchange 管理センター (EAC) と PowerShell (Exchange Online のメールボックスを使用する Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を実行する前に、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理 **(グローバル** 管理者)、および **レコード** 管理の役割グループに割り当てられるトランスポート ルールの役割が必要です。

  詳細については、次のトピックをご覧ください。

  - [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [スタンドアロン EOP のアクセス許可](feature-permissions-in-eop.md)
  - [EAC を使用して役割グループのメンバーの一覧を変更する](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online で EAC を開く方法については [、Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。 スタンドアロン EOP で EAC を開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメール フロー ルールの詳細については、次のトピックを参照してください。
  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [Exchange Online のメール フロー ルールでの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **[名前**]: ルールのわかりやすい一意の名前を入力します。 たとえば、BCC メッセージは Microsoft に報告されます。

   - [**その他のオプション**] をクリックします。

   - [受信者のアドレスに次のいずれかの単語が含まれる場合に適用する]: 表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 \>    ![ ](../../media/ITPro-EAC-AddIcon.png)

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

     完了したら、 **[OK]** をクリックします。

   - **[BCC ボックスに** 受信者 **を追加する**] を \> **選択します**。 表示されるダイアログで、追加する受信者を見つけて選択します。 完了したら、 **[OK]** をクリックします。

4. 追加の選択を行って、ルールの監査、ルールのテスト、特定の期間のルールのアクティブ化、その他の設定を行います。 ルールを適用する前に、ルールをテストすることをお勧めします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell を使用して、報告されたメッセージのコピーを受信するメール フロー ルールを作成する

この例では、この記事で説明する方法を使用して Microsoft に報告される電子メール メッセージを参照する、BCC Messages Reported to Microsoft という名前の新しいメール フロー ルールを作成し、ユーザー laura@contoso.com と julia@contoso.com を BCC 受信者として追加します。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

報告されたメッセージのコピーを受信するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。

- EAC で、メール フロー ルールに **移動** し、ルールを選択して編集アイコンをクリックし、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- レポート電子メール アドレスの 1 つにテスト メッセージを送信し、結果を確認します。
