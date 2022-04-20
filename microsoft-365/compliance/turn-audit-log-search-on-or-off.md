---
title: 監査のオンとオフを切り替える
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Microsoft Purview コンプライアンス ポータルで監査ログ検索機能をオンまたはオフにして、管理者が監査ログを検索する機能を有効または無効にする方法。
ms.openlocfilehash: e74effad1803b9a55167d1cd3bb5725bd042616a
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64991822"
---
# <a name="turn-auditing-on-or-off"></a>監査のオンとオフを切り替える

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

監査ログは、Microsoft 365およびOffice 365エンタープライズ組織に対して既定で有効になります。 ただし、新しいMicrosoft 365またはOffice 365組織を設定する場合は、組織の監査状態を確認する必要があります。 手順については、この記事の「 [組織の監査状態を確認する](#verify-the-auditing-status-for-your-organization) 」セクションを参照してください。 

Microsoft Purview コンプライアンス ポータルで監査を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて最大 1 年間、90 日間保持されます。 ただし、組織には、監査ログ データを記録および保持したくない理由が考えられます。 このような場合、グローバル管理者は、Microsoft 365で監査を無効にすることを決定する場合があります。

> [!IMPORTANT]
> Microsoft 365で監査を無効にした場合、Office 365 Management Activity API または Microsoft Sentinel を使用して組織の監査データにアクセスすることはできません。 この記事の手順に従って監査を無効にすると、コンプライアンス ポータルを使用して監査ログを検索するとき、または PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行したときに結果Exchange Online返されないことを意味します。 これは、Office 365 Management アクティビティ API または Microsoft Sentinel を使用して監査ログを使用できないことも意味します。
  
## <a name="before-you-turn-auditing-on-or-off"></a>監査をオンまたはオフにする前に

- Microsoft 365組織で監査を有効または無効にするには、Exchange Onlineで監査ログ ロールを割り当てる必要があります。 既定では、このロールは、Exchange管理センターの **[アクセス許可**] ページのコンプライアンス管理と組織管理の役割グループに割り当てられます。 Microsoft 365のグローバル管理者は、Exchange Onlineの組織管理役割グループのメンバーです。

    > [!NOTE]
    > 監査を有効または無効にするには、Exchange Onlineでユーザーにアクセス許可を割り当てる必要があります。 コンプライアンス ポータルの **[アクセス許可** ] ページでユーザーに監査ログ ロールを割り当てると、監査をオンまたはオフにすることはできません。 これは、基になるコマンドレットが powerShell コマンドレットExchange Onlineであるためです。

- 監査ログの検索の詳細な手順については、「監査ログ [の検索」を](search-the-audit-log-in-security-and-compliance.md)参照してください。 Microsoft 365 Management アクティビティ API の詳細については、「[Microsoft 365 Management API を使用した概要」を参照してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="verify-the-auditing-status-for-your-organization"></a>組織の監査状態を確認する

組織の監査が有効になっていることを確認するには、[powerShell で](/powershell/exchange/connect-to-exchange-online-powershell)次のコマンドExchange Online実行します。

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

_UnifiedAuditLogIngestionEnabled_ プロパティの`True`値は、監査が有効になっていることを示します。 値 `False` は、監査が有効になっていないことを示します。

> [!NOTE]
> PowerShell で前のコマンドExchange Online実行してください。 Security & Compliance PowerShell を使用してこのコマンドを実行することはできません。

## <a name="turn-on-auditing"></a>監査を有効にする

組織で監査が有効になっていない場合は、コンプライアンス ポータルで、または PowerShell Exchange Online使用して、監査を有効にすることができます。 監査ログを検索するときに結果を返すには、監査を有効にしてから数時間かかる場合があります。
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>コンプライアンス センターを使用して監査を有効にする

1. <https://compliance.microsoft.com> に移動し、サインインします。

2. コンプライアンス ポータルの左側のナビゲーション ウィンドウで、[ **監査**] をクリックします。

   組織で監査が有効になっていない場合は、ユーザーと管理者のアクティビティの記録を開始するように求めるバナーが表示されます。

   ![[監査] ページのバナー。](../media/AuditingBanner.png)

3. [ **ユーザーと管理者のアクティビティの記録を開始する** ] バナーをクリックします。

   変更が有効になるまでに最大で 60 分かかる場合があります。

### <a name="use-powershell-to-turn-on-auditing"></a>PowerShell を使用して監査を有効にする

1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次の PowerShell コマンドを実行して監査を有効にします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更が有効になるまでに最大 60 分かかる可能性があるというメッセージが表示されます。
  
## <a name="turn-off-auditing"></a>監査を無効にする

監査を無効にするには、Exchange Online PowerShell を使用する必要があります。
  
1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次の PowerShell コマンドを実行して、監査を無効にします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくすると、監査がオフ (無効) になっていることを確認します。 このようにするには、次の 2 つの方法があります。

    - Exchange Online PowerShell で、次のコマンドを実行します。

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      _UnifiedAuditLogIngestionEnabled_ プロパティの`False`値は、監査がオフになっていることを示します。

    - コンプライアンス ポータルの **[監査** ] ページに移動します。

      組織で監査が有効になっていない場合は、ユーザーと管理者のアクティビティの記録を開始するように求めるバナーが表示されます。

## <a name="audit-records-when-auditing-status-is-changed"></a>監査の状態が変更されたときにレコードを監査する

組織内の監査状態に対する変更は、それ自体が監査されます。 つまり、監査レコードは、監査がオンまたはオフになっているときにログに記録されます。 これらの監査レコードについては、Exchange管理者監査ログを検索できます。

Exchange管理者監査ログで、監査のオンとオフを切り替えるときに生成される監査レコードを検索するには、[powerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行します。

```powershell
Search-AdminAuditLog -Cmdlets Set-AdminAuditLogConfig -Parameters UnifiedAuditLogIngestionEnabled
```

これらのイベントの監査レコードには、監査の状態がいつ変更されたか、それを変更した管理者、および変更を行うために使用されたコンピューターの IP アドレスに関する情報が含まれます。 次のスクリーンショットは、組織内の監査状態の変更に対応する監査レコードを示しています。

### <a name="audit-record-for-turning-on-auditing"></a>監査を有効にするための監査レコード

![監査を有効にするための監査レコード](../media/AuditStatusAuditingEnabled.png)

*CmdletParameters* プロパティの`Confirm`値は、コンプライアンス センターまたは **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true** コマンドレットを実行して、統合監査ログが有効になっていることを示します。

### <a name="audit-record-for-turning-off-auditing"></a>監査を無効にするための監査レコード

![監査を無効にするための監査レコード](../media/AuditStatusAuditingDisabled.png)

の値 `Confirm` は、 *CmdletParameters* プロパティには含まれません。 これは、 **Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false** コマンドを実行して、統合監査ログが無効になっていることを示します。

Exchange管理者監査ログの検索の詳細については、「[Search-AdminAuditLog」を](/powershell/module/exchange/search-adminauditlog)参照してください。
