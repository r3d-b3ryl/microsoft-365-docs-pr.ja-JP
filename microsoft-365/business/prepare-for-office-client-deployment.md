---
title: ビジネス向けOfficeクライアントの展開Microsoft 365準備する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32 ビット アプリをコンピューターに自動的Officeし、Windows 10する方法について学習します。
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580056"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="8ddc5-103">ビジネス向けOfficeクライアントの展開Microsoft 365準備する</span><span class="sxs-lookup"><span data-stu-id="8ddc5-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="8ddc5-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="8ddc5-105">Office アプリをクライアント コンピューターに自動的にインストールするための準備</span><span class="sxs-lookup"><span data-stu-id="8ddc5-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="8ddc5-106">32 ビット Microsoft 365 Business Premiumを使用して、32 ビット Office アプリをWindows 10更新プログラムで最新の状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="8ddc5-107">自動インストールは、エンド ユーザーのコンピューターが次の手順で実行されている場合Windows 10 Business最適です。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="8ddc5-108">既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="8ddc5-109">または</span><span class="sxs-lookup"><span data-stu-id="8ddc5-109">or</span></span>
    
- <span data-ttu-id="8ddc5-110">Office のクイック実行の既存バージョンがインストールされている。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="8ddc5-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="8ddc5-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="8ddc5-112">次の図に **Office更新** プログラムが表示される場合は、インストールは次の手順で実行クイック実行。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="8ddc5-114">**Who機能を持つことの利点**</span><span class="sxs-lookup"><span data-stu-id="8ddc5-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="8ddc5-115">次の PC を持つエンドユーザー:</span><span class="sxs-lookup"><span data-stu-id="8ddc5-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="8ddc5-116">**ユーザー** ライセンスWindows 10 Business、ビジネス ライセンス、Microsoft 365クリエーター更新プログラムWindows 10アクティブなユーザー ライセンスを持ち、Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="8ddc5-117">**64** ビット アプリ (Word、Office、Excel など) をPowerPoint。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="8ddc5-118">64 ビット Office アプリが必要な場合、ビジネス管理コンソール用の Microsoft 365 から 64 ビット 2016 クイック実行 バージョンの Office をトリガーするサポートが存在しないので、この機能は適しています。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="8ddc5-119">任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="8ddc5-120">Microsoft 365 Office クイック実行 バージョン Office 2016 にアップグレードする場合、Office MSI スタンドアロン アプリでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="8ddc5-121">次の表に、エンド ユーザー/管理者が、ビジネス管理コンソール用の Microsoft 365 から 32 ビット クイック実行 バージョンの Office 展開を成功するために必要なアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="8ddc5-122">**Office インストールの開始状態**</span><span class="sxs-lookup"><span data-stu-id="8ddc5-122">**Starting Office install status**</span></span>|<span data-ttu-id="8ddc5-123">**ビジネス アプリケーションのインストールMicrosoft 365前に実行Officeアクション**</span><span class="sxs-lookup"><span data-stu-id="8ddc5-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="8ddc5-124">**終了状態**</span><span class="sxs-lookup"><span data-stu-id="8ddc5-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ddc5-125">Office スイート製品がインストールされない</span><span class="sxs-lookup"><span data-stu-id="8ddc5-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="8ddc5-126">なし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-126">None</span></span>  <br/> |<span data-ttu-id="8ddc5-127">Officeを使用して 2016 32 ビットがインストールクイック実行</span><span class="sxs-lookup"><span data-stu-id="8ddc5-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="8ddc5-128">Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない</span><span class="sxs-lookup"><span data-stu-id="8ddc5-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="8ddc5-129">なし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-129">None</span></span>  <br/> |<span data-ttu-id="8ddc5-130">必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\***</span><span class="sxs-lookup"><span data-stu-id="8ddc5-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="8ddc5-131">既存クイック実行 32 ビット バージョンの Office および クイック実行 32 ビットまたは 64 ビットスタンドアロン Office アプリ (Visio、Project など)</span><span class="sxs-lookup"><span data-stu-id="8ddc5-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="8ddc5-132">なし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-132">None</span></span>  <br/> |<span data-ttu-id="8ddc5-133">スタンドアロン アプリは影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="8ddc5-134">スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8ddc5-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="8ddc5-135">Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある</span><span class="sxs-lookup"><span data-stu-id="8ddc5-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="8ddc5-136">なし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-136">None</span></span>  <br/> |<span data-ttu-id="8ddc5-137">スタンドアロン アプリは影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="8ddc5-138">スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8ddc5-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="8ddc5-139">任意の Office の 64 ビット版クイック実行バージョンがある</span><span class="sxs-lookup"><span data-stu-id="8ddc5-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="8ddc5-140">64 ビット アプリをアンインストールOffice 32 ビット アプリに置き換Officeします。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="8ddc5-141">64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする</span><span class="sxs-lookup"><span data-stu-id="8ddc5-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="8ddc5-142">Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)</span><span class="sxs-lookup"><span data-stu-id="8ddc5-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="8ddc5-143">MSI Office 2016 をアンインストールする</span><span class="sxs-lookup"><span data-stu-id="8ddc5-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="8ddc5-p106">Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="8ddc5-146">既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ</span><span class="sxs-lookup"><span data-stu-id="8ddc5-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="8ddc5-147">なし</span><span class="sxs-lookup"><span data-stu-id="8ddc5-147">None</span></span>  <br/> |<span data-ttu-id="8ddc5-148">Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する</span><span class="sxs-lookup"><span data-stu-id="8ddc5-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="8ddc5-149">**(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="8ddc5-150">修正が進行中です。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-150">A fix is in progress.</span></span> 
  
