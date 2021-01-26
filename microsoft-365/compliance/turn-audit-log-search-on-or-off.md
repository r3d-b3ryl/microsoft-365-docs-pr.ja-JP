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
description: セキュリティ & コンプライアンス センターで監査ログ検索機能を有効または無効にして、管理者が監査ログを検索する機能を有効または無効にする方法について。
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976330"
---
# <a name="turn-audit-log-search-on-or-off"></a>監査ログ検索を有効または無効にする

監査ログは、Microsoft 365 および 365 エンタープライズOffice既定で有効になっています。 これには、E3/G3 または E5/G5 サブスクリプションを持つ組織が含まれます。 コンプライアンス センターで監査ログ検索を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて 90 日間、最大 1 年間保持されます。 ただし、組織には監査ログ データを記録して保持したくない理由がある場合があります。 このような場合、グローバル管理者は Microsoft 365 で監査をオフにできます。

> [!IMPORTANT]
> Microsoft 365 で監査ログ検索をオフにした場合、Office 365 マネージメント アクティビティ API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。 この記事の手順に従って監査ログ検索をオフにした場合、セキュリティ & コンプライアンス センターを使用して監査ログを検索したり、Exchange Online PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行したりすると、結果は返されません。 つまり、監査ログは、Office 365 マネージメント アクティビティ API または Azure Sentinel を通じて利用できません。
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>監査ログ検索を有効またはオフにする前に

- Microsoft 365 組織で監査ログ検索を有効またはオフに切り替えするには、Exchange Online の監査ログの役割が割り当てられている必要があります。 既定では、この役割は Exchange 管理センターの [アクセス許可]ページの [コンプライアンス管理] 役割グループと [組織の管理] 役割グループに割り当てられます。 Microsoft 365 のグローバル管理者は、Exchange Online の Organization Management 役割グループのメンバーです。 
    
    > [!NOTE]
    > 監査ログ検索を有効またはオフに切り替えするには、Exchange Online でユーザーにアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに監査ログの役割を割り当てると、監査ログの検索を有効またはオフにすることはできません。 これは、基になるコマンドレットが Exchange Online PowerShell コマンドレットだからです。 
    
- 監査ログの検索に関する詳しい手順については、セキュリティ/コンプライアンス センターの「監査ログを& [参照してください](search-the-audit-log-in-security-and-compliance.md)。 Microsoft 365 マネージメント アクティビティ API の詳細については [、「Microsoft 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)API の概要」を参照してください。

- 監査ログの検索が有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    `True` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログ検索が有効になっていることを示します。 
    
## <a name="turn-on-audit-log-search"></a>監査ログ検索を有効にする

組織で監査ログの検索が有効ではない場合は、コンプライアンス センターで有効にするか、Exchange Online PowerShell を使用して有効にできます。 監査ログの検索を有効にしてから、監査ログの検索時に結果を返すまで数時間かかる場合があります。
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>コンプライアンス センターを使用して監査ログ検索を有効にする

1. [コンプライアンス センターに移動し、](https://protection.office.com) サインインします。

2. コンプライアンス センターで、検索監査ログ **の検索**  >  **に移動します**。

   組織の監査ログ検索が有効ではない場合は、ユーザーと管理者のアクティビティを記録するために監査を有効にする必要があるというバナーが表示されます。

3. [ **監査を有効にする] をクリックします**。

    ![[監査を有効にする] をクリックします。](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    バナーが更新され、監査ログが準備中であり、数時間後にユーザーと管理者のアクティビティを検索できます。

### <a name="use-powershell-to-turn-on-audit-log-search"></a>PowerShell を使用して監査ログ検索を有効にする

1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 次の PowerShell コマンドを実行して、365 で監査ログOfficeします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更が有効にな最大 60 分かかる可能性があるというメッセージが表示されます。
  
## <a name="turn-off-audit-log-search"></a>監査ログ検索をオフにする

Exchange Online PowerShell を使用して監査ログ検索をオフにする必要があります。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. 次の PowerShell コマンドを実行して監査ログ検索をオフにします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくすると、監査ログ検索がオフ (無効) になっていることを確認します。 これを行うには 2 つの方法があります。

    - Exchange Online PowerShell で、次のコマンドを実行します。

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査ログ検索が無効になっていることを示します。 

    - コンプライアンス センター [で、検索](https://protection.office.com)監査ログ **の検索** \> **に移動します**。

      ユーザーと管理者のアクティビティを記録するには、監査を有効にする必要があるというバナーが表示されます。
