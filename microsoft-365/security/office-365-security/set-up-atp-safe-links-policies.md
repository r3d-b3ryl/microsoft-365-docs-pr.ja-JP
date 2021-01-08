---
title: Microsoft Defender で安全なリンク ポリシーを Office 365 用にセットアップする
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
description: 管理者は、Microsoft Defender for Office 365 で安全なリンクポリシーとグローバルな安全なリンクの設定を表示、作成、変更、削除する方法について説明します。
ms.openlocfilehash: ef83d0dba1de03aa2b36384474791783e926059f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780534"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender で安全なリンク ポリシーを Office 365 用に設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。 If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

「安全なリンク」は [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信メール メッセージの URL スキャンや、電子メール メッセージや他の場所での URL とリンクのクリック検証の時間を提供します。 詳細については [、Microsoft Defender の 「安全なリンク」を参照してください。Office 365](atp-safe-links.md).

組み込みまたは既定の安全なリンク ポリシーはありません。 URL の安全なリンクのスキャンを取得するには、この記事で説明するように、1 つ以上の安全なリンク ポリシーを作成する必要があります。

> [!NOTE]
> 安全なリンクの保護のグローバル設定は、安全なリンク **ポリシーの外部** で構成します。 手順については、「Microsoft Defender で安全なリンクのグローバル設定を構成する (Office [365)」](configure-global-settings-for-safe-links.md)を参照してください。

安全なリンクポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプションの場合)。

安全なリンク ポリシーの基本的な要素は次のとおりです。

- 安全なリンクの **ポリシー:** 安全なリンク保護を有効にする、リアルタイムの URL スキャンを有効にする、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定する、内部メッセージのスキャンを有効にする、URL をクリックしたユーザーを追跡するかどうかを指定する、元の URL に対してユーザーが trough をクリックできるかどうかを指定する。
- **安全なリンクルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ/コンプライアンス センターで安全なリンク ポリシーを管理する場合、これら 2 つの要素の違い&明らかではありません。

- 安全なリンク ポリシーを作成する場合、実際には安全なリンク ルールと関連付けられた安全なリンク ポリシーを、両方に同じ名前を使用して同時に作成します。
- 安全なリンク ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全なリンク ルールが変更されます。 その他のすべての設定では、関連付けられている安全なリンク ポリシーが変更されます。
- 安全なリンク ポリシーを削除すると、安全なリンク ルールと関連付けられている安全なリンク ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、後の [「Exchange Online PowerShell またはスタンドアロンの EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) を使用して安全なリンク ポリシーを構成する」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [安全なリンク] ページ **に直接移動するには** 、次の値を使用します <https://protection.office.com/safelinksv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する前に、アクセス許可を割り当てる必要があります。
  - 安全なリンク ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの Organization **Management** または **Security Administrator** 役割グループのメンバーであり、Exchange Online の **Organization Management** 役割グループのメンバーである必要があります。
  - 安全なリンク ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。

  詳細については、「Exchange Online [のセキュリティ/コンプライアンス センター&](permissions-in-the-security-and-compliance-center.md) アクセス許可」 [を参照してください](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 安全なリンク ポリシーの推奨設定については、「安全なリンクのポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新しい機能は、Microsoft Defender](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加され、Office 365 です。 新機能が追加された場合は、既存の安全なリンク ポリシーを調整する必要がある場合があります。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムの安全なリンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [安全な **リンク] ページで** 、[作成] を **クリックします**。

3. 安全 **なリンクの新しいポリシー** ウィザードが開きます。 [ポリシー **に名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[設定** ] ページで、次の設定を構成します。

   - **メッセージ内の悪意のある可能性** のある不明な URL に対するアクションを選択します。[ **オン** ] を選択すると、電子メール メッセージ内のリンクに対する安全なリンク保護が有効になります。

   - **Microsoft Teams 内の不明な URL** または悪意のある可能性のある URL に対するアクションを選択します。[ **オン** ] を選択すると、Teams のリンクに対する安全なリンク保護が有効になります。

   - **疑わしいリンク** やファイルを指すリンクに対してリアルタイム URL スキャンを適用する: 電子メール メッセージ内のリンクのリアルタイム スキャンを有効にするには、この設定を選択します。

   - **メッセージを配信する前** に URL のスキャンが完了するのを待つ: この設定を選択すると、リアルタイム URL スキャンが完了してからメッセージが配信されます。

   - **組織内で送信される電子** メール メッセージに安全なリンクを適用する : この設定を選択すると、内部送信者と内部受信者の間のメッセージに安全なリンク ポリシーが適用されます。

   - **ユーザークリックを追跡しない**: この設定をオフのままにして、メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。

   - **ユーザーがクリックして元** の URL にアクセスできない: この設定を選択すると、ユーザーが警告ページ内の元の URL にクリックスルー [されるのをブロックします](atp-safe-links.md#warning-pages-from-safe-links)。

   - **次の URL を書き換え** ない: 安全なリンクによってブロックされる指定された URL へのアクセスを許可します。

     ボックスに必要な URL または値を入力し、 ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png).

     既存のエントリを削除するには、そのエントリを選択し、 ![[削除] ボタン アイコン](../../media/ITPro-EAC-DeleteIcon.png).

     エントリ構文については、「次の URL を書き換えない」の一覧のエントリ [構文を参照してください](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   これらの設定の詳細については、「電子メール メッセージの安全なリンクの設定 [」および](atp-safe-links.md#safe-links-settings-for-email-messages) 「Microsoft Teams の安全なリンクの [設定」を参照してください](atp-safe-links.md#safe-links-settings-for-microsoft-teams)。

   Standard および Strict ポリシー設定の推奨値の詳細については、「安全なリンクのポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用] の下の条件を **選択します**。

   - **受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。
   - **受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。
   - **[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。

   条件を選択すると、対応するドロップダウンが [Any **of these] ボックスと一緒に表示** されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。
   - 値を追加するには、ボックス内の空の領域をクリックします。
   - 個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。
   - 条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   追加の条件を追加するには、[条件の追加] **をクリック** し、[適用する条件] の下の残りの値 **を選択します**。

   例外を追加するには、[条件の追加] をクリックし、[次の場合を除く] で例外 **を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

6. 表示される **[設定の確認** ] ページで、設定を確認します。 各設定で **[編集]** をクリックして変更できます。

   完了したら、 **[完了]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを表示する

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを変更する

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。

3. 表示されたポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。

表示されるフライアウトで使用可能な設定は、「セキュリティ/コンプライアンス センターを使用して安全なリンク ポリシーを作成する」セクション& [説明されている設定と同](#use-the-security--compliance-center-to-create-safe-links-policies) じです。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、以下のセクションを参照してください。

### <a name="enable-or-disable-safe-links-policies"></a>安全なリンク ポリシーを有効または無効にする

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [状態] 列の値 **に注意** してください。

   - ポリシーを無効にするには、左に切り替えます。 ![ポリシーをオフにする](../../media/scc-toggle-off.png).

   - ポリシーを有効にするには、右に切り替えます。 ![ポリシーを有効にする](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>安全なリンク ポリシーの優先度を設定する

既定では、安全なリンク ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

安全なリンク ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。

**注**: セキュリティ/コンプライアンス センター&、安全なリンク ポリシーの優先度は、作成後にのみ変更できます。 PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。

3. ポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。

   - 優先度の値が **0** の安全なリンク **ポリシー** では、[優先度を下がる]**ボタン** しか使用できません。

   - 優先度の値が最も低い安全なリンク **ポリシー** ( **たとえば、3)** には、[優先度の引き上げ] **ボタン** しか使用できません。

   - 3 つ以上の安全なリンク ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方を使用** できます。

4. [優先度 **の引き上げ****] または [優先度の下げ**] をクリックして、[優先度] の **値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを削除する

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。

2. [安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。

3. 表示されたポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで [はい] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なリンク ポリシーを構成する

前述のように、安全なリンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。

PowerShell では、安全なリンク ポリシーと安全なリンクルールの違いは明白です。 **\* -SafeLinksPolicy** コマンドレットを使用して安全なリンク ポリシーを管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。

- PowerShell では、最初に安全なリンク ポリシーを作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。
- PowerShell では、安全なリンク ポリシーと安全なリンクルールの設定を個別に変更します。
- PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンクルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを作成する

PowerShell で安全なリンク ポリシーを作成するには、次の 2 つの手順を実行します。

1. 安全なリンク ポリシーを作成します。
2. ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。

 **注**:

- 新しい安全なリンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーをそのルールに割り当てできます。 安全なリンク ルールは、複数の安全なリンク ポリシーに関連付け設定できます。

- ポリシーを作成するまで、セキュリティ/コンプライアンス センターでは使用できない新しい &安全リンク ポリシーに関する次の設定を構成できます。

  - 無効な新しいポリシーを作成します `$false` **(New-SafeLinksRule コマンドレットで有効**)。
  -  _\<Number\>_ **New-SafeLinksRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>手順 1: PowerShell を使用して安全なリンク ポリシーを作成する

安全なリンク ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**注**:

- _DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」の一覧のエントリ構文を [参照してください](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

- **Set-SafeLinksPolicy** コマンドレットを使用して既存の安全なリンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できるその他の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。

この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。

- 電子メール メッセージで URL のスキャンと書き換えを有効にする。
- Teams で URL スキャンを有効にする (TAP プレビューのみ)。
- クリックされた URL のリアルタイム スキャン (ファイルをポイントするクリックされたリンクを含む) を有効にする。
- メッセージを配信する前に URL のスキャンが完了するのを待ちます。
- 内部メッセージの URL のスキャンと書き換えを有効にする。
- 安全なリンク保護に関連するユーザー クリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザークリックが追跡されます)。
- ユーザーがクリックして元の URL にアクセスできない。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

構文およびパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>手順 2: PowerShell を使用して安全なリンク ルールを作成する

安全なリンク ルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。

- ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。
- ルールは、ドメイン内のすべての受信者にcontoso.comされます。
- _Priority_ パラメーターを使用していないので、既定の優先度が使用されます。
- ルールは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文およびパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを表示する

既存の安全なリンク ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンク ポリシーの要約リストを返します。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを表示する

既存の安全なリンク ルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンク ルールの要約リストを返します。

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

この例では、Contoso Executives という名前の安全なリンク ルールの詳細情報を返します。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを変更する

PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ/コンプライアンス センターで安全なリンク ポリシーの名前を変更&、安全なリンクルールの名前を変更 _するのみです_。

PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターに使用できる構文です (「次の [URL](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)を書き換えない」の一覧)。

- 既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。
- 他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」セクションで説明したように、安全なリンク ポリシーを作成する場合と同じ設定を使用できます。

安全なリンク ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを変更する

PowerShell で安全なリンク ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。 既存の安全なリンク ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。

安全なリンク ルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを有効または無効にする

PowerShell で安全なリンク ルールを有効または無効にすると、安全なリンクポリシー全体 (安全なリンクルールと割り当てられた安全なリンク ポリシー) を有効または無効にできます。

PowerShell で安全なリンク ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の安全なリンク ルールを無効にします。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Enable-SafeLinksRule」](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全なリンク ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**注**: 新しいルールを作成するときに優先度を設定するには、代わりに **New-SafeLinksRule** コマンドレットの _Priority_ パラメーターを使用します。

構文およびパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを削除する

PowerShell を使用して安全なリンク ポリシーを削除する場合、対応する安全なリンクルールは削除されません。

PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを削除する

PowerShell を使用して安全なリンク ルールを削除する場合、対応する安全なリンク ポリシーは削除されません。

PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンク ルールを削除します。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。

安全なリンクがメッセージをスキャンしているのを確認するには、365 レポートで利用可能な Microsoft Defender Office確認します。 詳細については、「Defender [for Office 365](view-reports-for-atp.md) のレポートを表示する」および「セキュリティ/コンプライアンス センターでエクスプローラー [&参照してください](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全なリンク ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。

- セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。 ポリシーの一覧、状態の値、 **および優先度** の値を **確認** します。 詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して、設定 \<Name\> を確認します。

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
