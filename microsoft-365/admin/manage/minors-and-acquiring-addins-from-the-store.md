---
title: 未成年者とストアからのアドインの取得
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 未成年者の個人データを管理する一般的なデータ保護規則 (GDPR) の規則について説明します。
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306553"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="36248-103">未成年者とストアからのアドインの取得</span><span class="sxs-lookup"><span data-stu-id="36248-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="36248-104">一般的なデータ保護規則 (GDPR) は、2018年5月25日に有効になる欧州連合規制です。</span><span class="sxs-lookup"><span data-stu-id="36248-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="36248-105">ユーザーがデータを保護するための権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="36248-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="36248-106">GDPR の1つの側面は、親またはガーディアンが許可されていない個人データを、未成年者が他者に送信することができないことです。</span><span class="sxs-lookup"><span data-stu-id="36248-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="36248-107">マイナーとして定義された特定の年齢は、個人が配置されている地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="36248-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="36248-108">保護者の同意に関する法的な規制がある地域には、米国、南韓国、英国、および欧州連合があります。</span><span class="sxs-lookup"><span data-stu-id="36248-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="36248-109">これらの地域では、マイナーがブロックされます (Azure Active Directory によって)。新しい Office アドインをストアから取得し、以前に取得したアドインを実行します。</span><span class="sxs-lookup"><span data-stu-id="36248-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="36248-110">法律上の規定がない国では、ダウンロードの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="36248-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="36248-111">ユーザーは、Azure Active Directory で指定されているデータに基づいて、マイナーであると判断されます。</span><span class="sxs-lookup"><span data-stu-id="36248-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="36248-112">組織管理者は、法務年齢グループと、そのユーザーの上位下位の同意を宣言します。</span><span class="sxs-lookup"><span data-stu-id="36248-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="36248-113">親/ガーディアンが特定のアドインを使用して小規模に同意場合、組織管理者は一元展開を使用して、同意を得ているすべての未成年者にそのアドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="36248-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="36248-114">GDPR を未成年者に準拠させるには、次のいずれかの Office ビルドが学校/組織に展開されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36248-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="36248-115">**Word、Excel、PowerPoint、Project の場合**:</span><span class="sxs-lookup"><span data-stu-id="36248-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="36248-116">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="36248-116">**Platform**</span></span> <br/> |<span data-ttu-id="36248-117">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="36248-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="36248-118">Microsoft 365 enterprise 用アプリ (現在のチャネル)</span><span class="sxs-lookup"><span data-stu-id="36248-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="36248-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="36248-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="36248-120">Microsoft 365 enterprise 用アプリ (半期エンタープライズチャネル)</span><span class="sxs-lookup"><span data-stu-id="36248-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="36248-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="36248-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="36248-122">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="36248-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="36248-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="36248-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="36248-124">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="36248-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="36248-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="36248-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="36248-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="36248-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="36248-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="36248-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="36248-128">Web 用 Office</span><span class="sxs-lookup"><span data-stu-id="36248-128">Office for the web</span></span>  <br/> |<span data-ttu-id="36248-129">N/A</span><span class="sxs-lookup"><span data-stu-id="36248-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="36248-130">**Outlook の場合**:</span><span class="sxs-lookup"><span data-stu-id="36248-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="36248-131">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="36248-131">**Platform**</span></span> <br/> |<span data-ttu-id="36248-132">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="36248-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="36248-133">Outlook 2016 for Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="36248-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="36248-134">ビルドの未定</span><span class="sxs-lookup"><span data-stu-id="36248-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="36248-135">Windows 版 Outlook 2016 (C2R)</span><span class="sxs-lookup"><span data-stu-id="36248-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="36248-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="36248-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="36248-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="36248-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="36248-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="36248-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="36248-139">IOS 用の Outlook mobile</span><span class="sxs-lookup"><span data-stu-id="36248-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="36248-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="36248-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="36248-141">Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="36248-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="36248-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="36248-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="36248-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="36248-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="36248-144">N/A</span><span class="sxs-lookup"><span data-stu-id="36248-144">N/A</span></span>  <br/> |

 <span data-ttu-id="36248-145">**Office 2013 の要件**</span><span class="sxs-lookup"><span data-stu-id="36248-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="36248-146">Windows 版 Word、Excel、PowerPoint 2013 は、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じ未成年者チェックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="36248-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="36248-147">次に説明するように、2つのコンプライアンスオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="36248-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="36248-148">**ADAL を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="36248-148">**Enable ADAL**.</span></span> <span data-ttu-id="36248-149">この記事では、office [クライアントでの Microsoft 365 モダン認証](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)2013 の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36248-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="36248-150">「 [Windows デバイスで Office 2013 の先進認証を有効](../security-and-compliance/enable-modern-authentication.md)にする」で説明されているように、レジストリキーを設定して ADAL を有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="36248-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="36248-151">さらに、Office 2013 用の次の4月の更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36248-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="36248-152">Office 2013 のセキュリティ更新プログラムの説明: 2018 年4月10日</span><span class="sxs-lookup"><span data-stu-id="36248-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="36248-153">2018年4月3日 Office 2013 の更新プログラム (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="36248-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="36248-154">**ADAL を有効にしない**でください。</span><span class="sxs-lookup"><span data-stu-id="36248-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="36248-155">Office 2013 で ADAL を有効にできない場合は、グループポリシーを使用して Office クライアントのストアをオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36248-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="36248-156">Office 用アプリの設定を無効にする方法については、 [ここ](https://technet.microsoft.com/library/cc178992.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36248-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="36248-157">関連記事</span><span class="sxs-lookup"><span data-stu-id="36248-157">Related articles</span></span>

[<span data-ttu-id="36248-158">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="36248-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="36248-159">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="36248-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
