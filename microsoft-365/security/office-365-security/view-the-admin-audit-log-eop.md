---
title: 管理者監査ログをスタンドアロン EOP で表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者監査ログの表示と検索を行う方法を学習できます。
ms.openlocfilehash: 8890ab8f2f2db01ed6bd22657a9bea8f77b25d08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825079"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>管理者監査ログをスタンドアロン EOP で表示する

Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell を使用して管理者監査ログ内のエントリを検索および表示できます。

管理者監査ログには、管理者や管理者特権を割り当てられたユーザーが実行するスタンドアロン EOP PowerShell コマンドレットに基づく特定の操作が記録されます。 管理者監査ログのエントリは、実行されたコマンドレット、使われたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報を提供します。

> [!NOTE]
>
> - 管理者監査ログ出力は既定では有効になっており、無効にできません。
>
> - 管理者監査ログには、動詞 **Get、Search、Test**で始まるコマンドレットに基 **づく操作**は記録 **されないからです**。
>
> - 監査ログのエントリは 90 日間維持されます。 90 日間の保存期間を過ぎるエントリは削除されます

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センターを開くには、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定で ComplianceManagement、OrganizationManagement (グローバル管理者)、および SecurityAdministrator 役割グループに割り当てる "Audit Logs/監査ログ" 役割または "View-Only Audit Logs/監査ログ収集のみ" 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>EAC を使用して管理者監査ログを表示する

1. EAC で、コンプライアンス管理 **の監査に** \> **移動し、** 管理者監査ログ **レポートの実行を選択します**。

2. 開いた **管理者の役割グループに対する変更の** 検索で、[ **開始** 日と **終了** 日] を選択し (既定の範囲は、前の 2 週間です)、[検索] を **選みます**。 次の情報を使用して、指定した期間中に行われたすべての構成の変更が表示され、並べ替えの対象となったりできます。

   - **日付**: 構成の変更が行われた日時です。 日時は、世界協定時刻 (UTC) 形式で格納されます。

   - **コマンドレット**: 構成変更に使用されたコマンドレットの名前。

   - **User**: 構成の変更を行ったユーザーのユーザー アカウント名。

     最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。

   - **オブジェクトが**変更されました。コマンドレットによって変更されたオブジェクト。

   - **パラメーター (パラメーター:値)**: 使用されたコマンドレット パラメーターと、そのパラメーターで指定された値。

3. 特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>スタンドアロン EOP PowerShell を使用して管理者監査ログを表示する

スタンドアロンの EOP PowerShell を使用して、指定した条件に合う監査ログ エントリを検索できます。 次の構文を使用してください。

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**注**:

- Cmdlets パラメーターと _共に_ パラメーターパラメーター _のみを使用_ できます。

- _ObjectIds パラメーター_は、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。 有効な値は、オブジェクトが監査ログでの表される方法に依存します。 例:

  - Name
  - 正規の識別名 (たとえば、Al-Zuhairi contoso.com/Users/Akia)

  結果を絞り込み、目的のオブジェクトの種類を特定するには、このコマンドレットで他のフィルター処理パラメーターを使用する必要があります。

- _UserIds パラメーターは_、(コマンドレットを実行したユーザー) 変更を行ったユーザーによって結果をフィルター処理します。

- _StartDate および_ _EndDate_パラメーターに対しては、タイム ゾーンのない日付/時刻値を指定すると、値は協定世界時 (UTC) になります。 このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。

  - UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z

  - 日付/時刻の値を、ローカル タイム ゾーンの日付/時刻を UTC に変換する数式として指定する (例: `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` . 詳細については、「[Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)」を参照してください。

- このコマンドレットを実行すると、既定で最大 1,000 個のログ エントリが返されます。 _ResultSize パラメーターを使用_して、最大 250,000 のログ エントリを指定します。 または、この値を使用 `Unlimited` してすべてのエントリを返します。

この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。

- **開始日**: 2019 年 8 月 4 日
- **終了日**: 2019 年 10 月 3 日
- **コマンドレット**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。

### <a name="view-details-of-audit-log-entries"></a>監査ログ エントリの詳細を表示する

**Search-AdminAuditLog コマンドレットは**、このトピックで後述する監査[ログの内容セクションで説明](#audit-log-contents)されているフィールドを返します。 コマンドレットによって返されるフィールドの **、CmdletParameters** と **ModifiedProperties**の 2 つのフィールドには、既定では返されず、追加情報が含まれます。

**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。

1. 検索条件を決定して **Search-AdminAuditLog** コマンドレットを実行し、次のコマンドを使用してその結果を変数に格納します。

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. 各監査ログ エントリは、変数に配列要素として格納されます `$Results` 。 配列要素のインデックスを指定することで、配列要素を選択できます。 配列要素のインデックスは、最初の配列要素のゼロ (0) から始まります。 たとえば、5 番目の配列要素 (インデックスは 4) を取得するには、次のコマンドを使用します。

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

****

|Field|説明|
|---|---|
|`RunspaceId`|このフィールドは、EOP によって内部的に使用されます。|
|`ObjectModified`|このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含 `CmdletName` まれます。|
|`CmdletName`|このフィールドには、フィールド内のユーザーによって実行されたコマンドレットの名前が含 `Caller` まれます。|
|`CmdletParameters`|このフィールドには、フィールドのコマンドレットが実行されるときに指定されたパラメーター `CmdletName` が含まれます。 パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。|
|`ModifiedProperties`|このフィールドには、フィールド内のオブジェクトで変更されたプロパティが含 `ObjectModified` まれます。 プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。|
|`Caller`|このフィールドには、フィールドのコマンドレットを実行したユーザーのユーザー アカウントが含 `CmdletName` まれます。|
|`ExternalAccess`|このフィールドは、EOP によって内部的に使用されます。|
|`Succeeded`|このフィールドは、フィールドのコマンドレットが正常 `CmdletName` に実行されたかどうかを示します。 値は、1 つまたは `True` 2 つです `False` 。|
|`Error`|このフィールドには、フィールド内のコマンドレットが正常に完了しなかった場合 `CmdletName` に生成されるエラー メッセージが含まれます。|
|`RunDate`|このフィールドには、フィールドのコマンドレットが実行された日時 `CmdletName` が含まれます。 日時は、世界協定時刻 (UTC) 形式で格納されます。|
|`OriginatingServer`|このフィールドは、フィールドで指定されたコマンドレットが実行されたサーバー `CmdletName` を示します。|
|`ClientIP`|このフィールドは、EOP によって内部的に使用されます。|
|`SessionId`|このフィールドは、EOP によって内部的に使用されます。|
|`AppId`|このフィールドは、EOP によって内部的に使用されます。|
|`ClientAppId`|このフィールドは、EOP によって内部的に使用されます。|
|`Identity`|このフィールドは、EOP によって内部的に使用されます。|
|`IsValid`|このフィールドは、EOP によって内部的に使用されます。|
|`ObjectState`|このフィールドは、EOP によって内部的に使用されます。|
|
