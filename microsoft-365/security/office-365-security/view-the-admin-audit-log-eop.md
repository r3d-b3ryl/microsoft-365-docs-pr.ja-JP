---
title: スタンドアロン EOP で管理者監査ログを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 管理者は、スタンドアロン 監査ログ (EOP) で管理者監査ログを表示およびExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205043"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a>スタンドアロン EOP で管理者監査ログを表示する

**適用対象**
- [Exchange Online Protectionスタンドアロン](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織では、Exchange 管理センター (EAC) またはスタンドアロン EOP PowerShell を使用して、管理監査ログ内のエントリを検索および表示できます。

管理者監査ログには、管理者および管理者特権が割り当てられているユーザーによって実行されるスタンドアロン EOP PowerShell コマンドレットに基づいて、特定のアクションが記録されます。 管理者監査ログのエントリには、実行されたコマンドレット、使用されたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報が提供されます。

> [!NOTE]
>
> - 管理者監査ログは既定で有効になっているので、無効にすることはできません。
>
> - 管理者監査ログは、動詞 Get、Search、または Test で始まるコマンドレットに基づいてアクションを記録 **します**。
>
> - 監査ログのエントリは 90 日間維持されます。 エントリが 90 日を超える場合、そのエントリは削除されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 管理センターを開Exchange、スタンドアロン[EOP Exchange管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Online Protectionにアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理、およびセキュリティ管理者の役割グループに割り当てられている監査ログまたはビュー専用監査ログの役割が必要です。  詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。

- この記事の手順 Exchangeに適用されるキーボード ショートカットの詳細については、「Exchange Online の管理センターのキーボード ショートカット」[を参照Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-view-the-admin-audit-log"></a>EAC を使用して管理監査ログを表示する

1. EAC で、[コンプライアンス管理の監査] に移動し、[管理者監査ログ レポートの実行 \> **] を選択します**。

2. 開いた **[管理者役割グループ** への変更の検索] ページで、[開始日] と **[終了日**] (既定の範囲は過去 2 週間) を選択し、[検索] を **選択します**。 指定した期間中に行われた構成変更はすべて表示され、次の情報を使用して並べ替えできます。

   - **日付**: 構成の変更が行われた日付と時刻。 日時は、世界協定時刻 (UTC) 形式で格納されます。

   - **コマンドレット**: 構成を変更するために使用されたコマンドレットの名前。

   - **User**: 構成を変更したユーザーのユーザー アカウントの名前。

     最大 5,000 エントリが複数のページに表示されます。結果を絞り込む必要がある場合は、指定する日付範囲を短くします。個々の検索結果を選択すると、詳細ウィンドウに次の追加情報が表示されます。

   - **変更されたオブジェクト**: コマンドレットによって変更されたオブジェクト。

   - **パラメーター (Parameter:Value)**: 使用されたコマンドレット パラメーターと、パラメーターで指定された任意の値。

3. 特定の監査ログ エントリを印刷するには、詳細ウィンドウの **[印刷]** ボタンを選択します。

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a>スタンドアロンの EOP PowerShell を使用して管理監査ログを表示する

スタンドアロン EOP PowerShell を使用して、指定した条件を満たす監査ログ エントリを検索できます。 次の構文を使用してください。

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

**注**:

- Parameters パラメーターは _、Cmdlets_ パラメーターと共 _にのみ使用_ できます。

- _ObjectIds パラメーターは_、コマンドレットによって変更されたオブジェクトによって結果をフィルター処理します。 有効な値は、オブジェクトが監査ログでどのように表されるのかによって異なります。 以下に例を示します。

  - 名前
  - 標準の識別名 (たとえば、al-Zuhairi contoso.com/Users/Akia)

  このコマンドレットで他のフィルター パラメーターを使用して結果を絞り込み、対象のオブジェクトの種類を特定する必要があります。

- _UserIds パラメーターは_、変更を行ったユーザー (コマンドレットを実行したユーザー) によって結果をフィルター処理します。

- _StartDate パラメーターと_ _EndDate_ パラメーターの場合、タイム ゾーンのない日付/時刻の値を指定すると、値は協定世界時 (UTC) になります。 このパラメーターの日付/時刻値を指定するには、次のいずれかのオプションを使用します。

  - UTC の日付/時刻値を指定する場合の例: 2016-05-06 14:30:00z

  - 日付/時刻の値を、ローカル タイム ゾーンの日付/時刻を UTC に変換する数式として指定します。たとえば、 を指定します `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 。 詳細については、「[Get-Date](/powershell/module/microsoft.powershell.utility/get-date)」を参照してください。

- コマンドレットは、既定で最大 1,000 のログ エントリを返します。 _ResultSize パラメーターを使用_ して、最大 250,000 のログ エントリを指定します。 または、値を使用して `Unlimited` すべてのエントリを返します。

この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。

- **開始日 :** 2019 年 8 月 4 日
- **終了日 :** 2019 年 10 月 3 日
- **コマンドレット**: Update-RoleGroupMember

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

構文およびパラメーターの詳細については、「[Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)」を参照してください。

### <a name="view-details-of-audit-log-entries"></a>監査ログ エントリの詳細を表示する

**Search-AdminAuditLog コマンドレットは**、この記事の後半の [](#audit-log-contents)「監査ログの内容」セクションで説明されているフィールドを返します。 コマンドレットによって返されるフィールドの中で **、CmdletParameters** と **ModifiedProperties** という 2 つのフィールドには、既定では返されていない追加情報が含まれています。

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
|`ObjectModified`|このフィールドには、フィールドで指定されたコマンドレットによって変更されたオブジェクトが含 `CmdletName` まれる。|
|`CmdletName`|このフィールドには、フィールド内のユーザーが実行したコマンドレットの名前が含 `Caller` まれる。|
|`CmdletParameters`|このフィールドには、フィールド内のコマンドレットの実行時に指定された `CmdletName` パラメーターが含まれます。 パラメーターで指定された値があれば、それもこのフィールドに格納されますが、既定の出力では表示されません。|
|`ModifiedProperties`|このフィールドには、フィールド内のオブジェクトで変更されたプロパティが含 `ObjectModified` まれる。 プロパティの以前の値と格納された新しい値も、このフィールドに格納されますが、既定の出力では表示されません。|
|`Caller`|このフィールドには、フィールドでコマンドレットを実行したユーザーのユーザー アカウントが含 `CmdletName` まれる。|
|`ExternalAccess`|このフィールドは、EOP によって内部的に使用されます。|
|`Succeeded`|このフィールドは、フィールド内のコマンドレットが正常に実行 `CmdletName` されたかどうかを指定します。 値は、 または `True` `False` です。|
|`Error`|このフィールドには、フィールド内のコマンドレットが正常に完了しなかった場合に生成 `CmdletName` されるエラー メッセージが含まれる。|
|`RunDate`|このフィールドには、フィールド内のコマンドレットが実行された日時 `CmdletName` が含まれる。 日時は、世界協定時刻 (UTC) 形式で格納されます。|
|`OriginatingServer`|このフィールドは、フィールドで指定されたコマンドレットが実行されたサーバー `CmdletName` を示します。|
|`ClientIP`|このフィールドは、EOP によって内部的に使用されます。|
|`SessionId`|このフィールドは、EOP によって内部的に使用されます。|
|`AppId`|このフィールドは、EOP によって内部的に使用されます。|
|`ClientAppId`|このフィールドは、EOP によって内部的に使用されます。|
|`Identity`|このフィールドは、EOP によって内部的に使用されます。|
|`IsValid`|このフィールドは、EOP によって内部的に使用されます。|
|`ObjectState`|このフィールドは、EOP によって内部的に使用されます。|
|