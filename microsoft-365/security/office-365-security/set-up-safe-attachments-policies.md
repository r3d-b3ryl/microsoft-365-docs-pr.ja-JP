---
title: Microsoft Defender for Office 365でセーフ添付ファイル ポリシーを設定する
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
description: メール内の悪意のあるファイルから組織を保護するためにセーフ添付ファイル ポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 811730ce12af80b2ac8df7db068b63b96b856bbd
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64847091"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365でセーフ添付ファイル ポリシーを設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlookでの添付ファイルのスキャンに関する情報を探しているホーム ユーザーの場合は、「[Advanced Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

セーフ添付ファイルは[、Exchange Online Protection](whats-new-in-defender-for-office-365.md) [(EOP) のマルウェア対策保護](anti-malware-protection.md)によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信電子メール メッセージ内の添付ファイルを確認するMicrosoft Defender for Office 365の機能です。 詳細については、「[Microsoft Defender for Office 365の添付ファイルのセーフ](safe-attachments.md)」を参照してください。

既定のセーフ添付ファイル ポリシーはありませんが、**組み込みの保護** プリセット セキュリティ ポリシーでは、すべての受信者 (カスタム セーフ添付ファイル ポリシーで定義されていないユーザー) にセーフ添付ファイル保護が提供されます。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。 この記事の手順を使用して、特定のユーザー、グループ、またはドメインに適用されるセーフ添付ファイル ポリシーを作成することもできます。

セーフ添付ファイル ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell で構成できます (Exchange Onlineのメールボックスを持つ適格なMicrosoft 365組織に対して PowerShell をExchange Onlineし、スタンドアロンの EOP PowerShell を使用しない組織向けメールボックスをExchange Onlineしますが、アドオン サブスクリプションDefender for Office 365)。

セーフ添付ファイル ポリシーの基本的な要素は次のとおりです。

- **安全な添付ファイル ポリシー**: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定したメール アドレスに送信するかどうか、および添付ファイルスキャンセーフ完了できない場合にメッセージを配信するかどうかを指定します。
- **安全な添付規則**: 優先度フィルターと受信者フィルター (ポリシーが適用されるユーザー) を指定します。

Microsoft 365 Defender ポータルでセーフ添付ファイル ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。

- セーフ添付ファイル ポリシーを作成する場合、実際には、安全な添付ファイルルールと、関連付けられている安全な添付ファイル ポリシーを同時に作成し、両方に同じ名前を使用します。
- セーフ添付ファイル ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって安全な添付規則が変更されます。 その他のすべての設定では、関連付けられている安全な添付ファイル ポリシーが変更されます。
- セーフ添付ファイル ポリシーを削除すると、安全な添付ファイルルールと関連する安全な添付ファイル ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半の「[PowerShell またはスタンドアロンの EOP PowerShell Exchange Online使用して セーフ添付ファイル ポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)」セクションを参照してください。

> [!NOTE]
> セーフ添付ファイル設定のグローバル設定領域で、セーフ添付ファイル ポリシーに依存しない機能を構成します。 手順については、「[Microsoft 365 E5のドキュメントのSharePoint、OneDrive、Microsoft Teamsとセーフ](turn-on-mdo-for-spo-odb-and-teams.md)[の添付ファイルのセーフ](safe-docs.md)を有効にする」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、アクセス許可が必要です。
  - 添付ファイル ポリシーセーフ作成、変更、削除するには、Microsoft 365 Defender ポータルの **組織管理** または **セキュリティ管理者** の役割グループのメンバー **であり**、Exchange Onlineの **組織管理** 役割グループのメンバーである必要があります。
  - セーフ添付ファイル ポリシーへの読み取り専用アクセスの場合は、Microsoft 365 Defender ポータルで **グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)と[Exchange Onlineのアクセス許可に関するページを参照](/exchange/permissions-exo/permissions-exo)してください。

  **注意**:

  - Microsoft 365 管理センターで対応するAzure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- セーフ添付ファイル ポリシーの推奨設定については、「[セーフ添付ファイルの設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)」を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ添付ファイル ポリシーを作成する

Microsoft 365 Defender ポータルでカスタム セーフ添付ファイル ポリシーを作成すると、安全な添付ファイル規則と関連付けられた安全な添付ファイル ポリシーが同時に作成されます。両方に同じ名前が使用されます。

1. Microsoft 365 Defender ポータルの [ポリシー] **セクション****の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[セーフ添付ファイル**] ページで、[作成] アイコンをクリックします![。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. ポリシー ウィザードが開きます。 [ **ポリシーの名前]** ページで、次の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[ユーザーとドメイン]** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 
     - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
     - 指定した Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. **設定** ページで、次の設定を構成します。

   - **セーフ 添付ファイルの不明なマルウェア応答**: 次のいずれかの値を選択します。
     - **オフ**: 通常、この値はお勧めしません。
     - **モニター**
     - **ブロック**: これは既定値であり、Standard および Strict [の事前設定済みセキュリティ ポリシー](preset-security-policies.md)で推奨される値です。
     - **置換**
     - **動的配信 (プレビュー機能)**

     これらの値については、「[セーフ添付ファイルポリシーの設定」を参照してください](safe-attachments.md#safe-attachments-policy-settings)。

   - **検疫ポリシー**: セーフ添付ファイル (**ブロック**、**置換**、または **動的配信**) によって検疫されたメッセージに適用される検疫ポリシーを選択します。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

     空白の値は、既定の検疫ポリシーが使用されていることを意味します (添付ファイルをセーフして電子メールを検出する場合は AdminOnlyAccessPolicy)。 後でセーフ添付ファイル ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。

   - **検出された添付ファイルを含むメッセージをリダイレクト** する: **[リダイレクトを有効にする**] を選択した場合、 **ブロック、監視、または置き換えられた添付ファイルを含むメール アドレスを指定して、指定したメール アドレス ボックスに電子メール アドレス** を指定して、マルウェアの添付ファイルを含むメッセージを分析および調査用に送信できます。

     Standard ポリシーと Strict ポリシー設定の推奨事項は、リダイレクトを有効にすることです。 詳細については、「[セーフ添付ファイルの設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)」を参照してください。

   - **スキャンが完了できない場合にセーフ添付ファイル検出応答を適用します (タイムアウトまたはエラー)**:添付ファイルのスキャンを完了できない場合でも **、セーフ添付ファイルの不明なマルウェア応答** で指定されたアクションがメッセージに対して実行セーフ。 このオプションを選択した場合は、常に **[リダイレクトを有効にする]** を選択し、マルウェアの添付ファイルを含むメッセージを送信する電子メール アドレスを指定します。 そうしないと、メッセージが失われる可能性があります。

   完了したら、**[次へ]** をクリックします。

6. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

7. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ添付ファイル ポリシーを表示する

1. Microsoft 365 Defender ポータルの [ポリシー] **セクション****の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[セーフ添付ファイル**] ページで、ポリシーの一覧に次のプロパティが表示されます。
   - **名前**
   - **状態**
   - **優先度**

3. ポリシーの名前をクリックして選択すると、ポリシー設定がポップアウトで表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ添付ファイル ポリシーを変更する

1. IIn Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> **ポリシー&ルール** \> **の脅威ポリシー**\>セーフ [**ポリシー]** セクションの **[添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[セーフ添付ファイル**] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「[Microsoft 365 Defender ポータルを使用してセーフ添付ファイル ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)」セクションを参照してください。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションをご覧ください。

### <a name="enable-or-disable-safe-attachments-policies"></a>添付ファイル ポリシーセーフ有効または無効にする

1. Microsoft 365 Defender ポータルの [ポリシー] **セクション****の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[セーフ添付ファイル**] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-safe-attachments-policies"></a>セーフ添付ファイル ポリシーの優先度を設定する

既定では、セーフ添付ファイル ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは古いポリシーよりも優先順位が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

セーフ添付ファイル ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。

**注**: Microsoft 365 Defender ポータルでは、セーフ添付ファイル ポリシーの優先度は、作成後にのみ変更できます。 PowerShell では、安全な添付ファイル規則を作成するときに既定の優先度をオーバーライドできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

1. Microsoft 365 Defender ポータルで、[**ポリシー] セクションの [電子メール & コラボレーション** \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。

2. **[セーフ添付ファイル**] ページで、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部に、現在の優先度の値とポリシーの数に基づいて **、優先度** の **増加** または優先度の低下が表示されます。
   - **優先度** の値が **0** のポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。
   - **優先度** 値が最低のポリシー (例: **3**) では、**[優先度を下げる]** オプションのみ利用可能です。
   - 3 つ以上のポリシーがある場合、優先度の値が最も高いポリシーと最も低いポリシーの間では、**[優先度を上げる]** と **[優先度を下げる]** の両方のオプションが利用可能です。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Microsoft 365 Defender ポータルを使用してセーフ添付ファイル ポリシーを削除する

1. Microsoft 365 Defender ポータルの [ポリシー] **セクション****の** <https://security.microsoft.com>[電子メール & コラボレーション \> **ポリシー&ルール** \> **の脅威ポリシー** \> **セーフ添付ファイル**] に移動します。 **[安全な添付ファイル]** ページに直接移動するには、<https://security.microsoft.com/safeattachmentv2> を使用します。

2. **[セーフ添付ファイル**] ページで、ポリシーの名前をクリックして、一覧からカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \> ![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png) **[ポリシーの削除]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>PowerShell またはスタンドアロンの EOP PowerShell Exchange Onlineを使用してセーフ添付ファイル ポリシーを構成する

前述のように、セーフ添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル規則で構成されています。

PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いは明らかです。 **SafeAttachmentPolicy コマンドレットを\*** 使用して安全な添付ファイル ポリシーを管理し、**-SafeAttachmentRule コマンドレットを\*** 使用して安全な添付ファイル規則を管理します。

- PowerShell では、最初に安全な添付ファイル ポリシーを作成し、ルールが適用されるポリシーを識別する安全な添付ファイル規則を作成します。
- PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。
- PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル規則は自動的に削除されません。また、その逆も同様です。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell を使用してセーフ添付ファイル ポリシーを作成する

PowerShell でのセーフ添付ファイル ポリシーの作成は、次の 2 段階のプロセスです。

1. 安全な添付ファイル ポリシーを作成します。
2. ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付規則を作成します。

 **注意**:

- 新しい安全な添付規則を作成し、関連付けられていない既存の安全な添付ファイル ポリシーを割り当てることができます。 安全な添付ファイルルールを複数の安全な添付ファイル ポリシーに関連付けることはできません。

- ポリシーを作成するまで、Microsoft 365 Defender ポータルでは使用できない PowerShell の新しい安全な添付ファイル ポリシーに対して、次の設定を構成できます。
  - 無効として新しいポリシーを作成します (**New-SafeAttachmentRule コマンドレットで**_有効)。_ `$false`
  - **New-SafeAttachmentRule** コマンドレットの作成時のポリシーの _優先度 (優先度__\<Number\>_) を設定します。

- PowerShell で作成した新しい安全な添付ファイル ポリシーは、安全な添付規則にポリシーを割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する

安全な添付ファイル ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" -Enable $true [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>] [-QuarantineTag <QuarantinePolicyName>]
```

この例では、Contoso All という名前の安全な添付ポリシーを次の値で作成します。

- ドキュメントスキャンをセーフしてマルウェアが含まれていることが検出されたメッセージをブロックします (_アクション_ パラメーターは使用されておらず、既定値は`Block`次のとおりです)。
- QuarantineTag パラメーターを使用していないため、既定の[検疫ポリシー](quarantine-policies.md) (AdminOnlyAccessPolicy) が使用されます。
- リダイレクトが有効になっており、マルウェアが含まれていることが検出されたメッセージは、分析と調査のために sec-ops@contoso.com に送信されます。
- セーフ添付ファイルスキャンを使用できない場合、またはエラーが発生した場合は、メッセージを配信しないでください (_ActionOnError_ パラメーターは使用されておらず、既定値は`$true`指定されています)。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Enable $true -Redirect $true -RedirectAddress sec-ops@contoso.com
```

構文とパラメーターの詳細については、「 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)」を参照してください。

> [!NOTE]
> 安全な添付ファイル ポリシーで使用する[検疫ポリシー](quarantine-policies.md)を指定する詳細な手順については、「[PowerShell を使用して、セーフ添付ファイル ポリシーで検疫ポリシーを指定](quarantine-policies.md#safe-attachments-policies-in-powershell)する」を参照してください。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>手順 2: PowerShell を使用して安全な添付ファイルルールを作成する

安全な添付ファイル規則を作成するには、次の構文を使用します。

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

この例では、次の条件で Contoso All という名前の安全な添付規則を作成します。

- ルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられています。
- この規則は、contoso.com ドメイン内のすべての受信者に適用されます。
- _Priority_ パラメーターを使用していないため、既定の優先度が使用されます。
- ルールは有効です ( _Enabled_ パラメーターは使用せず、既定値は `$true`有効です)。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

構文とパラメーターの詳細については、「 [New-SafeAttachmentRule」を](/powershell/module/exchange/new-safeattachmentrule)参照してください。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを表示する

既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、すべての安全な添付ファイル ポリシーの概要リストを返します。

```PowerShell
Get-SafeAttachmentPolicy
```

この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については、「 [Get-SafeAttachmentPolicy」を参照](/powershell/module/exchange/get-safeattachmentpolicy)してください。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを表示する

既存の安全な添付ファイル規則を表示するには、次の構文を使用します。

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、すべての安全な添付ファイルルールの概要リストを返します。

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

この例では、Contoso Executives という名前の安全な添付ファイル規則の詳細情報を返します。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については、「 [Get-SafeAttachmentRule」を](/powershell/module/exchange/get-safeattachmentrule)参照してください。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを変更する

PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません ( **Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターがありません)。 Microsoft 365 Defender ポータルでセーフ添付ファイル ポリシーの名前を変更する場合は、安全な添付ファイル _ルール_ の名前を変更するだけです。

それ以外の場合は、この記事の「手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように [、安全な添付ファイル ポリシーを作成](#step-1-use-powershell-to-create-a-safe-attachment-policy) するときに、同じ設定を使用できます。

安全な添付ファイル ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)」を参照してください。

> [!NOTE]
> 安全な添付ファイル ポリシーで使用する[検疫ポリシー](quarantine-policies.md)を指定する詳細な手順については、「[PowerShell を使用して、セーフ添付ファイル ポリシーで検疫ポリシーを指定](quarantine-policies.md#safe-attachments-policies-in-powershell)する」を参照してください。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを変更する

PowerShell で安全な添付ファイル規則を変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の安全な添付ファイルルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、この記事の「 [手順 2: PowerShell を使用して安全な添付ファイルルールを作成する](#step-2-use-powershell-to-create-a-safe-attachment-rule) 」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

安全な添付ファイル規則を変更するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell を使用して安全な添付規則を有効または無効にする

PowerShell で安全な添付ファイル規則を有効または無効にすると、セーフ添付ファイル ポリシー全体 (安全な添付ファイル規則と割り当てられた安全な添付ファイル ポリシー) が有効または無効になります。

PowerShell で安全な添付ファイル規則を有効または無効にするには、次の構文を使用します。

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

構文とパラメーターの詳細については、「 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 」および「 [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で安全な添付ファイル規則の優先度を設定するには、次の構文を使用します。

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**注**: 作成時に新しいルールの優先度を設定するには、代わりに **New-SafeAttachmentRule** コマンドレットの _Priority_ パラメーターを使用します。

構文とパラメーターの詳細については、「 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)」を参照してください。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell を使用して安全な添付ファイル ポリシーを削除する

PowerShell を使用して安全な添付ファイル ポリシーを削除すると、対応する安全な添付ファイルルールは削除されません。

PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)」を参照してください。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell を使用して安全な添付ファイルルールを削除する

PowerShell を使用して安全な添付ファイル規則を削除すると、対応する安全な添付ファイル ポリシーは削除されません。

PowerShell で安全な添付ファイル規則を削除するには、次の構文を使用します。

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の安全な添付ファイルルールを削除します。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-SafeAttachmentRule」を](/powershell/module/exchange/remove-safeattachmentrule)参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

添付ファイル ポリシーを正常に作成、変更、または削除セーフ確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの **[セーフ添付ファイル**] ページで<https://security.microsoft.com/safeattachmentv2>、ポリシーの一覧、**状態** の値、および **優先度** の値を確認します。 詳細を表示するには、名前をクリックして一覧からポリシーを選択し、ポップアップで詳細を表示します。

- PowerShell または powerShell Exchange Online Protection Exchange Onlineで、ポリシーまたはルールの名前に置き換え\<Name\>、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

添付ファイルセーフメッセージをスキャンしていることを確認するには、使用可能なDefender for Office 365レポートを確認します。 詳細については、[Microsoft 365 Defender](view-reports-for-mdo.md) [ポータルでのDefender for Office 365およびエクスプローラーの使用に関するレポートの表示に関するMicrosoft 365 Defender](threat-explorer.md)を参照してください。
