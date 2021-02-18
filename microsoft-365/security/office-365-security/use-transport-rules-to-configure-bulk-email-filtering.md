---
title: メール フロー ルールを使用してバルク メールをフィルター処理する
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) でメール フロー ルール (トランスポート ルール) を使用してバルク メール (灰色のメール) を識別およびフィルター処理する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287295"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>メール フロー ルールを使用して EOP でバルク メールをフィルタリングする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージでスパムおよびバルク メール (グレー メールとも呼ばれる) をスキャンします。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

バルク メールをフィルター処理するその他のオプションが必要な場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、バルク メールでよく見られるテキスト パターンや語句を検索し、それらのメッセージをスパムとしてマークできます。 バルク メールの詳細については、「 [迷惑](what-s-the-difference-between-junk-email-and-bulk-email.md) メールとバルク メールの違い」と EOP のバルク苦情レベル [(BCL) を参照してください](bulk-complaint-level-values.md)。

このトピックでは、Exchange 管理センター (EAC) と PowerShell でこれらのメール フロー ルールを作成する方法について説明します (Exchange Online にメールボックスがある Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell)。

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

- 例でバルク メールを識別するために使用される単語とテキスト パターンのリストは完全ではありません。必要に応じてエントリを追加および削除できます。 ただし、これらは良い開始点です。

- メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた *後* に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。

- 次の手順では、バルク メッセージを組織全体のスパムとしてマークします。 ただし、別の条件を追加してこれらのルールを特定の受信者にのみ適用することができます。そのため、数名の対象を絞り込むユーザーに対して積極的なフィルター処理を使用できます。一方、他のユーザー (ほとんどがサインアップしたバルク メールを受け取るユーザー) は影響を受け取らない状態です。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC を使用してバルク メールをフィルター処理するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **[名前**]: ルールのわかりやすい一意の名前を入力します。

   - [**その他のオプション**] をクリックします。

   - **次のいずれかの** 設定を構成して、正規表現 (RegEx) または単語または語句を使用してメッセージ内のコンテンツを検索する場合に、このルールを適用します。

     - **件名または本文** \>**件名** または本文が次のテキスト パターンと一致する: 表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 ![ ](../../media/ITPro-EAC-AddIcon.png)

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完了したら、 **[OK]** をクリックします。

     - **件名または本文** \>**件名または** 本文に次のいずれかの単語が含まれています:表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 ![ ](../../media/ITPro-EAC-AddIcon.png)

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完了したら、 **[OK]** をクリックします。

   - **Do the following**: Select **Modify the message properties** set the spam confidence level \> **(SCL)**. 表示される **[SCL の** 指定] ダイアログで、次のいずれかの設定を構成します。

     - メッセージをスパムとしてマーク **するには****、6 を選択します**。 スパム対策ポリシーでスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動]**です**)。

     - メッセージを信頼度の **高いスパムとしてマークするには****、9 を選択します**。 スパム対策ポリシーで信頼度の高いスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動]**です)。**

    SCL 値の詳細については [、EOP の「Spam Confidence Level (SCL)」を参照してください](spam-confidence-levels.md)。

   完了したら、[保存] をクリック **します。**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell を使用してバルク メールをフィルター処理するメール フロー ルールを作成する

メール フロー ルール (正規表現と単語) の一方または両方を作成するには、次の構文を使用します。

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

この例では、トピックの以前の正規表現の同じリストを使用してメッセージをスパムとして設定する、"バルク メール フィルター - RegEx" という名前の新しいルールを作成 **します**。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

この例では、トピックの前の部分と同じ単語の一覧を使用してメッセージを信頼度の高いスパムとして設定する、"バルク メール フィルター - 単語" という名前の新しいルール **を作成します**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

バルク メールをフィルター処理するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。

- EAC で、メール フロー ルールに **移動** し、ルールを選択して編集アイコンをクリックし、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、ルールの名前に置き換え、次のコマンドを \<Rule Name\> 実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 外部アカウントから、影響を受ける受信者に、語句またはテキスト パターンのいずれかを含むテスト メッセージを送信し、結果を確認します。
