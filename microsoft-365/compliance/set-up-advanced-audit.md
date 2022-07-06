---
title: Microsoft 365 で監査 (Premium) を設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: この記事では、ユーザー アカウントが侵害されたときにフォレンジック調査を実行したり、他のセキュリティ関連のインシデントを調査したりできるように、監査 (Premium) を設定する方法について説明します。
ms.openlocfilehash: adffd696a3eca2d51fb5325cd79c1ba26e58936c
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639338"
---
# <a name="set-up-microsoft-purview-audit-premium"></a>Microsoft Purview 監査を設定する (Premium)

組織に監査 (Premium) をサポートするサブスクリプションとエンド ユーザー ライセンスがある場合は、次の手順に従って、監査 (Premium) の追加機能を設定して使用します。

![監査 (プレミアム) を設定するためのワークフロー。](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-audit-premium-for-users"></a>手順 1: ユーザーの監査 (Premium) を設定する

MailItemsAccessed や Send などの重要なイベントをログに記録する機能などの監査 (プレミアム) 機能を使用するには、ユーザーに適切な E5 ライセンスが割り当てられている必要があります。 さらに、それらのユーザーに対して高度な監査アプリ/サービス プランを有効にする必要があります。 高度な監査アプリがユーザーに割り当てられていることを確認するには、ユーザーごとに次の手順を実行します。

1. Microsoft 365 管理センターで、[**ユーザー** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**のアクティブなユーザー**</a>] に移動し、ユーザーを選択します。

2. ユーザー プロパティのポップアップ ページで、**[ライセンスとアプリ]** をクリックします。

3. [ **ライセンス** ] セクションで、ユーザーに E5 ライセンスが割り当てられているか、適切なアドオン ライセンスが割り当てられていることを確認します。 監査 (Premium) をサポートするライセンスの一覧については、 [監査 (Premium) のライセンス要件に関するページを](auditing-solutions-overview.md#audit-premium-1)参照してください。

4. **[アプリ]** セクションを展開して、**[Microsoft 365 高度な監査]** チェック ボックスが選択されていることを確認します。

5. チェック ボックスがオンになっていない場合は、それを選択し、[変更の **保存]** をクリックします。

   MailItemsAccessed と Send の監査レコードのログ記録は、24 時間以内に開始されます。 他の 2 つの監査 (Premium) イベント (SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint) のログ記録を開始するには、手順 3 を実行する必要があります。

また、ユーザー メールボックスまたは共有メールボックスにログオンするメールボックスアクションをカスタマイズした場合、Microsoft によってリリースされた新しい監査 (Premium) イベントは、それらのメールボックスに対して自動的に監査されません。 ログオンの種類ごとに監査されるメールボックス操作の変更については、 「[メールボックスの監査を管理する](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)」の「既定でログに記録されるメールボックスの操作を変更または復元する」セクションを参照してください。

## <a name="step-2-enable-audit-premium-events"></a>手順 2: 監査 (Premium) イベントを有効にする

ユーザーがExchange Onlineと SharePoint Online で検索を実行するときに、2 つの監査 (Premium) イベント (SearchQueryInitiatedExchange と SearchQueryInitiatedSharePoint) をログに記録する必要があります。 これらの 2 つのイベントをユーザーに対して監査できるようにするには、[powerShell](/powershell/exchange/connect-to-exchange-online-powershell) で (ユーザーごとに) 次のコマンドExchange Online実行します。

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

複数地域環境では、ユーザーのメールボックスがあるフォレストで、前の **Set-Mailbox** コマンドを実行する必要があります。 ユーザーのメールボックスの場所を特定するには、次のコマンドを実行します。 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

検索クエリの監査を有効にするコマンドが、ユーザーのメールボックスとは異なるフォレストで以前に実行されていた場合は、実行 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` してユーザーのメールボックスから SearchQueryInitiated 値を削除し、ユーザーのメールボックスがあるフォレスト内のユーザーのメールボックスに追加する必要があります。

## <a name="step-3-set-up-audit-retention-policies"></a>手順 3: 監査アイテム保持ポリシーを設定する

Exchange、SharePoint、および Azure AD の監査記録を 1 年間保持する既定のポリシーに加えて、組織のセキュリティ運用チーム、IT チーム、およびコンプライアンス チームの要件に合わせて、監査ログの保持ポリシーを追加で作成することができます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="step-4-search-for-audit-premium-events"></a>手順 4: 監査 (Premium) イベントを検索する

組織に監査 (Premium) を設定したので、フォレンジック調査を行う際に重要な監査 (Premium) イベントやその他のアクティビティを検索できます。 手順 1 と手順 2 を完了すると、侵害されたアカウントやその他の種類のセキュリティまたはコンプライアンス調査のフォレンジック調査中に、監査 (Premium) イベントやその他のアクティビティについて監査ログを検索できます。 MailItemsAccessed Audit (Premium) イベントを使用して侵害されたユーザー アカウントのフォレンジック調査を行う方法の詳細については、「 [監査 (Premium) を使用して侵害されたアカウントを調査する」を](mailitemsaccessed-forensics-investigations.md)参照してください。
