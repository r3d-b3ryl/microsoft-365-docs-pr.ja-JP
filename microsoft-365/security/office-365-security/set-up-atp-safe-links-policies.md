---
title: Office 365 ATP で安全なリンクに関するポリシーを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 Advanced Threat Protection (ATP) での安全なリンクポリシーおよびグローバルな安全リンクの設定を表示、作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: b6b013364fc763450ac8bef0d06bd2fad8d55daa
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350721"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a>Office 365 ATP で安全なリンクに関するポリシーを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook の Safelinks に関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

「安全なリンク」とは、 [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) の機能の1つで、メールフローで受信電子メールメッセージの url スキャンを行い、電子メールメッセージやその他の場所で url とリンクの確認をクリックする時間を示します。 詳細については、「 [Office 365 ATP」の「安全なリンク](atp-safe-links.md)」を参照してください。

組み込みまたは既定の安全なリンクポリシーはありません。 Url の安全なリンクスキャンを取得するには、この記事で説明されているように、1つ以上の安全なリンクポリシーを作成する必要があります。

セキュリティで保護されたリンクポリシーを構成するには、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する資格のある Microsoft 365 組織用の Exchange Online PowerShell、exchange Online メールボックスを使用しない組織の場合はスタンドアロン EOP PowerShell、Office 365 ATP アドオンサブスクリプション) を構成できます。

安全リンクポリシーの基本的な要素は次のとおりです。

- 「**安全なリンク」ポリシー**: [安全なリンクの保護] をオンにして、リアルタイムの URL スキャンを有効にし、メッセージを配信する前にリアルタイムスキャンが完了するのを待機するかどうかを指定し、ユーザーが url をスキャンするかどうかを指定し、ユーザーが元の url をクリックできるようにするかどうか
- "**安全なリンク" ルール**: 優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ & コンプライアンスセンターで安全なリンクポリシーを管理する場合、これらの2つの要素の違いは明白ではありません。

- 安全なリンクポリシーを作成する場合、実際には、両方の同じ名前を使用して、安全なリンクルールと関連する安全なリンクポリシーを作成しています。
- 安全なリンクポリシーを変更する場合、名前、優先度、有効または無効に関連する設定、および受信者フィルターは、安全なリンクのルールを変更します。 他のすべての設定は、関連する安全なリンクポリシーを変更します。
- 安全なリンクポリシーを削除すると、"安全なリンク" ルールと、それに関連する安全なリンクポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事で後述 [する「Exchange Online の powershell またはスタンドアロンの EOP powershell を使用して安全なリンクポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 」セクションを参照してください。

> [!NOTE]
> 「安全なリンク」ポリシーの **外部** にある安全なリンク保護のためのグローバル設定を構成します。 手順については、「 [Office 365 ATP で安全なリンクのグローバル設定を構成する](configure-global-settings-for-safe-links.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な **リンク** ] ページに直接移動するには、を使用 <https://protection.office.com/safelinksv2> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- 安全なリンクポリシーを表示、作成、変更、および削除するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**。

- 「安全なリンク」ポリシーの推奨設定については、「 [安全なリンクポリシー設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)」を参照してください。

- 新規または更新されたポリシーが適用されるまで最大30分かかります。

- [新機能は ATP に継続的に追加](office-365-atp.md#new-features-in-office-365-atp)されています。 新機能が追加されたときに、既存の安全なリンクポリシーを調整する必要がある場合があります。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを作成する

セキュリティ & コンプライアンスセンターでカスタムの安全なリンクポリシーを作成すると、両方に同じ名前を使用して、安全なリンクルールと関連する安全なリンクポリシーが作成されます。

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **安全なリンク** ] ページで、[ **作成**] をクリックします。

3. **新しい安全なリンクポリシー**ウィザードが開きます。 [ **ポリシーに名前** をつける] ページで、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される [ **設定** ] ページで、次の設定を構成します。

   - [**メッセージ内の不明な悪意のある url に対するアクション** **:] を**選択します。

   - [**メッセージ内の不明な悪意のある url に対するアクション** **: オン] または**[既定値を選択] のまま**にします**。

   - [**ファイルを参照する不審なリンクおよびリンクのリアルタイム URL スキャンを適用**する]: 電子メールメッセージ内のリンクをリアルタイムでスキャンできるようにするには、この設定を選択します。

   - **メッセージを配信する前に、url のスキャンが完了するのを待機**します。メッセージを配信する前に、リアルタイムの url のスキャンが完了するのを待機するには、この設定を選択します。

   - [**組織内で送信された電子メールメッセージに安全なリンクを適用**する]: 内部送信者と内部受信者の間のメッセージに安全なリンクポリシーを適用するには、この設定を選択します。

   - [**ユーザーのクリックを追跡**しない]: この設定をオフのままにすると、ユーザーが電子メールメッセージ内の url をクリックできるようになります。

   - **[ユーザーが元の url に移動できない**ようにする]: この設定を選択すると、ユーザーが [警告ページ](atp-safe-links.md#warning-pages-from-safe-links)で元の url に移動するのをブロックします。

   - **次の url を書き換えないで**ください。それ以外の場合は、安全なリンクによってブロックされる url へのアクセスが許可されます。

     ボックスに、必要な URL または値を入力して、[ ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png).

     既存のエントリを削除するには、そのエントリを選択して [ ![[ボタンの削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png).

     エントリの構文については、 [「次の url を書き換えないでください」リストのエントリの構文](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)を参照してください。

   これらの設定の詳細については、「 [Microsoft Teams の](atp-safe-links.md#safe-links-settings-for-microsoft-teams)電子メールメッセージと安全なリンクの設定」[の「安全なリンクの設定](atp-safe-links.md#safe-links-settings-for-email-messages)」を参照してください。

   標準および厳密なポリシー設定に推奨される値については、「 [安全なリンクポリシー設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)」を参照してください。

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

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>セキュリティ & コンプライアンスセンターを使用して、安全なリンクポリシーを表示する

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを変更する

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[ **ポリシーの編集**] をクリックします。

スライドインで使用可能な設定は、「 [セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを作成する](#use-the-security--compliance-center-to-create-safe-links-policies) 」セクションで説明されているものと同じです。

ポリシーを有効または無効にしたり、ポリシーの優先順位を設定したりするには、以下のセクションを参照してください。

### <a name="enable-or-disable-safe-links-policies"></a>安全なリンクポリシーを有効または無効にする

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **状態** ] 列の値に注目してください。

   - ポリシーを無効にするには、左に切り替えます。 ![ポリシーをオフにする](../../media/scc-toggle-off.png).

   - ポリシーを有効にするには、右に切り替えます。 ![ポリシーを有効にする](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>安全なリンクポリシーの優先度を設定する

既定では、「安全なリンク」ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、古いポリシーよりも優先度が低いです)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

「安全なリンク」ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0になります)。

**注**: セキュリティ & コンプライアンスセンターでは、安全なリンクのポリシーを作成した後にのみ、優先度を変更できます。 PowerShell では、安全なリンクルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[利用可能な優先度] ボタンをクリックします。

   - **優先度**の値が**0**の安全なリンクポリシーには、[**優先度を下げる**] ボタンのみが表示されます。

   - 最も低い **優先度** の値 (たとえば **3**) を持つ安全なリンクポリシーには、[ **優先度を上げる** ] ボタンだけが使用できます。

   - 3つ以上の安全なリンクポリシーがある場合、優先度の最大値と最小値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できます。

4. [優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを削除する

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。

2. [ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。

3. [ポリシーの詳細] が表示されたら、[ **ポリシーの削除**] をクリックし、表示される警告ダイアログで [ **はい** ] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なリンクポリシーを構成する

前述したように、安全なリンクポリシーは、安全なリンクポリシーと安全なリンクのルールで構成されます。

PowerShell では、安全なリンクのポリシーと安全なリンクのルールの違いが明らかです。 「安全なリンク」ポリシーは、 ** \* -SafeLinksPolicy**コマンドレットを使用して管理し、 ** \* -SafeLinksRule**コマンドレットを使用して安全なリンクルールを管理します。

- PowerShell では、まず安全なリンクポリシーを作成し、次に、ルールが適用されるポリシーを識別する安全なリンクルールを作成します。
- PowerShell では、"安全なリンク" ポリシーと "安全なリンク" ルールの設定を個別に変更します。
- 「安全なリンク」ポリシーを PowerShell から削除しても、対応する安全なリンクのルールは自動的には削除されません。また、その逆も同様です。

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell を使用して安全なリンクポリシーを作成する

PowerShell で安全なリンクポリシーを作成するには、2つの手順からなるプロセスがあります。

1. 安全なリンクポリシーを作成します。
2. ルールを適用する安全なリンクポリシーを指定する安全なリンクルールを作成します。

 **注**:

- 新しい安全なリンクルールを作成し、関連付けられていない既存の安全なリンクポリシーをそのルールに割り当てることができます。 安全なリンクのルールは、複数の安全なリンクポリシーに関連付けることはできません。

- ポリシーを作成するまでは、セキュリティ & コンプライアンスセンターで利用できない PowerShell の新しい安全なリンクポリシーで、次の設定を構成できます。

  - 新しいポリシーを無効として_Enabled_作成し `$false` ます ( **SafeLinksRule**コマンドレットでは有効)。
  - SafeLinksRule コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _\<Number\>_ )。 **New-SafeLinksRule**

- PowerShell で作成した新しい安全なリンクポリシーは、そのポリシーを安全なリンクルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>手順 1: PowerShell を使用して安全なリンクポリシーを作成する

安全なリンクポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**注**:

- 上書き _Rewriteurls_ パラメーターに使用するエントリの構文の詳細については、 [「次の url を書き換えないでください」リストのエントリの構文](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)を参照してください。

- **SafeLinksPolicy**コマンドレットを使用して_既存の安全_なリンクポリシーを変更するときに使用できるその他の構文については、この記事で後述[する「PowerShell を使用して安全なリンクポリシーを変更](#use-powershell-to-modify-safe-links-policies)する」セクションを参照してください。

この例では、次の値を持つ Contoso All という名前の安全なリンクポリシーを作成します。

- 電子メールメッセージで URL のスキャンとリライトを有効にします。
- Teams での URL スキャンを有効にします ([プレビューのみ] をタップします)。
- クリックされた Url のリアルタイムスキャンを有効にします。これには、[ファイル] をクリックするリンクも含まれています。
- URL のスキャンが完了するのを待ってから、メッセージを配信します。
- 内部メッセージの URL スキャンおよびリライトを有効にします。
- 「安全なリンクの保護に関連するユーザークリックを追跡する ( _このパラメーターは使用して_ いません。既定値は $false、ユーザークリックが追跡されることを意味します)。
- ユーザーが元の URL に移動することを許可しません。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>手順 2: PowerShell を使用して安全なリンクルールを作成する

安全なリンクルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、次の条件を満たす Contoso All という名前の安全なリンクルールを作成します。

- ルールは Contoso All という名前の安全なリンクポリシーに関連付けられています。
- ルールは、contoso.com ドメイン内のすべての受信者に適用されます。
- _Priority_パラメーターを使用していないので、既定の優先度が使用されます。
- ルールが有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)」を参照してください。

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell を使用して安全なリンクポリシーを表示する

既存の安全なリンクのポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンクポリシーの要約リストを返します。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

この例では、Contoso 重役という名前の安全なリンクポリシーの詳細情報を返します。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell を使用して安全なリンクルールを表示する

既存の安全リンクルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンクのルールの要約リストが返されます。

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

この例では、Contoso 重役という名前の安全なリンクルールの詳細情報を返します。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)」を参照してください。

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell を使用して安全なリンクポリシーを変更する

PowerShell で安全なリンクポリシーの名前を変更することはできません ( **SafeLinksPolicy** コマンドレットに _Name_ パラメーターがありません)。 セキュリティ & コンプライアンスセンターで安全なリンクポリシーの名前を変更する場合は、安全なリンクの _ルール_の名前のみを変更する必要があります。

PowerShell で安全なリンクポリシーを変更するための追加の考慮事項は、 ["次の url をリライトしない](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)" と_いうパラメーターで_使用可能な構文です。

- 既存のエントリを置換する値を追加するには、次の構文を使用し `"Entry1","Entry2,..."EntryN"` ます。
- 他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

それ以外の場合は、この記事の「 [手順 1: PowerShell を使用して安全リンクポリシーを作成する](#step-1-use-powershell-to-create-a-safe-links-policy) 」セクションで説明されているように、安全なリンクポリシーを作成する場合にも同じ設定を使用できます。

安全なリンクポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell を使用して安全なリンクルールを変更する

PowerShell の安全なリンクのルールを変更するときに使用できない設定は、無効にされたルールを作成できる _有効_ なパラメーターです。 既存の安全リンクルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、この記事の「 [手順 2: PowerShell を使用して安全なリンクのルールを作成する](#step-2-use-powershell-to-create-a-safe-links-rule) 」で説明されているように、同じ設定を使用できます。

安全なリンクルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell を使用して安全なリンクルールを有効または無効にする

PowerShell で安全なリンクルールを有効または無効にすると、安全なリンクポリシー全体 (安全なリンク規則と、割り当てられた安全なリンクポリシー) が有効または無効になります。

PowerShell で安全なリンクルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の安全なリンクのルールを無効にします。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 」および「 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell を使用して安全なリンクルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全なリンクのルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**注**: 作成時に新しいルールの優先度を設定するには、代わりに**SafeLinksRule**コマンドレットで_priority_パラメーターを使用します。

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)」を参照してください。

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell を使用して安全なリンクポリシーを削除する

PowerShell を使用して安全なリンクポリシーを削除しても、対応する安全なリンクのルールは削除されません。

PowerShell で安全なリンクポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンクポリシーを削除します。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)」を参照してください。

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell を使用して安全なリンクルールを削除する

PowerShell を使用して安全なリンクルールを削除しても、対応する安全なリンクポリシーは削除されません。

PowerShell で安全なリンクルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンクのルールを削除します。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)」を参照してください。

安全なリンクがメッセージをスキャンしていることを確認するには、利用可能な Advanced Threat Protection レポートを確認します。 詳細については、「 [View reports For Office 365 ATP](view-reports-for-atp.md) 」および「 [Security & コンプライアンスセンターのエクスプローラーを使用する](threat-explorer.md)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全なリンクポリシーが正常に作成、変更、または削除されたことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。 ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。 詳細を表示するには、一覧からポリシーを選択し、スライドアウトして詳細を表示します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
