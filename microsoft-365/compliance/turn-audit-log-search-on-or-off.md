---
title: 監査を有効またはオフにする
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
description: 管理者が監査ログを検索する機能を有効または無効にするには、Microsoft 365 コンプライアンス センターで監査ログ検索機能を有効または無効にする方法を示します。
ms.openlocfilehash: 091331a40a2ab6bf3c05bb289d49f63ab2dd2794
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657735"
---
# <a name="turn-auditing-on-or-off"></a>監査を有効またはオフにする

Microsoft 365 および Office 365 Enterprise 組織では、監査ログは既定でオンになっています。 これには、E3/G3 または E5/G5 サブスクリプションを持つ組織が含まれます。 コンプライアンス センターで監査を有効にすると、組織のユーザーと管理者のアクティビティが監査ログに記録され、ユーザーに割り当てられたライセンスに応じて 90 日間、最大 1 年間保持されます。 ただし、監査ログ データを記録および保持しない理由が組織にある場合があります。 このような場合、グローバル管理者は、管理者が監査をオフにMicrosoft 365。

> [!IMPORTANT]
> Microsoft 365 で監査をオフにした場合、Office 365 管理アクティビティ API または Azure Sentinel を使用して組織の監査データにアクセスすることはできません。 この記事の手順に従って監査をオフにした場合、セキュリティ & コンプライアンス センターを使用して監査ログを検索したり、Exchange Online PowerShell で **Search-UnifiedAuditLog** コマンドレットを実行したりすると、結果は返されません。 つまり、監査ログは、管理アクティビティ API または Azure Sentinel Office 365使用できません。
  
## <a name="before-you-turn-auditing-on-or-off"></a>監査を有効またはオフにする前に

- 組織で監査を有効またはExchange Onlineするには、監査ログの役割を割りMicrosoft 365があります。 既定では、この役割は、管理センターの [アクセス許可] ページの[コンプライアンス管理] および [組織の管理Exchange割り当てられます。 グループ内のグローバルMicrosoft 365は、組織の管理役割グループのメンバー Exchange Online。 

    > [!NOTE]
    > 監査を有効またはオフに切り替Exchange Onlineユーザーにアクセス許可を割り当てる必要があります。 セキュリティ & コンプライアンス センターの [アクセス許可] ページでユーザーに監査ログの役割を割り当てると、監査をオンまたはオフにすることはできません。 これは、基になるコマンドレットが PowerShell コマンドレットExchange Onlineです。 

- 監査ログの検索に関する詳細な手順については、「セキュリティ コンプライアンス センターで監査ログを検索する」 [を&してください](search-the-audit-log-in-security-and-compliance.md)。 管理アクティビティ API の詳細Microsoft 365、「管理 API の概要」を参照Microsoft 365[してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。

- 監査が有効になっていることを確認するには、PowerShell で次のコマンドExchange Onlineできます。

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    `True` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査が有効になっていることを示します。 

## <a name="turn-on-auditing"></a>監査を有効にする

組織で監査を有効にしていない場合は、コンプライアンス センターで有効にするか、PowerShell を使用Exchange Onlineできます。 監査ログを検索するときに結果を返す前に、監査を有効にしてから数時間かかる場合があります。
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>コンプライアンス センターを使用して監査を有効にする

1. <https://compliance.microsoft.com> に移動し、サインインします。

2. コンプライアンス センターの左側のナビゲーション ウィンドウMicrosoft 365、[すべて表示]をクリックし、[監査] を **クリックします**。

   組織の監査が有効ではない場合は、ユーザーと管理アクティビティの記録を開始するように求めるバナーが表示されます。

   ![[監査] ページのバナー](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)

3. [ユーザーと **管理アクティビティの記録を開始する] バナーをクリック** します。

   変更を有効にするには、最大 60 分かかる場合があります。

### <a name="use-powershell-to-turn-on-auditing"></a>PowerShell を使用して監査を有効にする

1. [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

2. 次の PowerShell コマンドを実行して、監査を有効にOffice 365。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    変更を有効にするには、最大 60 分かかる可能性があるというメッセージが表示されます。
  
## <a name="turn-off-auditing"></a>監査をオフにする

監査をオフExchange Online PowerShell を使用する必要があります。
  
1. [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)

2. 次の PowerShell コマンドを実行して監査をオフにします。

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. しばらくすると、監査が無効 (無効) になっていることを確認します。 これを行うには次に示す 2 つの方法があります。

    - PowerShell Exchange Onlineで、次のコマンドを実行します。

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      `False` _UnifiedAuditLogIngestionEnabled_ プロパティの値は、監査がオフになっていることを示します。

    - コンプライアンス センターの **[** 監査] ページMicrosoft 365移動します。

      組織の監査が有効ではない場合は、ユーザーと管理アクティビティの記録を開始するように求めるバナーが表示されます。
