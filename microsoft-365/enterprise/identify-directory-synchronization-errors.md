---
title: Microsoft 365 のディレクトリ同期エラーの表示
ms.author: josephd
author: JoeDavies-MSFT
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
description: Microsoft 365 管理センターでディレクトリ同期エラーと考えられる修正プログラムを表示する方法について説明します。
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907506"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Microsoft 365 のディレクトリ同期エラーの表示

ディレクトリ同期エラーは、Microsoft 365 管理センターで表示できます。 User オブジェクトのエラーだけが表示されます。 PowerShell のエラーを表示するには [、「DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)を使用してオブジェクトを識別する」を参照してください。

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでディレクトリ同期エラーを表示する

Microsoft 365 管理センターでエラーを表示するには、次の方法を実行します。
  
1. グローバル管理者アカウント [を使用して Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。 
    
2. [ホーム **] ページ** に[ユーザー管理] **カードが表示** されます。 
    
    ![Microsoft 365 管理センターのユーザー管理カード](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. カードで、[Azure  AD接続] の [同期エラー]**を選択して、[** ディレクトリ同期エラー **] ページにエラーを表示** します。   
    
    ![ディレクトリ同期エラー ページの例](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. エラーを選択して、エラーに関する情報と修正方法に関するヒントを含む詳細ウィンドウを表示します。

   ![ディレクトリ同期エラーの詳細の例](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
表示後 [、「Microsoft 365](fix-problems-with-directory-synchronization.md) のディレクトリ同期に関する問題を修正する」を参照して、特定された問題を修正してください。