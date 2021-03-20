---
title: 未成年者とストアからアドインを取得する
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
description: 未成年者の個人データを管理する一般データ保護規則 (GDPR) の規制について学ぶ。
ms.openlocfilehash: c49ea719bc85166cc8082200eb833273b0ab5835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915256"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="0f73d-103">未成年者とストアからアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="0f73d-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="0f73d-104">一般データ保護規則 (GDPR) は、2018 年 5 月 25 日に発効する欧州連合の規則です。</span><span class="sxs-lookup"><span data-stu-id="0f73d-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="0f73d-105">これにより、ユーザーはデータに対する権限と保護をユーザーに与えます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="0f73d-106">GDPR の側面の 1 つは、未成年者が自分の個人データを親または保護者が承認しない当事者に送信できないことです。</span><span class="sxs-lookup"><span data-stu-id="0f73d-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="0f73d-107">未成年者として定義される特定の年齢は、個人が位置する地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0f73d-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="0f73d-108">親の同意に関する法的規制を持つ地域には、米国、韓国、英国、および欧州連合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="0f73d-109">これらの地域では、マイナーが (Azure Active Directory 経由で) ストアから新しい Office アドインを取得し、以前に取得したアドインを実行してブロックされます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="0f73d-110">法的規制のない国では、ダウンロードの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="0f73d-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="0f73d-111">ユーザーは、Azure Active Directory で指定されたデータに基づいてマイナーと判断されます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="0f73d-112">組織管理者は、法的年齢グループと、そのユーザーの親の同意を宣言する責任があります。</span><span class="sxs-lookup"><span data-stu-id="0f73d-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="0f73d-113">親/保護者が特定のアドインを使用して未成年者に同意した場合、組織管理者は集中展開を使用して、同意を得たすべての未成年者にアドインを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="0f73d-114">未成年者に対して GDPR に準拠するには、次の 1 つのビルドの Officeが学校/組織に展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f73d-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="0f73d-115">**Word、Excel、PowerPoint、および Project の場合**:</span><span class="sxs-lookup"><span data-stu-id="0f73d-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="0f73d-116">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0f73d-116">**Platform**</span></span> <br/> |<span data-ttu-id="0f73d-117">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="0f73d-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="0f73d-118">Microsoft 365 Apps for enterprise (Current Channel)</span><span class="sxs-lookup"><span data-stu-id="0f73d-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="0f73d-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="0f73d-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="0f73d-120">Microsoft 365 Apps for enterprise (半期エンタープライズ チャネル)</span><span class="sxs-lookup"><span data-stu-id="0f73d-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="0f73d-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="0f73d-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="0f73d-122">Office 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="0f73d-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="0f73d-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="0f73d-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="0f73d-124">Office 2013 for Windows</span><span class="sxs-lookup"><span data-stu-id="0f73d-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="0f73d-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="0f73d-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="0f73d-126">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="0f73d-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="0f73d-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="0f73d-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="0f73d-128">Web 用 Office</span><span class="sxs-lookup"><span data-stu-id="0f73d-128">Office for the web</span></span>  <br/> |<span data-ttu-id="0f73d-129">該当なし</span><span class="sxs-lookup"><span data-stu-id="0f73d-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="0f73d-130">**Outlook の場合**:</span><span class="sxs-lookup"><span data-stu-id="0f73d-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="0f73d-131">**プラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="0f73d-131">**Platform**</span></span> <br/> |<span data-ttu-id="0f73d-132">**ビルド番号**</span><span class="sxs-lookup"><span data-stu-id="0f73d-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="0f73d-133">Outlook 2016 for Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="0f73d-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="0f73d-134">ビルド TBD なし</span><span class="sxs-lookup"><span data-stu-id="0f73d-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="0f73d-135">Outlook 2016 for Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="0f73d-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="0f73d-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="0f73d-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="0f73d-137">Office 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="0f73d-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="0f73d-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="0f73d-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="0f73d-139">Outlook mobile for iOS</span><span class="sxs-lookup"><span data-stu-id="0f73d-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="0f73d-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="0f73d-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="0f73d-141">Android 用 Outlook モバイル</span><span class="sxs-lookup"><span data-stu-id="0f73d-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="0f73d-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="0f73d-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="0f73d-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="0f73d-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="0f73d-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="0f73d-144">N/A</span></span>  <br/> |

 <span data-ttu-id="0f73d-145">**Office 2013要件**</span><span class="sxs-lookup"><span data-stu-id="0f73d-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="0f73d-146">Word、Excel、PowerPoint 2013 for Windows では、Active Directory 認証ライブラリ (ADAL) が有効になっている場合と同じマイナー チェックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0f73d-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="0f73d-147">次に説明したように、コンプライアンスには 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0f73d-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="0f73d-148">**ADAL を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="0f73d-148">**Enable ADAL**.</span></span> <span data-ttu-id="0f73d-149">この記事では、ADAL for Office 2013: [Microsoft 365](../../enterprise/modern-auth-for-office-2013-and-2016.md)モダン認証をクライアントとOfficeします。</span><span class="sxs-lookup"><span data-stu-id="0f73d-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](../../enterprise/modern-auth-for-office-2013-and-2016.md).</span></span><br/><span data-ttu-id="0f73d-150">また、「Windows デバイスで最新の認証を有効にする」の説明に基Office 2013 [する必要があります](../security-and-compliance/enable-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="0f73d-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="0f73d-151">さらに、次の 4 月の更新プログラムをインストールする必要Office 2013。</span><span class="sxs-lookup"><span data-stu-id="0f73d-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="0f73d-152">2018 年 4 月 10 日Office 2013セキュリティ更新プログラムの説明</span><span class="sxs-lookup"><span data-stu-id="0f73d-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="0f73d-153">2018 年 4 月 3 日、Office 2013更新プログラム (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="0f73d-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="0f73d-154">**ADAL を有効にしない**。</span><span class="sxs-lookup"><span data-stu-id="0f73d-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="0f73d-155">ADAL を Office 2013 で有効にできない場合は、グループ ポリシーを使用してクライアントのストアを無効にOfficeします。</span><span class="sxs-lookup"><span data-stu-id="0f73d-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="0f73d-156">アプリの設定をオフにする方法については、Officeを参照 [してください](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))。</span><span class="sxs-lookup"><span data-stu-id="0f73d-156">Information on how to turn off the app for Office settings is located [here](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).</span></span>

## <a name="related-articles"></a><span data-ttu-id="0f73d-157">関連記事</span><span class="sxs-lookup"><span data-stu-id="0f73d-157">Related articles</span></span>

[<span data-ttu-id="0f73d-158">管理センターでアドインを展開する</span><span class="sxs-lookup"><span data-stu-id="0f73d-158">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

[<span data-ttu-id="0f73d-159">管理センターでアドインを管理する</span><span class="sxs-lookup"><span data-stu-id="0f73d-159">Manage add-ins in the admin center</span></span>](./manage-addins-in-the-admin-center.md)
