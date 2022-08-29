---
title: テナント許可/禁止リストを使用して電子メールを許可またはブロックする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストで、電子メールとスプーフィングされた送信者エントリを許可またはブロックする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 912743015041bc610c3f44607b8ee21f8c715cc9
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441879"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>テナント許可/禁止リストを使用して電子メールを許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、テナント許可/ブロック リストで使用できるドメインと電子メール アドレス (スプーフィングされた送信者を含む) の許可エントリを作成および管理し、ブロックする方法について説明します。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

メールの許可とブロックのエントリは、Microsoft 365 Defender ポータルまたは powerShell Exchange Onlineで管理します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナントの許可/ブロック一覧**] ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>. **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- ドメインと電子メール アドレスの場合、許可エントリの最大数は 500 で、ブロック エントリの最大数は 500 (ドメインと電子メール アドレスの合計 1,000 個) です。

- スプーフィングされた送信者の場合、エントリの最大数は 1024 です。

- スプーフィングされた送信者のエントリが期限切れになることはありません。

- スプーフィングされた送信者エントリの構文の詳細については、この記事の後半の「 [スプーフィングされた送信者エントリのドメイン ペア構文](#domain-pair-syntax-for-spoofed-sender-entries) 」セクションを参照してください。

- エントリは 30 分以内にアクティブにする必要がありますが、エントリがアクティブになるまでに最大で 24 時間かかる場合があります。

- この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。
  - テナント許可/ブロック リストの値を追加および削除するには、次のいずれかの役割グループのメンバーである必要があります。
    - **組織の管理** または **セキュリティ管理者** の役割グループ (**セキュリティ管理者ロール**)
    - **Security Operator** ロール グループ (**テナント AllowBlockList Manager**)。
  - テナント許可/ブロック リストへの読み取り専用アクセスの場合は、次のいずれかの役割グループのメンバーである必要があります。
    - **グローバル リーダー**  の役割グループ
    - **セキュリティ 閲覧者** の役割グループ
    - **ビューのみの構成** 役割グループ

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 *および* Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="domains-and-email-addresses-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リスト内のドメインと電子メール アドレス

### <a name="create-block-entries-for-domains-and-email-addresses"></a>ドメインと電子メール アドレスのブロック エントリを作成する

ドメインと電子メール アドレスのブロック エントリを作成するには、次のオプションがあります。

- [Microsoft 365 Defender ポータルの [申請] ページ](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- [Microsoft 365 Defender ポータル](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list)または [PowerShell](#use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list) のテナント許可/ブロックリスト

スプーフィングされた送信者のブロック エントリを作成するには、この記事の後半の「[テナント許可/ブロックリスト」セクションの「Microsoft 365 Defender ポータルを使用してスプーフィングされた送信者の許可エントリまたはブロック エントリを表示](#use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list)する」を参照してください。

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルでドメインと電子メール アドレスのブロック エントリを作成する

送信ポータル <https://security.microsoft.com/reportsubmission> を使用して、電子メール メッセージを **[ブロックされている必要があります ] (False negative)** として報告する場合は、[ **この受信者からのすべてのメールをブロックする** ] を選択して、テナント許可/ブロック リストにドメインまたは送信者のブロック エントリを追加できます。

手順については、「 [問題のあるメールを Microsoft に報告する」を参照してください](admin-submission.md#report-questionable-email-to-microsoft)。

#### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック 一覧でドメインと電子メール アドレスのブロック エントリを作成する

テナント許可/ブロック リストで、ドメインと電子メール アドレスのブロック エントリを直接作成します。

> [!NOTE]
> これらの送信者からのEmailメッセージは *、高信頼スパム* (SCL = 9) としてマークされます。 メッセージに対する処理は、受信者のメッセージを検出した [スパム対策ポリシー](configure-your-spam-filter-policies.md) によって決まります。 既定のスパム対策ポリシーと新しいカスタム ポリシーでは、信頼度の高いスパムとしてマークされたメッセージが既定で迷惑メール Email フォルダーに配信されます。 Standard および Strict [の事前設定済みセキュリティ ポリシー](preset-security-policies.md)では、信頼度の高いスパム メッセージが検疫されます。
>
> 組織内のユーザーは、これらのブロックされたドメインとアドレスに電子メールを送信できません。 次の配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) を受け取ります。 `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.`

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **ドメイン&アドレス** ] タブが選択されていることを確認します。

3. **[ドメイン&アドレス** ] タブで、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

4. 表示される **[ブロック ドメイン&アドレス** ポップアップ] で、次の設定を構成します。

   - **ドメイン & アドレス**: 1 行あたり 1 つの電子メール アドレスまたはドメインを入力し、最大 20 個まで入力します。

   - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
     - **1 日**
     - **7 日間**
     - **30 日間**
     - **有効期限が切れない**
     - **特定の日付**: 最大値は今日から 90 日です。

   - **省略可能な注**: エントリの説明テキストを入力します。

5. 完了したら、**[追加]** をクリックします。

##### <a name="use-powershell-to-create-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック 一覧でドメインと電子メール アドレスのブロック エントリを作成する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "DomainOrEmailAddress1","DomainOrEmailAddress1",..."DomainOrEmailAddressN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

この例では、特定の日付に有効期限が切れる指定したメール アドレスのブロック エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com","test2@anotherattackerdomain.com" -ExpirationDate 8/20/2022
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルでドメインと電子メール アドレスの許可エントリを作成する

テナント許可/ブロックリストにドメインと電子メール アドレスの許可エントリを直接作成することはできません。 代わりに、送信ポータルを <https://security.microsoft.com/reportsubmission> 使用して、メッセージを誤検知として報告します。 管理者の提出の詳細については、「 [申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当な電子メール、および電子メールの添付ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

> [!NOTE]
> Microsoft が許可エントリを管理するため、不要なドメインと電子メール アドレスの許可エントリは削除されます。 この動作により、組織が保護され、構成の誤った許可エントリを防ぐことができます。 判定に同意しない場合は、メッセージが依然として不適切と見なされる理由を判断するためにサポート ケースを開く必要がある場合があります。
>
> ドメインまたは電子メール アドレスがまだブロックされていない場合、ドメインまたは電子メール アドレスの許可エントリは作成されません。
>
> メッセージが誤ってブロックされた誤検知であると判断されたほとんどの場合、許可エントリは指定された有効期限日に削除されます。
>
> スプーフィングされた送信者の許可エントリを作成するには、この記事の後半の「 [スプーフィングされた送信者の許可エントリを作成する](#create-allow-entries-for-spoofed-senders) 」セクションを参照してください。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信] ページで** 、[ **電子メール** ] タブが選択されていることを確認します。

3. [ **電子メール** ] タブで、[分析用に Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** に、次の情報を入力します。

   - **申請の種類を選択します**。**Email** 値が選択されていることを確認します。

   - **ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロード** します。次のいずれかのオプションを選択します。

     - **電子メール ネットワーク メッセージ ID を追加します**。これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。

     - **電子メール ファイル (.msg または .eml) をアップロード** する: [ **ファイルの参照**] をクリックします。 開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[ **開く**] をクリックします。

   - **問題が発生した受信者を選択** します。ポリシー チェックを実行する受信者を指定します。 ポリシー チェックでは、ユーザーポリシーまたは組織ポリシーが原因で電子メールがブロックされたかどうかが決定されます。

   - **Microsoft に送信する理由を選択** します: [ **ブロックされていない必要があります (False positive)]**、[次の設定の構成] の順に選択します。

     - **類似した属性 (URL、送信者など) を持つ電子メールを許可** する:この設定 ![をオンに切り替えます](../../media/scc-toggle-on.png)。.

         - **許可エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **特定の日付**: 最大値は今日から 30 日です。

         - **入力を許可する注**: このメールを許可する理由に関するオプション情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

   :::image type="content" source="../../media/admin-submission-email-allow.png" alt-text="Defender ポータルの [提出] ページで、分析のために Microsoft に誤検知 (適切な) メールを送信します。" lightbox="../../media/admin-submission-email-allow.png":::

5. しばらくすると、[テナントの許可 **とブロックの一覧**] ページの [**ドメイン & アドレス**] タブに許可エントリが表示されます。

> [!NOTE]
>
> - 許可は、メッセージが悪意のあると判断したフィルターに基づいて、メール フロー中に追加されます。 たとえば、送信者とメッセージ内の URL が正しくないと判断された場合、送信者の許可エントリが作成され、URL に対して許可エントリが作成されます。
> - そのエンティティ (ドメインまたは電子メール アドレス、URL、ファイル) が再び検出されると、そのエンティティに関連付けられているすべてのフィルターがスキップされます。
> - メール フロー中に、ドメインまたは電子メール アドレスからのメッセージがフィルター処理スタック内の他のチェックに合格した場合、メッセージは配信されます。 たとえば、 [電子メール認証](email-validation-and-authentication.md) に合格した場合、許可エントリの送信者からのメッセージが配信されます。

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のドメインと電子メール アドレスの許可エントリまたはブロック エントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. **[ドメイン&アドレス**] タブが選択されていることを確認します。 次の列を使用できます。

   - **値**: ドメインまたは電子メール アドレス。
   - **アクション**: 値 **Allow** または **Block**。
   - **変更者**
   - **最終更新日時**
   - **[削除日**]: 有効期限。
   - **注**

   列見出しをクリックすると、昇順または降順で並べ替えることができます。

   [グループ] アイコンをクリック ![します。](../../media/m365-cc-sc-group-icon.png) **結果** を **[なし]** または **[アクション**] でグループ化します。

   [検索] アイコンをクリック ![します。](../../media/m365-cc-sc-search-icon.png) **値** のすべてまたは一部を検索して入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] アイコンをクリックします ![。](../../media/m365-cc-sc-close-icon.png) **検索をクリアします**。

   [フィルター] アイコンをクリック ![します。](../../media/m365-cc-sc-filter-icon.png) **フィルター処理** して結果をフィルター処理します。 次の値は、表示される **フィルター** ポップアップで使用できます。

   - **アクション**: **許可** と **ブロック**。
   - **期限切れになることはありません**: ![オンに切り替えます。](../../media/scc-toggle-on.png) または ![トグルオフにします。](../../media/scc-toggle-off.png)
   - **最終更新日**: **[開始日** ] と [ **終了日]** を選択します。
   - **[削除日**]: **[開始日** ] と [ **終了日]** を選択します。

   完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

#### <a name="use-powershell-to-view-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リスト内のドメインと電子メール アドレスの許可エントリまたはブロック エントリを表示する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType Sender [-Allow] [-Block] [-Entry <Domain or Email address value>] [<-ExpirationDate Date | -NoExpiration>]
```

この例では、ドメインと電子メール アドレスのすべての許可エントリとブロック エントリを返します。

```powershell
Get-TenantAllowBlockListItems -ListType Sender
```

次の使用例は、ドメインと電子メール アドレスのブロック エントリの結果をフィルター処理します。

```powershell
Get-TenantAllowBlockListItems -ListType Sender -Block
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のドメインと電子メール アドレスの許可エントリまたはブロック エントリを変更する

テナントの許可/ブロックの一覧でドメインと電子メール アドレスの許可エントリまたはブロック エントリを変更する場合は、有効期限とメモのみを変更できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. **[ドメイン&アドレス**] タブが選択されていることを確認します。

3. [ **ドメイン & アドレス** ] タブで、変更するエントリのチェック ボックスをオンにし、[編集] アイコンを ![クリックします。](../../media/m365-cc-sc-edit-icon.png) **表示される [編集]** ボタン。

4. 次の設定は、表示される **[ドメイン&アドレスのポップアップの編集]** で使用できます。

   - **許可エントリを削除した後に削除** するか **、ブロック エントリを削除します。**
     - 許可エントリは、作成日から最大 30 日間延長できます。
     - ブロック エントリは、作成日から最大 90 日間延長することも、 **期限切れにならないように** 設定することもできます。

   - **省略可能なメモ**

   完了したら、**[保存]** をクリックします。

> [!NOTE]
> エントリを許可する場合にのみ、チェック ボックス以外の行の任意の場所をクリックしてエントリを選択した場合は、[提出の表示] アイコンを選択 ![できます。](../../media/m365-cc-sc-view-submission-icon.png) **[申請]** ページ<https://security.microsoft.com/reportsubmission>に移動するように表示される詳細ポップアップで **提出を** 表示します。

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリスト内のドメインと電子メール アドレスの許可エントリまたはブロック エントリを変更する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

この例では、ドメインと電子メール アドレスに対して指定されたブロック エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Sender -Entries "julia@fabrikam.com" -ExpirationDate "9/1/2022"
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-domains-and-email-addresses-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のドメインと電子メール アドレスの許可エントリまたはブロック エントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. **[ドメイン&アドレス**] タブが選択されていることを確認します。

3. [ **ドメイン&アドレス** ] タブで、次のいずれかの手順を実行します。

   - 削除するエントリのチェック ボックスをオンにし、[削除] アイコンを ![クリックします。](../../media/m365-cc-sc-delete-icon.png) **表示される削除** アイコン。
   - チェック ボックス以外の行の任意の場所をクリックして、削除するエントリを選択します。 表示される詳細ポップアップで、[削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **Delete**

4. 表示される警告ダイアログで、[削除] をクリック **します**。

> [!NOTE]
> 複数のエントリを選択するには、各チェック ボックスをオンにするか、 **値** 列ヘッダーの横にあるチェック ボックスをオンにしてすべてのエントリを選択します。

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-domains-and-email-addresses-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストからドメインと電子メール アドレスの許可エントリまたはブロック エントリを削除する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType Sender <-Ids <Identity value> | -Entries <Value value>>
```

次の使用例は、テナント許可/ブロック リストからドメインと電子メール アドレスの指定されたブロック エントリを削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Sender -Entries "adatum.com"
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="spoofed-senders-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストのスプーフィングされた送信者

### <a name="create-allow-entries-for-spoofed-senders"></a>スプーフィングされた送信者の許可エントリを作成する

スプーフィングされた送信者のブロック エントリを作成するには、次のオプションがあります。

- [Microsoft 365 Defender ポータルの [申請] ページ](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)
- [Microsoft 365 Defender ポータル](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list)または [PowerShell](#use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list) のテナント許可/ブロックリスト

> [!NOTE]
> スプーフィングされた送信者のエントリが組織内、組織間、および DMARC スプーフィングを処理することを許可します。
>
> スプーフィングされたユーザー *と*[、ドメイン ペア](#domain-pair-syntax-for-spoofed-sender-entries)で定義されている送信インフラストラクチャの組み合わせのみがスプーフィングを許可されます。
>
> ドメイン ペアの許可エントリを構成すると、そのドメイン ペアからのメッセージは [スプーフィング インテリジェンス 分析情報](learn-about-spoof-intelligence.md)に表示されなくなります。
>
> スプーフィングされた送信者のエントリが期限切れにならないようにします。

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、送信ポータルでスプーフィングされた送信者の許可エントリを作成する

**[送信]** ページからス [プーフィング インテリジェンス](learn-about-spoof-intelligence.md)によってブロックされたメッセージを Microsoft に送信すると、テナント許可/ブロック リストの [**スプーフィングされた送信者**] タブに送信者が許可エントリとして追加されます。

> [!NOTE]
> スプーフィング インテリジェンス分析情報の判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロックリストの [ **スプーフィングされた送信者** ] タブにのみ表示される手動の許可エントリまたはブロック エントリになります。
>
> 送信者がスプーフィング インテリジェンスによってブロックされていない場合、電子メール メッセージを Microsoft に送信しても、テナント許可/ブロック リストに許可エントリは作成されません。

メッセージを報告する手順は、「[Microsoft 365 Defender ポータルを使用して送信ポータルでドメインと電子メール アドレスのエントリを許可する」の手順とほぼ](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)同じです。

違いは次の点のみです。

- スプーフィングされた送信者のエントリが期限切れになることがないため、手順 4 の設定後に許可エントリを **削除** することは意味がありません。
- 手順 4 の **[エントリメモを許可する** ] 設定は、テナント許可/ブロックリストのスプーフィングされた送信者のエントリには適用されません。

#### <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリを作成する

テナントの許可/ブロックの一覧で、スプーフィングされた送信者がスプーフィン [グ インテリジェンス](learn-about-spoof-intelligence.md)によって検出およびブロックされる前に、許可エントリを作成できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **スプーフィングされた送信者** ] タブを選択し、[追加] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加]** ポップアップで、次の設定を構成します。

   - **ワイルドカードを使用してドメイン ペアを追加する**:最大 20 行のドメイン ペアを入力します。 スプーフィングされた送信者エントリの構文の詳細については、この記事の後半の「 [スプーフィングされた送信者エントリのドメイン ペア構文](#domain-pair-syntax-for-spoofed-sender-entries) 」セクションを参照してください。

   - **スプーフィングの種類**: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織に属するドメイン ( [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) にあります。
     - **外部**: スプーフィングされた送信者は外部ドメインにあります。

   - **アクション**: **[許可]** または [ブロック] を選択 **します**。

   完了したら、**[追加]** をクリックします。

##### <a name="use-powershell-to-create-allow-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリを作成する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

この例では、送信元 contoso.com から送信者 bob@contoso.com の許可エントリを作成します。

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure contoso.com -SpoofedUser bob@contoso.com -SpoofType External
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リストでスプーフィングされた送信者のブロック エントリを作成する

スプーフィングされた送信者のブロック エントリは、テナント許可/ブロック リストに直接作成します。

> [!NOTE]
> これらの送信者からのEmailメッセージは *フィッシング* としてブロックされます。
>
> [ドメイン ペア](#domain-pair-syntax-for-spoofed-sender-entries)で定義されているスプーフィングされたユーザー *と* 送信インフラストラクチャの組み合わせのみが、スプーフィングからブロックされます。
>
> ドメイン ペアのブロック エントリを構成すると、そのドメイン ペアからのメッセージは [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)に表示されなくなります。
>
> スプーフィングされた送信者のエントリをブロックすると、有効期限が切れることはありません。

メッセージを報告する手順は、「[Microsoft 365 Defender ポータルを使用して送信ポータルでドメインと電子メール アドレスのエントリを許可する」の手順とほぼ](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)同じです。

唯一の違いは、手順 4 の **アクション** 値に対して、[許可] ではなく [ **ブロック** ] を選択 **することです**。

#### <a name="use-powershell-to-create-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストでスプーフィングされた送信者のブロック エントリを作成する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Block -SpoofedUser <Domain | EmailAddress> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal>
```

この例では、送信元 172.17.17.17/24 から送信者 laura@adatum.com のブロック エントリを作成します。

```powershell
New-TenantAllowBlockListSpoofItems -Identity Default -Action Allow -SendingInfrastructure 172.17.17.17/24 -SpoofedUser laura@adatum.com -SpoofType External
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリまたはブロック エントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. **[スプーフィングされた送信者**] タブが選択されていることを確認します。 次の列を使用できます。

   - **偽のユーザー**
   - **インフラストラクチャの送信**
   - **スプーフィングの種類**: 値 **内部** または **外部**。
   - **アクション**: 値 **[ブロック]** または **[許可] を指定** します。

   列見出しをクリックすると、昇順または降順で並べ替えることができます。

   [グループ] アイコンをクリック ![します。](../../media/m365-cc-sc-group-icon.png) **結果** を **None**、 **Action**、または **スプーフィングの種類** でグループ化します。

   [検索] アイコンをクリック ![します。](../../media/m365-cc-sc-search-icon.png) **値** のすべてまたは一部を検索して入力し、Enter キーを押して特定の値を検索します。 完了したら、[検索のクリア] アイコンをクリックします ![。](../../media/m365-cc-sc-close-icon.png) **検索をクリアします**。

   [フィルター] アイコンをクリック ![します。](../../media/m365-cc-sc-filter-icon.png) **フィルター処理** して結果をフィルター処理します。 次の値は、表示される **フィルター** ポップアップで使用できます。

   - **アクション**: **許可** と **ブロック**。
   - **スプーフィングの種類**: **内部** と **外部**。

   完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[フィルター] ポップアップで [フィルターのクリア] アイコンの **[フィルターのクリア****] を**](../../media/m365-cc-sc-clear-filters-icon.png)クリック![します。

#### <a name="use-powershell-to-view-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリまたはブロック エントリを表示する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

次の使用例は、テナント許可/ブロック リスト内のすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems
```

この例では、内部であるすべての許可されたスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

次の使用例は、外部にある、ブロックされているすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)」を参照してください。

### <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロックリストのスプーフィングされた送信者の許可エントリまたはブロック エントリを変更する

テナントの許可/ブロックの一覧でスプーフィングされた送信者の許可エントリまたはブロック エントリを変更する場合は、エントリを **[許可] から [****ブロック**] に変更することのみ、またはその逆に変更できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **スプーフィングされた送信者** ] タブを選択します。

3. [ **スプーフィングされた送信者** ] タブで、変更するエントリを選択し、[編集] アイコンを ![クリックします。](../../media/m365-cc-sc-edit-icon.png) **表示される [編集]** ボタン。

4. 表示 **される [スプーフィングされた送信者の編集]** ポップアップで、[ **許可** ] または [ブロック] を選択 **します**。

5. 完了したら、**[保存]** をクリックします。

#### <a name="use-powershell-to-modify-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストのスプーフィングされた送信者の許可エントリまたはブロック エントリを変更する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Set-TenantAllowBlockListSpoofItems -Identity Default -Ids <Identity value> -Action <Allow | Block>
```

この例では、スプーフィングされた送信者エントリを許可からブロックに変更します。

```powershell
Set-TenantAllowBlockListItems -Identity Default -Ids 3429424b-781a-53c3-17f9-c0b5faa02847 -Action Block
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListSpoofItems」を参照](/powershell/module/exchange/set-tenantallowblocklistspoofitems)してください。

### <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-spoofed-senders-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロックリストでスプーフィングされた送信者の許可エントリまたはブロック エントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **スプーフィングされた送信者** ] タブを選択します。

3. [ **スプーフィングされた送信者** ] タブで、削除するエントリを選択し、[削除] アイコンを ![クリックします。](../../media/m365-cc-sc-delete-icon.png) **表示される削除** アイコン。

4. 表示される警告ダイアログで、[削除] をクリック **します**。

> [!NOTE]
> 複数のエントリを選択するには、各チェック ボックスをオンにするか、ス **プーフィングされたユーザー** 列ヘッダーの横にあるチェック ボックスをオンにしてすべてのエントリを選択します。

#### <a name="use-powershell-to-remove-allow-or-block-entries-for-spoofed-senders-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リストからスプーフィングされた送信者の許可エントリまたはブロック エントリを削除する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids <Identity value>
```

```powershell
Remove-TenantAllowBlockListSpoofItems -Identity domain.com\Default -Ids d86b3b4b-e751-a8eb-88cc-fe1e33ce3d0c
```

この例では、指定したスプーフィングされた送信者を削除します。 Ids パラメーターの値は、Get-TenantAllowBlockListSpoofItems コマンドの出力の Identity プロパティから取得します。

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)」を参照してください。

### <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>スプーフィングされた送信者エントリのドメイン ペア構文

テナント許可/ブロック リストのスプーフィングされた送信者のドメイン ペアでは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>`。

- **スプーフィングされたユーザー**: この値には、メール クライアントの [ **差** 出人] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれます。 このアドレスは、アドレスとも `5322.From` 呼ばれます。 有効な値は次のとおりです。
  - 個々の電子メール アドレス (chris@contoso.com など)。
  - 電子メール ドメイン (contoso.com など)。
  - ワイルドカード文字 (たとえば)。 \*

- **インフラストラクチャの送信**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。 有効な値は次のとおりです。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (fabrikam.com など)。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。
  - 検証済みの DKIM ドメイン。

スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

ドメイン ペアを追加すると、スプーフィングされたユーザー *と* 送信インフラストラクチャの *組み合わせ* のみが許可またはブロックされます。 スプーフィングされたユーザーからの任意のソースからのメールは許可されず、スプーフィングされたユーザーの送信インフラストラクチャ ソースからの電子メールも許可されません。

たとえば、次のドメイン ペアの許可エントリを追加します。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングを許可できるのは、そのドメインからのメッセージ *と* 送信インフラストラクチャ ペアからのメッセージだけです。 gmail.com をスプーフィングしようとしている他の送信者は許可されません。 tms.mx.com から発信された他のドメインの送信者からのメッセージは、スプーフィング インテリジェンスによってチェックされます。

> [!NOTE]
> 送信インフラストラクチャではワイルドカードを使用できません。

## <a name="about-impersonated-domains-or-senders"></a>偽装されたドメインまたは送信者について

Microsoft Defender for Office 365を持つ組織では、[ドメインまたは送信者](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)の偽装保護による偽装として検出されたメッセージの許可エントリをテナント/許可/ブロックリストに作成することはできません。

申請ポータルで <https://security.microsoft.com/reportsubmission>  偽装として誤ってブロックされたメッセージを報告しても、テナント許可/ブロック リストに送信者またはドメインが許可エントリとして追加されることはありません。

代わりに、メッセージを検出した [フィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies)の **[信頼された送信者とドメイン] セクション** にドメインまたは送信者が追加されます。

メッセージを報告する手順は、「[Microsoft 365 Defender ポータルを使用して、申請ポータルでドメインと電子メール アドレスの許可エントリを作成](#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal)する」の手順と同じです。

> [!NOTE]
> 現時点では、Graph 偽装はここからは処理されません。

## <a name="related-articles"></a>関連記事

- [送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当なメール、および電子メールの添付ファイルを Microsoft に送信する](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナント許可/ブロック リスト内のファイルを許可またはブロックする](allow-block-files.md)
- [テナント許可/ブロック リストの URL を許可またはブロックする](allow-block-urls.md)
