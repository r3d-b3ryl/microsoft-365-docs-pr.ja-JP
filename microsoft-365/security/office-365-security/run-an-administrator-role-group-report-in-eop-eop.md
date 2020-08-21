---
title: スタンドアロン EOP で管理者役割グループ レポートを実行する
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
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) で管理者の役割グループ レポートを実行する方法を学習できます。 このレポートは、管理者が管理者役割グループのメンバーを追加または削除すると、それぞれの発生箇度をログに取り示します。
ms.openlocfilehash: db1934c7865209d358d164ff5165bb23026589cc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827507"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a>スタンドアロン EOP で管理者役割グループ レポートを実行する

Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織では、管理者が管理役割グループのメンバーの追加または削除を行えると、そのサービスによってそれぞれの発生をログに格納します。 スタンドアロン EOP の役割グループの詳細については、「スタンドアロン EOP の [アクセス許可」を参照してください](feature-permissions-in-eop.md)。

Exchange 管理センター (EAC) で管理者の役割グループ レポートを実行すると、エントリが検索結果として表示されます。各エントリには、影響を受ける役割グループ、役割グループのメンバーシップを変更したユーザー、およびメンバーシップの更新が実行された日時が含まれます。 このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可の変更を監視します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange 管理センターを開くには、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定で ComplianceManagement、OrganizationManagement (グローバル管理者)、および SecurityAdministrator 役割グループに割り当てる "Audit Logs/監査ログ" 役割または "View-Only Audit Logs/監査ログ収集のみ" 役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>EAC を使用して管理者役割グループ レポートを実行する

管理者役割グループ レポートを実行して、特定の期間に組織の管理役割グループに加えられた変更を確認します。

1. EAC で、コンプライアンス管理 **の監査に** \> **移動し、** 管理者の役割 **グループ レポートの実行を選択します**。

2. 表示された **管理者の役割グループに対する変更の** 検索で、以下の設定を行います。

   - **[開始日** ] **と [終了日**] : 日付範囲を入力します。 既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。

   - **役割グループの選択**: 既定では、すべての役割グループが検索されます。 特定の役割グループに対して結果をフィルター処理するには、[ **役割グループの選択] をクリックします**。 表示されるダイアログで、役割グループを選択して [Add ->]**をクリック>。 ** 必要な回数だけこの手順を繰り返し、完了したら **[OK]** をクリックします。

3. 完了したら、[検索] をクリック **します**。

指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。

## <a name="monitor-changes-to-role-group-membership"></a>役割グループのメンバーシップに対する変更の監視

役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。

ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。

> 2018/1/27 4:43 PM <br> 管理者 <br> Updated members: Administrator;annb,florencef;pilarp <br> 2018/2/06 午前 10:09 <br> 管理者 <br> Updated members: Administrator;annb;florencef;pilarp;tonip <br> 2018/2/19 2:12 PM <br> 管理者 <br> Updated members: Administrator;annb;florencef;tonip

この例では、管理者ユーザー アカウントによって次の変更が加えられています。

- 2018 年 2 月 6 日に、ユーザー tonip が追加されました。

- 2018 年 2 月 19 日に、ユーザー pilarp が削除されました。

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a>スタンドアロンの Exchange Online PowerShell を使用して監査ログ エントリを検索する

Exchange Online PowerShell を使用して、指定した条件に合う監査ログ エントリを検索できます。 検索条件の一覧については [、「Search-AdminAuditLog 検索条件」を参照してください](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#search-adminauditlog-cmdlet)。 この手順では **Search-AdminAuditLog コマンドレットを使用** し、Exchange Online PowerShell に検索結果を表示します。 このコマンドレットは、 **New-AdminAuditLogSearch** コマンドレットまたは EAC 監査レポートのレポートで定義されている制限値を超える結果セットを返す必要がある場合に使用できます。

指定した条件で監査ログを検索するには、次の構文を使用します。

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> **Search-AdminAuditLog** コマンドレットを実行すると、既定で最大 1,000 個のログ エントリが返されます。 _ResultSize パラメーターを使用_して、最大 250,000 のログ エントリを指定します。 または、この値を使用 `Unlimited` してすべてのエントリを返します。

この例では、次の条件を使用してすべての監査ログ エントリで検索を実行します。

- **開始日**: 2018 年 8 月 4 日

- **終了日**: 2018 年 10 月 3 日

- **ユーザー ID**: davids、chrisd、kima

- **コマンドレット**: **Set-Mailbox**

- **パラメーター**: ProhibitSendQuota、ProhibitSendReceiveQuota、IssueWarningQuota、MaxSendSize _、MaxReceiveSize_ _ProhibitSendQuota_ _ProhibitSendReceiveQuota_ _IssueWarningQuota_ _MaxSendSize_

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

この例では、特定のメールボックスの変更を検索します。これは、トラブルシューティングを実行している場合や、調査のために情報を入手する必要がある場合に便利です。次の条件を使用します。

- **開始日**: 2018 年 5 月 1 日

- **終了日**: 2018 年 10 月 3 日

- **オブジェクト ID**: contoso.com/Users/DavidS

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

検索の結果返されるログ エントリが多い場合は **、Exchange Online PowerShell を使用して監査** ログ エントリを検索し、その結果を受信者に送信する方法をお勧めします。 その手順を実行すると、指定した受信者に XML ファイルが電子メールの添付ファイルとして送信されるため、目的のデータをより簡単に抽出することができます。

構文およびパラメーターの詳細については、「[Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)」を参照してください。

### <a name="view-details-of-audit-log-entries"></a>監査ログ エントリの詳細を表示する

**Search-AdminAuditLog コマンドレットは**、監査ログの内容に記述されている[フィールドを返します](https://docs.microsoft.com/Exchange/policy-and-compliance/admin-audit-logging/admin-audit-logging#audit-log-contents)。 コマンドレットによって返されるフィールドのうち、 **CmdletParameters** と **ModifiedProperties** の 2 つのフィールドには、既定では表示できない追加情報が含まれます。

**CmdletParameters** フィールドと **ModifiedProperties** フィールドの内容を表示するには、次の手順を実行します。 または **、Exchange Online PowerShell を使用して監査** ログ エントリを検索し、結果を受信者に送信できます。この操作を行うには、このトピックの後半で説明した XML ファイルを作成します。

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
