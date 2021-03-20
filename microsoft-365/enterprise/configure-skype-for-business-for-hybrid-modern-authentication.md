---
title: Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッドモダン認証 (HMA) を使用する Skype for Business オンプレミスを構成する方法について説明します。より安全なユーザー認証と承認を提供します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911152"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="c65af-103">Skype for Business をオンプレミスで構成して、ハイブリッド先進認証を使用するには</span><span class="sxs-lookup"><span data-stu-id="c65af-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="c65af-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="c65af-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c65af-105">モダン認証は、より安全なユーザー認証と承認を提供する ID 管理の方法であり、オンプレミスの Skype for Business サーバーとオンプレミスの Exchange サーバー、およびスプリットドメイン Skype for Business ハイブリッドで利用できます。</span><span class="sxs-lookup"><span data-stu-id="c65af-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="c65af-106">**重要** モダン認証 (MA) の詳細と、会社や組織で使用する理由について知りたがっていますか?</span><span class="sxs-lookup"><span data-stu-id="c65af-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="c65af-107">概要 [については、](hybrid-modern-auth-overview.md) このドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c65af-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="c65af-108">Skype for Business トポロジがサポートされている skype for Business トポロジをMAする必要がある場合は、ここで説明します。</span><span class="sxs-lookup"><span data-stu-id="c65af-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="c65af-109">**開始する前に**、次の用語を使用します。</span><span class="sxs-lookup"><span data-stu-id="c65af-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="c65af-110">モダン認証 (MA)</span><span class="sxs-lookup"><span data-stu-id="c65af-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="c65af-111">ハイブリッドモダン認証 (HMA)</span><span class="sxs-lookup"><span data-stu-id="c65af-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="c65af-112">Exchange オンプレミス (EXCH)</span><span class="sxs-lookup"><span data-stu-id="c65af-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="c65af-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="c65af-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="c65af-114">Skype for Business オンプレミス (SFB)</span><span class="sxs-lookup"><span data-stu-id="c65af-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="c65af-115">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="c65af-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="c65af-116">また、この記事のグラフィックにグレー表示または淡色表示のオブジェクトがある場合は、灰色で表示される要素が MA固有の構成に含まれません。</span><span class="sxs-lookup"><span data-stu-id="c65af-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="c65af-117">概要を読む</span><span class="sxs-lookup"><span data-stu-id="c65af-117">Read the summary</span></span>

<span data-ttu-id="c65af-118">この概要では、プロセスを実行中に迷子になる可能性がある手順に分け、全体のチェックリストでプロセスの場所を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="c65af-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="c65af-119">最初に、すべての前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c65af-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="c65af-120">Skype for Business **と** Exchange の両方で多くの前提条件が一般的なので、プレ req チェックリストの概要 [に関する記事を参照してください](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c65af-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="c65af-121">この記事  *の手順*  を開始する前に、これを行います。</span><span class="sxs-lookup"><span data-stu-id="c65af-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="c65af-122">ファイルまたは OneNote で必要な HMA 固有の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="c65af-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="c65af-123">EXO のモダン認証を有効にします (まだ有効にしていない場合)。</span><span class="sxs-lookup"><span data-stu-id="c65af-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c65af-124">SFBO のモダン認証を有効にします (まだ有効ではない場合)。</span><span class="sxs-lookup"><span data-stu-id="c65af-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="c65af-125">Exchange オンプレミスのハイブリッドモダン認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c65af-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="c65af-126">オンプレミスの Skype for Business のハイブリッドモダン認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c65af-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="c65af-127">これらの手順は、SFB、SFBO、EXCH、EXO の MA を有効にします。つまり、SFB と SFBO の HMA 構成に参加できるすべての製品 (EXCH/EXO への依存関係を含む)。</span><span class="sxs-lookup"><span data-stu-id="c65af-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="c65af-128">つまり、ユーザーがハイブリッドの任意の部分 (EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB) にメールボックスを作成している場合、完成した製品は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c65af-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![混在 6 Skype for business HMA トポロジは、MA 4 つの場所すべてでオンになります。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="c65af-130">ご覧のように、この機能を有効にする場所は 4 MA!</span><span class="sxs-lookup"><span data-stu-id="c65af-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="c65af-131">最適なユーザー エクスペリエンスを得る場合は、これらの 4 つの場所MAを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c65af-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="c65af-132">これらのすべての場所で MA をオンにできない場合は、環境に必要な場所でのみ MA を有効にできるよう手順を調整します。</span><span class="sxs-lookup"><span data-stu-id="c65af-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="c65af-133">サポートされる [トポロジについては、「Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) サポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65af-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>
  
 <span data-ttu-id="c65af-134">**重要** 開始する前に、すべての前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c65af-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="c65af-135">この情報については、「ハイブリッドモダン認証の概要 [と前提条件」を参照してください](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c65af-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="c65af-136">必要なすべての HMA 固有の情報を収集する</span><span class="sxs-lookup"><span data-stu-id="c65af-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="c65af-137">モダン認証を使用するための前提条件を満たしていることを確認[](hybrid-modern-auth-overview.md)した後 (上記のメモを参照)、前の手順で HMA を構成するために必要な情報を保持するファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="c65af-138">この記事で使用される例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c65af-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="c65af-139">**SIP/SMTP ドメイン**</span><span class="sxs-lookup"><span data-stu-id="c65af-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="c65af-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="c65af-140">Ex.</span></span> <span data-ttu-id="c65af-141">contoso.com (365 とOfficeされます)</span><span class="sxs-lookup"><span data-stu-id="c65af-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="c65af-142">**テナント ID**</span><span class="sxs-lookup"><span data-stu-id="c65af-142">**Tenant ID**</span></span>

  - <span data-ttu-id="c65af-143">365 テナント (Officeログイン時) を表す GUID contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c65af-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="c65af-144">**SFB 2015 CU5 Web サービス URL**</span><span class="sxs-lookup"><span data-stu-id="c65af-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="c65af-145">すべての SfB 2015 プールを展開するには、内部および外部の Web サービス URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="c65af-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="c65af-146">これらを取得するには、Skype for Business 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65af-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="c65af-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="c65af-147">Ex.</span></span> <span data-ttu-id="c65af-148">内部: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c65af-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="c65af-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="c65af-149">Ex.</span></span> <span data-ttu-id="c65af-150">外部: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c65af-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="c65af-151">Standard Edition サーバーを使用している場合、内部 URL は空白になります。</span><span class="sxs-lookup"><span data-stu-id="c65af-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="c65af-152">この場合は、内部 URL にプール fqdn を使用します。</span><span class="sxs-lookup"><span data-stu-id="c65af-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="c65af-153">EXO のモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="c65af-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="c65af-154">手順については [、「Exchange Online: テナントで最新の認証を有効にする方法」を参照してください。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="c65af-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="c65af-155">SFBO のモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="c65af-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="c65af-156">「Skype for Business Online: モダン認証のためにテナントを有効にする」の手順 [に従います](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c65af-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="c65af-157">Exchange オンプレミスのハイブリッドモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="c65af-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="c65af-158">「ハイブリッドモダン認証を使用するオンプレミスExchange Server構成する方法」の手順 [に従います](configure-exchange-server-for-hybrid-modern-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="c65af-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="c65af-159">Skype for Business オンプレミスのハイブリッドモダン認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="c65af-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="c65af-160">Azure Active Directory でオンプレミス Web サービス URL を SPN として追加する</span><span class="sxs-lookup"><span data-stu-id="c65af-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="c65af-161">これで、SFBO のサービス プリンシパルとして URL (前に収集) を追加するコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="c65af-162">**メモ** サービス プリンシパル名 (SPN) は、Web サービスを識別し、それらをセキュリティ プリンシパル (アカウント名やグループなど) に関連付けて、サービスが承認されたユーザーの代理として機能します。</span><span class="sxs-lookup"><span data-stu-id="c65af-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="c65af-163">サーバーに対して認証されるクライアントは、SPN に含まれる情報を利用します。</span><span class="sxs-lookup"><span data-stu-id="c65af-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="c65af-164">まず、次の手順に従って Azure Active Directory (Azure AD) [に接続します](/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="c65af-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="c65af-165">このコマンドをオンプレミスで実行して、SFB Web サービス URL の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c65af-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="c65af-166">AppPrincipalId はで始まる点に注意してください `00000004` 。</span><span class="sxs-lookup"><span data-stu-id="c65af-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="c65af-167">これは Skype for Business Online に対応しています。</span><span class="sxs-lookup"><span data-stu-id="c65af-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="c65af-168">このコマンドの出力には SE と WS URL が含まれますが、大部分はで始まる SPN で構成されます。 `00000004-0000-0ff1-ce00-000000000000/`</span><span class="sxs-lookup"><span data-stu-id="c65af-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="c65af-169">社内 **の内部または** 外部の SFB URL が見つからない場合 (たとえば、これらの特定のレコードをこのリスト https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) に追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c65af-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="c65af-170">[追加] コマンド  *で、以下の URL の* 例を実際の URL に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="c65af-171">手順 2 から **Get-MsolServicePrincipal** コマンドを再度実行し、出力を確認して、新しいレコードが追加されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="c65af-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="c65af-172">前のリストまたはスクリーンショットを SPN の新しいリストと比較します。</span><span class="sxs-lookup"><span data-stu-id="c65af-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="c65af-173">レコードの新しいリストのスクリーンショットを撮る場合があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="c65af-174">成功した場合は、リストに 2 つの新しい URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c65af-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="c65af-175">この例では、SPN の一覧に特定の URL と https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="c65af-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="c65af-176">EvoSTS Auth Server オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c65af-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="c65af-177">Skype for Business 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65af-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="c65af-178">ハイブリッドモダン認証の有効化</span><span class="sxs-lookup"><span data-stu-id="c65af-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="c65af-179">これは、実際にユーザー設定をオンにするMA。</span><span class="sxs-lookup"><span data-stu-id="c65af-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="c65af-180">前のすべての手順は、クライアント認証フローを変更せずに、前もって実行できます。</span><span class="sxs-lookup"><span data-stu-id="c65af-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="c65af-181">認証フローを変更する準備ができたら、Skype for Business 管理シェルでこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c65af-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="c65af-182">確認する</span><span class="sxs-lookup"><span data-stu-id="c65af-182">Verify</span></span>

<span data-ttu-id="c65af-183">HMA を有効にした後、クライアントの次のログインでは新しい認証フローが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c65af-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="c65af-184">HMA をオンにしても、クライアントに対して再認証がトリガーされるという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c65af-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="c65af-185">クライアントは、持っている認証トークンまたは証明書の有効期間に基づいて再認証されます。</span><span class="sxs-lookup"><span data-stu-id="c65af-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="c65af-186">HMA が有効にした後で動作しているテストを行う場合は、テスト SFB Windows クライアントからサインアウトし、[自分の資格情報を削除する] をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="c65af-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="c65af-187">もう一度サインインします。</span><span class="sxs-lookup"><span data-stu-id="c65af-187">Sign in again.</span></span> <span data-ttu-id="c65af-188">クライアントはモダン認証フローを使用する必要があります。ログインには、クライアントがサーバーに接続してログインする直前に表示される「仕事または学校」アカウントの Office **365** プロンプトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c65af-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="c65af-189">また、「OAuth Authority」の Skype for Business クライアントの 「構成情報」 も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="c65af-190">クライアント コンピューターでこれを行うには、Windows 通知トレイで Skype for Business アイコンを右クリックすると同時に、Ctrl キーを押したままにしてください。</span><span class="sxs-lookup"><span data-stu-id="c65af-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="c65af-191">表示 **されるメニューの** [構成情報] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65af-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="c65af-192">デスクトップに表示される [Skype for Business 構成情報] ウィンドウで、次の情報を探します。</span><span class="sxs-lookup"><span data-stu-id="c65af-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![モダン認証を使用した Skype for Business クライアントの構成情報には、 の Lync および EWS OAUTH Authority URL が表示されます https://login.windows.net/common/oauth2/authorize 。](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="c65af-194">また、Outlook クライアントのアイコン (Windows 通知トレイ) を右クリックし、[接続状態] をクリックすると同時に、Ctrl キーを押したままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65af-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="c65af-195">OAuth で使用されるベアラー トークンを表す'Bearer'の AuthN 型に対してクライアントの SMTP アドレス \* を探します。</span><span class="sxs-lookup"><span data-stu-id="c65af-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c65af-196">関連記事</span><span class="sxs-lookup"><span data-stu-id="c65af-196">Related articles</span></span>

<span data-ttu-id="c65af-197">[モダン認証の概要にリンクします](hybrid-modern-auth-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c65af-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="c65af-198">Skype for Business クライアントでモダン認証 (ADAL) を使用する方法を知る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c65af-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="c65af-199">ここに手順[があります。](./hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c65af-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>