---
title: ディレクトリ同期エラーの Microsoft 365表示
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: ディレクトリ同期エラーと考えられる修正プログラムを表示する方法については、Microsoft 365 管理センター。
ms.openlocfilehash: d48b67f31241777368cd27cf0385d34757495eef
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58353758"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>ディレクトリ同期エラーの Microsoft 365表示

ディレクトリ同期エラーは、ディレクトリの同期エラー Microsoft 365 管理センター。 User オブジェクトのエラーだけが表示されます。 PowerShell のエラーを表示するには [、「DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)を使用してオブジェクトを識別する」を参照してください。

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>ディレクトリ同期エラーを表示するMicrosoft 365 管理センター

エラーを表示するには、次のMicrosoft 365 管理センター。
  
1. グローバル管理者アカウントで[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 
    
2. [ホーム **] ページ** に[ユーザー管理] **カードが表示** されます。 
    
    ![[ユーザー管理] カードのMicrosoft 365 管理センター](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. カードで **、[Azure** **の同期** エラー] を選択しAD Connect[ディレクトリ同期エラー **] ページにエラーを表示** します。   
    
    ![ディレクトリ同期エラー ページの例](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. エラーを選択して、エラーに関する情報と修正方法に関するヒントを含む詳細ウィンドウを表示します。

   ![ディレクトリ同期エラーの詳細の例](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
表示後、「ディレクトリ同期に関する問題を修正する[」を参照Microsoft 365](fix-problems-with-directory-synchronization.md)特定された問題を修正する必要があります。