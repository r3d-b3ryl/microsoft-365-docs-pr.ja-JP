---
title: Windows 10 デバイスで Office を自動的にインストールまたはアンインストールする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: 'インストールまたは Microsoft 365 ビジネス管理センター」からの 10 の Windows デバイス上の Office をアンインストールします。 '
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869427"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="75a5b-103">Windows 10 デバイスで Office を自動的にインストールまたはアンインストールする</span><span class="sxs-lookup"><span data-stu-id="75a5b-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="75a5b-104">Microsoft 365 Business 管理センターから Office を Windows 10 PC に迅速かつ簡単にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="75a5b-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="75a5b-105">以前にインストールした Office アプリでこれがどのように機能するかを理解するには、開始する前に、「[Microsoft 365 Business による Office クライアントの展開を準備する](prepare-for-office-client-deployment.md)」をお読みください。</span><span class="sxs-lookup"><span data-stu-id="75a5b-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="75a5b-106">Office 展開を管理する</span><span class="sxs-lookup"><span data-stu-id="75a5b-106">Manage Office deployments</span></span>

1. <span data-ttu-id="75a5b-107">グローバル管理者の資格情報を使用して、[管理センター](https://aka.ms/bcsportal)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="75a5b-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="75a5b-p101">**デバイス**カード上には、 **Office の展開の管理**を選択します。   **デバイスのアクション**カードが表示されない場合は、管理センターの**ホーム**ページの**追加**(+)、管理者のホームに追加するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="75a5b-p101">On the **Devices** card, choose **Manage Office Deployment**.    If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="75a5b-111">表示された [ **Office 展開を管理する**] ウィンドウで、[ **グループの追加**] を選び、使用するグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="75a5b-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="75a5b-112">使用するグループを追加したら、[ **展開アクション**] ドロップダウンから、[ **できるだけ早く Office をインストールする**] または [ **Office をアンインストールする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="75a5b-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="75a5b-114">**次へ**を選択して\>の設定を確認して、**確認**します。</span><span class="sxs-lookup"><span data-stu-id="75a5b-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="75a5b-115">32 ビット版 Office は使用したグループで指定したユーザーが所有するデバイスに自動的にインストールまたはアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="75a5b-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="75a5b-116">Office のインストールに選択したコンピューターでタスク マネージャーが開けることを確認するには、Microsoft Office クイック実行プロセスを探します。</span><span class="sxs-lookup"><span data-stu-id="75a5b-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


