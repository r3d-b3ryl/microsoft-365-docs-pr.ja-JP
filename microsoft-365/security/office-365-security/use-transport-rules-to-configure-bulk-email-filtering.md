---
title: メールフロールールを使用してバルクメールをフィルター処理する
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、メールフロールール (トランスポートルール) を使用して、Exchange Online Protection (EOP) で大量メール (灰色のメール) を識別し、フィルター処理する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c6a8ad5dd2752f86c0ff9ec96dafe621804b4856
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197305"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>メール フロー ルールを使用して EOP でバルク メールをフィルタリングする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP はスパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) を使用して、スパムやバルクメール (灰色のメール) の受信メッセージをスキャンします 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

バルクメールをフィルター処理するためのその他のオプションが必要な場合は、メールフロールール (トランスポートルールとも呼ばれる) を作成して、バルクメールでよく見られるテキストパターンや語句を検索し、それらのメッセージをスパムとしてマークします。 バルクメールの詳細については、EOP の「 [迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md) 」および「 [バルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。

このトピックでは、exchange 管理センター (EAC) および PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange Online PowerShell、exchange Online メールボックスを使用しない組織の場合はスタンドアロン EOP PowerShell) でこれらのメールフロールールを作成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- これらの手順を実行する前に、アクセス許可を割り当てる必要があります。

  - Exchange Online の場合は、「 [Exchange online の機能のアクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)」の「メールフロー」エントリを参照してください。
  
  - スタンドアロン EOP では、既定で、組織の管理、ComplianceManagement、およびレコードの管理役割に割り当てられているトランスポートルールの役割が必要です。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、 [役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。 スタンドアロン EOP で EAC を開くには、「 [Exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメール フロー ルールでの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- この例では、バルクメールを識別するために使用される単語とテキストパターンの一覧は完全ではありません。必要に応じて、エントリを追加および削除できます。 ただし、開始点として適しています。

- メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた*後*に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。

- 次の手順では、組織全体に対してバルクメッセージをスパムとしてマークします。 ただし、これらのルールを特定の受信者にのみ適用する別の条件を追加することができます。そのため、一部の高度な対象ユーザーに対して積極的にフィルターを適用することができます。ただし、ユーザーの残りの部分 (頻繁に使用するバルクメールを取得する場合) は影響を受けません。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC を使用して、バルクメールをフィルター処理するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン **をクリックし**、[ ![ ](../../media/ITPro-EAC-AddIcon.png) **新しいルールの作成**] を選択します。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。

   - [**その他のオプション**] をクリックします。

   - [次の**場合、このルールを適用**する]: 正規表現 (RegEx) または単語または語句を使用したメッセージのコンテンツを検索するには、次のいずれかの設定を構成します。

     - **件名または本文** \>**件名または本文が次のテキストパターンと一致**する: 表示される [**単語または語句の指定**] ダイアログボックスで、次のいずれかの値を入力し、[追加] アイコン**をクリックし**て、 ![ ](../../media/ITPro-EAC-AddIcon.png) すべての値を入力するまで繰り返します。

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      エントリを編集するには、エントリを選択し、[編集] [編集] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-EditIcon.png) ます。 エントリを削除するには、エントリを選択し、[削除] [削除] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ます。

       完了したら、 **[OK]** をクリックします。

     - **件名または本文** \>**件名または本文に次のいずれかの単語が含まれ**ている場合: 表示される [**単語または語句の指定**] ダイアログボックスで、次のいずれかの値を入力し、[追加] アイコンを**クリックして**、 ![ ](../../media/ITPro-EAC-AddIcon.png) すべての値を入力するまで繰り返します。

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

      エントリを編集するには、エントリを選択し、[編集] [編集] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-EditIcon.png) ます。 エントリを削除するには、エントリを選択し、[削除] [削除] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ます。

       完了したら、 **[OK]** をクリックします。

   - **次の操作を行い**ます。 [ **メッセージのプロパティを変更する**] [ \> **スパム信頼レベル (SCL) を設定**する] を選択します。 表示される [ **SCL の指定** ] ダイアログで、次のいずれかの設定を構成します。

     - メッセージを **スパム**としてマークするには、[ **6**] を選択します。 スパム対策ポリシーで verdicts **スパム** フィルター処理用に構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。

     - メッセージを **高精度のスパム** としてマークするには、[ **9**] を選択します。 迷惑メール対策ポリシーで、 **高信頼度の高いスパム** フィルター処理に対して構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**] です)。

    SCL 値の詳細については、「 [EOP」の「スパム信頼レベル (SCL)](spam-confidence-levels.md)」を参照してください。

   完了したら、[**保存**] をクリックします。

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell を使用してバルクメールをフィルター処理するメールフロールールを作成する

次の構文を使用して、1つまたは両方のメールフロールール (正規表現と単語の比較) を作成します。

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

この例では、メッセージを **スパム**として設定するために、前述したものと同じ正規表現のリストを使用する "バルクメールフィルター-RegEx" という名前の新しいルールを作成します。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

この例では、「バルクメールフィルター-単語」という名前の新しいルールを作成して、このトピックの前の部分と同じ単語リストを使用して、メッセージを **高精度のスパム**として設定します。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

バルクメールをフィルター処理するようにメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、[ **メールフロー** \> **ルール**] に移動し \> 、 \> [ **編集** ![ ] 編集アイコンをクリックして ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、を \<Rule Name\> ルールの名前に置き換え、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 外部アカウントから、語句またはテキストパターンの1つを含む、影響を受ける受信者にテストメッセージを送信し、結果を確認します。
