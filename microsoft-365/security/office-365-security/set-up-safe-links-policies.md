---
title: Microsoft Defender セーフのリンク ポリシーを設定Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for microsoft Defender の セーフ リンク ポリシーとグローバル セーフ リンクの設定を表示、作成、変更、および削除する方法をOffice 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 61cb4746289a8acbdd9af7f668010604de511902
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694499"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender セーフのリンク ポリシーを設定Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 セーフリンクに関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

セーフ[リンクは、Microsoft Defender for Office 365](defender-for-office-365.md)の機能で、メール フロー内の受信電子メール メッセージの URL スキャン、および電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。 詳細については[、「Microsoft Defender セーフリンク」を参照Office 365。](safe-links.md)

リンク ポリシーに組み込みまたは既定セーフはありません。 URL のセーフを取得するには、この記事で説明するように 1 つ以上の セーフリンク ポリシーを作成する必要があります。

> [!NOTE]
> リンクの保護のグローバル設定は、セーフリンク ポリシー以外セーフ構成します。 手順については、「Microsoft Defender for セーフリンクのグローバル設定を構成する[」を参照Office 365。](configure-global-settings-for-safe-links.md)

セーフ リンク ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online PowerShell で、Exchange Online のメールボックスを持つ対象の Microsoft 365 組織、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプション) で構成できます。

リンク ポリシーの基本的なセーフは次のとおりです。

- 安全なリンク **ポリシー:** セーフ リンク保護を有効にし、リアルタイム URL スキャンを有効にし、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定し、内部メッセージのスキャンをオンにし、URL のユーザークリックを追跡するかどうかを指定し、ユーザーが元の URL へのトラフをクリックできるかどうかを指定します。
- **安全なリンクルール**: 優先度と受信者のフィルター (ポリシーが適用されるユーザー) を指定します。

> [!IMPORTANT]
> 管理者は、SafeLinks の異なる構成設定を検討する必要があります。 使用できるオプションの 1 つは、ユーザー識別可能な情報を SafeLinks に含める方法です。 この機能により *、セキュリティ Ops チームは* 、潜在的なユーザー侵害を調査し、是正措置を取り、コストのかかる侵害を制限できます。

これらの 2 つの要素の違いは、セキュリティ セーフ コンプライアンス センターでリンクポリシーを管理&ではありません。

- セーフ リンク ポリシーを作成するときに、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーを同時に作成します。
- リンク ポリシーを変更セーフ、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全なリンク ルールが変更されます。 その他の設定はすべて、関連付けられたセーフ リンク ポリシーを変更します。
- リンク ポリシーを削除セーフ、セーフ リンク ルールと関連付けられたセーフ リンク ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半Exchange Online「PowerShell またはスタンドアロン[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)を使用して セーフリンク ポリシーを構成する」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [リンク] ページに直接 **移動セーフを** 使用します <https://protection.office.com/safelinksv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - セーフ リンク ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。
  - リンク ポリシーへの読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。

  詳細については、「セキュリティ コンプライアンス センター[のアクセス](permissions-in-the-security-and-compliance-center.md)許可」および「&の[アクセス許可」を参照Exchange Online。](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  . - ビュー **専用の組織の管理** 役割グループ [](/Exchange/permissions-exo/permissions-exo#role-groups)は、Exchange Online機能への読み取り専用アクセスも提供します。

- リンク ポリシーの推奨設定についてはセーフリンク ポリシー[のセーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新しい機能は、Microsoft Defender](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加Office 365。 新しい機能が追加された場合、既存のリンク ポリシーを調整するセーフがあります。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>セキュリティ コンプライアンス センターを&リンク ポリシーセーフ作成する

セキュリティ & コンプライアンス センターでカスタム セーフ リンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [リンクの **セーフ] ページで、[** 作成] を **クリックします**。

3. [**新しいリンクセーフ] ポリシー ウィザードが** 開きます。 [ポリシーに **名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[設定]** ページで、次の設定を構成します。

   - **メッセージ内の不明な潜在的に** 悪意のある URL のアクションを選択します:[**オン**] を選択して、セーフリンク保護を有効にします。

   - **[リンク内の不明な** URL または潜在的に悪意のある URLのアクションをMicrosoft Teams: [オン] を選択して、セーフ リンクの保護を有効Teams。

   - **ファイルを指す** 疑わしいリンクやリンクに対してリアルタイム URL スキャンを適用する: この設定を選択すると、電子メール メッセージ内のリンクをリアルタイムでスキャンできます。

   - **メッセージを配信する前** に URL のスキャンが完了するのを待つ: この設定を選択すると、メッセージを配信する前にリアルタイムの URL スキャンが完了するのを待ちます。

   - **[セーフ** 組織内で送信された電子メール メッセージへのリンクを適用する: この設定を選択して、セーフ リンク ポリシーを内部送信者と内部受信者の間のメッセージに適用します。

   - **ユーザーのクリックを追跡しない**: この設定を選択しないままにして、電子メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。

   - **ユーザーに元の URL** へのクリックを許可しない : この設定を選択すると、警告ページ内の元の URL へのユーザーのクリックが [ブロックされます](safe-links.md#warning-pages-from-safe-links)。

   - **次の URL を書き換えない**: 指定された URL にアクセスし、それ以外の場合はリンクによってブロックセーフします。

     ボックスに、必要な URL または値を入力し、 をクリックします。 ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png).

     既存のエントリを削除するには、そのエントリを選択して、 ![[削除] ボタン アイコン](../../media/ITPro-EAC-DeleteIcon.png).

     エントリの構文については、「次の URL を書き換えない」リストの Entry 構文 [を参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   これらの設定の詳細については、「電子メール[](safe-links.md#safe-links-settings-for-email-messages)メッセージセーフリンクの設定」および「セーフリンクの設定」[を参照](safe-links.md#safe-links-settings-for-microsoft-teams)Microsoft Teams。

   Standard および Strict ポリシー設定の推奨値の詳細については、「リンク[ポリシー設定セーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。

   - **受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。
   - **受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。
   - **[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。

   条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。
   - 追加の値を追加するには、ボックス内の空の領域をクリックします。
   - 個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。
   - 条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。

   例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

6. 表示される **[設定の確認]** ページで、設定を確認します。 各設定で **[編集]** をクリックして変更できます。

   完了したら、 **[完了]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>セキュリティ コンプライアンス センターを&リンク ポリシーセーフ表示する

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>セキュリティ コンプライアンス センターを&リンク ポリシーセーフ変更する

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。

表示されるフライアウトで使用可能な設定は、「セキュリティ & コンプライアンス センターを使用してリンク ポリシーを作成する」セクションで説明セーフ[同](#use-the-security--compliance-center-to-create-safe-links-policies)じです。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。

### <a name="enable-or-disable-safe-links-policies"></a>リンク ポリシーを有効セーフ無効にする

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [状態] 列の値 **に注意** してください。

   - ポリシーを無効にするには、左に切り替えます。 ![ポリシーをオフにする](../../media/scc-toggle-off.png).

   - ポリシーを有効にするには、右に切り替えます。 ![ポリシーを有効にする](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>リンク ポリシーの優先度セーフ設定する

既定では、セーフリンク ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

セーフリンク ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。

> [!NOTE]
> セキュリティ コンプライアンス センター&、ポリシーを作成した後セーフリンク ポリシーの優先度のみを変更できます。 PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。

   - 優先度セーフ **0** の [リンク] ポリシーには、[優先度の下がる]**ボタンのみを** 使用できます。

   - [セーフの優先度] の値が最も低い [リンク] ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタンだけが** 使用できます。

   - リンク ポリシーが 3 つ以上セーフ場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方があります。**

4. [優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>コンプライアンス センターのセキュリティ &を使用して、リンク ポリシーセーフ削除する

1. セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。

2. [リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで **[は** い] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して、リンク ポリシーセーフ構成する

前に説明したように、セーフリンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。

PowerShell では、安全なリンク ポリシーと安全なリンク ルールの違いが明らかです。 安全なリンク ポリシーは **\* 、-SafeLinksPolicy** コマンドレットを使用して管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。

- PowerShell では、安全なリンク ポリシーを最初に作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。
- PowerShell では、安全なリンク ポリシーの設定と安全なリンク ルールを個別に変更します。
- PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell を使用してリンク ポリシーセーフ作成する

PowerShell で セーフリンク ポリシーを作成するには、次の 2 つの手順を実行します。

1. 安全なリンク ポリシーを作成します。
2. ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。

> [!NOTE]
> 
> - 新しいセーフ リンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーを割り当てできます。 安全なリンク ルールを複数の安全なリンク ポリシーに関連付けできない。
> 
> - ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しい安全なリンク ポリシーで、次の設定を構成できます。
> 
>   - 新しいポリシーを _無効として作成_ します `$false` **(New-SafeLinksRule コマンドレットで有効** )。
>   -  _\<Number\>_ **New-SafeLinksRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。
> 
> - PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>手順 1: PowerShell を使用して安全なリンク ポリシーを作成する

安全なリンク ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - _DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」リストのエントリ構文を [参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。
> 
> - **Set-SafeLinksPolicy** コマンドレットを使用して既存のセーフ リンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できる追加の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。

この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。

- 電子メール メッセージで URL のスキャンと書き換えを有効にする。
- [URL のスキャン] を [Teamsオンにする (TAP プレビューのみ)。
- クリックした URL (ファイルを指すクリックされたリンクを含む) のリアルタイム スキャンを有効にする。
- メッセージを配信する前に、URL のスキャンが完了するのを待ちます。
- 内部メッセージの URL スキャンと書き換えを有効にする。
- セーフ Links 保護に関連するユーザークリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザーのクリックが追跡されます)。
- ユーザーが元の URL をクリックしてクリックを許可しない。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

構文とパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](/powershell/module/exchange/new-safelinkspolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>手順 2: PowerShell を使用して安全なリンク ルールを作成する

安全なリンク ルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。

- ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。
- ルールは、ドメイン内のすべての受信者に contoso.com されます。
- Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。
- ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文とパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](/powershell/module/exchange/new-safelinksrule)。

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを表示する

既存の安全なリンク ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンク ポリシーの概要一覧を返します。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

構文とパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](/powershell/module/exchange/get-safelinkspolicy)。

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを表示する

既存のセーフ リンク ルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全なリンク ルールの概要一覧を返します。

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

構文とパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを変更する

PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。 コンプライアンス センターのセキュリティ セーフリンク ポリシーの名前を変更&、セーフ リンク ルールの名前を変更 _するのみです_。

PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターで使用可能な構文です ("次の [URL を](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)書き換えない" リスト)。

- 既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。
- 他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」のセクションで説明したように、安全なリンク ポリシーを作成するときに同じ設定を使用できます。

安全なリンク ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを変更する

PowerShell で安全なリンク ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存のセーフ リンク ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

安全なリンク ルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを有効または無効にする

PowerShell で安全なリンク ルールを有効または無効にすると、セーフ リンク ポリシー全体 (セーフ リンク ルールと割り当てられた安全なリンク ポリシー) が有効または無効となります。

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

構文とパラメーターの詳細については [、「Enable-SafeLinksRule」](/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](/powershell/module/exchange/disable-safelinksrule)。

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

> [!NOTE]
> 新しいルールを作成するときに優先度を設定するには **、New-SafeLinksRule** コマンドレットの Priority パラメーターを使用します。 

構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell を使用して安全なリンク ポリシーを削除する

PowerShell を使用して安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは削除されません。

PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](/powershell/module/exchange/remove-safelinkspolicy)。

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell を使用して安全なリンク ルールを削除する

PowerShell を使用して安全なリンク ルールを削除しても、対応する安全なリンク ポリシーは削除されません。

PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全なリンク ルールを削除します。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](/powershell/module/exchange/remove-safelinksrule)。

リンクがメッセージセーフ確認するには、使用可能な Microsoft Defender のレポートをOffice 365してください。 詳細については、「セキュリティ コンプライアンス センター」の[「Defender for Office 365](view-reports-for-mdo.md)レポートの表示」および「Use [Explorer」を参照&してください](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

リンク ポリシーが正常に作成、変更、または削除されたことを確認するには、セーフ手順を実行します。

- セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** \>  \> **] [ATP]**[リンク] セーフします。 ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。

- PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```