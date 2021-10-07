---
title: Microsoft Defender セーフの添付ファイル ポリシーをセットアップOffice 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: メール内の悪意のあるファイルセーフ組織を保護するために、添付ファイルポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2eefdbdfd9121bdc778425fe63ea35d3f97a4adc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196443"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender セーフの添付ファイル ポリシーをセットアップOffice 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) をご利用の法人のお客様を対象としています。 ホーム ユーザーが Outlookファイルの添付ファイルのスキャンに関する情報を探している場合は[、「Advanced Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

セーフ添付ファイルは[、Exchange Online Protection (EOP)](anti-malware-protection.md)でマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認する Microsoft Defender for [Office 365](whats-new-in-defender-for-office-365.md)の機能です。 詳細については、「Microsoft [Defender セーフ添付ファイル」を参照Office 365。](safe-attachments.md)

組み込みまたは既定の添付ファイル ポリシーセーフはありません。 電子メール セーフの添付ファイルスキャンを取得するには、この記事で説明するように 1 つ以上セーフ添付ファイル ポリシーを作成する必要があります。

セーフ 添付ファイル ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online PowerShell で、Exchange Online 内のメールボックスを持つ適格な Microsoft 365 組織に対して構成できます。スタンドアロンの EOP PowerShell は組織に対して構成できます。Exchange Onlineが、Defender を使用して、Office 365サブスクリプションを作成します)。

添付ファイル ポリシーのセーフは次のとおりです。

- 安全 **な** 添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定した電子メール アドレスに送信するかどうか、および セーフ 添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。
- **安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、セーフの添付ファイル ポリシーを管理するときにMicrosoft 365 Defenderされません。

- セーフ添付ファイル ポリシーを作成するときに、両方に同じ名前を使用して、実際に安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。
- [添付ファイル] セーフ変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。 その他の設定はすべて、関連付けられた安全な添付ファイル ポリシーを変更します。
- 添付ファイル ポリシーをセーフすると、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半Exchange Online「PowerShell またはスタンドアロン[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)を使用して添付ファイルポリシーセーフ構成する」を参照してください。

> [!NOTE]
> [添付ファイル] 設定のセーフ領域で、添付ファイル ポリシーに依存しない機能セーフ構成します。 手順については、「セーフ ドキュメントの[SharePoint、OneDrive、Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)および セーフ 添付ファイルを有効にする」を[参照Microsoft 365 E5。](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 [添付ファイル] ページに **直接移動セーフを** 使用します <https://security.microsoft.com/safeattachmentv2> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可が必要です。
  - セーフ 添付ファイル ポリシーを作成、変更、および削除するには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。 
  - 添付ファイル ポリシーへの読み取りセーフアクセスするには、ポータルでグローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー Microsoft 365 Defender必要があります。

  詳細については、「Microsoft 365 Defender[](permissions-microsoft-365-security-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。

  **注意**:

  - Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 添付ファイル ポリシーの推奨設定セーフ、添付ファイルの設定[セーフ参照してください](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>添付ファイル ポリシー Microsoft 365 Defender作成するには、セーフポータルを使用します。

Microsoft 365 Defender ポータルでカスタム セーフ 添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付ファイル **セーフ] ページで**、[作成] ![ アイコンをクリックします。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. ポリシー ウィザードが開きます。 [ポリシーに **名前を付け] ページ** で、次の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[ユーザーとドメイン] ページ** で、ポリシーが適用される内部受信者 (受信者の条件) を特定します。
   - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。 ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. [設定]**設定** で、次の設定を構成します。

   - **セーフ添付ファイルの不明なマルウェアの応答**: 次のいずれかの値を選択します。
     - **Off**: 通常、この値はお勧めしません。
     - **モニター**
     - **ブロック**: これは既定値で、Standard および Strict の事前設定されたセキュリティ ポリシーで [推奨される値です](preset-security-policies.md)。
     - **Replace**
     - **動的配信 (プレビュー機能)**

     これらの値については、「添付ファイルポリシー[セーフ」で説明します](safe-attachments.md#safe-attachments-policy-settings)。

   - **検疫ポリシー**: [添付ファイル] ([ブロック]、[置換]、または [動的配信]) によって検疫セーフに適用される検疫ポリシー **を選択します**。  検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

     空白の値は、既定の検疫ポリシーが使用セーフします。 [添付ファイル] ポリシーを後セーフ編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

   - 検出された添付ファイルを含むメッセージをリダイレクト **する**: [リダイレクトを有効にする]を選択した場合は、[ブロック、監視、または置換された添付ファイルを含むメール アドレスを指定して指定した電子メール アドレス] ボックスに電子メール アドレスを指定して、分析と調査のためにマルウェア添付ファイルを含むメッセージを送信できます。

     標準ポリシーと厳密なポリシー設定の推奨事項は、リダイレクトを有効にしてください。 詳細については、「添付ファイルの[設定セーフ参照してください](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

   - スキャンが **完了できない**(タイムアウトまたはエラー) 場合は、セーフ 添付ファイル検出応答を適用します。セーフ 添付ファイルの不明なマルウェア応答で指定されたアクションは **、セーフ** 添付ファイルのスキャンが完了できない場合でもメッセージに対して実行されます。 このオプションを選択した場合は、常に [リダイレクトを有効にする] **を** 選択し、マルウェアの添付ファイルを含むメッセージを送信する電子メール アドレスを指定します。 それ以外の場合、メッセージが失われる可能性があります。

   完了したら、**[次へ]** をクリックします。

6. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

7. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>添付ファイル ポリシー Microsoft 365 Defenderを表示するには、セーフポータルを使用します。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付 **セーフ] ページ** で、ポリシーの一覧に次のプロパティが表示されます。
   - **名前**
   - **状態**
   - **優先度**

3. 名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>添付ファイル ポリシー Microsoft 365 Defender変更するには、セーフポータルを使用します。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の前[](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)の「Microsoft 365 Defenderを使用して添付セーフポリシーを作成する」を参照してください。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。

### <a name="enable-or-disable-safe-attachments-policies"></a>添付ファイル ポリシーのセーフまたは無効にする

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-safe-attachments-policies"></a>添付ファイル ポリシーのセーフ設定する

既定では、セーフ添付ファイル ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

セーフ添付ファイル ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。

**注**: このポータルMicrosoft 365 Defender、添付ファイル ポリシーの優先度を変更できるのは、セーフ後のみです。 PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。 ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシー詳細のフライアウトの上部に、現在の優先度の値とポリシーの数に基づいて[優先度の増加] または [優先度の下げ] が表示されます。
   - 優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。
   - 優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。
   - 3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>添付ファイル ポリシー Microsoft 365 Defender削除するには、セーフポータルを使用します。

1. [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。

2. [添付 **セーフ] ページ** で、ポリシーの名前をクリックして、一覧からカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して添付ファイル ポリシーセーフ構成する

前に説明したように、セーフ添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。

PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いが明らかです。 **\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。

- PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。
- PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。
- PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell を使用して添付ファイル ポリシーセーフ作成する

PowerShell でセーフ添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。

1. 安全な添付ファイル ポリシーを作成します。
2. ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。

 **注意**:

- 新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーを割り当てできます。 安全な添付ファイル ルールを複数の安全な添付ファイル ポリシーに関連付けできない。

- PowerShell の新しい安全な添付ファイル ポリシーで、ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない次の設定を構成できます。
  - 新しいポリシーを無効として作成 _します_ `$false` **(New-SafeAttachmentRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-SafeAttachmentRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しい安全な添付ファイル ポリシーは、ポリシーを安全な添付ファイル ルールに割り当てるMicrosoft 365 Defenderポータルには表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する

安全な添付ファイル ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" -Enable $true [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>] [-QuarantineTag <QuarantinePolicyName>]
```

この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。

- [ドキュメント] スキャンによってマルウェアがセーフ検出されたメッセージをブロックします _(Action_ パラメーターは使用していないので、既定値はです `Block` )。
- QuarantineTag [パラメーターを](quarantine-policies.md) 使用していないので、既定の検疫ポリシー (AdminOnlyAccessPolicy) _が使用_ されます。
- リダイレクトが有効になっていると、マルウェアが含まれていると検出されたメッセージは、分析と調査のために sec-ops@contoso.com に送信されます。
- 添付セーフスキャンが使用できない場合、またはエラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用していないので、既定値はです `$true` )。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Enable $true -Redirect $true -RedirectAddress sec-ops@contoso.com
```

構文とパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/new-safeattachmentpolicy)。

> [!NOTE]
> 安全な添付ファイル ポリシーで使用[](quarantine-policies.md)する検疫ポリシーを指定する詳細な手順については[、「Use PowerShell](quarantine-policies.md#safe-attachments-policies-in-powershell)to specify the quarantine policy in セーフ 添付ファイル ポリシー」を参照してください。

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

PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。 新しい添付ファイル セーフポリシーの名前を変更Microsoft 365 Defender、安全な添付ファイル ルールの名前を変更 _する必要があります_。

それ以外の場合は、この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成するときに同じ設定を使用できます。

安全な添付ファイル ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/set-safeattachmentpolicy)。

> [!NOTE]
> 安全な添付ファイル ポリシーで使用[](quarantine-policies.md)する検疫ポリシーを指定する詳細な手順については[、「Use PowerShell](quarantine-policies.md#safe-attachments-policies-in-powershell)to specify the quarantine policy in セーフ 添付ファイル ポリシー」を参照してください。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを変更する

PowerShell で安全な添付ファイル ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイルルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

安全な添付ファイル ルールを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイル ルールを有効または無効にする

PowerShell で安全な添付ファイル ルールを有効または無効にすると、セーフ 添付ファイル ポリシー (安全な添付ファイル ルールと割り当てられた安全な添付ファイル ポリシー) 全体が有効または無効となります。

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

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

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

添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するにはセーフ手順を実行します。

- [ポリシー] Microsoft 365 Defenderで、[ポリシー]セクション&の [&脅威ポリシーと添付ファイルセーフメールを送信する] \>  \>  \> **に移動** します。 ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、名前をクリックして一覧からポリシーを選択し、詳細を表示します。

- PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

[添付ファイル] セーフスキャンメッセージを確認するには、使用可能な Defender でレポートをOffice 365します。 詳細については、「View [reports for Defender for Office 365」](view-reports-for-mdo.md)および「Use Explorer in the [Microsoft 365 Defender ポータル」を参照してください](threat-explorer.md)。
