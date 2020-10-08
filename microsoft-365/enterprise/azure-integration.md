---
title: Microsoft 365 との Azure の統合
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: オンプレミス環境でのパスワード同期またはシングルサインオンを行う場合は、Microsoft 365 を Azure AD と統合します。
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384747"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="df8f2-103">Microsoft 365 との Azure の統合</span><span class="sxs-lookup"><span data-stu-id="df8f2-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="df8f2-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="df8f2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="df8f2-105">Microsoft 365 では、Azure Active Directory (Azure AD) を使用して、バックグラウンドでユーザー id を管理しています。</span><span class="sxs-lookup"><span data-stu-id="df8f2-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="df8f2-106">Microsoft 365 サブスクリプションには、オンプレミスの Active Directory ドメインサービス (AD DS) を統合してユーザーアカウントとパスワードを同期したり、シングルサインオンを設定したりできるように、Azure AD サブスクリプションが無料で用意されています。</span><span class="sxs-lookup"><span data-stu-id="df8f2-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="df8f2-107">また、高度な機能を購入して、アカウントをより適切に管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="df8f2-108">Azure AD では、統合アプリの管理などのその他の機能も提供されており、これを使用して Microsoft 365 サブスクリプションを拡張およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="df8f2-109">Microsoft 365 管理センターで、ガイド付きのセットアップと構成の手順に Azure AD 展開アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="df8f2-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="df8f2-110">Azure AD Connect advisor</span><span class="sxs-lookup"><span data-stu-id="df8f2-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="df8f2-111">AD FS 展開アドバイザー</span><span class="sxs-lookup"><span data-stu-id="df8f2-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="df8f2-112">Azure AD セットアップガイド</span><span class="sxs-lookup"><span data-stu-id="df8f2-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="df8f2-113">Azure AD エディションと Microsoft 365 id 管理</span><span class="sxs-lookup"><span data-stu-id="df8f2-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="df8f2-114">Microsoft 365 への有料サブスクリプションを保有している場合は、Azure AD サブスクリプションも無料で利用できます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="df8f2-115">Azure AD を使用して、ユーザーアカウントとグループアカウントを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="df8f2-116">このサブスクリプションをアクティブ化するには、1回限りの登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df8f2-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="df8f2-117">その後、Microsoft 365 管理センターから Azure AD にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="df8f2-118">無料の Azure AD サブスクリプションを登録する手順については、「 [Free AZURE ad サブスクリプションを使用](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="df8f2-119">Azure.microsoft.com に直接進んでサインアップしないでください。 microsoft Azure の試用版または有償版サブスクリプションが、Microsoft 365 を使用して無料の Azure AD サブスクリプションとは別のものになります。</span><span class="sxs-lookup"><span data-stu-id="df8f2-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="df8f2-120">無料のサブスクリプションを使用すると、オンプレミスのディレクトリと同期したり、シングルサインオンを設定したり、サービスアプリケーション (Salesforce、DropBox など) などの多くのソフトウェアと同期したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="df8f2-121">拡張された AD DS 機能、双方向同期、およびその他の管理機能が必要な場合は、無料のサブスクリプションを有料プレミアムサブスクリプションにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="df8f2-122">詳細については、「 [Azure Active Directory のエディション](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="df8f2-123">Microsoft 365 と Azure AD の詳細については、「 [microsoft 365 identity モデル](about-microsoft-365-identity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="df8f2-124">Microsoft 365 テナントの機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="df8f2-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="df8f2-125">**機能**</span><span class="sxs-lookup"><span data-stu-id="df8f2-125">**Feature**</span></span>|<span data-ttu-id="df8f2-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="df8f2-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df8f2-127">統合アプリ</span><span class="sxs-lookup"><span data-stu-id="df8f2-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="df8f2-128">メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなど、Microsoft 365 データへの個別のアプリのアクセスを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="df8f2-129">また、グローバル管理者レベルでこれらのアプリを承認し、Azure AD にアプリを登録することにより、会社全体でそれらを利用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="df8f2-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="df8f2-130">Formore の情報については、「 [Microsoft 365 管理者向けの統合アプリおよび AZURE AD](integrated-apps-and-azure-ads.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="df8f2-131">また [、「シングルサインオン](https://go.microsoft.com/fwlink/p/?LinkId=698604)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="df8f2-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="df8f2-132">PowerApps</span></span>  <br/> | <span data-ttu-id="df8f2-133">Power apps は、SharePoint リストやその他のデータアプリなどの既存のデータソースに接続できるモバイルデバイス用のフォーカスアプリです。</span><span class="sxs-lookup"><span data-stu-id="df8f2-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="df8f2-134">詳細については、「 [SharePoint Online のリスト用の PowerApp の作成](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) 」および「 [PowerApps ページ](https://powerapps.microsoft.com/) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df8f2-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="df8f2-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="df8f2-135">See also</span></span>

[<span data-ttu-id="df8f2-136">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="df8f2-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
