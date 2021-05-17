---
title: 以前のバージョンのメッセージ暗号化用に Azure Rights Management を設定する
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
description: 以前のバージョンの Office 365 Message Encryptionは、Microsoft Azure Rights Management (以前は Windows Azure Active Directory Rights Management) に依存します。
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919493"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="9ec2b-103">以前のバージョンのメッセージ暗号化用に Azure Rights Management を設定する</span><span class="sxs-lookup"><span data-stu-id="9ec2b-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="9ec2b-104">このトピックでは、以前のバージョンの Office 365 Message Encryption (OME) で使用するために Azure Information Protection の一部である Azure Rights Management (RMS) をアクティブ化してセットアップするために従う必要がある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="9ec2b-105">この記事は、以前のバージョンの OME にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="9ec2b-106">組織を新しい OME 機能にまだ移動していないが、既に OME を展開している場合は、この記事の情報が組織に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="9ec2b-107">Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="9ec2b-108">手順については、「新しい機能を[セットアップする」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="9ec2b-109">新しい機能の最初の動作の詳細については、「Office 365 Message Encryption」[を参照してください](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="9ec2b-110">この記事の残りの部分は、新しい OME 機能のリリース前の OME 動作を参照します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="9ec2b-111">以前のバージョンのサーバーを使用するための前提条件Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="9ec2b-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="9ec2b-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="9ec2b-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="9ec2b-113">Office 365 Message Encryption (OME) は、Azure Rights Management (Azure RMS) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="9ec2b-114">Azure RMS は、Azure Information Protection で使用される保護テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="9ec2b-115">OME を使用するには、組織に Azure Rights Management サブスクリプションExchange Onlineまたは Exchange Online Protectionサブスクリプションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="9ec2b-116">サブスクリプションに含まれる内容が不明な場合は、「メッセージ ポリシー、回復、およびコンプライアンスExchange Onlineサービスの説明」[を参照してください](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="9ec2b-117">Azure Rights Management を使用しているが、Exchange Online または Exchange Online Protection に対して設定されていない場合、この記事では Azure Rights Management をアクティブ化する方法と、Azure Rights Management で動作するように OME をセットアップする最適な方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="9ec2b-118">Exchange Online または Exchange Online Protection の Azure Rights Management を使用するように OME を既にセットアップしている場合は、設定方法に応じて、すぐに OME とその新しい機能の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="9ec2b-119">この記事では、OME を正しく設定したかどうかを判断する方法、セットアップを変更する必要がある場合の処理、セットアップを変更しない場合の処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="9ec2b-120">たとえば、新しい機能を使用するには、Azure RMS と OME を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="9ec2b-121">オンプレミスの Active Directory RMS では、新しい機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="9ec2b-122">以前のバージョンの OME に対して Azure Rights Management をアクティブ化Office 365</span><span class="sxs-lookup"><span data-stu-id="9ec2b-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="9ec2b-123">組織のユーザーが送信するメッセージに情報保護を適用し、Azure Rights Management サービスによって保護されているメッセージとファイルを開くことができるので、Azure Rights Management をアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="9ec2b-124">手順については [、「Azure Rights Management のアクティブ化」を参照してください](/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="9ec2b-125">ライセンス認証が完了したら、ここに戻り、この記事のタスクを続行します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="9ec2b-126">信頼できる発行ドメイン (TPD) をインポートして Azure RMS を使用するように以前のバージョンの OME をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9ec2b-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="9ec2b-127">TPD は、組織の権限管理設定に関する情報を含む XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="9ec2b-128">たとえば、TPD には、証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)、ライセンスおよび発行に使用される URL に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="9ec2b-129">TPD を組織にインポートするには、次のWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ec2b-130">以前は、Active Directory Rights Management サービス (RMS) から組織に TPD をインポートAD選択できます。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="9ec2b-131">ただし、そうすると、新しい OME 機能を使用できないので、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="9ec2b-132">組織が現在この方法で構成されている場合は、オンプレミスの Active Directory RMS からクラウドベースの Azure Information Protection に移行する計画を作成するようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="9ec2b-133">詳細については、「RMS から Azure Information Protection への [移行AD」を参照してください](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="9ec2b-134">Azure Information Protection への移行が完了するまで、新しい OME 機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="9ec2b-135">**Azure RMS から TPD をインポートするには**</span><span class="sxs-lookup"><span data-stu-id="9ec2b-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="9ec2b-136">[Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="9ec2b-137">組織の地理的な場所に対応するキー共有 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="9ec2b-138">**Location**</span><span class="sxs-lookup"><span data-stu-id="9ec2b-138">**Location**</span></span>|<span data-ttu-id="9ec2b-139">**キー共有場所の URL**</span><span class="sxs-lookup"><span data-stu-id="9ec2b-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ec2b-140">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="9ec2b-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="9ec2b-141">欧州連合</span><span class="sxs-lookup"><span data-stu-id="9ec2b-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="9ec2b-142">アジア</span><span class="sxs-lookup"><span data-stu-id="9ec2b-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="9ec2b-143">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="9ec2b-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="9ec2b-144">行政機関向け Office 365 (行政機関のコミュニティ クラウド)</span><span class="sxs-lookup"><span data-stu-id="9ec2b-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="9ec2b-145">この RMS キー共有の場所は、政府機関向け SKU 用にOffice 365予約されています。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="9ec2b-146">[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、キー共有の場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="9ec2b-147">たとえば、組織が北アメリカにある場合にキー共有の場所を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="9ec2b-148">-RMSOnline スイッチを使用 [して Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) コマンドレットを実行し、AZURE Rights Management から TPD をインポートします。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="9ec2b-149">*TPDName* は、TPD に使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="9ec2b-150">たとえば、「Contoso 北アメリカ TPD」とします。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="9ec2b-151">Azure Rights Management サービスを使用するように組織が正常に構成されたことを確認するには、次のように -RMSOnline スイッチを使用して [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="9ec2b-152">とりわけ、このコマンドレットは Azure Rights Management サービスとの接続をチェックし、TPD をダウンロードし、その有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="9ec2b-153">[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、Azure Rights Management テンプレートが Web 上の Outlookおよびサーバーで使用Outlook。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="9ec2b-154">[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)コマンドレットを次のように実行して、クラウドベースの電子メール組織で Azure Rights Management を有効にし、Azure Rights Management を使用するように構成Office 365 Message Encryption。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="9ec2b-155">TPD を正常にインポートし、Azure Rights Management を有効にしたと確認するには、Test-IRMConfiguration コマンドレットを使用して Azure Rights Management の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="9ec2b-156">詳細については [、「Test-IRMConfiguration」の「例 1」を参照してください](/powershell/module/exchange/test-irmconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="9ec2b-157">以前のバージョンの OME は、Azure Information Protection ではなく Active Directory Rights Management でセットアップされています。何をしますか?</span><span class="sxs-lookup"><span data-stu-id="9ec2b-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="9ec2b-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="9ec2b-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="9ec2b-159">Active Directory Rights Management を使用して、既存Office 365 Message Encryptionメール フロー ルールを引き続き使用できますが、新しい OME 機能を構成または使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="9ec2b-160">代わりに、Azure Information Protection に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="9ec2b-161">組織の移行とこれが何を意味するのかについては、「RMS から Azure Information Protection への移行 [AD」を参照してください](/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="9ec2b-162">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ec2b-162">Next steps</span></span>
<span data-ttu-id="9ec2b-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="9ec2b-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="9ec2b-164">Azure Rights Management のセットアップが完了したら、新しい OME 機能を有効にする場合は[、「Azure](./set-up-new-message-encryption-capabilities.md) Information Protection の上に構築された新しい Office 365 Message Encryption 機能をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="9ec2b-165">新しい OME 機能を使用する組織をセットアップした後、新しい OME 機能を使用して電子メール メッセージを保護するためのメール フロー ルールを定義する [準備が整いました](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec2b-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9ec2b-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ec2b-166">Related topics</span></span>
<span data-ttu-id="9ec2b-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="9ec2b-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="9ec2b-168">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="9ec2b-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="9ec2b-169">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="9ec2b-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="9ec2b-170">Azure Active Directory Rights Management の概要</span><span class="sxs-lookup"><span data-stu-id="9ec2b-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)