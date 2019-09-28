---
title: Microsoft 365 Business による Office クライアントの展開を準備する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新したままにする方法について説明します。
ms.openlocfilehash: fe1f946e4a216050e533604afa7c6e74e7b5980f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288397"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="800e0-103">Microsoft 365 Business による Office クライアントの展開を準備する</span><span class="sxs-lookup"><span data-stu-id="800e0-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="800e0-104">Office アプリをクライアント コンピューターに自動的にインストールするための準備</span><span class="sxs-lookup"><span data-stu-id="800e0-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="800e0-105">Microsoft 365 Business を使用すると、32 ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新プログラムで最新状態に維持することができます。</span><span class="sxs-lookup"><span data-stu-id="800e0-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="800e0-106">これは、エンドユーザーのコンピューターで Windows 10 Business が実行されていて、なおかつ次の場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="800e0-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="800e0-107">既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。</span><span class="sxs-lookup"><span data-stu-id="800e0-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="800e0-108">または</span><span class="sxs-lookup"><span data-stu-id="800e0-108">or</span></span>
    
- <span data-ttu-id="800e0-109">Office のクイック実行の既存バージョンがインストールされている。</span><span class="sxs-lookup"><span data-stu-id="800e0-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="800e0-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="800e0-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="800e0-113">**この機能の恩恵を受けるユーザー**</span><span class="sxs-lookup"><span data-stu-id="800e0-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="800e0-114">次の PC を持つエンドユーザー:</span><span class="sxs-lookup"><span data-stu-id="800e0-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="800e0-115">Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 Business ライセンス、および Windows 10 Creators Update が **あり** 、Azure Active Directory に参加している。</span><span class="sxs-lookup"><span data-stu-id="800e0-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="800e0-p102">64 ビット版の Office アプリが **ない** (例:Word、Excel、PowerPoint)。64 ビット版の Office アプリが必要な場合、この機能は適合しません。Microsoft 365 Business 管理コンソールから Office 2016 の 64 ビット版のクイック実行バージョンのトリガーがサポートされていないからです。</span><span class="sxs-lookup"><span data-stu-id="800e0-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="800e0-p103">任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。Microsoft 365 Business では Office は Office 2016 のクイック実行バージョンにアップグレードされますが、これは Office 2016 MSI 単体アプリでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="800e0-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="800e0-120">次の表では、Microsoft 365 Business管理コンソールから 32 ビット版クイック実行バージョンの Office を正しく展開するために、開始状態に応じて、エンドユーザー/管理者が実行する必要のあるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="800e0-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="800e0-121">**Office インストールの開始状態**</span><span class="sxs-lookup"><span data-stu-id="800e0-121">**Starting Office install status**</span></span>|<span data-ttu-id="800e0-122">**Microsoft 365 Business Office のインストール前に行うアクション**</span><span class="sxs-lookup"><span data-stu-id="800e0-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="800e0-123">**終了状態**</span><span class="sxs-lookup"><span data-stu-id="800e0-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="800e0-124">Office スイート製品がインストールされない</span><span class="sxs-lookup"><span data-stu-id="800e0-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="800e0-125">なし</span><span class="sxs-lookup"><span data-stu-id="800e0-125">None</span></span>  <br/> |<span data-ttu-id="800e0-126">クイック実行を使用して Office 2016 の 32 ビット版をインストールする</span><span class="sxs-lookup"><span data-stu-id="800e0-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="800e0-127">Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない</span><span class="sxs-lookup"><span data-stu-id="800e0-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="800e0-128">なし</span><span class="sxs-lookup"><span data-stu-id="800e0-128">None</span></span>  <br/> |<span data-ttu-id="800e0-129">必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\***</span><span class="sxs-lookup"><span data-stu-id="800e0-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="800e0-130">Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版クイック実行の単体 Office アプリ (Visio、Project など) がある</span><span class="sxs-lookup"><span data-stu-id="800e0-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="800e0-131">なし</span><span class="sxs-lookup"><span data-stu-id="800e0-131">None</span></span>  <br/> |<span data-ttu-id="800e0-p104">単体アプリは影響を受けない。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="800e0-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="800e0-134">Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある</span><span class="sxs-lookup"><span data-stu-id="800e0-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="800e0-135">なし</span><span class="sxs-lookup"><span data-stu-id="800e0-135">None</span></span>  <br/> |<span data-ttu-id="800e0-p105">単体アプリは影響を受けない。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="800e0-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="800e0-138">任意の Office の 64 ビット版クイック実行バージョンがある</span><span class="sxs-lookup"><span data-stu-id="800e0-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="800e0-139">32 ビット版の Office アプリに置き換えても問題ない場合は、64 ビット版の Office アプリをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="800e0-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="800e0-140">64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする</span><span class="sxs-lookup"><span data-stu-id="800e0-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="800e0-141">Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)</span><span class="sxs-lookup"><span data-stu-id="800e0-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="800e0-142">MSI Office 2016 をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="800e0-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="800e0-p106">Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし</span><span class="sxs-lookup"><span data-stu-id="800e0-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="800e0-145">既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="800e0-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="800e0-146">なし</span><span class="sxs-lookup"><span data-stu-id="800e0-146">None</span></span>  <br/> |<span data-ttu-id="800e0-147">Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する</span><span class="sxs-lookup"><span data-stu-id="800e0-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="800e0-p107">**(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。修正中です。</span><span class="sxs-lookup"><span data-stu-id="800e0-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


