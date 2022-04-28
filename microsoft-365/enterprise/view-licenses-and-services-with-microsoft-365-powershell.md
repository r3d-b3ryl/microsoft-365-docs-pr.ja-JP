---
title: PowerShell を使用してMicrosoft 365ライセンスとサービスを表示する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: PowerShell を使用して、Microsoft 365組織で使用できるライセンスプラン、サービス、ライセンスに関する情報を表示する方法について説明します。
ms.openlocfilehash: 1d0d514cc0d821e8958a35c3598b41554260716d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091943"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>PowerShell を使用してMicrosoft 365ライセンスとサービスを表示する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

すべてのMicrosoft 365サブスクリプションは、次の要素で構成されます。

- **ライセンス プラン** これらは、ライセンス プランまたはMicrosoft 365 プランとも呼ばれます。 ライセンス プランは、ユーザーが利用できるMicrosoft 365 サービスを定義します。 Microsoft 365 サブスクリプションには、複数のライセンス プランが含まれている場合があります。 ライセンス プランの例をMicrosoft 365 E3。
    
- **サービス** これらはサービス プランとも呼ばれます。 サービスは、Exchange OnlineやMicrosoft 365 Apps for enterprise (以前は名前が付けられたOffice 365 ProPlus) など、各ライセンス プランで使用できるMicrosoft 365製品、機能、および機能です。 ユーザーは、さまざまなサービスへのアクセスを許可するさまざまなライセンス プランから割り当てられた複数のライセンスを持つことができます。
    
- **ライセンス** 各ライセンス プランには、購入したライセンスの数が含まれています。 ライセンス プランで定義されているMicrosoft 365 サービスを使用できるように、ユーザーにライセンスを割り当てます。 すべてのユーザー アカウントには、Microsoft 365にログオンしてサービスを使用できるように、1 つのライセンス プランから少なくとも 1 つのライセンスが必要です。
    
PowerShell を使用して、Microsoft 365組織で使用可能なライセンス プラン、ライセンス、およびサービスの詳細 Microsoft 365を表示できます。 別の Office 365 サブスクリプションで利用可能な製品、機能、サービスについての詳細は、「[Office 365 プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)」を参照してください。


## <a name="use-the-microsoft-graph-powershell-sdk"></a>Microsoft Graph PowerShell SDK を使用する

まず、[Microsoft 365 テナントに接続します](/graph/powershell/get-started#authentication)。

サブスクリプション ライセンス プランを読み取る場合は、Organization.Read.All アクセス許可スコープ、または[参照ページの [List subscribedSkus] Graph APIに一覧表示されている](/graph/api/subscribedsku-list)他のアクセス許可のいずれかが必要です。

```powershell
Connect-Graph -Scopes Organization.Read.All
```

現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。
  
```powershell
Get-MgSubscribedSku | Select -Property Sku*, ConsumedUnits -ExpandProperty PrepaidUnits | Format-List
```

結果には次のものが含まれます。
  
- **SkuPartNumber:** 組織で使用可能なライセンス プランを表示します。 たとえば、 `ENTERPRISEPACK` Office 365 Enterprise E3 のライセンス プラン名です。
    
- **有効：** 特定のライセンス プランで購入したライセンスの数。
    
- **ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。
    
すべてのライセンス プランで使用できるMicrosoft 365 サービスの詳細を表示するには、最初にライセンス プランの一覧を表示します。

```powershell
Get-MgSubscribedSku
```

次に、ライセンス プラン情報を変数に格納します。

```powershell
$licenses = Get-MgSubscribedSku
```

次に、特定のライセンス プランでサービスを表示します。

```powershell
$licenses[<index>].ServicePlans
```

\<index> は、コマンドの表示 `Get-MgSubscribedSku | Select SkuPartNumber` からライセンス プランの行番号を指定する整数で、1 を引いた値です。

たとえば、コマンドの表示が次の `Get-MgSubscribedSku | Select SkuPartNumber` 場合です。

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

次に、ENTERPRISEPREMIUM ライセンス プランのサービスを表示するコマンドは次のとおりです。

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM は 3 番目の行です。 したがって、インデックス値は (3 から 1)、または 2 です。

ライセンス プラン (製品名とも呼ばれます)、含まれるサービス プラン、および対応するフレンドリ名の完全な一覧については、 [ライセンスの製品名とサービス プラン識別子に関するページを](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)参照してください。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

結果には次のものが含まれます。
  
- **SkuPartNumber:** 組織で使用可能なライセンス プランを表示します。 たとえば、 `ENTERPRISEPACK` Office 365 Enterprise E3 のライセンス プラン名です。
    
- **有効：** 特定のライセンス プランで購入したライセンスの数。
    
- **ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。
    
すべてのライセンス プランで使用できるMicrosoft 365 サービスの詳細を表示するには、最初にライセンス プランの一覧を表示します。

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

次に、ライセンス プラン情報を変数に格納します。

```powershell
$licenses = Get-AzureADSubscribedSku
```

次に、特定のライセンス プランでサービスを表示します。

```powershell
$licenses[<index>].ServicePlans
```

\<index> は、コマンドの表示 `Get-AzureADSubscribedSku | Select SkuPartNumber` からライセンス プランの行番号を指定する整数で、1 を引いた値です。

たとえば、コマンドの表示が次の `Get-AzureADSubscribedSku | Select SkuPartNumber` 場合です。

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

次に、ENTERPRISEPREMIUM ライセンス プランのサービスを表示するコマンドは次のとおりです。

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM は 3 番目の行です。 したがって、インデックス値は (3 から 1)、または 2 です。

ライセンス プラン (製品名とも呼ばれます)、含まれるサービス プラン、および対応するフレンドリ名の完全な一覧については、 [ライセンスの製品名とサービス プラン識別子に関するページを](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)参照してください。

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

まず、[Microsoft 365 テナントに接続します](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)。

>[!Note]
>このトピックで説明されている手順を自動化する PowerShell スクリプトが利用可能です。 具体的には、このスクリプトを使用すると、Swayを含む、Microsoft 365組織内のサービスを表示および無効にすることができます。 詳細については、「[PowerShell を使用してSwayへのアクセスを無効にする](disable-access-to-sway-with-microsoft-365-powershell.md)」を参照してください。
>
    
現在のライセンス プランと各プランで使用可能なライセンスに関する概要情報を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に **Msol** が含まれるコマンドレットをサポートしていません。 これらのコマンドレットを引き続き使用するには、Windows PowerShell から実行する必要があります。
>

結果には次の情報が含まれます。
  
- **AccountSkuId:** 構文 `<CompanyName>:<LicensingPlan>`を使用して、組織で使用可能なライセンス プランを表示します。  _\<CompanyName>_ は、Microsoft 365に登録したときに指定した値であり、組織に対して一意です。 _\<LicensingPlan>_ の値は、すべてのユーザーに対して同じです。 たとえば、値 `litwareinc:ENTERPRISEPACK` では、会社名が `litwareinc`、ライセンス プラン名が  `ENTERPRISEPACK` で、これが Office 365 Enterprise E3 のシステム名になります。
    
- **ActiveUnits:** 特定のライセンス プランで購入したライセンスの数。
    
- **WarningUnits:** 更新していないライセンス プランのライセンスの数。30 日の猶予期間を過ぎると有効期限切れになります。
    
- **ConsumedUnits:** 特定のライセンス プランでユーザーに割り当てたライセンスの数。
    
すべてのライセンス プランで使用できるMicrosoft 365 サービスの詳細を表示するには、次のコマンドを実行します。
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

次の表は、Microsoft 365サービス プランとその最も一般的なサービスのフレンドリ名を示しています。 実際のサービス プランの一覧とは、異なる場合があります。 
  
|**サービス プラン**|**説明**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for enterprise *(以前の名前Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |事業所  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online プラン 2  <br/> |
   
ライセンス プラン (製品名とも呼ばれます)、含まれるサービス プラン、および対応するフレンドリ名の完全な一覧については、 [ライセンスの製品名とサービス プラン識別子に関するページを](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)参照してください。

特定のライセンス プランで使用できるMicrosoft 365 サービスの詳細を表示するには、次の構文を使用します。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

この例は、litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) ライセンス プランで利用できるサービスを示しています。
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)