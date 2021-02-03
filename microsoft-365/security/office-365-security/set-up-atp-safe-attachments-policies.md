---
title: Microsoft Defender で安全な添付ファイル ポリシーを Office 365 用にセットアップする
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
description: 安全な添付ファイル ポリシーを定義して、電子メール内の悪意のあるファイルから組織を保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084615"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender で安全な添付ファイル ポリシーを Office 365 用にセットアップする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。 If you're a home user looking about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

「安全な添付ファイル」は、Exchange [Online Protection (EOP)](anti-malware-protection.md)のマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認する[、Microsoft Defender for Office 365](office-365-atp.md)の機能です。 詳細については [、「Microsoft Defender の安全な添付ファイル」で Office 365](atp-safe-attachments.md)を参照してください。

組み込みまたは既定の安全な添付ファイル ポリシーはありません。 電子メール メッセージの添付ファイルの安全な添付ファイル のスキャンを取得するには、この記事で説明するように、1 つ以上の安全な添付ファイル ポリシーを作成する必要があります。

安全な添付ファイル ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Defender for Office 365 アドオン サブスクリプションの場合)。

安全な添付ファイル ポリシーの基本的な要素は次のとおりです。

- **安全** な添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定された電子メール アドレスに送信するかどうか、および安全な添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。
- **安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ/コンプライアンス センターで安全な添付ファイル ポリシーを管理する場合、これら 2 つの要素の違い&明らかではありません。

- 安全な添付ファイル ポリシーを作成する場合、実際には両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。
- 安全な添付ファイル ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。 その他のすべての設定では、関連付けられている安全な添付ファイル ポリシーが変更されます。
- 安全な添付ファイル ポリシーを削除すると、安全な添付ファイル ルールと関連付けられている安全な添付ファイル ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、後の [「Exchange Online PowerShell またはスタンドアロンの EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) を使用して安全な添付ファイル ポリシーを構成する」を参照してください。

> [!NOTE]
> 安全な添付ファイルの設定のグローバル設定領域では、安全な添付ファイル ポリシーに依存しない機能を構成します。 手順については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) の安全な添付ファイルと [Microsoft 365 E5](safe-docs.md)の安全なドキュメントを有効にする」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [安全な添付ファイル] **ページに直接移動するには** 、次のコマンドを使用します <https://protection.office.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する前に、アクセス許可を割り当てる必要があります。
  - 安全な添付ファイル ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの Organization **Management** または **Security Administrator** 役割グループのメンバーであり、Exchange Online の **Organization Management** 役割グループのメンバーである必要があります。
  - 安全な添付ファイル ポリシーに読み取り専用でアクセスするには、セキュリティ/コンプライアンスセンターのグローバル閲覧者またはセキュリティ閲覧者の役割グループの&必要があります。

  詳細については、「Exchange Online [のセキュリティ/コンプライアンス センター&](permissions-in-the-security-and-compliance-center.md) アクセス許可」 [を参照してください](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 安全な添付ファイル ポリシーの推奨設定については、「安全な添付ファイルの [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムの安全な添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [安全な **添付ファイル] ページで** 、[作成] を **クリックします**。

3. 安全 **な添付ファイルの新しいポリシー** ウィザードが開きます。 [ポリシー **に名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[設定** ] ページで、次の設定を構成します。

   - **「安全な添付ファイル」の不明なマルウェアの応答**: 次のいずれかの値を選択します。

     - **オフ**: 通常、この値はお勧めしません。
     - **モニター**
     - **Block**: これは既定値であり、Standard および Strict の既定のセキュリティ ポリシーの推奨 [値です](preset-security-policies.md)。
     - **Replace**
     - **動的配信 (プレビュー機能)**

     これらの値については、「安全な添付ファイル [」ポリシー設定で説明されています](atp-safe-attachments.md#safe-attachments-policy-settings)。

   - 添付ファイルを次の電子メール アドレスに送信します。アクションの値が  **Block、Monitor、** または Replace の場合は、[リダイレクトを有効にする] を選択して、マルウェアの添付ファイルを含むメッセージを、分析と調査のために指定された内部または外部の電子メール アドレスに送信できます。

     標準ポリシーと厳密なポリシー設定では、リダイレクトを有効にしてください。 詳細については、「安全な添付ファイル [の設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

   - **添付ファイルのマルウェア** スキャンがタイム アウトまたはエラーが発生した場合は、上記の選択を適用します。「安全な添付ファイル」のスキャンが完了できない場合でも、メッセージに対して「安全な添付ファイル」の不明なマルウェア応答によって指定されたアクションが実行されます。 このオプションを選択した場合は、常に [有効なリダイレクト] **を選択します**。 そうしないと、メッセージが失われる可能性があります。

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを表示する

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。

   ポリシーの詳細がフライアウトに表示される

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを変更する

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。

3. 表示されたポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。

表示されるフライアウトで使用可能な設定は、「セキュリティ/コンプライアンス センターを使用して安全な添付ファイル ポリシーを作成する」セクション&説明 [されている設定と同](#use-the-security--compliance-center-to-create-safe-attachments-policies) じです。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、以下のセクションを参照してください。

### <a name="enable-or-disable-safe-attachments-policies"></a>安全な添付ファイル ポリシーを有効または無効にする

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [状態] 列の値 **に注意** してください。

   - トグルを左に移動する ![ポリシーをオフにする](../../media/scc-toggle-off.png) をクリックしてポリシーを無効にします。

   - トグルを右に移動する ![ポリシーを有効にする](../../media/scc-toggle-on.png) をクリックしてポリシーを有効にしてください。

### <a name="set-the-priority-of-safe-attachments-policies"></a>安全な添付ファイル ポリシーの優先度を設定する

既定では、安全な添付ファイル ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

安全な添付ファイル ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。

**注**: セキュリティ/コンプライアンス センター&、安全な添付ファイル ポリシーの優先度は、作成後にのみ変更できます。 PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。

3. ポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。

   - 優先度の値が **0****の安全** な添付ファイル ポリシーには、[優先度を下く]**ボタン** しか使用できません。

   - 優先度の値が最も低い安全な添付ファイル ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタン** しか使用できません。

   - 3 つ以上の安全な添付ファイル ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方を使用** できます。

4. [優先度 **の引き上げ** ] または **[優先度の下げ** ] をクリックして、[優先度] の **値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを削除する

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。

2. [安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。

3. 表示されたポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで [はい] をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する

前述のように、安全な添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。

PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いは明白です。 **\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。

- PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。
- PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。
- PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを作成する

PowerShell で安全な添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。

1. 安全な添付ファイル ポリシーを作成します。
2. ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。

 **注**:

- 新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーをそのルールに割り当てできます。 安全な添付ファイル ルールは、複数の安全な添付ファイル ポリシーに関連付け設定できます。

- ポリシーを作成するまで、セキュリティ/コンプライアンス センターでは使用できない新しい安全な添付ファイル ポリシーに関する次&設定を構成できます。
  - 新しいポリシーを無効な状態 _で作成_ `$false` します **(New-SafeAttachmentRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-SafeAttachmentRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しい安全な添付ファイル ポリシーは、そのポリシーを安全な添付ファイル ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する

安全な添付ファイル ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。

- 安全なドキュメント のスキャンによってマルウェアが含まれていると検出されたメッセージをブロックします _(Action_ パラメーターは使用しません。既定値は次のとおりです `Block` )。
- リダイレクトが有効にされ、マルウェアが含まれていると検出されたメッセージは、分析と調査のためにsec-ops@contoso.comに送信されます。
- 安全な添付ファイルのスキャンが使用できない場合、またはエラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用しません。既定値は次のとおりです `$true` )。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

構文およびパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>手順 2: PowerShell を使用して安全な添付ファイル ルールを作成する

安全な添付ファイル ルールを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、Contoso All という名前の安全な添付ファイル ルールを次の条件で作成します。

- ルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられている。
- ルールは、ドメイン内のすべての受信者にcontoso.comされます。
- _Priority_ パラメーターを使用していないので、既定の優先度が使用されます。
- ルールは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文およびパラメーターの詳細については [、「New-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを表示する

既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全な添付ファイル ポリシーの要約リストを返します。

```PowerShell
Get-SafeAttachmentPolicy
```

この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

構文およびパラメーターの詳細については [、「Get-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを表示する

既存の安全な添付ファイルルールを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべての安全な添付ファイル ルールの要約リストを返します。

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

構文およびパラメーターの詳細については [、「Get-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを変更する

PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ & コンプライアンス センターで安全な添付ファイル ポリシーの名前を変更する場合は、安全な添付ファイル ルールの名前を変更 _する必要があります_。

それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成する場合と同じ設定を使用できます。

安全な添付ファイル ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを変更する

PowerShell で安全な添付ファイル ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。 既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイル ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。

安全な添付ファイル ルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを有効または無効にする

PowerShell で安全な添付ファイル ルールを有効または無効にすると、安全な添付ファイル ポリシー全体 (安全な添付ファイルルールと割り当てられた安全な添付ファイル ポリシー) を有効または無効にできます。

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

構文およびパラメーターの詳細については [、「Enable-SafeAttachmentRule」](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) および [「Disable-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)。

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

**注**: 新しいルールを作成するときに優先度を設定するには、代わりに **New-SafeAttachmentRule** コマンドレットの _Priority_ パラメーターを使用します。

構文およびパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを削除する

PowerShell を使用して安全な添付ファイル ポリシーを削除する場合、対応する安全な添付ファイルルールは削除されません。

PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを削除する

PowerShell を使用して安全な添付ファイル ルールを削除する場合、対応する安全な添付ファイル ポリシーは削除されません。

PowerShell で安全な添付ファイル ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ルールを削除します。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

安全な添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。

- セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。 ポリシーの一覧、状態の値、 **および優先度** の値を **確認** します。 詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。

- Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して、設定 \<Name\> を確認します。

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

安全な添付ファイルがメッセージをスキャンしているのを確認するには、365 レポートの利用可能な Defender Office確認します。 詳細については、「Defender for [Office 365](view-reports-for-atp.md) のレポートを表示する」と「セキュリティ/コンプライアンス センターでエクスプローラー [&参照してください](threat-explorer.md)。
