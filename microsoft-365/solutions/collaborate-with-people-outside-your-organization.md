---
title: 組織外部のユーザーとの共有
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
description: Teams、OneDrive、SharePoint のような Microsoft 365 アプリを組織外のユーザーと共同作業するために構成する方法について説明します。
ms.openlocfilehash: 7b8e5e30d8222d055fc5f64472c4083db614d4bd
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261515"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="7163a-103">組織外部のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="7163a-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="7163a-104">Microsoft 365 の外部共有機能は、ディレクトリにアカウントを持たなかったパートナー、ベンダー、顧客、その他のユーザーと共同作業を行う機会を組織内のユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="7163a-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="7163a-105">チーム全体またはサイト全体を組織外のユーザーと共有したり、個々のファイルと共有することができます。</span><span class="sxs-lookup"><span data-stu-id="7163a-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="7163a-106">組織外のユーザーとの共同作業は、次の 2 つの主要なコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7163a-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="7163a-107">**共有を** 有効にする - Azure Active Directory、Teams、Microsoft 365 グループ、および SharePoint 全体の共有コントロールを構成して、組織に必要な共有レベルを許可します。</span><span class="sxs-lookup"><span data-stu-id="7163a-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="7163a-108">追加のセキュリティを有効にする **-** 基本的な共有機能は組織外のユーザーに認証を要求するように構成することができますが、Microsoft 365 には、データを保護し、外部と共有しながらガバナンス ポリシーを維持するのに役立つ多くの追加のセキュリティ機能とコンプライアンス機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="7163a-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="7163a-109">共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="7163a-109">Enable sharing</span></span>

<span data-ttu-id="7163a-110">既定では、Microsoft 365 では、組織外のユーザーとの共有が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7163a-110">By default, in Microsoft 365, sharing with people outside your organization is enabled.</span></span> <span data-ttu-id="7163a-111">多くの外部共有シナリオは、それ以上の構成なしで動作します。</span><span class="sxs-lookup"><span data-stu-id="7163a-111">Many external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="7163a-112">使用しているシナリオの設定を確認するか、新しいシナリオを有効にするには、次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="7163a-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="7163a-113">[ドキュメントで](collaborate-on-documents.md) 共同作業を行う - Microsoft 365 を構成して、組織外のユーザー (ゲストと認証されていないユーザーの両方) とのファイルとフォルダーの共有とコラボレーションを許可する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7163a-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="7163a-114">[サイトで共同作業を行う](collaborate-in-site.md) - ゲストと SharePoint サイトを共有するために Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7163a-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="7163a-115">[チームとして共同作業を行う](collaborate-as-team.md) - Teams でゲストコラボレーションを有効にするために Microsoft 365 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7163a-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="7163a-116">Microsoft 365 全体で利用可能なゲスト共有設定の包括的な説明については [、Microsoft 365 ゲスト共有設定のリファレンスを参照してください](microsoft-365-guest-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="7163a-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="7163a-117">追加のセキュリティを有効にする</span><span class="sxs-lookup"><span data-stu-id="7163a-117">Enable additional security</span></span>

<span data-ttu-id="7163a-118">組織外のユーザーとの共有に使用するシナリオを有効にしたら、偶発的または意図的な不適切な共有からコンテンツを保護するための追加のセーフガードを検討します。</span><span class="sxs-lookup"><span data-stu-id="7163a-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="7163a-119">[認証されていないユーザーとファイル](best-practices-anonymous-sharing.md) やフォルダーを共有するためのベスト プラクティス - 認証されていないユーザーと共有するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7163a-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="7163a-120">[偶発的な](share-limit-accidental-exposure.md) 露出を制限する - 組織外のユーザーと機密性の高いコンテンツを誤って共有する可能性を減らす方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="7163a-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="7163a-121">セキュリティで保護されたゲスト共有環境を作成する[-](create-secure-guest-sharing-environment.md)組織外のユーザーとの共有が安全で安全な方法で行われ、ガバナンス要件を満たしていることを確認するために Microsoft 365 で提供されるツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7163a-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="7163a-122">パートナー企業との共同作業</span><span class="sxs-lookup"><span data-stu-id="7163a-122">Collaborate with partner companies</span></span>

<span data-ttu-id="7163a-123">別の組織の多くのゲストが関与する大規模なプロジェクトに取り組む場合、またはゲストが頻繁に変更される継続的なベンダー関係がある場合は、Azure Active Directory の権利管理を使用してゲスト管理を簡素化し、パートナー企業が責任を共有できます。</span><span class="sxs-lookup"><span data-stu-id="7163a-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="7163a-124">詳細 [については、「管理されたゲストと B2B エクストラネットを作成する」](b2b-extranet.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7163a-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="7163a-125">共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7163a-125">Limit sharing</span></span>

<span data-ttu-id="7163a-126">Microsoft 365 の共有機能の一部がガバナンス ポリシーと競合する場合は [、「Microsoft 365](microsoft-365-limit-sharing.md) で共有を制限する」を参照して、共有を制限するオプションについて確認してください。</span><span class="sxs-lookup"><span data-stu-id="7163a-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7163a-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7163a-127">Related topics</span></span>

[<span data-ttu-id="7163a-128">Microsoft 365 でのファイルコラボレーションの説明</span><span class="sxs-lookup"><span data-stu-id="7163a-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="7163a-129">Microsoft 365 で SharePoint でのファイルのコラボレーションを計画する</span><span class="sxs-lookup"><span data-stu-id="7163a-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
