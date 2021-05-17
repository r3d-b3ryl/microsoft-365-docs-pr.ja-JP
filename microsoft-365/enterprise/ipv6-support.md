---
title: Office 365 サービスでの IPv6 サポート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '概要: IPv6 のサポートについて、Microsoft Office 365および政府機関のOffice 365説明します。'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909684"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="a2ac2-103">Office 365 サービスでの IPv6 サポート</span><span class="sxs-lookup"><span data-stu-id="a2ac2-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="a2ac2-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="a2ac2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2ac2-105">Office 365 IPv6 と IPv4 の両方をサポートしています。ただし、IPv6 でOffice 365機能が完全に有効になっているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="a2ac2-106">つまり、IPv4 と IPv6 の両方を使用してデバイスに接続するOffice 365。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="a2ac2-107">送信トラフィックを Office 365 にフィルター処理する場合、Office 365 でサポートされている IPv6 アドレスの完全な一覧は[、「Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレス範囲」の記事で確認できます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="a2ac2-108">ネットワークが構成され、適切な IPv6 アドレスが許可された後、Microsoft ダウンロード センターから Office 365 [IPv6](https://go.microsoft.com/fwlink/?LinkId=293447)テスト プランをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="a2ac2-109">サブスクリプション サービスでの IPv6 Office 365サポート</span><span class="sxs-lookup"><span data-stu-id="a2ac2-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="a2ac2-110">Exchange Online IPv6</span><span class="sxs-lookup"><span data-stu-id="a2ac2-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="a2ac2-111">IPv6 への接続に使用するプログラムExchange Online IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="a2ac2-112">ネットワークへの通信を制御する場合Exchange Online URL と IP アドレス範囲の IP Office 365[を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="a2ac2-113">SharePointオンラインと IPv6</span><span class="sxs-lookup"><span data-stu-id="a2ac2-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="a2ac2-114">**Office 365 Government G1/G3/G4/K1** オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 の使用が試行されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="a2ac2-115">**パブリック マルチテナント クラウド** Microsoft は、SharePointオンライン IPv6 を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="a2ac2-116">組織の DNS インフラストラクチャに CIDR の指定された IP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="a2ac2-117">IPv6 をテナントで有効にするために、この DNS インフラストラクチャを他の組織と共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="a2ac2-118">IPv6 が有効になると、オンラインに接続するために使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="a2ac2-119">オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="a2ac2-120">オンラインへの通信を制御する場合SharePoint URL と IP アドレス範囲の IP [Office 365を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 <span data-ttu-id="a2ac2-121">**Office 365 Government G1/G3/G4/K1** オンラインへの接続に使用するプログラムSharePoint IPv6 がサポートされている場合は、既定で IPv6 の使用が試行されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-121">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="a2ac2-122">Skype for Business IPv6</span><span class="sxs-lookup"><span data-stu-id="a2ac2-122">Skype for Business and IPv6</span></span>

<span data-ttu-id="a2ac2-123">IPv6 はサポートされていないのでSkype for Business有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-123">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="a2ac2-124">Microsoft Teams IPV6</span><span class="sxs-lookup"><span data-stu-id="a2ac2-124">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="a2ac2-125">Microsoft Teamsダイレクト ルーティングは IPv4 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-125">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="a2ac2-126">サービスMicrosoft Teamsクライアントは、IPv4 と IPv6 の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-126">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="a2ac2-127">サーバーへの通信を制御する場合Microsoft Teams URL と IP アドレス範囲の IP [Office 365を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-127">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="a2ac2-128">Exchange Online Protection IPv6</span><span class="sxs-lookup"><span data-stu-id="a2ac2-128">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="a2ac2-129">Exchange Online Protection (EOP) は、トランスポート層セキュリティ プロトコルを使用して送信が行われる場合に IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-129">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="a2ac2-130">EOP 範囲の場合は、URL [Office 365 IP アドレス範囲を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-130">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="a2ac2-131">政府機関向け製品の IPv6 Office 365サポート</span><span class="sxs-lookup"><span data-stu-id="a2ac2-131">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="a2ac2-132">Office 365政府機関向け IPv6 サポートは、Office の経営部門および機関の最高情報責任者のための管理予算 (OMB) メモ、およびインターネット プロトコル バージョン 6 (IPv6) の連邦政府導入覚書に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-132">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="a2ac2-133">[Microsoft Office 365は](https://go.microsoft.com/fwlink/p/?LinkId=325414)、分離されたコミュニティ クラウドに米国政府のデータを格納するマルチテナント サービスです。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-133">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="a2ac2-134">他のOffice 365製品と同様に、Exchange Online、Skype for Business、SharePoint Online、およびMicrosoft 365 Apps for enterprise。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-134">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="a2ac2-135">政府機関Microsoft Office 365は、2013 以降にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-135">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="a2ac2-136">政府機関向けサービスのOffice 365詳細については[、「Annouing Office 365: A US](https://go.microsoft.com/fwlink/p/?LinkId=325414)Government Community Cloud」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-136">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="a2ac2-137">国際武器規制 (ITAR) は、米国軍需リスト [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)の防衛関連の記事やサービスの輸出入を制御する米国政府の規制のセットです。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-137">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="a2ac2-138">Microsoft Office 365 for Enterprises は、ITAR の対象となる連邦情報セキュリティ管理 (FISMA) 認定および商用エンティティを必要とする米国連邦政府機関のセキュリティ、プライバシー、および規制コンプライアンス要件をサポートする Microsoft 生産性ソリューション向け専用のホスティング サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-138">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="a2ac2-139">IPv6 と IPv6 を使用する場合のOffice 365</span><span class="sxs-lookup"><span data-stu-id="a2ac2-139">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="a2ac2-140">IPv6 を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-140">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="a2ac2-141">詳細については、このガイダンス記事 [を参照してください](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-141">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="a2ac2-142">ネットワークで使用されている IP バージョンを確認するには、次の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-142">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="a2ac2-143">コマンド プロンプトでの **IPConfig** コマンドの表示に"IPv6 Address" または "Temporary IPv6 Address" という名前の行が含まれている場合は、環境に IPv6 があります。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-143">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="a2ac2-144">すべての IPv6 アドレスが "fe80" で始まり、"Link-Local IPv6 Address" という名前の行に対応する場合は、環境に IPv6 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-144">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="a2ac2-145">これらの考慮事項は、ネットワークに適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-145">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="a2ac2-146">パブリック サブスクリプション サービスでは、IPv6 を使用したクレジット カードによる購入はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-146">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="a2ac2-147">これは、政府が (EA) Government Community Cloud (GCC) ライセンスEnterprise Agreement適用されません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-147">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="a2ac2-148">IPv6 は、一部の Rights Management Services (RMS) シナリオをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-148">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="a2ac2-149">IPv6 は IPv6 をサポート® Enterprise BlackBerry サーバー (BES) をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-149">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="a2ac2-150">Active Directory フェデレーション サービス (AD FS) を Office 365 で使用する場合、IPv6 を使用して AD FS ネットワーク エンドポイントを Office 365 に宣伝することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-150">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="a2ac2-151">これらのレコードを使用する場合は、FS DNS ADに AAAA レコードを含Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a2ac2-151">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="a2ac2-152">ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="a2ac2-152">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2ac2-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2ac2-153">See also</span></span>

<span data-ttu-id="a2ac2-154">[IPv6 ラーニング ロードマップ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="a2ac2-154">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="a2ac2-155">IPv6 サバイバル ガイド</span><span class="sxs-lookup"><span data-stu-id="a2ac2-155">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)