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
description: セキュリティ & コンプライアンス センターの監査ログ検索機能を有効または無効にして、管理者が監査ログを検索する機能を有効または無効にする方法。
ms.openlocfilehash: 3f3e1b913dd163e74f9e5359de772dfcbf3bd786
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423678"
---
# <a name="turn-audit-log-search-on-or-off"></a>監査ログ検索を有効または無効にする

Microsoft 365 および Office 365 Enterprise 組織では、監査ログは既定でオンになっています。 これには、E3/G3 または E5/G5 サブスクリプションを持つ組織が含まれます。 コンプライアンス センターで監査ログ検索を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、90 日間保持され、ユーザーに割り当てられたライセンスに応じて最大 1 年間保持されます。 ただし、監査ログ データを記録および保持しない理由が組織にある場合があります。 このような場合、グローバル管理者は Microsoft 365 で監査をオフにできます。

> [!IMPORTANT]
> Microsoft 365 で監査ログ検索をオフにした場合、Office 365 管理アクティビティ API または Azure Sentinel を使用して、組織の監査データにアクセスすることはできません。 この記事の手順に従って監査ログ検索をオフにした場合、セキュリティ & コンプライアンス センターを使用して監査ログを検索する場合、または Exchange Online PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行すると、結果は返されません。 つまり、監査ログは、365 管理アクティビティ API または Azure Sentinel Office使用できません。
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>監査ログの検索を有効またはオフにする前に

- Microsoft 365 組織で監査ログ検索をオンまたはオフにする場合は、Exchange Online で監査ログの役割を割り当てる必要があります。 既定では、この役割は Exchange 管理センターの [アクセス許可]ページのコンプライアンス管理役割グループと組織管理役割グループに割り当てられます。 Microsoft 365 のグローバル管理者は、Exchange Online の組織管理役割グループのメンバーです。 
    
    > [!NOTE]
    > 監査ログの検索を有効またはオフにするには、Exchange Online でユーザーにアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに監査ログの役割を割り当てると、監査ログの検索をオンまたはオフにすることはできません。 これは、基になるコマンドレットが Exchange Online PowerShell コマンドレットだからです。 
    
- 監査ログの検索に関する詳細な手順については、「セキュリティ コンプライアンス センターで監査ログを検索する」 [を&してください](search-the-audit-log-in-security-and-compliance.md)。 Microsoft 365 管理アクティビティ API の詳細については [、「Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)管理 API の概要」を参照してください。

- 監査ログ検索が有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    `True` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログ検索が有効になっていることを示します。 
    
## <a name="turn-on-audit-log-search"></a>監査ログ検索を有効にする

組織の監査ログ検索が有効ではない場合は、コンプライアンス センターで有効にするか、Exchange Online PowerShell を使用して有効にできます。 監査ログの検索時に結果を返す前に、監査ログ検索を有効にしてから数時間かかる場合があります。
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>コンプライアンス センターを使用して監査ログ検索を有効にする

1. [コンプライアンス センターに移動し、](https://protection.office.com) サインインします。

2. コンプライアンス センターで、[監査ログ検索の **検索**  >  **] に移動します**。

   組織の監査ログ検索が有効ではない場合は、ユーザーと管理者のアクティビティを記録するために監査を有効にする必要があるというバナーが表示されます。

3. [ **監査を有効にする] をクリックします**。

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    バナーが更新され、監査ログが準備され、数時間でユーザーと管理者のアクティビティを検索できます。

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell を使用して監査ログ検索を有効にする

1. [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. 次の PowerShell コマンドを実行して、365 で監査ログOfficeします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更を有効にするには、最大 60 分かかる可能性があるというメッセージが表示されます。
  
## <a name="turn-off-audit-log-search"></a>監査ログの検索をオフにする

Exchange Online PowerShell を使用して監査ログ検索をオフにする必要があります。
  
1. [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. 次の PowerShell コマンドを実行して監査ログの検索をオフにします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくすると、監査ログの検索が無効 (無効) になっていることを確認します。 これを行うには 2 つの方法があります。

    - Exchange Online PowerShell で、次のコマンドを実行します。

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログの検索が無効になっていることを示します。 

    - コンプライアンス センター [で、[監査](https://protection.office.com)ログ検索 **の検索** \> **] に移動します**。

      ユーザーと管理者のアクティビティを記録するには、監査を有効にする必要があるというバナーが表示されます。
