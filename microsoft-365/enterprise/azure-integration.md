---
title: Azure と Microsoft 365 の統合
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
description: パスワード同期またはシングル サインオンをオンプレミス環境AD場合は、Microsoft 365 と Azure ADを統合します。
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905334"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="4fc06-103">Azure と Microsoft 365 の統合</span><span class="sxs-lookup"><span data-stu-id="4fc06-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="4fc06-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="4fc06-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4fc06-105">Microsoft 365 では、Azure Active Directory (Azure Active Directory AD) を使用して、ユーザー ID を背後で管理します。</span><span class="sxs-lookup"><span data-stu-id="4fc06-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="4fc06-106">Microsoft 365 サブスクリプションには無料の Azure AD サブスクリプションが含まれています。そのため、オンプレミスの Active Directory ドメイン サービス (AD DS) を統合してユーザー アカウントとパスワードを同期したり、シングル サインオンを設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="4fc06-107">また、高度な機能を購入して、アカウントの管理を向上することもできます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="4fc06-108">Azure ADは、Microsoft 365 サブスクリプションの拡張およびカスタマイズに使用できる統合アプリの管理など、他の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="4fc06-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="4fc06-109">Microsoft 365 管理センターでのガイド付きセットアップと構成エクスペリエンスには、Azure AD 展開アドバイザーを使用できます (Microsoft 365 にサインインする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="4fc06-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="4fc06-110">Azure AD Connect アドバイザー</span><span class="sxs-lookup"><span data-stu-id="4fc06-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="4fc06-111">AD FS 展開アドバイザー</span><span class="sxs-lookup"><span data-stu-id="4fc06-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="4fc06-112">Azure ADセットアップ ガイド</span><span class="sxs-lookup"><span data-stu-id="4fc06-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="4fc06-113">Azure ADエディションと Microsoft 365 ID 管理</span><span class="sxs-lookup"><span data-stu-id="4fc06-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="4fc06-114">Microsoft 365 の有料サブスクリプションをお持ちの場合は、無料の Azure サブスクリプションADがあります。</span><span class="sxs-lookup"><span data-stu-id="4fc06-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="4fc06-115">Azure ADを使用して、ユーザー アカウントとグループ アカウントを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="4fc06-116">このサブスクリプションをアクティブ化するには、1 回の登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fc06-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="4fc06-117">その後、Microsoft 365 管理センターから Azure ADにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4fc06-118">無料の Azure AD サブスクリプションを登録する手順については、「無料の Azure ADサブスクリプション [を使用する」を参照してください](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc06-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="4fc06-119">azure.microsoft.com に直接アクセスしてサインアップしたり、Microsoft 365 で無料の Azure AD サブスクリプションとは別の試用版または有料サブスクリプションを利用したりします。</span><span class="sxs-lookup"><span data-stu-id="4fc06-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="4fc06-120">無料サブスクリプションを使用すると、オンプレミスのディレクトリと同期し、シングル サインオンを設定し、Salesforce、DropBox などのサービス アプリケーションとして多くのソフトウェアと同期できます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="4fc06-121">DS 機能、双方向AD、その他の管理機能を強化する場合は、無料サブスクリプションを有料のプレミアム サブスクリプションにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="4fc06-122">詳細については [、「Azure Active Directory エディション」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="4fc06-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="4fc06-123">Microsoft 365 および Azure ADについては [、「Microsoft 365 ID モデル」を参照してください](about-microsoft-365-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="4fc06-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="4fc06-124">Microsoft 365 テナントの機能を拡張する</span><span class="sxs-lookup"><span data-stu-id="4fc06-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="4fc06-125">**機能**</span><span class="sxs-lookup"><span data-stu-id="4fc06-125">**Feature**</span></span>|<span data-ttu-id="4fc06-126">**説明**</span><span class="sxs-lookup"><span data-stu-id="4fc06-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fc06-127">統合アプリ</span><span class="sxs-lookup"><span data-stu-id="4fc06-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="4fc06-128">個々のアプリに、メール、予定表、連絡先、ユーザー、グループ、ファイル、フォルダーなどの Microsoft 365 データへのアクセス権を付与できます。</span><span class="sxs-lookup"><span data-stu-id="4fc06-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="4fc06-129">また、これらのアプリをグローバル管理者レベルで承認し、Azure AD にアプリを登録することで、会社全体で利用AD。</span><span class="sxs-lookup"><span data-stu-id="4fc06-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="4fc06-130">詳細については [、「Integrated Apps and Azure AD Microsoft 365](integrated-apps-and-azure-ads.md)管理者向け」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fc06-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="4fc06-131">「シングル [サインオン」も参照してください](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="4fc06-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="4fc06-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="4fc06-132">PowerApps</span></span>  <br/> | <span data-ttu-id="4fc06-133">Power Apps は、SharePoint リストや他のデータ アプリなどの既存のデータ ソースに接続できるモバイル デバイス向けアプリです。</span><span class="sxs-lookup"><span data-stu-id="4fc06-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="4fc06-134">詳細 [については、「Create a PowerApp for a list in SharePoint Online」](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) および [「PowerApps」ページ](https://powerapps.microsoft.com/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fc06-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4fc06-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fc06-135">See also</span></span>

[<span data-ttu-id="4fc06-136">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="4fc06-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)