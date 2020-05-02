---
title: 組織外のユーザーとの共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
ms.custom:
- M365solutions
localization_priority: Normal
f1.keywords: NOCSH
description: 組織外のユーザーとのグループ作業用に Microsoft 365 を構成する方法について説明します。
ms.openlocfilehash: 338b486725f727506d654a4507d8ea47c6fa2bab
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002254"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="10734-103">組織外のユーザーとの共同作業</span><span class="sxs-lookup"><span data-stu-id="10734-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="10734-104">Microsoft 365 の外部共有機能を使用すると、組織内のユーザーが、自分のディレクトリにアカウントを持っていないパートナー、ベンダー、顧客、および他のユーザーと共同作業を行う機会を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="10734-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="10734-105">組織外のユーザーや個別のファイルに対して、チームまたはサイト全体を共有することができます。</span><span class="sxs-lookup"><span data-stu-id="10734-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="10734-106">組織外のユーザーとの共同作業は、次の2つの主要コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="10734-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="10734-107">**共有を有効**にする-Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint の間で共有コントロールを構成して、組織で必要とされるレベルの共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="10734-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="10734-108">**追加のセキュリティを有効**にします。組織外のユーザーによる認証を要求するように基本の共有機能を構成することはできますが、Microsoft 365 には、データを保護し、外部共有している間にガバナンスポリシーを維持するために役立つ、多くの追加のセキュリティおよびコンプライアンス機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="10734-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="10734-109">共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="10734-109">Enable sharing</span></span>

<span data-ttu-id="10734-110">Microsoft 365 では、既定では、組織外のユーザーとの共有は SharePoint と OneDrive で有効になっていますが、Teams では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="10734-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="10734-111">SharePoint および OneDrive の外部共有シナリオの多くは、それ以上の構成を行わなくても動作します。</span><span class="sxs-lookup"><span data-stu-id="10734-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="10734-112">使用しているシナリオの設定を確認するか、または新しいシナリオを有効にするには、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="10734-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="10734-113">[ドキュメントに対して共同作業](collaborate-on-documents.md)を行う: Microsoft 365 を構成して、ファイルとフォルダーの組織外のユーザー (ゲストと認証されていないユーザーの両方) との共有と共同作業を可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="10734-114">[サイトでの共同作業](collaborate-in-site.md)-ゲストを使用した SharePoint サイトの共有を有効にするように Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="10734-115">[チームとしての共同作業](collaborate-as-team.md)-Teams でゲストコラボレーションを有効にするように Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="10734-116">Microsoft 365 で使用可能なゲスト共有設定の包括的な説明については、「 [microsoft 365 ゲスト共有設定のリファレンス](microsoft-365-guest-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10734-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="10734-117">追加のセキュリティを有効にする</span><span class="sxs-lookup"><span data-stu-id="10734-117">Enable additional security</span></span>

<span data-ttu-id="10734-118">組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または故意に不適切な共有からコンテンツを保護するための追加の保護機能を検討します。</span><span class="sxs-lookup"><span data-stu-id="10734-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="10734-119">認証されていない[ユーザーとファイルやフォルダーを共有するためのベストプラクティス](best-practices-anonymous-sharing.md)-認証されていないユーザーとの共有のベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="10734-120">[偶発的な公開を制限](share-limit-accidental-exposure.md)する: 機密コンテンツを誤って組織外のユーザーと共有する危険性を軽減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="10734-121">[セキュリティで保護されたゲスト共有環境を作成](create-secure-guest-sharing-environment.md)する-組織外のユーザーとの共有が安全かつ安全な方法で行われ、ガバナンス要件を満たしていることを確認するために、Microsoft 365 で提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="10734-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="10734-122">パートナー企業との共同作業</span><span class="sxs-lookup"><span data-stu-id="10734-122">Collaborate with partner companies</span></span>

<span data-ttu-id="10734-123">他の組織から多数のゲストが関係する大規模なプロジェクトで作業している場合や、ゲストが頻繁に変更される可能性のある継続的なベンダーの関係がある場合は、Azure Active Directory の資格管理を使用して、ゲスト管理を簡略化し、パートナー会社がその責任で共有できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10734-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="10734-124">詳細について[は、「管理されたゲストでの B2B エクストラネットの作成](b2b-extranet.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10734-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="10734-125">共有を制限する</span><span class="sxs-lookup"><span data-stu-id="10734-125">Limit sharing</span></span>

<span data-ttu-id="10734-126">Microsoft 365 の共有機能の一部がガバナンスポリシーと競合している場合は、「 [365 microsoft の](microsoft-365-limit-sharing.md)共有を制限する」を参照して、共有の制限のオプションについて確認してください。</span><span class="sxs-lookup"><span data-stu-id="10734-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="see-also"></a><span data-ttu-id="10734-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="10734-127">See Also</span></span>

[<span data-ttu-id="10734-128">Microsoft 365 でのファイルの共同作業の概要</span><span class="sxs-lookup"><span data-stu-id="10734-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="10734-129">Microsoft 365 を使用して SharePoint でファイルのコラボレーションを計画する</span><span class="sxs-lookup"><span data-stu-id="10734-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
