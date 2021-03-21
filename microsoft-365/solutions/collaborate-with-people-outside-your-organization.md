---
title: 組織外のユーザーとの共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: 組織外のユーザーと共同作業をするために、Teams、OneDrive、SharePoint など、Microsoft 365 アプリを構成する方法について説明します。
ms.openlocfilehash: 359e72c12c43ca1ea984f93d87ab4868e6d1eb66
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916396"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="f15bc-103">組織外のユーザーとの共同作業</span><span class="sxs-lookup"><span data-stu-id="f15bc-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="f15bc-104">Microsoft 365 の外部共有機能により、組織内のユーザーはディレクトリにアカウントを持たないパートナー、ベンダー、顧客などと共同作業ができます。</span><span class="sxs-lookup"><span data-stu-id="f15bc-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="f15bc-105">チームやサイト全体または単に個人的なファイルを組織外のユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="f15bc-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="f15bc-106">組織外のユーザーとの共同作業には、次の 2 つの主要なコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="f15bc-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="f15bc-107">**共有を有効にする** - Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint 全体で共有コントロールを構成して、組織に必要な共有レベルを許可します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="f15bc-108">**追加のセキュリティを有効にする** - 組織外のユーザーに認証を要求するように基本的な共有機能を構成することができると同時に、Microsoft 365 には、データを保護し、外部と共有しながらガバナンス ポリシーを維持するのに役立つ多くの追加のセキュリティとコンプライアンス機能があります。</span><span class="sxs-lookup"><span data-stu-id="f15bc-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="f15bc-109">共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="f15bc-109">Enable sharing</span></span>

<span data-ttu-id="f15bc-110">Microsoft 365では規定で、組織外のユーザーとの共有が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="f15bc-110">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="f15bc-111">多くの外部共有シナリオは、追加の構成なしでも動作します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-111">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="f15bc-112">使用しているシナリオの設定を確認するか、新しいシナリオを有効にするには、次のオプションから選びます。</span><span class="sxs-lookup"><span data-stu-id="f15bc-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="f15bc-113">[ドキュメントの共同作業](collaborate-on-documents.md) - 組織外のユーザー (ゲストと認証されていないユーザーの両方) とファイルやフォルダーを共有および共同作業を許可するように Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="f15bc-114">[サイトでの共同作業](collaborate-in-site.md) - ゲストとの SharePoint サイトの共有を有効にするために Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="f15bc-115">[チームとして共同作業](collaborate-as-team.md) - Teams でゲスト コラボレーションを有効にするために Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="f15bc-116">Microsoft 365 で利用できるゲスト共有設定の全体像については、「[Microsoft 365 ゲスト共有設定リファレンス」](microsoft-365-guest-settings.md) をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="f15bc-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="f15bc-117">追加のセキュリティを有効にする</span><span class="sxs-lookup"><span data-stu-id="f15bc-117">Enable additional security</span></span>

<span data-ttu-id="f15bc-118">組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または意図的な不適切な共有からコンテンツを保護するために追加の安全対策を検討します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="f15bc-119">[認証されていないユーザーとファイルとフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md) - 非認証ユーザーと共有するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="f15bc-120">[偶発的な露出を制限する](share-limit-accidental-exposure.md) - 組織外のユーザーと機密性の高いコンテンツを誤って共有する可能性を減らす方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="f15bc-121">[セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md) -組織外のユーザーとの共有が安全かつセキュリティで保護された方法で行われ、ガバナンス要件を満たしていることを確認するために Microsoft 365 で提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f15bc-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="f15bc-122">パートナー企業と共同作業する</span><span class="sxs-lookup"><span data-stu-id="f15bc-122">Collaborate with partner companies</span></span>

<span data-ttu-id="f15bc-123">別の組織の多くのゲストが関与する大規模なプロジェクトに取り組む場合、またはゲストが頻繁に変更される継続的なベンダー 関係がある場合は、Azure Active Directory の権利管理を使用してゲスト管理を簡素化し、パートナー企業が共同責任を持つようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f15bc-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="f15bc-124">詳細については、「[Create a B2B extranet with managed guests (管理されたゲストで B2B エクストラネットを作成する)](b2b-extranet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f15bc-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="f15bc-125">共有を制限する</span><span class="sxs-lookup"><span data-stu-id="f15bc-125">Limit sharing</span></span>

<span data-ttu-id="f15bc-126">Microsoft 365 の共有機能の一部がガバナンス ポリシーと競合する場合、共有を制限するオプションについては、「 [Microsoft 365で共有を制限する](microsoft-365-limit-sharing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f15bc-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f15bc-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f15bc-127">Related topics</span></span>

[<span data-ttu-id="f15bc-128">Microsoft 365 でのファイル共同作業の概要</span><span class="sxs-lookup"><span data-stu-id="f15bc-128">Intro to file collaboration in Microsoft 365</span></span>](/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="f15bc-129">Microsoft 365 を使用して SharePoint のファイルの共同作業を計画する</span><span class="sxs-lookup"><span data-stu-id="f15bc-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](/sharepoint/deploy-file-collaboration)