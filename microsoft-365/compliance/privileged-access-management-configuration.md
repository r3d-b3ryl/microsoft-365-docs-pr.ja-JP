---
title: 特権アクセス管理の使用を開始する
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: この記事では、Office 365 での特権アクセス管理の有効化と構成について説明します。
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126534"
---
# <a name="get-started-with-privileged-access-management"></a>特権アクセス管理の使用を開始する

このトピックでは、組織内で特権アクセス管理を有効にし、構成する方法について説明します。 Microsoft 365 管理センターまたは Exchange Management PowerShell を使用して、特権アクセスを管理および使用できます。

## <a name="before-you-begin"></a>開始する前に

特権アクセス管理を開始する前に [、Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) とアドオンを確認する必要があります。 特権アクセス管理にアクセスして使用するには、組織に次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5 サブスクリプション (有料版または試用版)
- Microsoft 365 E3 サブスクリプション (または Office 365 E3 サブスクリプション + Enterprise Mobility and Security E3 サブスクリプション) + Microsoft 365 E5 コンプライアンス アドオン
- Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for Business サブスクリプション + Microsoft 365 E5 Insider Risk Management アドオン  
- Microsoft 365 A5 サブスクリプション (有料版または試用版)
- Microsoft 365 A3 サブスクリプション (または Office 365 A3 サブスクリプション + Enterprise Mobility and Security A3 サブスクリプション) + Microsoft A5 コンプライアンス アドオン
- Microsoft 365、Office 365、Exchange、SharePoint、または OneDrive for Education サブスクリプション + Microsoft 365 A5 Insider Risk Management アドオン
- Office 365 Enterprise E5 サブスクリプション (有料版または試用版)
- Office 365 Enterprise E3 サブスクリプション + Office 365 Advanced Compliance アドオン (新しいサブスクリプションでは使用できなくなりました。注を参照)

特権アクセス管理要求を送信して応答するユーザーには、上記のいずれかのライセンスが割り当てられている必要があります。

>[!IMPORTANT]
>Office 365 Advanced Compliance は、スタンドアロン サブスクリプションとして販売されなくなりました。 現在のサブスクリプションの有効期限が切れた場合、お客様は上記のいずれかのサブスクリプションに移行する必要があります。このサブスクリプションには、同じまたは追加のコンプライアンス機能が含まれている必要があります。

既存の Office 365 Enterprise E5 プランをお持ちで、特権アクセス管理を試す場合は、既存の Office [365 サブスクリプションに Microsoft 365](/office365/admin/try-or-buy-microsoft-365)を追加[](https://www.microsoft.com/microsoft-365/enterprise)するか、Microsoft 365 Enterprise E5 の試用版にサインアップできます。

## <a name="enable-and-configure-privileged-access-management"></a>特権アクセス管理を有効にして構成する

組織内で特権アクセスを設定して使用するには、次の手順を実行します。

- [手順 1: 承認者のグループを作成する](privileged-access-management-configuration.md#step1)

    特権アクセスの使用を開始する前に、昇格されたタスクおよび権限のあるタスクへのアクセスを要求するための承認権限を必要とするユーザーを決定します。 承認者グループの一部であるユーザーは、アクセス要求を承認することができます。 このグループは、メールが有効なセキュリティ グループを Office 365 で作成することで有効になります。

- [手順 2: 特権アクセスを有効にする](privileged-access-management-configuration.md#step2)

    特権アクセスは、既定の承認者グループを使用して Office 365 で明示的に有効にする必要があります。これには、特権アクセス管理アクセス制御から除外する一連のシステム アカウントが含まれます。

- [手順 3: アクセス ポリシーを作成する](privileged-access-management-configuration.md#step3)

    承認ポリシーを作成すると、個々のタスクでスコープを設定する特定の承認要件を定義できます。 承認の種類のオプションは **自動** または **手動** です。

- [手順 4: 特権アクセス要求を送信/承認する](privileged-access-management-configuration.md#step4)

    有効にすると、特権アクセスは関連付けられた承認ポリシーが定義されているすべてのタスクにて承認が必要になります。 承認ポリシーに含まれるタスクの場合、タスクを実行するために必要なアクセス権限を持つには、ユーザーはアクセスを要求し、アクセスが許可されている必要があります。

承認が与えられると、アクセス要求したユーザーは目的のタスクを実行でき、特権アクセスはユーザーに代わってタスクを承認および実行します。 承認は、要求された期間 (既定の期間は 4 時間) にわたって有効で、その間依頼者は目的のタスクを複数回実行できます。 これらのすべての実行はログに記録され、セキュリティとコンプライアンスの監査で利用されます。 

>[!NOTE]
>Exchange Management PowerShell を使用して特権アクセスを有効にして構成する場合は、「多要素認証を使用して [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) に接続する」の手順に従って、Office 365 資格情報を使用して Exchange Online PowerShell に接続します。 Exchange Online PowerShell への接続中に特権アクセスを有効にする手順を使用するには、組織で多要素認証を有効にする必要があります。 多要素認証を使用して接続すると、要求に署名するために特権アクセスによって使用される OAuth トークンが作成されます。

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>手順 1: 承認者のグループを作成する

1. 組織内の管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. 管理センターで、[グループの追加 **]**  >  **に移動します**。

3. メール **が有効なセキュリティ** グループを選択し、新しいグループの [名前 **]、[グループの電子** メール アドレス]、および **[** 説明] フィールドに入力します。

4. グループを保存します。  グループが完全に構成され、Microsoft 365 管理センターに表示するには、数分かかることがあります。

5. 新しい承認者のグループを選択し、[編集] **を選択** してユーザーをグループに追加します。

6. グループを保存します。

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>手順 2: 特権アクセスを有効にする

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで

1. 組織内の管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. In the Admin Center, go to **Settings**  >  **Org Settings** Security &  >  **Privacy**  >  **Privileged access**.

3. [特権 **タスクの承認を必要とする] コントロールを有効** にする。

4. 手順 1 で作成した承認者のグループを既定の承認者グループ **として割り当てる**。

5. **保存して****閉じます**。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

特権アクセスを有効にし、承認者のグループを割り当てるには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

例:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>システム アカウント機能を使用すると、特権アクセスに依存することなく、組織内の特定の自動化を確実に動作できます。ただし、このような除外は例外的であり、許可される除外は定期的に承認および監査する必要があります。

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>手順 3: アクセス ポリシーを作成する

組織に対して最大 30 の特権アクセス ポリシーを作成して構成できます。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで

1. 組織内の管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. In the Admin Center, go to **Settings**  >  **Org Settings** Security &  >  **Privacy**  >  **Privileged access**.

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [ポリシー **の構成] を選択し、[** ポリシーの **追加] を選択します**。

5. ドロップダウン フィールドから、組織に適した値を選択します。
    
    **ポリシーの種類**: タスク、役割、役割グループ

    **ポリシースコープ**: 交換

    **ポリシー名**: 利用可能なポリシーから選択します。

    **承認の種類**: 手動または自動

    **承認グループ**: 手順 1で作成した承認者グループを選択します。

6. [作成 **] を選択** し、[閉じる] **を選択します**。 ポリシーが完全に構成され、有効になるには数分かかる場合があります。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

承認ポリシーを作成して定義するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

例:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>手順 4: 特権アクセス要求を送信/承認する

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>特権タスクを実行するための昇格認証の要求

特権アクセスの要求は、要求が送信されてから最大24時間有効です。 承認または拒否されない場合、要求は期限切れになり、アクセスは承認されません。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで

1. 資格情報を使用 [して Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。

2. In the Admin Center, go to **Settings**  >  **Org Settings** Security &  >  **Privacy**  >  **Privileged access**.

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [新 **しい要求] を選択します**。 ドロップダウン フィールドから、組織に適した値を選択します。

    **要求の種類**: タスク、役割、役割グループ

    **要求スコープ**: 交換

    **要求名**: 利用可能なポリシーから選択します。

    **期間 (時間)**: アクセスを希望する時間数。 要求できる時間数に制限はありません。

    **Comments**: アクセス要求に関連するコメントのテキスト フィールド

5. [保存 **] を選択** し、[閉じる] **を選択します**。 要求は、承認者のグループに電子メールで送信されます。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

Exchange Online PowerShell で次のコマンドを実行して、承認者のグループに承認要求を作成して送信します。

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

例:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>昇格要求の状態を表示する

承認要求が作成されると、要求 ID に関連付けられた情報を使用して、管理センターまたは Exchange Management PowerShell で昇格要求の状態を確認できます。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 資格情報を使用 [して Microsoft 365 管理](https://admin.microsoft.com) センターにサインインします。

2. 管理センターで、[Settings Org Settings Security]**および**  >    >  [Privacy Privileged **access] &**  >  **に移動します**。

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [**表示]** を選択して、承認待ち、承認済み、拒否、またはカスタマー ロックボックスの状態で送信された要求 **をフィルター処理** します。 

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

特定の要求 ID の承認要求の状態を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

例:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>昇格承認要求の承認

承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知を受信し、要求 ID に関連付けられた要求を承認できます。 アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。

#### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 資格情報を使用 [して Microsoft 365 管理](https://admin.microsoft.com) センターにサインインします。

2. 管理センターで、[Settings Org Settings Security]**および**  >    >  [Privacy Privileged **access] &**  >  **に移動します**。

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. リストされた要求を選択して詳細を表示し、要求に対してアクションを実行します。

5. [ **承認]** を選択して要求を承認するか、[ **拒否]** を選択して要求を拒否します。 以前に承認された要求は、[取り消し] を選択してアクセスを取り消 **す可能性があります**。

#### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

昇格承認要求を承認するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

例:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

昇格承認要求を拒否するには、Exchange Online PowerShell で次のコマンドを実行します。

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

例:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Office 365 で特権アクセス ポリシーを削除する

組織で不要になった場合は、特権アクセス ポリシーを削除できます。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. 管理センターで、[Settings Org Settings Security]**および**  >    >  [Privacy Privileged **access] &**  >  **に移動します**。

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [ポリシー **の構成] を選択します**。

5. 削除するポリシーを選択し、[ポリシーの削除] **を選択します**。

6. **[閉じる]** を選択します。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

特権アクセス ポリシーを削除するには、Exchange Online Powershell で次のコマンドを実行します。

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Office 365 で特権アクセスを無効にする

必要に応じて、組織の特権アクセス管理を無効にできます。 特権アクセスを無効にしても、関連付けられている承認ポリシーや承認者グループは削除されません。

### <a name="in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センター

1. 組織内の管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. In the Admin Center, go to **Settings**  >  **Org Settings** Security &  >  **Privacy**  >  **Privileged access**.

3. 特権アクセス **制御の承認を必要と** します。

### <a name="in-exchange-management-powershell"></a>Exchange 管理 PowerShell の場合

特権アクセスを無効にするには、Exchange Online Powershell で次のコマンドを実行します。

```PowerShell
Disable-ElevatedAccessControl
```
