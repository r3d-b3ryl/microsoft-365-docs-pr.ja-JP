---
title: 以前のバージョンのメッセージ暗号化用に Azure Rights Management をセットアップする
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 以前のバージョンの Office 365 メッセージの暗号化は、Microsoft Azure Rights Management (旧称 Windows Azure Active Directory Rights Management) に依存します。
ms.openlocfilehash: 234115a76116fe9033e8da7868f846658d0d3eee
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943266"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="a1032-103">以前のバージョンのメッセージ暗号化用に Azure Rights Management をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a1032-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="a1032-104">このトピックでは、以前のバージョンの Office 365 Message Encryption (OME) を使用するために、azure Information Protection の一部である azure Rights Management (RMS) をアクティブ化してからセットアップするために従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1032-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="a1032-105">この記事は、以前のバージョンの OME にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1032-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="a1032-106">まだ組織を新しい OME 機能に移行していない場合でも、既に OME を展開している場合は、この記事の情報が組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1032-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="a1032-107">Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="a1032-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="a1032-108">手順については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="a1032-109">新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="a1032-110">この記事の残りの部分では、新しい OME 機能のリリース前の OME の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="a1032-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="a1032-111">以前のバージョンの Office 365 メッセージ暗号化を使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="a1032-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="a1032-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="a1032-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="a1032-113">Office 365 Message Encryption (OME) は、IRM を含め、Azure Rights Management (Azure RMS) に依存しています。</span><span class="sxs-lookup"><span data-stu-id="a1032-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="a1032-114">Azure RMS は、Azure Information Protection で使用される保護テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="a1032-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="a1032-115">OME を使用するには、組織に Exchange Online または Exchange Online Protection のサブスクリプションを含める必要があります。これには、Azure Rights Management サブスクリプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1032-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="a1032-116">サブスクリプションに含まれる内容がわからない場合は、「Exchange Online サービスの[メッセージポリシー、回復、および準拠](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)」の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="a1032-117">Azure rights Management を使用していても、Exchange Online または Exchange Online Protection 用にセットアップされていない場合は、この記事で azure rights management をアクティブ化する方法について説明します。次に、Azure Rights Management と連携するように OME をセットアップするための最適な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1032-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="a1032-118">Exchange Online または Exchange Online Protection の Azure Rights Management で作業するための OME を既にセットアップしている場合は、設定方法によっては、OME とその新機能をすぐに使用する準備ができている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1032-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="a1032-119">この記事では、OME が正しく設定されているかどうかを判断する方法、設定を変更する必要がある場合の対処方法、および設定を変更しない場合の対処方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1032-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="a1032-120">たとえば、新しい機能を使用するためには、Azure RMS を OME と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1032-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="a1032-121">オンプレミスの Active Directory RMS で新しい機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1032-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="a1032-122">Office 365 の以前のバージョンの OME の Azure Rights Management をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="a1032-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="a1032-123">組織内のユーザーが情報保護を送信するメッセージに適用できるように、azure rights Management サービスで保護されたメッセージやファイルを開くには、Azure Rights Management をアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1032-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="a1032-124">手順については、「 [Azure Rights Management をアクティブ化](https://go.microsoft.com/fwlink/p/?LinkId=525775)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-124">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="a1032-125">ライセンス認証を完了したら、ここに戻り、この記事のタスクを続行します。</span><span class="sxs-lookup"><span data-stu-id="a1032-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="a1032-126">信頼された発行ドメインをインポートすることによって Azure RMS を使用するように以前のバージョンの OME をセットアップする (TPDs)</span><span class="sxs-lookup"><span data-stu-id="a1032-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="a1032-127">TPD は、組織の権限管理設定に関する情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a1032-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="a1032-128">たとえば、TPD には、証明書とライセンスの署名と暗号化、ライセンスと発行に使用される Url などに使用されるサーバーライセンサー証明書 (SLC) に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1032-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="a1032-129">Windows PowerShell を使用して、TPD を組織にインポートします。</span><span class="sxs-lookup"><span data-stu-id="a1032-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a1032-130">以前は、Active Directory Rights Management サービス (AD RMS) から組織に TPDs をインポートすることを選択できました。</span><span class="sxs-lookup"><span data-stu-id="a1032-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="a1032-131">ただし、これを行うと、新しい OME 機能を使用できなくなり、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="a1032-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="a1032-132">現在組織がこの方法で構成されている場合は、オンプレミスの Active Directory RMS からクラウドベースの Azure Information Protection に移行する計画を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1032-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="a1032-133">詳細については、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-133">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="a1032-134">Azure Information Protection への移行が完了するまで、新しい OME 機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a1032-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="a1032-135">**Azure RMS から TPDs をインポートするには**</span><span class="sxs-lookup"><span data-stu-id="a1032-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="a1032-136">[リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="a1032-136">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="a1032-137">組織の地理的な場所に対応するキー共有 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1032-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="a1032-138">**Location**</span><span class="sxs-lookup"><span data-stu-id="a1032-138">**Location**</span></span>|<span data-ttu-id="a1032-139">**キー共有場所の URL**</span><span class="sxs-lookup"><span data-stu-id="a1032-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a1032-140">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="a1032-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="a1032-141">欧州連合</span><span class="sxs-lookup"><span data-stu-id="a1032-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="a1032-142">アジア</span><span class="sxs-lookup"><span data-stu-id="a1032-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="a1032-143">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="a1032-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="a1032-144">行政機関向け Office 365 (行政機関のコミュニティ クラウド)</span><span class="sxs-lookup"><span data-stu-id="a1032-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="a1032-145">この RMS キー共有場所は、Office 365 を Government Sku 用に購入したお客様向けに予約されています。</span><span class="sxs-lookup"><span data-stu-id="a1032-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="a1032-146">次のように、 [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)コマンドレットを実行して、キー共有の場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="a1032-146">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="a1032-147">たとえば、組織が北米に配置されている場合に、主な共有場所を構成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a1032-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="a1032-148">-RMSOnline スイッチを使用して[import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)コマンドレットを実行し、Azure Rights MANAGEMENT から TPD をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a1032-148">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="a1032-149">ここで、 *Tpdname*は、TPD に対して使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="a1032-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="a1032-150">たとえば、「Contoso 社の北米 TPD」とします。</span><span class="sxs-lookup"><span data-stu-id="a1032-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="a1032-151">Azure Rights Management サービスを使用するように組織が正常に構成されたことを確認するには、次のように、-RMSOnline スイッチを使用して[Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1032-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="a1032-152">特に、このコマンドレットでは、Azure Rights Management サービスとの接続を確認し、TPD をダウンロードして、有効性をチェックします。</span><span class="sxs-lookup"><span data-stu-id="a1032-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="a1032-153">次のように、 [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行して、outlook on the Web および Outlook で Azure Rights Management テンプレートを使用できないようにします。</span><span class="sxs-lookup"><span data-stu-id="a1032-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="a1032-154">次のように、 [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行して、クラウドベースの電子メール組織の Azure rights management を有効にし、Office 365 メッセージの暗号化に Azure rights management を使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="a1032-154">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="a1032-155">TPD および有効にされた Azure Rights Management が正常にインポートされたことを確認するには、Test-IRMConfiguration コマンドレットを使用して Azure Rights Management 機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="a1032-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="a1032-156">詳細については、「 [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)」の「例1」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-156">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="a1032-157">以前のバージョンの OME が Azure Information Protection ではなく、Active Directory Rights Management を使用して設定されている場合は、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="a1032-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="a1032-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="a1032-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="a1032-159">Active Directory Rights Management で既存の Office 365 メッセージ暗号化のメールフロールールを引き続き使用することはできますが、新しい OME 機能を構成したり使用したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a1032-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="a1032-160">代わりに、Azure Information Protection に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1032-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="a1032-161">移行の詳細と、組織にとっての意味については、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a1032-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="a1032-162">Next steps</span></span>
<span data-ttu-id="a1032-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="a1032-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="a1032-164">Azure Rights Management のセットアップを完了した後、新しい OME 機能を有効にする場合は、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1032-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="a1032-165">新しい OME 機能を使用するように組織を設定した後、[メールフロールールを定義して、新しい OME 機能で電子メールメッセージを保護](define-mail-flow-rules-to-encrypt-email.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="a1032-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a1032-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1032-166">Related topics</span></span>
<span data-ttu-id="a1032-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="a1032-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="a1032-168">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="a1032-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="a1032-169">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="a1032-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="a1032-170">Azure Active Directory Rights Management の概要</span><span class="sxs-lookup"><span data-stu-id="a1032-170">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
