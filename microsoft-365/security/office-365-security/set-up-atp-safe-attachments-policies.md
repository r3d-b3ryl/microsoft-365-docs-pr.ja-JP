---
title: Office 365 ATP で安全な添付ファイルに関するポリシーを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 電子メールで悪意のあるファイルから組織を保護する安全な添付ファイルポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6794cf72afdb94e587e06319f87a406521ad2710
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350381"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a>Office 365 ATP で安全な添付ファイルに関するポリシーを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、 [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md)を使用しているビジネスお客様を対象としています。 Outlook で添付ファイルのスキャンに関する情報を探しているホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

「安全な添付ファイル」は、 [Exchange Online protection (EOP) でマルウェア対策保護](anti-malware-protection.md)によってスキャンされた後、受信者に配信される前に、仮想環境を使用して受信電子メールメッセージの添付ファイルをチェックする、 [Office 365 Advanced THREAT Protection (ATP)](office-365-atp.md)の機能です。 詳細については、「 [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)」を参照してください。

組み込みまたは既定の安全な添付ファイルポリシーはありません。 電子メールメッセージの添付ファイルの安全な添付ファイルのスキャンを取得するには、この記事で説明されているように、1つ以上の安全な添付ファイルポリシーを作成する必要があります。

セキュリティで保護された添付ファイルのポリシーを構成するには、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスを持つ対象の Microsoft 365 組織用の Exchange Online PowerShell、exchange Online メールボックスを持たない組織の場合はスタンドアロンの EOP PowerShell、および Office 365 ATP アドオンサブスクリプション) を使用します。

安全添付ファイルポリシーの基本的な要素は次のとおりです。

- **安全添付ファイルポリシー**: 不明なマルウェアの検出のアクション、マルウェアの添付ファイル付きのメッセージを指定された電子メールアドレスに送信するかどうか、および安全な添付ファイルのスキャンを完了できない場合にメッセージを配信するかどうかを指定します。
- **安全な添付ファイルルール**: 優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ & コンプライアンスセンターで安全な添付ファイルポリシーを管理する場合、この2つの要素の違いは明白ではありません。

- 安全添付ファイルポリシーを作成する場合、実際には、両方に同じ名前を使用して、安全な添付ファイルルールと関連する安全添付ファイルポリシーを同時に作成しています。
- 安全添付ファイルポリシーを変更する場合、名前、優先度、有効または無効に関連する設定、および受信者フィルターは、安全な添付ファイルルールを変更します。 他のすべての設定は、関連する安全添付ファイルポリシーを変更します。
- 安全添付ファイルポリシーを削除すると、安全な添付ファイルルールと、それに関連付けられた安全添付ファイルポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事で後述 [する「Exchange Online の powershell またはスタンドアロンの EOP powershell を使用して安全な添付ファイルポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 」セクションを参照してください。

> [!NOTE]
> [安全な添付ファイル] 設定の [グローバル設定] 領域では、安全な添付ファイルポリシーに依存しない機能を構成します。 手順については、「 [microsoft 365 E5](safe-docs.md)の「 [SharePoint、OneDrive、Microsoft Teams および安全なドキュメントの ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な **添付ファイル** ] ページに直接移動するには、を使用 <https://protection.office.com/safeattachmentv2> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 安全な添付ファイルポリシーを表示、作成、変更、削除するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**。

- 「安全な添付ファイル」ポリシーの推奨設定については、「安全な添付 [ファイルの設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)」を参照してください。

- 新規または更新されたポリシーが適用されるまで最大30分かかります。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全添付ファイルポリシーを作成する

セキュリティ & コンプライアンスセンターでのカスタムの安全な添付ファイルポリシーの作成両方の同じ名前を使用して、安全な添付ファイルルールと関連する安全添付ファイルポリシーを同時に作成します。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **安全な添付ファイル** ] ページで、[ **作成**] をクリックします。

3. [ **安全な添付ファイルポリシーの新規作成** ] ウィザードが開きます。 [ **ポリシーに名前** をつける] ページで、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される [ **設定** ] ページで、次の設定を構成します。

   - **安全な添付ファイルの不明なマルウェア応答**: 次のいずれかの値を選択します。

     - **Off**: 通常、この値は推奨されていません。
     - **モニター**
     - [**ブロック**]: これは既定値であり、標準および厳密な設定済みの[セキュリティポリシー](preset-security-policies.md)で推奨される値です。
     - **Replace**
     - **動的配信 (プレビュー機能)**

     これらの値については、「 [安全な添付ファイルのポリシー設定](atp-safe-attachments.md#safe-attachments-policy-settings)」で説明します。

   - **添付ファイルを次の電子メールアドレスに送信**します。操作の値 **ブロック**、 **監視**、または **置換**の場合は、[ **リダイレクトの有効化** ] を選択して、マルウェアの添付ファイルを含むメッセージを、指定した内部または外部の電子メールアドレスに送信して分析および調査することができます。

     標準および厳密なポリシー設定に関する推奨事項は、リダイレクトを有効にすることです。 詳細については、「 [安全な添付ファイルの設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)」を参照してください。

   - **マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用**します。安全な添付ファイルのスキャンが完了していなくても、メッセージに対して [ **不明なマルウェア応答** があります。 [ **有効なリダイレクト**] を選択した場合は、常にこのオプションを選択します。 そうしないと、メッセージが失われる可能性があります。

   完了したら、**[次へ]** をクリックします。

5. 表示される [ **適用先** ] ページで、ポリシーが適用される内部の受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [ **条件の追加] を**クリックします。 表示されるドロップダウンで、[適用済みの **場合**] の条件を選択します。

   - **受信者は**次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。
   - **受信者が次のメンバーの**場合: 組織内の1つまたは複数のグループを指定します。
   - **[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。

   条件を選択すると、対応するドロップ **ダウンボックスが** 表示されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。
   - その他の値を追加するには、ボックスの空の領域をクリックします。
   - 個々のエントリを削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。
   - 条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。

   別の条件を追加するには、[ **条件の追加** ] をクリックし、[ **適用**時] で残りの値を選択します。

   例外を追加するには、[ **条件の追加** ] をクリックし、 **Except if**で例外を選択します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

6. 表示される [ **設定の確認** ] ページで、設定を確認します。 各設定で [ **編集** ] をクリックして、変更を行うことができます。

   完了したら、 **[完了]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>セキュリティ & コンプライアンスセンターを使用して、安全な添付ファイルポリシーを表示する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **安全な添付ファイル** ] ページで、一覧からポリシーを選択してクリックします (チェックボックスをオンにしないでください)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全添付ファイルポリシーを変更する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **安全な添付ファイル** ] ページで、一覧からポリシーを選択してクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[ **ポリシーの編集**] をクリックします。

スライドインで使用可能な設定は、「 [セキュリティ & コンプライアンスセンターを使用して安全添付ファイルポリシーを作成する](#use-the-security--compliance-center-to-create-safe-attachments-policies) 」セクションに記載されている設定と同じです。

ポリシーを有効または無効にしたり、ポリシーの優先順位を設定したりするには、以下のセクションを参照してください。

### <a name="enable-or-disable-safe-attachments-policies"></a>安全添付ファイルポリシーを有効または無効にする

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **状態** ] 列の値に注目してください。

   - トグルを左に移動する ![ポリシーをオフにする](../../media/scc-toggle-off.png) ポリシーを無効にします。

   - トグルを右に移動する ![ポリシーを有効にする](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ポリシーを有効にします。

### <a name="set-the-priority-of-safe-attachments-policies"></a>安全な添付ファイルポリシーの優先度を設定する

既定では、[安全な添付ファイル] ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

「安全な添付ファイル」ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0です)。

**注**: セキュリティ & コンプライアンスセンターでは、安全な添付ファイルのポリシーの作成後にのみ、優先度を変更できます。 PowerShell では、安全な添付ファイルルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **安全な添付ファイル** ] ページで、一覧からポリシーを選択してクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[利用可能な優先順位] ボタンをクリックします。

   - **優先度**の値が**0**の安全な添付ファイルポリシーには、[**優先度を下げる**] ボタンのみが表示されます。

   - 最も低い **優先度** の値 (たとえば **3**) を持つ安全な添付ファイルのポリシーには、[ **優先度を上げる** ] ボタンだけが使用できます。

   - 3つ以上の安全な添付ファイルポリシーを持っている場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できる

4. [優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全添付ファイルポリシーを削除する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。

2. [ **安全な添付ファイル** ] ページで、一覧からポリシーを選択してクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[ **ポリシーの削除**] をクリックし、表示される警告ダイアログで [ **はい** ] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online の PowerShell またはスタンドアロンの EOP PowerShell を使用して、安全な添付ファイルのポリシーを構成する

前述したように、安全な添付ファイルポリシーは、安全な添付ファイルポリシーと安全な添付ファイルルールで構成されます。

PowerShell では、安全な添付ファイルのポリシーと安全な添付ファイルの規則の違いが明らかです。 ** \* -Safeattachmentpolicy**コマンドレットを使用して、安全な添付ファイルポリシーを管理し、 ** \* -new-safeattachmentrule**コマンドレットを使用して安全な添付ファイルルールを管理します。

- PowerShell では、まず安全な添付ファイルポリシーを作成し、次に、ルールが適用されるポリシーを識別する安全な添付ファイルルールを作成します。
- PowerShell では、安全な添付ファイルポリシーと安全な添付ファイルルールの設定を個別に変更します。
- 安全な添付ファイルのポリシーを PowerShell から削除しても、対応する安全な添付ファイルルールは自動的には削除されません。また、その逆も同様です。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell を使用して安全添付ファイルポリシーを作成する

PowerShell での安全な添付ファイルポリシーの作成は、次の2つの手順からなるプロセスです。

1. 安全添付ファイルポリシーを作成します。
2. ルールを適用する安全な添付ファイルポリシーを指定する安全な添付ファイルルールを作成します。

 **注**:

- 新しい安全な添付ファイルルールを作成して、既存の関連付けられていない安全な添付ファイルポリシーをそれに割り当てることができます。 安全な添付ファイルルールは、複数の安全な添付ファイルポリシーに関連付けることはできません。

- ポリシーを作成するまで、セキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しい安全な添付ファイルポリシーでは、次の設定を構成できます。
  - 新しいポリシーを無効として_Enabled_作成し `$false` ます ( **new-safeattachmentrule**コマンドレットでは有効)。
  - New-safeattachmentrule コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _\<Number\>_ )。 **New-SafeAttachmentRule**

- PowerShell で作成した新しい安全な添付ファイルポリシーは、そのポリシーを安全な添付ファイルルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>手順 1: PowerShell を使用して安全添付ファイルポリシーを作成する

安全添付ファイルポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

この例では、次の値を使用して Contoso All という名前の安全な添付ファイルポリシーを作成します。

- マルウェアを含んでいることが検出されたメッセージを安全なドキュメントスキャンでブロックする ( _Action_ パラメーターは使用していません。既定値はです `Block` )。
- リダイレクトが有効になっており、マルウェアが含まれていることが検出されたメッセージは、分析および調査のために sec-ops@contoso.com に送信されます。
- 安全な添付ファイルのスキャンができない場合、またはエラーが発生した場合は、メッセージを配信しません ( _Actiononerror_ パラメーターは使用していません。既定値はです `$true` )。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

構文およびパラメーターの詳細については、「 [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>手順 2: PowerShell を使用して安全な添付ファイルルールを作成する

安全な添付ファイルルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、次の条件で Contoso All という名前の安全な添付ファイルルールを作成します。

- ルールは Contoso All という名前の安全な添付ファイルポリシーに関連付けられています。
- ルールは、contoso.com ドメイン内のすべての受信者に適用されます。
- _Priority_パラメーターを使用していないので、既定の優先度が使用されます。
- ルールが有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイルポリシーを表示する

既存の安全添付ファイルポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全な添付ファイルポリシーの要約リストが返されます。

```PowerShell
Get-SafeAttachmentPolicy
```

この例では、Contoso 重役という名前の安全な添付ファイルポリシーの詳細情報を返します。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

構文およびパラメーターの詳細については、「 [取得-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)」を参照してください。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを表示する

既存の安全添付ファイルルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全な添付ファイルルールの要約リストが返されます。

```PowerShell
Get-SafeAttachmentRule
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

この例では、Contoso 重役という名前の安全な添付ファイルルールの詳細情報を返します。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイルポリシーを変更する

PowerShell で安全な添付ファイルポリシーの名前を変更することはできません ( **Set-SafeAttachmentPolicy** コマンドレットに _Name_ パラメーターがありません)。 セキュリティ & コンプライアンスセンターで安全な添付ファイルポリシーの名前を変更する場合は、安全な添付ファイル _ルール_の名前のみを変更することになります。

それ以外の場合は、この記事の「 [手順 1: PowerShell を使用して安全な添付ファイルポリシーを作成する](#step-1-use-powershell-to-create-a-safe-attachment-policy) 」の説明に従って、安全な添付ファイルポリシーを作成するときに同じ設定を使用できます。

安全添付ファイルポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については、「 [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)」を参照してください。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを変更する

PowerShell で安全な添付ファイルルールを変更しても利用できない唯一の設定は、無効にされたルールを作成できる _有効_ なパラメーターです。 既存の安全添付ファイルルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、この記事で前述した「 [手順 2: PowerShell を使用して安全な添付ファイルルールを作成する](#step-2-use-powershell-to-create-a-safe-attachment-rule) 」に記載されている方法で、同じ設定を使用できます。

安全な添付ファイルルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを有効または無効にする

PowerShell で安全な添付ファイルルールを有効または無効にすると、安全な添付ファイルのポリシー (安全な添付ファイルルールおよび割り当てられた安全な添付ファイルポリシー) 全体が有効または無効になります。

PowerShell で安全な添付ファイルルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の安全な添付ファイルルールを無効にします。

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 」および「 [Disable-new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全な添付ファイルルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**注**: 作成時に新しいルールの優先度を設定するには、代わりに**new-safeattachmentrule**コマンドレットで_priority_パラメーターを使用します。

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイルポリシーを削除する

PowerShell を使用して安全添付ファイルポリシーを削除しても、対応する安全な添付ファイルルールは削除されません。

PowerShell で安全な添付ファイルポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイルポリシーを削除します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [削除-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)」を参照してください。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを削除する

PowerShell を使用して安全な添付ファイルルールを削除しても、対応する安全添付ファイルポリシーは削除されません。

PowerShell で安全な添付ファイルルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイルルールを削除します。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [new-safeattachmentrule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全な添付ファイルポリシーが正常に作成、変更、または削除されたことを確認するには、次のいずれかの手順を実行します。

- セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動します。 ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。 詳細を表示するには、一覧からポリシーを選択し、スライドアウトして詳細を表示します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

安全な添付ファイルがメッセージをスキャンしていることを確認するには、利用可能な Advanced Threat Protection レポートを確認します。 詳細については、「 [View reports For Office 365 ATP](view-reports-for-atp.md) 」および「 [Security & コンプライアンスセンターのエクスプローラーを使用する](threat-explorer.md)」を参照してください。
