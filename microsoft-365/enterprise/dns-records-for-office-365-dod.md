---
title: Office 365 DoD の DNS レコード
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '概要: DoD の DNS レコードOffice 365します。'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691835"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="9eef1-103">Office 365 DoD の DNS レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="9eef1-104">*この記事は DoD および DoD Office 365にMicrosoft 365します。*</span><span class="sxs-lookup"><span data-stu-id="9eef1-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="9eef1-105">DoD へのオンボーディングOffice 365、オンライン サービス テナントに SMTP ドメインと SIP ドメインを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eef1-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="9eef1-106">これを行うには、Azure AD PowerShell の New-MsolDomain コマンドレットを使用するか [、Azure Government Portal](https://portal.azure.us) を使用してドメインを追加して所有権を確認するプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="9eef1-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="9eef1-107">ドメインをテナントに追加して検証したら、次のガイダンスを使用して、以下のサービスに適切な DNS レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9eef1-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="9eef1-108">受信 MX レコードおよび既存の Exchange 自動検出レコードに関して、組織のニーズに合わせて以下の表を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9eef1-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="9eef1-109">これらの DNS レコードをメッセージング チームと調整して、電子メールの停止や配信の誤りを避けることを強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="9eef1-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="9eef1-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9eef1-110">Exchange Online</span></span>

| <span data-ttu-id="9eef1-111">Type</span><span class="sxs-lookup"><span data-stu-id="9eef1-111">Type</span></span> | <span data-ttu-id="9eef1-112">Priority</span><span class="sxs-lookup"><span data-stu-id="9eef1-112">Priority</span></span> | <span data-ttu-id="9eef1-113">ホスト名</span><span class="sxs-lookup"><span data-stu-id="9eef1-113">Host name</span></span> | <span data-ttu-id="9eef1-114">アドレスまたは値をポイントする</span><span class="sxs-lookup"><span data-stu-id="9eef1-114">Points to address or value</span></span> | <span data-ttu-id="9eef1-115">TTL</span><span class="sxs-lookup"><span data-stu-id="9eef1-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="9eef1-116">MX</span><span class="sxs-lookup"><span data-stu-id="9eef1-116">MX</span></span> | <span data-ttu-id="9eef1-117">0</span><span class="sxs-lookup"><span data-stu-id="9eef1-117">0</span></span> | @ | <span data-ttu-id="9eef1-118">*tenant*.mail.protection.office365.us (詳細については、以下を参照してください)</span><span class="sxs-lookup"><span data-stu-id="9eef1-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="9eef1-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-119">1 Hour</span></span> |
| <span data-ttu-id="9eef1-120">TXT</span><span class="sxs-lookup"><span data-stu-id="9eef1-120">TXT</span></span> | - | @ | <span data-ttu-id="9eef1-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="9eef1-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="9eef1-122">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-122">1 Hour</span></span> |
| <span data-ttu-id="9eef1-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="9eef1-123">CNAME</span></span> | - | <span data-ttu-id="9eef1-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9eef1-124">autodiscover</span></span> | <span data-ttu-id="9eef1-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="9eef1-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="9eef1-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="9eef1-127">Exchange自動検出レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="9eef1-128">オンプレミスでExchange Server場合は、Exchange Online への移行中に既存のレコードを残し、移行が完了したらそのレコードを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9eef1-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="9eef1-129">Exchange OnlineMX レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-129">Exchange Online MX Record</span></span>

<span data-ttu-id="9eef1-130">受け入れドメインの MX レコード値は、上記の標準形式に従います。テナント *.mail.protection.office365.us* は、テナントを既定のテナント名の最初の部分に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9eef1-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="9eef1-131">たとえば、テナント名が contoso.onmicrosoft.us、MX レコード contoso.mail.protection.office365.us として使用します。</span><span class="sxs-lookup"><span data-stu-id="9eef1-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="9eef1-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9eef1-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="9eef1-133">CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-133">CNAME records</span></span>

| <span data-ttu-id="9eef1-134">型</span><span class="sxs-lookup"><span data-stu-id="9eef1-134">Type</span></span> | <span data-ttu-id="9eef1-135">ホスト名</span><span class="sxs-lookup"><span data-stu-id="9eef1-135">Host name</span></span> | <span data-ttu-id="9eef1-136">アドレスまたは値をポイントする</span><span class="sxs-lookup"><span data-stu-id="9eef1-136">Points to address or value</span></span> | <span data-ttu-id="9eef1-137">TTL</span><span class="sxs-lookup"><span data-stu-id="9eef1-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="9eef1-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="9eef1-138">CNAME</span></span> | <span data-ttu-id="9eef1-139">sip</span><span class="sxs-lookup"><span data-stu-id="9eef1-139">sip</span></span> | <span data-ttu-id="9eef1-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9eef1-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9eef1-141">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-141">1 Hour</span></span> |
| <span data-ttu-id="9eef1-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="9eef1-142">CNAME</span></span> | <span data-ttu-id="9eef1-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9eef1-143">lyncdiscover</span></span> | <span data-ttu-id="9eef1-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9eef1-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9eef1-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="9eef1-146">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-146">SRV records</span></span>

| <span data-ttu-id="9eef1-147">型</span><span class="sxs-lookup"><span data-stu-id="9eef1-147">Type</span></span> | <span data-ttu-id="9eef1-148">サービス</span><span class="sxs-lookup"><span data-stu-id="9eef1-148">Service</span></span> | <span data-ttu-id="9eef1-149">プロトコル</span><span class="sxs-lookup"><span data-stu-id="9eef1-149">Protocol</span></span> | <span data-ttu-id="9eef1-150">ポート</span><span class="sxs-lookup"><span data-stu-id="9eef1-150">Port</span></span> | <span data-ttu-id="9eef1-151">太さ</span><span class="sxs-lookup"><span data-stu-id="9eef1-151">Weight</span></span> | <span data-ttu-id="9eef1-152">Priority</span><span class="sxs-lookup"><span data-stu-id="9eef1-152">Priority</span></span> | <span data-ttu-id="9eef1-153">名前</span><span class="sxs-lookup"><span data-stu-id="9eef1-153">Name</span></span> | <span data-ttu-id="9eef1-154">Target</span><span class="sxs-lookup"><span data-stu-id="9eef1-154">Target</span></span> | <span data-ttu-id="9eef1-155">TTL</span><span class="sxs-lookup"><span data-stu-id="9eef1-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="9eef1-156">SRV</span><span class="sxs-lookup"><span data-stu-id="9eef1-156">SRV</span></span> | <span data-ttu-id="9eef1-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="9eef1-157">\_sip</span></span> | <span data-ttu-id="9eef1-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="9eef1-158">\_tls</span></span> | <span data-ttu-id="9eef1-159">443</span><span class="sxs-lookup"><span data-stu-id="9eef1-159">443</span></span> | <span data-ttu-id="9eef1-160">1</span><span class="sxs-lookup"><span data-stu-id="9eef1-160">1</span></span> | <span data-ttu-id="9eef1-161">100</span><span class="sxs-lookup"><span data-stu-id="9eef1-161">100</span></span> | @ | <span data-ttu-id="9eef1-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9eef1-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9eef1-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-163">1 Hour</span></span> |
| <span data-ttu-id="9eef1-164">SRV</span><span class="sxs-lookup"><span data-stu-id="9eef1-164">SRV</span></span> | <span data-ttu-id="9eef1-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="9eef1-165">\_sipfederationtls</span></span> | <span data-ttu-id="9eef1-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="9eef1-166">\_tcp</span></span> | <span data-ttu-id="9eef1-167">5061</span><span class="sxs-lookup"><span data-stu-id="9eef1-167">5061</span></span> | <span data-ttu-id="9eef1-168">1</span><span class="sxs-lookup"><span data-stu-id="9eef1-168">1</span></span> | <span data-ttu-id="9eef1-169">100</span><span class="sxs-lookup"><span data-stu-id="9eef1-169">100</span></span> | @ | <span data-ttu-id="9eef1-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="9eef1-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="9eef1-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="9eef1-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="9eef1-172">追加の DNS レコード</span><span class="sxs-lookup"><span data-stu-id="9eef1-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9eef1-173">DNS ゾーンに既存の *msoid* CNAME レコードがある場合は、この時点で DNS からレコードを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eef1-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="9eef1-174">msoid レコードは、Microsoft 365 Enterprise (以前は *Office 365 ProPlus)* と互換性がなく、ライセンス認証が成功しなかれない。</span><span class="sxs-lookup"><span data-stu-id="9eef1-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
