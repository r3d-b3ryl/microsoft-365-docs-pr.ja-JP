---
title: メールフロールールを使用して Office 365 でバルクメールをフィルター処理する
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でのメールフロールールをバルクメールフィルターに使用する方法について説明します。
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895049"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>メールフロールールを使用して Office 365 でバルクメールをフィルター処理する

Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Office 365 お客様の場合、EOP では、スパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) を使用してスキャンします。スパムおよびバルクメールの受信メッセージ (灰色のメールとも呼ばれます)。 詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

バルクメールをフィルター処理するためのその他のオプションが必要な場合は、メールフロールール (トランスポートルールとも呼ばれる) を作成して、バルクメールでよく見られるテキストパターンや語句を検索し、それらのメッセージをスパムとしてマークします。 バルクメールの詳細については、Office 365 の「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」および「[バルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。

このトピックでは、Exchange 管理センター (EAC) および PowerShell (Office 365 のお客様向け Exchange Online PowerShell) でこれらのメールフロールールを作成する方法について説明します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの Exchange Online Protection の PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- この例では、バルクメールを識別するために使用される単語とテキストパターンの一覧は完全ではありません。必要に応じて、エントリを追加および削除できます。 ただし、開始点として適しています。

- メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた*後*に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。

- 次の手順では、組織全体に対してバルクメッセージをスパムとしてマークします。 ただし、これらのルールを特定の受信者にのみ適用する別の条件を追加することができます。そのため、一部の高度な対象ユーザーに対して積極的にフィルターを適用することができます。ただし、ユーザーの残りの部分 (頻繁に使用するバルクメールを取得する場合) は影響を受けません。

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>EAC を使用して、バルクメールをフィルター処理するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン](../../media/ITPro-EAC-AddIcon.png) **をクリックし**、[**新しいルールの作成**] を選択します。 ![

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。

   - [**その他のオプション**] をクリックします。

   - [次の**場合、このルールを適用**する]: 正規表現 (RegEx) または単語または語句を使用したメッセージのコンテンツを検索するには、次のいずれかの設定を構成します。

     - **件名** \>または本文が次の**テキストパターンと一致**する場合: 表示された [**単語または語句の指定**] ダイアログボックスで、次のいずれ](../../media/ITPro-EAC-AddIcon.png)かの値を入力し、[ ![追加] アイコン**をクリックし**て、必要な回数だけ繰り返します。

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

      エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。 エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。

       完了したら、 **[OK]** をクリックします。

     - **件名または本文** \>に次**のいずれかの単語が含ま**れている場合: 表示される [**単語または語句の指定**] ダイアログボックスで、次](../../media/ITPro-EAC-AddIcon.png)のいずれかの値を入力し、[ ![追加] アイコン**をクリックし**て、必要な回数だけ繰り返します。

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

      エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。 エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。

       完了したら、 **[OK]** をクリックします。

   - **次の操作を行い**ます。 [ \> **メッセージのプロパティを変更する**] [**スパム信頼レベル (SCL) を設定**する] を選択します。 表示される [ **SCL の指定**] ダイアログで、次のいずれかの設定を構成します。

     - メッセージを**スパム**としてマークするには、[ **6**] を選択します。 スパム対策ポリシーで verdicts**スパム**フィルター処理用に構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。

     - メッセージを**高精度のスパム**としてマークするには、[ **9**] を選択します。 迷惑メール対策ポリシーで、**高信頼度の高いスパム**フィルター処理に対して構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**] です)。

    SCL 値の詳細については、「 [Office 365 のスパム信頼レベル (SCL)](spam-confidence-levels.md)」を参照してください。

   完了したら、[**保存**] をクリックします。

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a>PowerShell を使用して、バルクメールをフィルター処理するメールフロールールを作成する

次の構文を使用して、1つまたは両方のメールフロールール (正規表現と単語の比較) を作成します。

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

この例では、メッセージを**スパム**として設定するために、前述したものと同じ正規表現のリストを使用する "バルクメールフィルター-RegEx" という名前の新しいルールを作成します。

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

この例では、「バルクメールフィルター-単語」という名前の新しいルールを作成して、このトピックの前の部分と同じ単語リストを使用して、メッセージを**高精度のスパム**として設定します。

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

バルクメールをフィルター処理するようにメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、 \> [**メールフロー** \> **ルール** \> ] に移動し、[**編集]** ![編集](../../media/ITPro-EAC-EditIcon.png)アイコンをクリックして設定を確認します。

- PowerShell で、rule \<name\>をルールの名前に置き換え、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- 外部アカウントから、語句またはテキストパターンの1つを含む、影響を受ける受信者にテストメッセージを送信し、結果を確認します。
