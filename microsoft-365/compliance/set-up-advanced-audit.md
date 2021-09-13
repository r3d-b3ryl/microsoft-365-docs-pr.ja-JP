---
title: '[高度な監査] を [Microsoft 365'
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: この記事では、ユーザー アカウントが侵害された場合に法医学調査を実行したり、他のセキュリティ関連のインシデントを調査したりするために高度な監査を設定する方法について説明します。
ms.openlocfilehash: 45eef36cd0577708869846308c88f2dd0926d43e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216454"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>[高度な監査] を [Microsoft 365

組織に高度な監査をサポートするサブスクリプションとエンド ユーザー ライセンスがある場合は、次の手順を実行して、Advanced Audit の追加機能を設定して使用します。

![高度な監査を設定するためのワークフロー。](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>手順 1: ユーザーの高度な監査を設定する

MailItemsAccessed や Send などの重要なイベントをログに記録する機能などの高度な監査機能を使用するには、ユーザーに適切な E5 ライセンスが割り当てられている必要があります。 さらに、それらのユーザーに対して高度な監査アプリ/サービス プランを有効にする必要があります。 高度な監査アプリがユーザーに割り当てられていることを確認するには、ユーザーごとに次の手順を実行します。

1. [ユーザー] Microsoft 365 管理センター[アクティブな **ユーザー**] に  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**移動**</a>し、ユーザーを選択します。

2. ユーザー プロパティのポップアップ ページで、**[ライセンスとアプリ]** をクリックします。

3. [ライセンス **] セクション** で、ユーザーに E5 ライセンスが割り当てられているか、適切なアドオン ライセンスが割り当てられているか確認します。 高度な監査をサポートするライセンスの一覧については、「 [高度な監査ライセンス要件」を参照してください](auditing-solutions-overview.md#advanced-audit-1)。

4. **[アプリ]** セクションを展開して、**[Microsoft 365 高度な監査]** チェック ボックスが選択されていることを確認します。

5. チェック ボックスが選択されていない場合は、チェック ボックスをオンにして、[変更の保存] **をクリックします。**

   MailItemsAccessed と Send の監査レコードのログ記録は、24 時間以内に開始されます。 手順 3 を実行して、他の 2 つの高度な監査イベント (SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint) のログ記録を開始する必要があります。

グループ ベースのライセンスを使用してユーザーのグループにライセンスを割り当てている組織では、グループに対する Microsoft 365 Advanced Auditing のライセンス割り当てをオフにする必要があります。 変更を保存したら、Microsoft 365 Advanced Auditing がグループに対してオフになっていることを確認します。 その後、グループに対するライセンス割り当てをもう一度オンにします。 グループ ベースのライセンスの手順については、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。

また、ユーザー メールボックスまたは共有メールボックスにログオンしているメールボックスアクションをカスタマイズした場合、Microsoft がリリースした新しい Advanced Audit イベントは、それらのメールボックスで自動的に監査されません。 ログオンの種類ごとに監査されるメールボックス操作の変更については、 「[メールボックスの監査を管理する](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)」の「既定でログに記録されるメールボックスの操作を変更または復元する」セクションを参照してください。

## <a name="step-2-enable-advanced-audit-events"></a>手順 2: 高度な監査イベントを有効にする

ユーザーが Exchange Online と SharePoint Online で検索を実行するときに、2 つの Advanced Audit イベント (SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint) をログに記録する必要があります。 これらの 2 つのイベントをユーザーに対して監査するには、PowerShell で次のコマンド (ユーザーごとに)[をExchange Onlineします](/powershell/exchange/connect-to-exchange-online-powershell)。

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

複数地域環境では、ユーザーのメールボックスがあるフォレストで前の **Set-Mailbox** コマンドを実行する必要があります。 ユーザーのメールボックスの場所を特定するには、次のコマンドを実行します。 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

検索クエリの監査を有効にするコマンドが以前は、ユーザーのメールボックスが存在するフォレストとは異なるフォレストで実行されている場合は、実行してユーザーのメールボックスから SearchQueryInitiated 値を削除し、ユーザーのメールボックスがあるフォレスト内のユーザーのメールボックスに追加する必要があります。 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}`

## <a name="step-3-set-up-audit-retention-policies"></a>手順 3: 監査保持ポリシーを設定する

Exchange、SharePoint、および Azure AD の監査記録を 1 年間保持する既定のポリシーに加えて、組織のセキュリティ運用チーム、IT チーム、およびコンプライアンス チームの要件に合わせて、監査ログの保持ポリシーを追加で作成することができます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="step-4-search-for-advanced-audit-events"></a>手順 4: 高度な監査イベントを検索する

組織に対して高度な監査が設定されたので、高度な監査の重要なイベントや他のアクティビティを検索して、捜査を実施できます。 手順 1 と手順 2 を完了すると、侵害されたアカウントや他の種類のセキュリティまたはコンプライアンス調査の法医学調査中に、監査ログで高度な監査イベントや他のアクティビティを検索できます。 MailItemsAccessed Advanced Audit イベントを使用して侵害されたユーザー アカウントの forensics 調査を実行する方法の詳細については、「高度な監査を使用して侵害されたアカウントを調査する」を参照 [してください](mailitemsaccessed-forensics-investigations.md)。
