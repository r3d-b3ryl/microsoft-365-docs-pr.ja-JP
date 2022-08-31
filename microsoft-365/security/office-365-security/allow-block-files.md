---
title: テナント許可/禁止リストを使用してファイルを許可またはブロックする
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
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストでファイルを許可またはブロックする方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 2478328f47c278944abe523c1448704f0b8199ff
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67469429"
---
# <a name="allow-or-block-files-using-the-tenant-allowblock-list"></a>テナント許可/禁止リストを使用してファイルを許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、テナント許可/ブロックリストで使用できるファイル許可とブロックエントリを管理する方法について説明します。 テナント許可/ブロックリストの詳細については、「テナント許可/ブロック一 [覧で許可とブロックを管理する」を参照してください](manage-tenant-allow-block-list.md)。

ファイルの許可エントリとブロック エントリは、Microsoft 365 Defender ポータルまたは powerShell Exchange Onlineで管理します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナントの許可/ブロック一覧**] ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>. **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- ファイルの SHA256 ハッシュ値を使用してファイルを指定します。 Windows でファイルの SHA256 ハッシュ値を見つけるには、コマンド プロンプトで次のコマンドを実行します。

  ```DOS
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  値の例は `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. Perceptual hash (pHash) 値はサポートされていません。

- ファイルの場合、許可エントリの最大数は 500 で、ブロック エントリの最大数は 500 (合計 1,000 ファイル エントリ) です。

- ファイル エントリには最大 64 文字を入力できます。

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

## <a name="create-block-entries-for-files"></a>ファイルのブロック エントリを作成する

ファイルのブロック エントリを作成するには、次のオプションがあります。

- [Microsoft 365 Defender ポータルの [申請] ページ](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-submissions-portal)
- [Microsoft 365 Defender ポータル](#use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-tenant-allowblock-list)または [PowerShell](#use-powershell-to-create-block-entries-for-files-in-the-tenant-allowblock-list) のテナント許可/ブロックリスト

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルでファイルのブロック エントリを作成する

申請ポータルを <https://security.microsoft.com/reportsubmission> 使用して、 **ファイルを [ブロックされている必要があります ] (False negative)** として報告する場合は、[ **このファイルをブロックする** ] を選択して、テナント許可/ブロック リスト内のファイルのブロック エントリを追加できます。

手順については、「 [問題のある電子メールの添付ファイルを Microsoft に報告する」を参照してください](admin-submission.md#report-questionable-email-attachments-to-microsoft)。

### <a name="use-the-microsoft-365-defender-portal-to-create-block-entries-for-files-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のファイルのブロック エントリを作成する

テナント許可/ブロック リストでファイルのブロック エントリを直接作成します。

> [!NOTE]
> これらのブロックされたファイルを含むEmailメッセージは *、マルウェア* としてブロックされます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナント許可/ブロック 一覧** ] ページで、[ **ファイル** ] タブを選択します。

3. [ **ファイル** ] タブで、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

4. 表示される **[ブロック ファイル** ] ポップアップで、次の設定を構成します。

   - **ファイル ハッシュを追加** する: 行ごとに 1 つの SHA256 ハッシュ値を入力し、最大 20 個まで入力します。

   - **ブロック エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
     - **1 日**
     - **7 日間**
     - **30 日間**
     - **有効期限が切れない**
     - **特定の日付**: 最大値は今日から 90 日です。

   - **省略可能な注**: エントリの説明テキストを入力します。

5. 完了したら、**[追加]** をクリックします。

#### <a name="use-powershell-to-create-block-entries-for-files-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リスト内のファイルのブロック エントリを作成する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <FileHash> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

次の使用例は、有効期限が切れない指定されたファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-entries-for-files-in-the-submissions-portal"></a>Microsoft 365 Defender ポータルを使用して、申請ポータルでファイルの許可エントリを作成する

テナント許可/ブロック一覧でファイルの許可エントリを直接作成することはできません。 代わりに、送信ポータルを <https://security.microsoft.com/reportsubmission> 使用して、メッセージを誤検知として報告します。 管理者の提出の詳細については、「 [申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当な電子メール、および電子メールの添付ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

**[申請]** ページでファイルを誤検知として報告すると、テナント許可/ブロック リストにファイルの許可エントリが追加されます。

> [!IMPORTANT]
> Microsoft が許可エントリを管理するため、不要なファイルの許可エントリは削除されます。 この動作により、組織が保護され、構成の誤った許可エントリを防ぐことができます。 判定に同意しない場合は、ファイルがまだ不適切と見なされる理由を判断するためにサポート ケースを開く必要がある場合があります。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[アクション] & **[申請**] の [**申請]** ページ **に**\>移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [**申請] ページで**、[**Email添付ファイル**] タブを選択します。

3. **[Email添付ファイル**] タブで、[分析のために Microsoft に送信] アイコンをクリックします![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

4. 表示される **分析ポップアップの [Microsoft に送信]** で、次の情報を入力します。

   - **送信の種類を選択します**。**添付ファイルが選択Email** 値を確認します。

   - **ファイル**: [ **ファイルの参照]** をクリックして、送信するファイルを見つけて選択します。

   - **Microsoft に送信する理由を選択** します: [ **ブロックされていない必要があります (False positive)]**、[次の設定の構成] の順に選択します。

     - **このファイルを許可** する: この設定 ![をオンに切り替えます](../../media/scc-toggle-on.png)。.

         - **許可エントリの削除後**: 既定値は **30 日** ですが、次の値から選択できます。
           - **1 日**
           - **7 日間**
           - **30 日間**
           - **特定の日付**: 最大値は今日から 30 日です。

         - **入力を許可する注**: このファイルを許可する理由に関する省略可能な情報を入力します。

   完了したら、[ **送信]** をクリックし、[完了] をクリック **します**。

   :::image type="content" source="../../media/admin-submission-file-allow.png" alt-text="Defender ポータルの [提出] ページで、分析のために Microsoft に誤検知 (適切な) 電子メール添付ファイルを送信します。" lightbox="../../media/admin-submission-file-allow.png":::

5. しばらくすると、[テナントの許可 **/ブロック一覧**] ページの [**ファイル**] タブに許可エントリが表示されます。

> [!NOTE]
> ファイルが再び検出されると、 [安全な添付ファイル](safe-attachments.md) の起爆やファイルの評価チェックのために送信されず、他のすべてのファイル ベースのフィルターはスキップされます。 メール フロー中に、ファイルを含むメッセージがフィルター 処理スタック内の他のファイル以外のチェックに合格した場合、メッセージは配信されます。

## <a name="use-the-microsoft-365-defender-portal-to-view-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のファイルの許可エントリまたはブロック エントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **ファイル** ] タブを選択します。次の列を使用できます。

   - **値**: ファイル ハッシュ。
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

### <a name="use-powershell-to-view-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリスト内のファイルの許可エントリまたはブロック エントリを表示する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash [-Allow] [-Block] [-Entry <FileHashValue>] [<-ExpirationDate Date | -NoExpiration>]
```

次の使用例は、許可されているファイルとブロックされているすべてのファイルを返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash
```

この例では、指定したファイル ハッシュ値の情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

次の使用例は、ブロックされたファイルによって結果をフィルター処理します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Block
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-modify-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リスト内のファイルの許可エントリまたはブロック エントリを変更する

テナント許可/ブロックの一覧で許可ファイルまたはブロック ファイルエントリを変更する場合は、有効期限とメモのみを変更できます。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ファイル] タブ **を** 選択する

3. [ **ファイル** ] タブで、変更するエントリのチェック ボックスをオンにし、[編集] アイコンを ![クリックします。](../../media/m365-cc-sc-edit-icon.png) **表示される [編集]** ボタン。

4. 次の設定は、表示される **[ファイルの編集]** ポップアップで使用できます。

   - **許可エントリを削除した後に削除** するか **、ブロック エントリを削除します。**
     - 許可エントリは、作成日から最大 30 日間延長できます。
     - ブロック エントリは、作成日から最大 90 日間延長することも、 **期限切れにならないように** 設定することもできます。

   - **省略可能なメモ**

   完了したら、**[保存]** をクリックします。

> [!NOTE]
> エントリを許可する場合にのみ、チェック ボックス以外の行の任意の場所をクリックしてエントリを選択した場合は、[提出の表示] アイコンを選択 ![できます。](../../media/m365-cc-sc-view-submission-icon.png) **[申請]** ページ<https://security.microsoft.com/reportsubmission>に移動するように表示される詳細ポップアップで **提出を** 表示します。

### <a name="use-powershell-to-modify-allow-or-block-entries-for-files-in-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロック リスト内のファイルの許可エントリまたはブロック エントリを変更する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash> <-Ids <Identity value> | -Entries <Value value>> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

この例では、指定したファイル ブロック エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType FileHash -Entries "27c5973b2451db9deeb01114a0f39e2cbcd2f868d08cedb3e210ab3ece102214" -ExpirationDate "9/1/2022"
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-remove-allow-or-block-entries-for-files-from-the-tenant-allowblock-list"></a>Microsoft 365 Defender ポータルを使用して、テナント許可/ブロック リストからファイルの許可エントリまたはブロック エントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **ファイル** ] タブを選択します。

3. [ **ファイル** ] タブで、次のいずれかの手順を実行します。

   - 削除するエントリのチェック ボックスをオンにし、[削除] アイコンを ![クリックします。](../../media/m365-cc-sc-delete-icon.png) **表示される削除** アイコン。
   - チェック ボックス以外の行の任意の場所をクリックして、削除するエントリを選択します。 表示される詳細ポップアップで、[削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **Delete**

4. 表示される警告ダイアログで、[削除] をクリック **します**。

> [!NOTE]
> 複数のエントリを選択するには、各チェック ボックスをオンにするか、 **値** 列ヘッダーの横にあるチェック ボックスをオンにしてすべてのエントリを選択します。

### <a name="use-powershell-to-remove-allow-or-block-entries-for-files-from-the-tenant-allowblock-list"></a>PowerShell を使用して、テナント許可/ブロックリストからファイルの許可エントリまたはブロック エントリを削除する

[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType FileHash <-Ids <Identity value> | -Entries <Value value>>
```

次の使用例は、指定したファイル ブロックをテナント許可/ブロック リストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType FileHash -Entries "27c5973b2451db9deeb01114a0f39e2cbcd2f868d08cedb3e210ab3ece102214"
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="related-articles"></a>関連記事

- [送信ポータルを使用して、疑わしいスパム、フィッシング、URL、ブロックされる正当なメール、および電子メールの添付ファイルを Microsoft に送信する](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナントの許可/ブロック一覧で電子メールを許可またはブロックする](allow-block-email-spoof.md)
- [テナント許可/ブロック リストの URL を許可またはブロックする](allow-block-urls.md)
