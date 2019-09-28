---
title: Windows 10 デバイスで Office を自動的にインストールまたはアンインストールする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'Microsoft 365 Business 管理センターから Windows 10 デバイスに Office をインストールまたはアンインストールします。 '
ms.openlocfilehash: d82ab8292211d1adacba732922bf693dd2157ad6
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287537"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Windows 10 デバイスで Office を自動的にインストールまたはアンインストールする

[![[ラベル] 管理センターが変更されたことを知らせるために、aka.ms/aboutM365preview で詳細を確認できます。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Microsoft 365 Business 管理センターから Office を Windows 10 PC に迅速かつ簡単にインストールできます。
  
以前にインストールした Office アプリでこれがどのように機能するかを理解するには、開始する前に、「[Microsoft 365 Business による Office クライアントの展開を準備する](prepare-for-office-client-deployment.md)」をお読みください。 
  
## <a name="manage-office-deployments"></a>Office 展開を管理する

1. グローバル管理者の資格情報を使用して、[管理センター](https://aka.ms/bcsportal)にサインインします。 
    
2. **デバイス** カードで、[ **Office 展開を管理する**] を選びます。
      **デバイスアクション**カードが表示されない場合は、管理センターの**ホーム**ページで、[**追加**] (+) をクリックして管理者のホームに追加します。
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. 表示された [ **Office 展開を管理する**] ウィンドウで、[ **グループの追加**] を選び、使用するグループを選びます。
    
4. 使用するグループを追加したら、[ **展開アクション**] ドロップダウンから、[ **できるだけ早く Office をインストールする**] または [ **Office をアンインストールする**] を選びます。
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Choose **Next** \> review the settings and then choose **Confirm**.
    
32 ビット版 Office は使用したグループで指定したユーザーが所有するデバイスに自動的にインストールまたはアンインストールされます。
  
Office のインストールに選択したコンピューターでタスク マネージャーが開けることを確認するには、Microsoft Office クイック実行プロセスを探します。
  


