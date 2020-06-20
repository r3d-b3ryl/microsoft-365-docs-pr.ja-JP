---
title: 監査ログ検索を有効または無効にする
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: セキュリティ & コンプライアンスセンターで監査ログ検索機能をオンまたはオフにして、管理者が監査ログを検索する機能を有効または無効にします。
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819137"
---
# <a name="turn-audit-log-search-on-or-off"></a>監査ログ検索を有効または無効にする

監査ログの検索を開始する前に、自分 (または別の管理者) が監査ログを有効にする必要があります。 セキュリティ & コンプライアンスセンターで監査ログの検索が有効になっている場合は、組織のユーザーおよび管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられているライセンスに応じて、90日間、および最大1年間保持されます。 ただし、監査ログデータを記録して保持しない理由が組織にある場合があります。 そのような場合は、グローバル管理者が Microsoft 365 の監査を無効にすることを決定することがあります。

> [!IMPORTANT]
> Microsoft 365 で監査ログの検索を無効にした場合、Office 365 Management Activity API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。 この記事の手順に従って監査ログの検索を無効にすると、セキュリティ & コンプライアンスセンターを使用して監査ログを検索したとき、または Exchange Online PowerShell で**search-unifiedauditlog**コマンドレットを実行したときに結果が返されないことを意味します。 これは、Office 365 Management Activity API または Azure Sentinel を介して監査ログを利用できないことも意味します。
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>監査ログ検索をオンまたはオフにする前に

- Microsoft 365 組織で監査ログの検索をオンまたはオフにするには、Exchange Online の Audit Logs 役割が割り当てられている必要があります。 既定では、この役割は、Exchange 管理センターの [**アクセス許可**] ページで、コンプライアンス管理および組織の管理役割グループに割り当てられます。 Microsoft 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。 
    
    > [!NOTE]
    > 監査ログの検索を有効または無効にするには、Exchange Online のアクセス許可をユーザーに割り当てる必要があります。 セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページで監査ログの役割をユーザーに割り当てると、監査ログの検索をオンまたはオフにすることができなくなります。 これは、基礎となるコマンドレットが Exchange Online のコマンドレットであるためです。 
    
- 監査ログの検索の詳細な手順については、「[セキュリティ & のコンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。 Microsoft 365 Management Activity API の詳細については、「 [microsoft 365 管理 api の使用を開始](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)する」を参照してください。
    
## <a name="turn-on-audit-log-search"></a>監査ログ検索を有効にする

セキュリティ & コンプライアンスセンターまたは PowerShell を使用して、Microsoft 365 で監査ログの検索を有効にすることができます。 監査ログの検索を有効にすると、監査ログの検索時に結果を返す前に、数時間かかる場合があります。 監査ログ検索を有効にするには、Exchange Online で Audit Logs 役割を割り当てられている必要があります。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>セキュリティ & コンプライアンスセンターを使用して監査ログの検索を有効にする

1. [[セキュリティ & コンプライアンスセンター] に移動](https://protection.office.com)して、サインインします。

2. [セキュリティ & コンプライアンスセンター] で、[**検索** \> **監査ログの検索**] に移動します。

   ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。

3. [**監査を有効にする] を**クリックします。

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    バナーが更新され、監査ログの準備が完了し、ユーザーと管理者のアクティビティを数時間で検索できるようになります。

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell を使用して監査ログの検索を有効にする

1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Office 365 で監査ログの検索を有効にするには、次の PowerShell コマンドを実行します。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更が有効になるまでに最大60分かかる可能性があることを伝えるメッセージが表示されます。
  
## <a name="turn-off-audit-log-search"></a>監査ログの検索を無効にする

監査ログの検索を無効にするには、Exchange Online 組織に接続されたリモート PowerShell を使用する必要があります。 監査ログ検索を有効にするのと同様に、監査ログ検索を無効にするには、Exchange Online の Audit Logs 役割を割り当てられている必要があります。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Office 365 で監査ログの検索を無効にするには、次の PowerShell コマンドを実行します。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくした後、監査ログの検索がオフ (無効) になっていることを確認します。 これを行うには 2 つの方法があります。

    - PowerShell で、次のコマンドを実行します。

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      UnifiedAuditLogIngestionEnabled プロパティのの値は、 `False` 監査ログの検索がオフになっていることを示します。 _UnifiedAuditLogIngestionEnabled_ 

    - [[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[**検索** \> **監査ログの検索**] に移動します。

      ユーザーおよび管理者のアクティビティを記録するために、監査を有効にする必要があるというバナーが表示されます。