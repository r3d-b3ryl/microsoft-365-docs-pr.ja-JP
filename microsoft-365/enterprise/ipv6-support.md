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
description: '概要: 365 コンポーネントと 365 Microsoft Office 365 の政府機関製品での IPv6 サポートOffice説明します。'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909684"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="ea6b1-103">Office 365 サービスでの IPv6 サポート</span><span class="sxs-lookup"><span data-stu-id="ea6b1-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="ea6b1-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ea6b1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ea6b1-105">Office 365 は IPv6 と IPv4 の両方をサポートしています。ただし、IPv6 で 365 Office機能が完全に有効になっているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="ea6b1-106">つまり、IPv4 と IPv6 の両方を使用して 365 に接続Officeです。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="ea6b1-107">送信トラフィックを Office 365 にフィルター処理する場合、Office 365 でサポートされている IPv6 アドレスの完全な一覧は、記事 [Office 365 URL](urls-and-ip-address-ranges.md)と IP アドレス範囲に記載されています。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="ea6b1-108">ネットワークが構成され、適切な IPv6 アドレスが許可された後、microsoft ダウンロード センターから [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) テスト プランをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="ea6b1-109">IPv6 のサポート (Office 365 サブスクリプション サービス)</span><span class="sxs-lookup"><span data-stu-id="ea6b1-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="ea6b1-110">Exchange Online と IPv6</span><span class="sxs-lookup"><span data-stu-id="ea6b1-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="ea6b1-111">Exchange Online への接続に使用するプログラムが IPv6 をサポートしている場合は、有線ネットワークとワイヤレス ネットワークの両方で既定で IPv6 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="ea6b1-112">Exchange Online への通信を制御する場合は、365 の URL と IP アドレス範囲Office IP [アドレス範囲を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="ea6b1-113">SharePoint Online と IPv6</span><span class="sxs-lookup"><span data-stu-id="ea6b1-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="ea6b1-114">**Office 365 Government G1/G3/G4/K1** SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合は、既定で IPv6 の使用が試行されます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="ea6b1-115">**パブリック マルチテナント クラウド** Microsoft は、要求に応じて SharePoint Online IPv6 を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="ea6b1-116">組織の DNS インフラストラクチャに CIDR の指定された IP アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="ea6b1-117">IPv6 をテナントで有効にするために、この DNS インフラストラクチャを他の組織と共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="ea6b1-118">IPv6 を有効にした後、SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、IPv6 は既定で IPv6 を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="ea6b1-119">SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合、有線ネットワークとワイヤレス ネットワークの両方で IPv6 が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="ea6b1-120">SharePoint Online への通信を制御する場合は [、365](urls-and-ip-address-ranges.md)の URL と IP アドレス範囲Office IP アドレス範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 <span data-ttu-id="ea6b1-121">**Office 365 Government G1/G3/G4/K1** SharePoint Online への接続に使用するプログラムが IPv6 をサポートしている場合は、既定で IPv6 の使用が試行されます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-121">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="ea6b1-122">Skype for Business および IPv6</span><span class="sxs-lookup"><span data-stu-id="ea6b1-122">Skype for Business and IPv6</span></span>

<span data-ttu-id="ea6b1-123">IPv6 は Skype for Business ではサポートされていないので、有効にできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-123">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="ea6b1-124">Microsoft Teams と IPV6</span><span class="sxs-lookup"><span data-stu-id="ea6b1-124">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="ea6b1-125">Microsoft Teams ダイレクト ルーティングは IPv4 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-125">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="ea6b1-126">Microsoft Teams サービスとクライアントは、IPv4 と IPv6 の両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-126">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="ea6b1-127">Microsoft Teams への通信を制御する場合は [、365](urls-and-ip-address-ranges.md)の URL と IP アドレス範囲Office IP アドレス範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-127">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="ea6b1-128">Exchange Online Protection と IPv6</span><span class="sxs-lookup"><span data-stu-id="ea6b1-128">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="ea6b1-129">Exchange Online Protection (EOP) は、トランスポート層セキュリティ プロトコルを使用して送信が行われる場合、IPv6 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-129">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="ea6b1-130">EOP 範囲の場合は [、365 Office IP アドレス範囲を使用します](urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-130">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="ea6b1-131">365 の政府機関向Office IPv6 サポート</span><span class="sxs-lookup"><span data-stu-id="ea6b1-131">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="ea6b1-132">Office 365 IPv6 による政府機関向けサポートは、Office の経営部門および機関の最高情報責任者のための管理予算 (OMB) メモ、およびインターネット プロトコル バージョン 6 (IPv6) の連邦政府導入覚書に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-132">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="ea6b1-133">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) は、分離されたコミュニティ クラウドに米国政府のデータを格納するマルチテナント サービスです。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-133">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="ea6b1-134">他の Office 365 製品と同様に、Exchange Online、Skype for Business、SharePoint Online、Microsoft 365 Apps for enterprise などの生産性とコラボレーション サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-134">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="ea6b1-135">365 Microsoft Officeは、2013 以降にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-135">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="ea6b1-136">365 政府機関向Office詳細については [、「Annouing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-136">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="ea6b1-137">国際武器規制 (ITAR) は、米国軍需リスト [(USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415)の防衛関連の記事やサービスの輸出入を制御する米国政府の規制のセットです。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-137">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="ea6b1-138">Microsoft Office 365 for Enterprises は、ITAR の対象となる連邦情報セキュリティ管理 (FISMA) 認定および商用エンティティを必要とする米国連邦政府機関のセキュリティ、プライバシー、および規制コンプライアンス要件をサポートする Microsoft 生産性向上ソリューション向け専用のホスティング サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-138">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="ea6b1-139">IPv6 および 365 を使用する場合Office検討する</span><span class="sxs-lookup"><span data-stu-id="ea6b1-139">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="ea6b1-140">IPv6 を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-140">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="ea6b1-141">詳細については、このガイダンス記事 [を参照してください](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-141">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="ea6b1-142">ネットワークで使用されている IP バージョンを確認するには、次の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-142">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="ea6b1-143">コマンド プロンプトでの **IPConfig** コマンドの表示に"IPv6 Address" または "Temporary IPv6 Address" という名前の行が含まれている場合は、環境に IPv6 があります。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-143">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="ea6b1-144">すべての IPv6 アドレスが "fe80" で始まり、"Link-Local IPv6 Address" という名前の行に対応する場合は、環境に IPv6 が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-144">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="ea6b1-145">これらの考慮事項は、ネットワークに適用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-145">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="ea6b1-146">パブリック サブスクリプション サービスでは、IPv6 を使用したクレジット カードによる購入はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-146">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="ea6b1-147">これは、政府機関が EA (EA) ライセンスを使用マイクロソフトエンタープライズ契約コミュニティ クラウド (GCC) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-147">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="ea6b1-148">IPv6 は、一部の Rights Management Services (RMS) シナリオをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-148">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="ea6b1-149">IPv6 は IPv6 をサポート®ため、BlackBerry エンタープライズ サーバー (BES) はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-149">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="ea6b1-150">Active Directory フェデレーション サービス (AD FS) を Office 365 で使用する場合、IPv6 を使用して AD FS ネットワーク エンドポイントを Office 365 に広告はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-150">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="ea6b1-151">Exchange Online を使用する場合は、FS DNS AD AAAA レコードを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea6b1-151">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="ea6b1-152">ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="ea6b1-152">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea6b1-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea6b1-153">See also</span></span>

<span data-ttu-id="ea6b1-154">[IPv6 ラーニング ロードマップ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="ea6b1-154">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="ea6b1-155">IPv6 サバイバル ガイド</span><span class="sxs-lookup"><span data-stu-id="ea6b1-155">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)