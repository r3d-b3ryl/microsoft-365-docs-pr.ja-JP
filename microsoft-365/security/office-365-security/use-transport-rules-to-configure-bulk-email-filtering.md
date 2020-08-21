---
title: メール フロー ルールを使用してバルク メールをフィルター処理する
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
description: 管理者は、メール フロー ルール (トランスポート ルール) を使用して Exchange Online Protection (EOP) でバルク メールを識別してフィルター処理する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826755"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>メール フロー ルールを使用して EOP でバルク メールをフィルタリングする

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、スパムまたはバルク メール (グレー メールとしても知られています) の受信メッセージをスキャンします。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

バルク メールをフィルター処理する他のオプションを使用する場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、バルク メールでよく見られるテキスト パターンや語句を検索し、それらのメッセージにスパムのマークを付けることができます。 バルク メールの詳細については、迷惑メールとバルク メールの違 [い](what-s-the-difference-between-junk-email-and-bulk-email.md) 、および EOP のバルク メール [(BCL) の違いを参照してください](bulk-complaint-level-values.md)。

このトピックでは、Exchange 管理センター (EAC) および PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用 Exchange Online PowerShell; Exchange Online メールボックスを使用している組織用のスタンドアロン EOP PowerShell) でこれらのメール フロー ルールを作成する方法について説明します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する場合は、あかじにアクセス許可を割り当てる必要があります。

  - Exchange Online では、Exchange Online の機能アクセス許可の「メール [フロー」エントリを参照してください](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)。
  
  - スタンドアロン EOP では、トランスポート ルールの役割が必要です。この役割は、既定で OrganizationManagement、ComplianceManagement、および RecordsManagement の役割に割り当てられます。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- Exchange Online の EAC を開くには、「Exchange Online [の Exchange 管理センター」を参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。 スタンドアロン EOP の EAC を開くには、「スタンドアロン EOP [の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online でのメール フロー ルールとスタンドアロン EOP のメール フロー ルールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメール フロー ルールでの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- 例のバルク メールを識別するための単語とテキスト パターンのリストは、すべてが拡張的ではありません。必要に応じて、エントリの追加や削除を実行できます。 それでも、それらは出点として優れており、どうならいかもしれないわけです。

- メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた*後*に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。

- 以下の手順では、バルク メッセージを組織全体のスパムとしてマークします。 ただし、別の条件を追加することでこれらのルールを特定の受信者にのみ適用できるため、少数の高い対象ユーザーに集中的なフィルター処理を使用できます。それに対しては、他のユーザー (受信するもののほとんどが登録したバルク メール) には影響を与えません。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC を使用してバルク メールをフィルター処理するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: わかりやすい一意のルールの名前を入力します。

   - [**その他のオプション**] をクリックします。

   - **正規表現**(RegEx) または単語または語句を使用してメッセージ内のコンテンツを検索するには、次のいずれかの設定を構成します。

     - **件名または本文** \>**次のテキスト パターンと一致する**件名または本文。表示**される [単語または語句を**指定してください] ダイアログで、次の値のいずれかを入力して [**追加** ![ ] アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返されます。

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完了したら、 **[OK]** をクリックします。

     - **件名または本文** \>**件名または本文に次の単語のいずれかを含めます**。表示される [単語または語**句**の指定] ダイアログで、次の値のいずれかを入力して [**追加]** ![ アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返されます。

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

      エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。 エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。

       完了したら、 **[OK]** をクリックします。

   - **次の手順**を **行います。メッセージプロパティを** \> **変更すると、SCL (Spam Confidence Level) が設定されます**。 表示される **SCL の** 指定ダイアログで、以下のいずれかの設定を構成します。

     - メッセージをスパムとしてマーク **するには、6**を **選択します**。 スパム対策ポリシーでスパム フィルター **の確認について** 構成したアクションは、メッセージに適用されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。

     - メッセージに高信頼 **スパムのマークを付け、9** を選択 **します**。 スパム対策ポリシーで **高** 精度スパム対策フィルターの確認に構成したアクションが、そのメッセージに適用されます (既定値は **[迷惑メール フォルダーにメッセージを移動] です**)。

    SCL 値の詳細については、EOP の [Spam Confidence Level (SCL) を参照してください](spam-confidence-levels.md)。

   完了したら、[保存] をクリック **します。**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>PowerShell を使用してバルク メールをフィルター処理するメール フロー ルールを作成する

次の構文を使用して、1 つまたは両方のメール フロー ルール (正規表現と単語) を作成します。

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

この例では、メッセージをスパムとして設定するために、このトピックで前述した正規表現の同じリストを使用する「Bulk email filtering - RegEx」という名前の新しいルールを **作成します**。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

この例では、メッセージを「高信頼スパム」として設定するために、このトピックで前述した単語のリストと同じものを使用する「バルク メール フィルター - 語 **句」という名前の新しいルールを作成します**。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

バルク メールをフィルター処理するようにメール フロー ルールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、[メール フロー ルール]**に移動し** \> **Rules** \> 、[編集] アイコン \> をクリック**Edit** ![ して ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。

- PowerShell で、ルールの \<Rule Name\> 名前を置き換え、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 外部アカウントから、影響を受ける受信者にテスト メッセージ (語句またはテキスト パターンのいずれか 1 つを含む) を送信し、結果を確認します。
