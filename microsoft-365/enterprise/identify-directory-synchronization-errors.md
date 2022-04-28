---
title: Microsoft 365でディレクトリ同期エラーを表示する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
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
ms.openlocfilehash: 1aa6a9208c9ae3091c2490a003eaabb841b78dc5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096504"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Microsoft 365でディレクトリ同期エラーを表示する

ディレクトリ同期エラーは<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">、Microsoft 365 管理センター</a>で表示できます。 ユーザー オブジェクトのエラーのみが表示されます。 PowerShell でエラーを表示するには、「 [DirSyncProvisioningErrors を使用してオブジェクトを識別する](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)」を参照してください。

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでディレクトリ同期エラーを表示する

Microsoft 365 管理センターでエラーを表示するには:
  
1. グローバル管理者アカウントを[使用してMicrosoft 365 管理センター](https://admin.microsoft.com)にサインインします。 
    
2. **ホーム** ページに、**ユーザー管理** カードが表示されます。 
    
    ![Microsoft 365 管理センターのユーザー管理カード。](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. カードで、**Azure AD Connect** の [**同期エラー**] を選択して、[**ディレクトリ同期エラー**] ページでエラーを確認します。   
    
    ![ディレクトリ同期エラー ページの例。](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. エラーのいずれかを選択すると、エラーに関する情報と修正方法に関するヒントが表示された詳細ウィンドウが表示されます。

   ![ディレクトリ同期エラーの詳細の例。](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
表示後、特定された[問題を修正するためのMicrosoft 365のディレクトリ同期に関](fix-problems-with-directory-synchronization.md)する問題の修正に関するページを参照してください。