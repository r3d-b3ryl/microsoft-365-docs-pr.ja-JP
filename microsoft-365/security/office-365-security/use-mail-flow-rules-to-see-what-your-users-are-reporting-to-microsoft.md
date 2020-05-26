---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 管理者は、メールフロールール (トランスポートルールとも呼ばれます) を使用して、ユーザーが Microsoft に報告するメッセージのコピーを受信する方法を学習できます。
ms.openlocfilehash: f8e4310fef19a8925640c485d060389352218e0b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352410"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

Exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内のメールボックスを持つ Microsoft 365 組織では、「[レポートメッセージとファイル](report-junk-email-messages-to-microsoft.md)」で説明されているように、ユーザーが分析のために microsoft にメッセージを報告する方法が複数あります。

ユーザーが Microsoft に報告するメッセージを検索するメールフロールール (トランスポートルールとも呼ばれます) を作成し、これらのレポートされたメッセージのコピーを受信するように Bcc 受信者を構成することができます。

Exchange 管理センター (EAC) および PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange Online PowerShell、exchange Online メールボックスを使用していない組織の場合はスタンドアロン EOP PowerShell) でメールフロールールを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- これらの手順を実行する前に、Exchange Online または EOP でアクセス許可を割り当てる必要があります。 具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- EAC を開くには、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center) 」または「exchange [admin CENTER in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン**をクリックし**、[ ![ ](../../media/ITPro-EAC-AddIcon.png) **新しいルールの作成**] を選択します。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。 たとえば、Microsoft に報告される Bcc メッセージ。

   - [**その他のオプション**] をクリックします。

   - [次の**場合にこのルールを適用**する]:**受信者** \> **のアドレスに次のいずれかの単語が含まれ**ます。表示される [**単語または語句の指定**] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、 **Add** ![ ](../../media/ITPro-EAC-AddIcon.png) すべての値を入力するまで繰り返します。

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     エントリを編集するには、エントリを選択し、[編集] [編集] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-EditIcon.png) ます。 エントリを削除するには、エントリを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ます。

     完了したら、 **[OK]** をクリックします。

   - **次の手順を実行**します。 [**受信者** \> **を Bcc ボックスに追加する**] を選択します。 表示されるダイアログで、追加する受信者を見つけて選択します。 完了したら、 **[OK]** をクリックします。

4. ルールを監査したり、ルールをテストしたり、特定の期間にルールをアクティブ化したり、その他の設定を行ったりするには、追加の選択を行うことができます。 ルールを適用する前に、ルールをテストすることをお勧めします。

5. 完了したら、**[保存]** をクリックします。

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する

この例では、このトピックで説明する方法を使用して Microsoft に報告された電子メールメッセージを検索し、Bcc 受信者としてユーザー laura@contoso.com および julia@contoso.com を追加する Bcc メッセージという名前の新しいメールフロールールを作成します。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

レポートされたメッセージのコピーを受信するメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、[**メールフロー** \> **ルール**] に移動し \> 、 \> [**編集** ![ ] 編集アイコンをクリックして ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- テストメッセージをレポート電子メールアドレスのいずれかに送信し、結果を確認します。
