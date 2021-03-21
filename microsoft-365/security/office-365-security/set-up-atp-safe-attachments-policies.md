---
title: Microsoft Defender で安全な添付ファイル ポリシーを設定する (Office 365)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 電子メール内の悪意のあるファイルから組織を保護するために安全な添付ファイル ポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48e373dc95aaa65d0f436f99208d926477aacd6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918716"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender で安全な添付ファイル ポリシーを設定する (Office 365)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook で添付ファイルのスキャンに関する情報を探しているホーム ユーザーの場合は [、「Advanced Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全な添付ファイルは [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、Exchange [Online Protection (EOP)](anti-malware-protection.md)でマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認します。 詳細については [、「Safe Attachments in Microsoft Defender for microsoft Defender for Office 365」を参照してください](atp-safe-attachments.md)。

組み込みまたは既定の安全な添付ファイル ポリシーはありません。 電子メール メッセージの添付ファイルの安全な添付ファイルのスキャンを取得するには、この記事で説明するように、1 つ以上の安全な添付ファイル ポリシーを作成する必要があります。

安全な添付ファイル ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ対象となる Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell、ただし Defender for Office 365 アドオン サブスクリプション) で構成できます。

安全な添付ファイル ポリシーの基本的な要素は次のとおりです。

- **安全な** 添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定した電子メール アドレスに送信するかどうか、および安全な添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。
- **安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ コンプライアンス センターで安全な添付ファイルポリシーを管理する場合、これら 2 つの要素の違いは&ではありません。

- 安全な添付ファイル ポリシーを作成する場合、両方に同じ名前を使用して、実際に安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。
- 安全な添付ファイル ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。 その他の設定はすべて、関連付けられた安全な添付ファイル ポリシーを変更します。
- 安全な添付ファイル ポリシーを削除すると、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半の [「Exchange Online PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) またはスタンドアロン EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する」セクションを参照してください。

> [!NOTE]
> [安全な添付ファイル] 設定のグローバル設定領域で、安全な添付ファイル ポリシーに依存しない機能を構成します。 手順については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) の安全な添付ファイルを有効にする」および [「Microsoft 365 E5](safe-docs.md)の安全なドキュメント」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [安全な添付ファイル] ページ **に直接移動するには** 、 を使用します <https://protection.office.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - 安全な添付ファイル ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Onlineの組織の管理役割グループのメンバーである必要があります。  
  - 安全な添付ファイル ポリシーへの読み取り専用アクセスでは、セキュリティ コンプライアンスセンターのグローバルリーダーまたはセキュリティ リーダーの役割グループ&必要があります。

  詳細については、「セキュリティ コンプライアンス [センターのアクセス許可」と「exchange Online &アクセス](permissions-in-the-security-and-compliance-center.md) 許可 [」を参照してください](/exchange/permissions-exo/permissions-exo)。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 安全な添付ファイル ポリシーの推奨設定については、「安全な添付ファイルの [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>セキュリティ コンプライアンス センター&使用して安全な添付ファイル ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムの安全な添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [安全な **添付ファイル] ページで** 、[作成] を **クリックします**。

3. [ **新しい安全な添付ファイル] ポリシー ウィザード** が開きます。 [ポリシーに **名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[設定** ] ページで、次の設定を構成します。

   - **[安全な添付ファイル] 不明なマルウェアの応答**: 次のいずれかの値を選択します。

     - **Off**: 通常、この値はお勧めしません。
     - **モニター**
     - **ブロック**: これは既定値で、Standard および Strict の事前設定されたセキュリティ ポリシーで [推奨される値です](preset-security-policies.md)。
     - **Replace**
     - **動的配信 (プレビュー機能)**

     これらの値については、「安全な添付ファイル [ポリシー設定」で説明します](atp-safe-attachments.md#safe-attachments-policy-settings)。

   - **添付ファイル** を次の電子メール アドレスに送信する:アクション値 [ブロック]、[監視]、または [置換] の場合は、[リダイレクトを有効にする] を選択して、指定した内部または外部の電子メール アドレスにマルウェアの添付ファイルを含むメッセージを送信して、分析と調査を行います。 

     標準ポリシーと厳密なポリシー設定の推奨事項は、リダイレクトを有効にしてください。 詳細については、「安全な添付ファイル [の設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

   - **添付ファイルのマルウェア** スキャンが時間切れまたはエラーが発生した場合は、上記の選択を適用します。安全な添付ファイルのスキャンが完了できない場合でも、メッセージに対して安全な添付ファイルの不明なマルウェア応答で指定されたアクションが実行されます。 このオプションを選択した場合は、常に [リダイレクトの有効化 **] を選択します**。 それ以外の場合、メッセージが失われる可能性があります。

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>セキュリティ コンプライアンス センターを&して、安全な添付ファイル ポリシーを表示する

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>セキュリティ コンプライアンス センターを&安全な添付ファイル ポリシーを変更する

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。

表示されるフライアウトで使用可能な設定は、「セキュリティ コンプライアンス センターを使用して安全な添付ファイル&作成する」セクション [で説明されている設定と同](#use-the-security--compliance-center-to-create-safe-attachments-policies) じです。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。

### <a name="enable-or-disable-safe-attachments-policies"></a>安全な添付ファイル ポリシーを有効または無効にする

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [状態] 列の値 **に注意** してください。

   - トグルを左に移動する ![ポリシーをオフにする](../../media/scc-toggle-off.png) をクリックしてポリシーを無効にします。

   - トグルを右に移動する ![ポリシーを有効にする](../../media/scc-toggle-on.png) をクリックしてポリシーを有効にします。

### <a name="set-the-priority-of-safe-attachments-policies"></a>安全な添付ファイル ポリシーの優先度を設定する

既定では、安全な添付ファイル ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

安全な添付ファイル ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。

**注**: セキュリティ &コンプライアンス センターでは、安全な添付ファイル ポリシーを作成した後にのみ、優先度を変更できます。 PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。

   - 優先度の値が **0** の **安全な添付** ファイル ポリシーには、[優先度の下がり]**ボタンしか** 使用できません。

   - 優先度の値が最も低い安全な添付ファイル **ポリシー** ( **たとえば、3)** には、[優先度の引き上げ] **ボタンのみを** 使用できます。

   - 3 つ以上の安全な添付ファイル ポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方があります。**

4. [優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>セキュリティ コンプライアンス センター&使用して安全な添付ファイル ポリシーを削除する

1. セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。

2. [安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。

3. 表示されるポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで **[は** い] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する

前述したように、安全な添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。

PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いが明らかです。 **\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。

- PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。
- PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。
- PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを作成する

PowerShell で安全な添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。

1. 安全な添付ファイル ポリシーを作成します。
2. ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。

 **注**:

- 新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーを割り当てできます。 安全な添付ファイル ルールを複数の安全な添付ファイル ポリシーに関連付けできない。

- ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しい安全な添付ファイル ポリシーに対して、次の設定を構成できます。
  - 新しいポリシーを無効として作成 _します_ `$false` **(New-SafeAttachmentRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-SafeAttachmentRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しい安全な添付ファイル ポリシーは、ポリシーを安全な添付ファイル ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する

安全な添付ファイル ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。

- セーフ ドキュメント スキャンによってマルウェアが含まれていると見つかったメッセージをブロックします _(Action_ パラメーターは使用していないので、既定値はです `Block` )。
- リダイレクトが有効になっていると、マルウェアが含まれていると検出されたメッセージは、分析と調査のために sec-ops@contoso.com に送信されます。
- 安全な添付ファイルのスキャンが使用できない場合、またはエラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用していないので、既定値はです `$true` )。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

構文とパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/new-safeattachmentpolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>手順 2: PowerShell を使用して安全な添付ファイル ルールを作成する

安全な添付ファイル ルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、Contoso All という名前の安全な添付ファイル ルールを次の条件で作成します。

- このルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられている。
- ルールは、ドメイン内のすべての受信者に contoso.com されます。
- Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。
- ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文とパラメーターの詳細については [、「New-SafeAttachmentRule」を参照してください](/powershell/module/exchange/new-safeattachmentrule)。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを表示する

既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全な添付ファイル ポリシーの概要一覧を返します。

```PowerShell
Get-SafeAttachmentPolicy
```

この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/get-safeattachmentpolicy)。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを表示する

既存の安全な添付ファイル ルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、すべての安全な添付ファイル ルールの概要リストを返します。

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

この例では、Contoso Executives という名前の安全な添付ファイル ルールの詳細情報を返します。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-SafeAttachmentRule」を参照してください](/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを変更する

PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ コンプライアンス センターで安全な添付ファイル ポリシー&変更する場合は、安全な添付ファイル ルールの名前を変更 _する必要があります_。

それ以外の場合は、この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成するときに同じ設定を使用できます。

安全な添付ファイル ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを変更する

PowerShell で安全な添付ファイル ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイルルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

安全な添付ファイル ルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを有効または無効にする

PowerShell で安全な添付ファイル ルールを有効または無効にすると、安全な添付ファイル ポリシー (安全な添付ファイル ルールと割り当てられた安全な添付ファイル ポリシー) 全体が有効または無効となります。

PowerShell で安全な添付ファイル ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ルールを無効にします。

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Enable-SafeAttachmentRule」](/powershell/module/exchange/enable-safeattachmentrule) および [「Disable-SafeAttachmentRule」を参照してください](/powershell/module/exchange/disable-safeattachmentrule)。

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全な添付ファイル ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**注**: 新しいルールを作成するときに優先度を設定するには **、New-SafeAttachmentRule** コマンドレットの Priority パラメーターを使用します。 

構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを削除する

PowerShell を使用して安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは削除されません。

PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/remove-safeattachmentpolicy)。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを削除する

PowerShell を使用して安全な添付ファイル ルールを削除しても、対応する安全な添付ファイル ポリシーは削除されません。

PowerShell で安全な添付ファイル ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ルールを削除します。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-SafeAttachmentRule」を参照してください](/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全な添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。

- セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。 ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

安全な添付ファイルがメッセージをスキャンしているのを確認するには、365 レポートで使用可能な Defender Office確認します。 詳細については、「View [reports for Defender for Office 365」](view-reports-for-atp.md) および「Use Explorer in the Security & [コンプライアンス センター」を参照してください](threat-explorer.md)。