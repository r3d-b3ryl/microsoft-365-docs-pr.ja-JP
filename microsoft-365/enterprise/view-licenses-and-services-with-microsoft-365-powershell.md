---
title: PowerShell Microsoft 365ライセンスとサービスを表示する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: PowerShell を使用して、組織で利用可能なライセンス プラン、サービス、ライセンスに関する情報を表示するMicrosoft 365します。
ms.openlocfilehash: 920bc00dcfa774f7cf157be4a543bf30e18f406e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210384"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>PowerShell Microsoft 365ライセンスとサービスを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

サブスクリプションMicrosoft 365は、次の要素で構成されます。

- **ライセンス プラン** これらは、ライセンス プランまたはライセンス プランMicrosoft 365されます。 ライセンス プランは、ユーザーがMicrosoft 365サービスを定義します。 サブスクリプションMicrosoft 365複数のライセンス プランが含まれている場合があります。 ライセンス計画の例は、Microsoft 365 E3。
    
- **サービス** これらはサービス プランとも呼ばれる。 サービスは、Microsoft 365 Exchange Online および Microsoft 365 Apps for enterprise (以前に名前が付けられた Office 365 ProPlus) など、各ライセンス プランで利用可能な Microsoft 365 製品、機能、および機能です。 ユーザーは、さまざまなサービスへのアクセスを許可するさまざまなライセンス プランから割り当てられた複数のライセンスを持つことができます。
    
- **ライセンス** 各ライセンスプランには、購入したライセンスの数が含まれています。 ユーザーにライセンスを割り当て、ライセンス 計画Microsoft 365サービスを使用できます。 すべてのユーザー アカウントには、1 つのライセンス プランから少なくとも 1 つのライセンスが必要なので、ユーザーはサービスにログオンしてMicrosoft 365使用できます。
    
PowerShell を使用して、Microsoft 365組織で利用可能なライセンス プラン、ライセンス、サービスの詳細を表示Microsoft 365できます。 別の Office 365 サブスクリプションで利用可能な製品、機能、サービスについての詳細は、「[Office 365 プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を参照してください。


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

結果には次の情報が含まれる。
  
- **SkuPartNumber:** 組織で利用可能なライセンス プランを表示します。 たとえば `ENTERPRISEPACK` 、E3 のライセンス プランOffice 365 Enterpriseします。
    
- **有効:** 特定のライセンス プランで購入したライセンスの数。
    
- **ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。
    
すべてのライセンス プランで利用可能Microsoft 365サービスの詳細を表示するには、まずライセンス プランの一覧を表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンス プランの情報を変数に格納します。

```powershell
$licenses = Get-AzureADSubscribedSku
```

次に、特定のライセンス プランでサービスを表示します。

```powershell
$licenses[<index>].ServicePlans
```

\<index> は、コマンドの表示からライセンス プランの行番号を指定する整数で、1 を `Get-AzureADSubscribedSku | Select SkuPartNumber` 引いた値です。

たとえば、コマンドの表示が `Get-AzureADSubscribedSku | Select SkuPartNumber` 次の場合です。

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

次に、ENTERPRISEPREMIUM ライセンス プランのサービスを表示するコマンドは次のコマンドです。

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM は 3 行目です。 したがって、インデックス値は (3 ~ 1)、または 2 です。

ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に[、テナントにMicrosoft 365します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

>[!Note]
>このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。 具体的には、このスクリプトを使用すると、Sway を含む、Microsoft 365のサービスを表示および無効にできます。 詳細については [、「PowerShell を使用して Sway へのアクセスを無効にする」を参照してください](disable-access-to-sway-with-microsoft-365-powershell.md)。
>
    
現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

結果には次の情報が含まれます。
  
- **AccountSkuId:** 構文を使用して、組織で利用可能なライセンス プランを表示します `<CompanyName>:<LicensingPlan>` 。  _\<CompanyName>_ は、ユーザーが組織に登録するときに指定Microsoft 365、組織に固有の値です。 _\<LicensingPlan>_ の値は、すべてのユーザーに対して同じです。 たとえば、値 `litwareinc:ENTERPRISEPACK` では、会社名が `litwareinc`、ライセンス プラン名が  `ENTERPRISEPACK` で、これが Office 365 Enterprise E3 のシステム名になります。
    
- **ActiveUnits:** 特定のライセンス プランで購入したライセンスの数。
    
- **WarningUnits:** 更新していないライセンス プランのライセンスの数。30 日の猶予期間を過ぎると有効期限切れになります。
    
- **ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。
    
すべてのライセンス プランで使用可能Microsoft 365サービスの詳細を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

次の表に、最も一Microsoft 365サービスプランの名前と、その親近名を示します。 実際のサービス プランの一覧とは、異なる場合があります。 
  
|**サービス プラン**|**説明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for enterprise *(以前に名前が付Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |事業所  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online プラン 2  <br/> |
   
ライセンス プラン (製品名とも呼ばれる) の完全な一覧、付属のサービス プラン、対応する表示名については、「ライセンスの製品名とサービス プラン識別子」を [参照してください](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)。

特定のライセンス プランでMicrosoft 365サービスの詳細を表示するには、次の構文を使用します。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

次の使用例は、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランで利用できるサービスを示しています。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)