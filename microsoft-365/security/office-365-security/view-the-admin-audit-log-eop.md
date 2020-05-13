---
title: 管理者監査ログをスタンドアロン EOP で表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、管理者監査ログをスタンドアロンの Exchange Online Protection (EOP) で表示および検索する方法を学習できます。
ms.openlocfilehash: 3aedebc97ccd32c1641510017a276ddbe4770633
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208478"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>管理者監査ログをスタンドアロン EOP で表示する

Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell を使用して、管理者監査ログのエントリを検索して表示することができます。

管理者監査ログには、管理者や管理者特権が割り当てられているユーザーが実行したスタンドアロンの EOP PowerShell コマンドレットに基づいて、特定の操作が記録されます。 管理者監査ログのエントリは、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトについての情報を提供します。

> [!NOTE]
> <ul><li>管理者監査ログは既定で有効になっており、無効にすることはできません。</li><li>管理者監査ログには、 **Get**、 **Search**、または**Test**という動詞で始まるコマンドレットに基づいてアクションが記録されることはありません。</li><li>監査ログのエントリは 90 日間維持されます。 エントリが90日よりも古い場合は、削除されます。</li></ul>

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センターを開くには、「 [exchange admin center in STANDALONE EOP](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、ComplianceManagement、組織の管理 (グローバル管理者)、および SecurityAdministrator の役割グループに既定で割り当てられている監査ログまたは表示専用の監査ログの役割が必要です。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、[役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>EAC を使用して管理者監査ログを表示する

1. EAC で、[**コンプライアンス管理** \> ] [**監査**] に移動し、[**管理者監査ログレポートを実行**する] を選択します。

2. [**管理者の役割グループへの変更の検索**] ページが開いたら、**開始日**と**終了日**(既定の範囲は過去2週間) を選択し、[**検索**] を選択します。 指定した期間内に行われたすべての構成の変更が表示され、次の情報を使用して並べ替えることができます。

   - **日付**: 構成の変更が行われた日時。 日時は、世界協定時刻 (UTC) 形式で格納されます。

   - **コマンドレット**: 構成変更を行うために使用されたコマンドレットの名前。

   - **User**: 構成の変更を行ったユーザーのユーザーアカウントの名前。

     最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。

   - **変更**されたオブジェクト: コマンドレットによって変更されたオブジェクト。

   - **パラメーター (パラメーター: 値)**: 使用されたコマンドレットパラメーターと、パラメーターで指定された値。

3. 特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>スタンドアロンの EOP PowerShell を使用して管理者監査ログを表示する

スタンドアロンの EOP PowerShell を使用して、指定した条件に一致する監査ログエントリを検索できます。 次の構文を使用してください。

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**注**:

- _Parameters_パラメーターは、_コマンドレット_パラメーターと共にのみ使用できます。

- _Objectid_パラメーターは、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。 有効な値は、監査ログでのオブジェクトの表現方法によって異なります。 例:

  - 名前
  - 標準識別名 (たとえば、contoso.com/Users/Akia Al-Al-zuhairi)

  結果を絞り込んで、対象のオブジェクトの種類を特定するには、このコマンドレットの他のフィルター処理パラメーターを使用する必要があります。

- _UserIds_パラメーターは、変更を行ったユーザー (コマンドレットを実行したユーザー) によって結果をフィルター処理します。

- _StartDate_パラメーターと_EndDate_パラメーターに対して、タイムゾーンを指定せずに日付/時刻値を指定すると、値は協定世界時 (UTC) になります。 このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。

  - UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z

  - 日付/時刻値を、ローカルタイムゾーンの日付/時刻を UTC に変換する数式として指定します (例:) `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。 詳細については、「[Get-Date](https://go.microsoft.com/fwlink/p/?LinkID=113313)」を参照してください。

- コマンドレットは、既定で最大1000個のログエントリを返します。 _Resultsize_パラメーターを使用して、最大25万のログエントリを指定します。 または、値を使用して `Unlimited` すべてのエントリを返します。

この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。

- **開始日**: 2019 年8月4日
- **終了日**: 2019 年10月3日
- **コマンドレット**: add-rolegroupmember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)」を参照してください。

### <a name="view-details-of-audit-log-entries"></a>監査ログ エントリの詳細を表示する

**検索-Adminauditlog**コマンドレットは、このトピックで後述する「[監査ログの内容](#audit-log-contents)」セクションで説明されているフィールドを返します。 コマンドレットによって返されるフィールドの2つのフィールド、 **ModifiedProperties** **parameters**およびには、既定では返されない追加情報が含まれています。

**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。

1. 検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 各監査ログエントリは、変数に配列要素として格納され `$Results` ます。 配列要素のインデックスを指定することで、配列要素を選択できます。 配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。 たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。

    ```PowerShell
    $Results[4]
    ```

3. 上記のコマンドを実行すると、配列要素 4 に格納されているログ エントリが返されます。このログ エントリの **CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次のコマンドを使用します。

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. **CmdletParameters** フィールドや **ModifiedParameters** フィールドの内容を別のログ エントリに表示するには、配列要素のインデックスを変更します。

## <a name="audit-log-contents"></a>監査ログの内容

それぞれの監査ログ エントリには、次の表に記載されている情報が含まれます。 監査ログには、1 つまたは複数の監査ログ エントリが含まれています。

|||
|---|---|
|**Field**|**説明**|
|`RunspaceId`|このフィールドは、EOP によって内部的に使用されます。|
|`ObjectModified`|このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含まれてい `CmdletName` ます。|
|`CmdletName`|このフィールドには、フィールド内のユーザーによって実行されたコマンドレットの名前が含まれてい `Caller` ます。|
|`CmdletParameters`|このフィールドには、フィールドのコマンドレットの実行時に指定されたパラメーターが含まれてい `CmdletName` ます。 パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。|
|`ModifiedProperties`|このフィールドには、フィールドのオブジェクトで変更されたプロパティが含まれてい `ObjectModified` ます。 プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。|
|`Caller`|このフィールドには、フィールドでコマンドレットを実行したユーザーのユーザーアカウントが含まれてい `CmdletName` ます。|
|`ExternalAccess`|このフィールドは、EOP によって内部的に使用されます。|
|`Succeeded`|このフィールドでは、フィールドのコマンドレットが正常に実行されたかどうかを指定し `CmdletName` ます。 値はまたはのいずれか `True` `False` です。|
|`Error`|このフィールドには、フィールドのコマンドレットが正常に完了しなかった場合に生成されるエラーメッセージが含まれてい `CmdletName` ます。|
|`RunDate`|このフィールドには、フィールドのコマンドレットが実行された日付と時刻が含まれてい `CmdletName` ます。 日時は、世界協定時刻 (UTC) 形式で格納されます。|
|`OriginatingServer`|このフィールドは、フィールドに指定されたコマンドレットが実行されたサーバーを示し `CmdletName` ます。|
|`ClientIP`|このフィールドは、EOP によって内部的に使用されます。|
|`SessionId`|このフィールドは、EOP によって内部的に使用されます。|
|`AppId`|このフィールドは、EOP によって内部的に使用されます。|
|`ClientAppId`|このフィールドは、EOP によって内部的に使用されます。|
|`Identity`|このフィールドは、EOP によって内部的に使用されます。|
|`IsValid`|このフィールドは、EOP によって内部的に使用されます。|
|`ObjectState`|このフィールドは、EOP によって内部的に使用されます。|
|
