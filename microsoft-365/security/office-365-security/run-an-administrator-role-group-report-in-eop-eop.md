---
title: スタンドアロン EOP で管理者の役割グループ レポートを実行する
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
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者の役割グループ レポートを実行する方法について説明します。 このレポートは、管理者が管理者役割グループにメンバーを追加または削除するとログに記録されます。
ms.openlocfilehash: cd7ca13a3d863240a0f2608ed13321cbe3d50ad2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659289"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>スタンドアロン EOP で管理者の役割グループ レポートを実行する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、管理者が管理役割グループにメンバーを追加または削除すると、サービスは各発生をログに記録します。 スタンドアロン EOP の役割グループの詳細については、「 [スタンドアロン EOP のアクセス許可」を参照してください](feature-permissions-in-eop.md)。

Exchange 管理センター (EAC) で管理者役割グループ レポートを実行すると、エントリが検索結果として表示され、影響を受ける役割グループ、役割グループのメンバーシップを変更したユーザー、いつ、どのようなメンバーシップの更新が行われたかが含まれます。 このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可に対する変更を監視します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- Exchange 管理センターを開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- この記事の手順を実行する前に、Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理、およびセキュリティ管理者の役割グループに割り当てられる監査ログまたは表示専用の監査ログの役割が必要です。  詳細については、「スタンドアロン [EOP のアクセス許可](feature-permissions-in-eop.md) 」および「EAC を使用して役割グループのメンバーの一覧 [を変更する」を参照してください](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- この記事の手順に適用できるキーボード ショートカットの詳細については [、Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)の Exchange 管理センターのキーボード ショートカットを参照してください。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>EAC を使用して管理者役割グループ レポートを実行する

管理者役割グループ レポートを実行して、特定の時間枠内の管理役割グループに対する変更を検索します。

1. EAC で、**コンプライアンス管理の** 監査に移動し、[管理者の役割グループ レポートの実行] \> **を選択します**。

2. 開く **[管理者の役割グループに対する変更の検索** ] ページで、次の設定を構成します。

   - **開始日と** 終了日 : **日付** 範囲を入力します。 既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。

   - **役割グループの選択**: 既定では、すべての役割グループが検索されます。 特定の役割グループで結果をフィルター処理するには、[役割グループの選択] **をクリックします**。 表示されるダイアログで、役割グループを選択し、[追加] **->。** 必要な回数この手順を繰り返し、完了したら **[OK]** をクリックします。

3. 完了したら、[検索] をクリック **します**。

指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。

## <a name="monitor-changes-to-role-group-membership"></a>役割グループのメンバーシップに対する変更の監視

役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。

ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。

> 2018 年 1 月 27 日午後 4 時 43 分 <br> 管理者 <br> Updated members: Administrator;annb,florencef;pilarp <br> 2018/2/06 10:09 AM <br> 管理者 <br> Updated members: Administrator;annb;florencef;pilarp;tonip <br> 2018/2/19 14:12 <br> 管理者 <br> Updated members: Administrator;annb;florencef;tonip

この例では、管理者ユーザー アカウントによって次の変更が加えられています。

- 2018 年 2 月 6 日に、ユーザー tonip を追加しました。
- 2018 年 2 月 19 日に、ユーザー pilarp が削除されました。

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>スタンドアロンの Exchange Online PowerShell を使用して監査ログ エントリを検索する

Exchange Online PowerShell を使用して、指定した条件に一致する監査ログ エントリを検索できます。 検索条件の一覧については [、「Search-AdminAuditLog 検索条件」を参照してください](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。 この手順では **、Search-AdminAuditLog** コマンドレットを使用して、Exchange Online PowerShell で検索結果を表示します。 このコマンドレットは、 **New-AdminAuditLogSearch** コマンドレットまたは EAC 監査レポートのレポートで定義されている制限値を超える結果セットを返す必要がある場合に使用できます。

指定した条件で監査ログを検索するには、次の構文を使用します。

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> **Search-AdminAuditLog** コマンドレットを実行すると、既定で最大 1,000 個のログ エントリが返されます。 _ResultSize パラメーターを使用_ して、最大 250,000 のログ エントリを指定します。 または、値を使用して `Unlimited` すべてのエントリを返します。

この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。

- **開始日 :** 2018 年 8 月 4 日
- **終了日 :** 2018 年 10 月 3 日
- **ユーザー ID**: `davids` `chrisd` , , `kima`
- **コマンドレット**: **Set-Mailbox**
- **Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

この例では、特定のメールボックスの変更を検索します。これは、トラブルシューティングを実行している場合や、調査のために情報を入手する必要がある場合に便利です。次の条件を使用します。

- **開始日 :** 05/01/2018
- **終了日 :** 2018 年 10 月 3 日
- **オブジェクト ID**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

検索で多数のログ エントリが返される場合は **、「Exchange Online PowerShell** を使用する」の手順を使用して監査ログ エントリを検索し、後で受信者に結果を送信することをお勧めします。 その手順を実行すると、指定した受信者に XML ファイルが電子メールの添付ファイルとして送信されるため、目的のデータをより簡単に抽出することができます。

構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。

### <a name="view-details-of-audit-log-entries"></a>監査ログ エントリの詳細を表示する

**Search-AdminAuditLog** コマンドレットは、監査ログの内容で説明されている [フィールドを返します](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)。 コマンドレットによって返されるフィールドのうち、 **CmdletParameters** と **ModifiedProperties** の 2 つのフィールドには、既定では表示できない追加情報が含まれます。

**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。 または **、「Exchange Online PowerShell** を使用する」の手順を使用して監査ログ エントリを検索し、後で受信者に結果を送信して XML ファイルを作成することもできます。

この手順では、次の概念を使用します。

- [about_Arrays](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [about_Variables](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

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
