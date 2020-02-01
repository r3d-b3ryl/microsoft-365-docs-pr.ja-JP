---
title: Microsoft 365 Business による Office クライアントの展開を準備する
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新したままにする方法について説明します。
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593621"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="a7009-103">Microsoft 365 Business による Office クライアントの展開を準備する</span><span class="sxs-lookup"><span data-stu-id="a7009-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="a7009-104">Office アプリをクライアント コンピューターに自動的にインストールするための準備</span><span class="sxs-lookup"><span data-stu-id="a7009-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="a7009-105">Microsoft 365 Business を使用して、Windows 10 コンピューターに32ビットの Office アプリを自動的にインストールし、更新プログラムを最新の状態に保つことができます。</span><span class="sxs-lookup"><span data-stu-id="a7009-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="a7009-106">自動インストールは、エンドユーザーのコンピューターが Windows 10 Business 上にあり、次の場合に最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="a7009-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="a7009-107">既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。</span><span class="sxs-lookup"><span data-stu-id="a7009-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="a7009-108">または</span><span class="sxs-lookup"><span data-stu-id="a7009-108">or</span></span>
    
- <span data-ttu-id="a7009-109">Office のクイック実行の既存バージョンがインストールされている。</span><span class="sxs-lookup"><span data-stu-id="a7009-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="a7009-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="a7009-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="a7009-111">次の図に示すように**Office の更新プログラム**が表示された場合は、クイック実行を使用してインストールを実行しています。</span><span class="sxs-lookup"><span data-stu-id="a7009-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="a7009-113">**この機能を利用するメリット**</span><span class="sxs-lookup"><span data-stu-id="a7009-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="a7009-114">次の PC を持つエンドユーザー:</span><span class="sxs-lookup"><span data-stu-id="a7009-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="a7009-115">Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 Business ライセンス、および Windows 10 Creators Update が **あり** 、Azure Active Directory に参加している。</span><span class="sxs-lookup"><span data-stu-id="a7009-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="a7009-116">64ビットの Office アプリ (例: Word、Excel、PowerPoint)**はありません**。</span><span class="sxs-lookup"><span data-stu-id="a7009-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="a7009-117">64ビットの Office アプリが必要な場合、この機能は、Microsoft の 365 Business 管理コンソールからの、64 2016 ビットのクイック実行バージョンの Office の起動をサポートしていないため、この機能は適していません。</span><span class="sxs-lookup"><span data-stu-id="a7009-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="a7009-118">任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。</span><span class="sxs-lookup"><span data-stu-id="a7009-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="a7009-119">Microsoft 365 Business は office をクイック実行バージョンの Office 2016 にアップグレードします。これは Office 2016 MSI スタンドアロンアプリでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="a7009-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="a7009-120">次の表に、エンドユーザーまたは管理者が、その開始状態に応じて、Microsoft 365 Business 管理コンソールから Office 展開の32ビットクイック実行バージョンを正常にインストールするために必要となる可能性のあるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="a7009-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="a7009-121">**Office インストールの開始状態**</span><span class="sxs-lookup"><span data-stu-id="a7009-121">**Starting Office install status**</span></span>|<span data-ttu-id="a7009-122">**Microsoft 365 Business Office のインストール前に行うアクション**</span><span class="sxs-lookup"><span data-stu-id="a7009-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="a7009-123">**終了状態**</span><span class="sxs-lookup"><span data-stu-id="a7009-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7009-124">Office スイート製品がインストールされない</span><span class="sxs-lookup"><span data-stu-id="a7009-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="a7009-125">None</span><span class="sxs-lookup"><span data-stu-id="a7009-125">None</span></span>  <br/> |<span data-ttu-id="a7009-126">クイック実行を使用して Office 2016 32 ビットがインストールされている</span><span class="sxs-lookup"><span data-stu-id="a7009-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="a7009-127">Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない</span><span class="sxs-lookup"><span data-stu-id="a7009-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="a7009-128">None</span><span class="sxs-lookup"><span data-stu-id="a7009-128">None</span></span>  <br/> |<span data-ttu-id="a7009-129">必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\***</span><span class="sxs-lookup"><span data-stu-id="a7009-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="a7009-130">既存のクイック実行32ビットバージョンの Office とクイック実行の32ビットバージョンまたは64ビットバージョンの Office アプリ (たとえば、Visio、Project)</span><span class="sxs-lookup"><span data-stu-id="a7009-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="a7009-131">None</span><span class="sxs-lookup"><span data-stu-id="a7009-131">None</span></span>  <br/> |<span data-ttu-id="a7009-132">スタンドアロンアプリは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a7009-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="a7009-133">スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="a7009-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="a7009-134">Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある</span><span class="sxs-lookup"><span data-stu-id="a7009-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="a7009-135">None</span><span class="sxs-lookup"><span data-stu-id="a7009-135">None</span></span>  <br/> |<span data-ttu-id="a7009-136">スタンドアロンアプリは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a7009-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="a7009-137">スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="a7009-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="a7009-138">任意の Office の 64 ビット版クイック実行バージョンがある</span><span class="sxs-lookup"><span data-stu-id="a7009-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="a7009-139">64ビット版の Office アプリをアンインストールしても、32ビットの Office アプリに置き換えられる場合は、アンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7009-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="a7009-140">64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする</span><span class="sxs-lookup"><span data-stu-id="a7009-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="a7009-141">Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)</span><span class="sxs-lookup"><span data-stu-id="a7009-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="a7009-142">MSI Office 2016 をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="a7009-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="a7009-p106">Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし</span><span class="sxs-lookup"><span data-stu-id="a7009-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="a7009-145">既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="a7009-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="a7009-146">なし</span><span class="sxs-lookup"><span data-stu-id="a7009-146">None</span></span>  <br/> |<span data-ttu-id="a7009-147">Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する</span><span class="sxs-lookup"><span data-stu-id="a7009-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="a7009-148">**(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="a7009-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="a7009-149">修正が進行中です。</span><span class="sxs-lookup"><span data-stu-id="a7009-149">A fix is in progress.</span></span> 
  