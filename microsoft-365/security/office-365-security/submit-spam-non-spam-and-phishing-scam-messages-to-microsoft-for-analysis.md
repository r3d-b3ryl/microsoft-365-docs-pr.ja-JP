---
title: 分析のためにメッセージを手動で Microsoft に送信する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'ユーザーは、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することができます。 '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032806"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>分析のためにメッセージを手動で Microsoft に送信する

> [!NOTE]
> Office 365 組織の管理者が Exchange Online メールボックスを使用している場合は、Office 365 セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。 詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。

組織内のユーザーが迷惑メール (スパム) またはフィッシングメッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスがかかることがあります。 より正確になるように、スパムフィルターを常に微調整しています。

この処理を支援するには、誤検知 (不良としてマークされた良好な電子メール)、誤検知 (無効なメールが許可されている)、および Microsoft に対するフィッシングメッセージを分析用に送信します。

> [!NOTE]
> 大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。

## <a name="submit-false-negatives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> 次の手順を使用して誤検知を報告する代わりに、Outlook および web 上の Outlook (旧称 Outlook Web App) のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。 このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。

スパムまたはフィッシングとして識別されたスパムフィルタリングを通過したメッセージを受信した場合は、そのメッセージを Microsoft スパム分析および Microsoft フィッシング分析チームに適宜送信することができます。 アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。

1. 次のいずれかの受信者を使用して、新しい空の電子メールメッセージを作成します。

   - **迷惑メール**:`junk@office365.microsoft.com`

   - **フィッシング**:`phish@office365.microsoft.com`

2. 迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグアンドドロップします。 これにより、迷惑メールまたはフィッシングメッセージは新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。

   > [!NOTE]
   > <ul><li>新しいメッセージに複数のメッセージを添付することができます。 すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</li><li>新しいメッセージの本文は空のままにします。<li></li>添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</li></ul>

3. 完了したら、[**送信**] をクリックします。

> [!TIP]
> 管理者は、スパムとして misidentified されている特定のメッセージをブロックするいくつかの方法を用意しています。 詳細については、「 [Office 365 でブロックされる送信者のリストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。

## <a name="submit-false-positives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> 次の手順を使用して誤検知を報告するのではなく、Outlook および web 上の Outlook のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。 このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。

メッセージが誤ってスパムとして識別された場合は、メッセージを Microsoft スパム分析チームに送信できます。 アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整して、メッセージを通過できるようにすることができます。

1. 受信者としての`not_junk@office365.microsoft.com`新しい空の電子メールメッセージを作成します。

2. Misidentified メッセージを新しいメッセージにドラッグアンドドロップします。 これにより、misidentified メッセージは新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。

   > [!NOTE]
   > <ul><li>新しいメッセージに複数のメッセージを添付することができます。 すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</li><li>新しいメッセージの本文は空のままにします。<li></li>添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</li></ul>

3. 完了したら、[**送信**] をクリックします。

> [!TIP]
> 管理者は、特定のメッセージがスパムフィルタリングをスキップできるようにするいくつかの方法があります。 詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft に報告されたメッセージのコピーを受信するためのメールフロールールを作成する

このトピックで説明する方法を使用して Microsoft に報告された電子メールメッセージを検索するメールフロールール (トランスポートルールとも呼ばれます) を作成し、これらのレポートされたメッセージのコピーを受信するように Bcc 受信者を構成することができます。

メールフロールールは、Exchange 管理センター (EAC) および PowerShell (Office 365 お客様の場合は Exchange Online PowerShell) で作成できます。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの Exchange Online Protection の PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。

  - [Exchange Online のメール フロー ルール (トランスポート ルール)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Exchange Online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Exchange Online でのメール フロー ルールの処理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>EAC を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン](../../media/ITPro-EAC-AddIcon.png) **をクリックし**、[**新しいルールの作成**] を選択します。 ![

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。 たとえば、Microsoft に報告される Bcc メッセージ。

   - [**その他のオプション**] をクリックします。

   - [次の**場合にこのルールを適用**する]:**受信者** \> **のアドレスに次のいずれかの単語が含まれ**ます。表示される [**単語または語句の指定**] ダイアログで、次のいずれかの値を入力し、[ ![追加] アイコン](../../media/ITPro-EAC-AddIcon.png)をクリックして、すべての値を入力するまで繰り返します。 **Add**

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。 エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。

     完了したら、 **[OK]** をクリックします。

   - **次の手順を実行**します。 [**受信者** \> **を Bcc ボックスに追加する**] を選択します。 表示されるダイアログで、追加する受信者を見つけて選択します。 完了したら、 **[OK]** をクリックします。

4. ルールを監査したり、ルールをテストしたり、特定の期間にルールをアクティブ化したり、その他の設定を行ったりするには、追加の選択を行うことができます。 ルールを適用する前に、ルールをテストすることをお勧めします。

5. 完了したら、**[保存]** をクリックします。

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>PowerShell を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する

この例では、このトピックで説明する方法を使用して Microsoft に報告された電子メールメッセージを検索し、Bcc 受信者としてユーザー laura@contoso.com および julia@contoso.com を追加する Bcc メッセージという名前の新しいメールフロールールを作成します。

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

レポートされたメッセージのコピーを受信するメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。

- EAC で、 \> [**メールフロー** \> **ルール** \> ] に移動し、[**編集]** ![編集](../../media/ITPro-EAC-EditIcon.png)アイコンをクリックして設定を確認します。

- PowerShell で、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- テストメッセージをレポート電子メールアドレスのいずれかに送信し、結果を確認します。
