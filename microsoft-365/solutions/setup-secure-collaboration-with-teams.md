---
title: Microsoft 365 とセキュリティで保護された共同作業を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Teams でセキュリティで保護されたコンテンツのコラボレーションを設定して、データをその感度に基づいて保護する方法について学習します。
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233858"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="0a48a-103">Microsoft 365 とセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="0a48a-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="0a48a-104">適切なユーザーと情報を簡単に共有できる一方で、過剰な共有を防ぐことが、組織の成功の鍵となります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="0a48a-105">これには、機密データにアクセスする必要があるユーザーとのみ安全に共有できる機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="0a48a-106">プロジェクトによっては、組織外のユーザーとの機密データの共有が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

<span data-ttu-id="0a48a-107">このコラボレーション ソリューション ガイダンスには、次の 2 つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0a48a-107">This collaboration solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="0a48a-108">各プロジェクトの適切な保護レベルで Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="0a48a-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="0a48a-109">プロジェクトごとに適切なセキュリティ設定を使用して外部共有を構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-109">Configure external sharing with appropriate security settings for each project</span></span>

![適切な保護を使用して Teams を展開し、適切なセキュリティ設定を使用して外部共有を構成する](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="0a48a-111">用途が広く使いやすいコンテンツ コラボレーション ツールが利用できない場合、ユーザーはドキュメントを電子メールで送信して共同作業を行う場合がよくがあります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-111">If versatile and easy-to-use content collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="0a48a-112">これは、グループ化を行うのに時間がかからない、間違いを起こしやすい方法であり、情報の不適切な共有のリスクを高める可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="0a48a-113">情報の共有が難しすぎると感じ取った場合は、IT が管理していないコンシューマー製品の使用に戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="0a48a-114">これにより、さらに大きなリスクが生じ得る。</span><span class="sxs-lookup"><span data-stu-id="0a48a-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="0a48a-115">Microsoft 365 を使用すると、次に役立つさまざまな構成で Teams を展開できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="0a48a-116">知的財産を保護する</span><span class="sxs-lookup"><span data-stu-id="0a48a-116">Protect your intellectual property</span></span>
- <span data-ttu-id="0a48a-117">簡単な共同作業を可能にする</span><span class="sxs-lookup"><span data-stu-id="0a48a-117">Enable easy collaboration</span></span>
- <span data-ttu-id="0a48a-118">セキュリティと操作性のバランスを取り、ユーザー満足度を高め、シャドウ IT のリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="0a48a-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="0a48a-119">ほとんどの組織には、さまざまな情報があります。情報が不適切に共有されている場合は、さまざまなレベルの感度とビジネスへの影響度が異なります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="0a48a-120">特定の情報の感度に応じて、次の情報との共有を許可できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="0a48a-121">だれでも (認証されていない)</span><span class="sxs-lookup"><span data-stu-id="0a48a-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="0a48a-122">組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="0a48a-122">People inside the organization</span></span>
- <span data-ttu-id="0a48a-123">組織内の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="0a48a-123">Specific people inside the organization</span></span>
- <span data-ttu-id="0a48a-124">組織内外の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="0a48a-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="0a48a-125">マーケティング部門などの情報は、組織外で広く共有することを目的とします。</span><span class="sxs-lookup"><span data-stu-id="0a48a-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="0a48a-126">このメニューなどの情報は、外部共有を意図した情報ではなく、外部で共有されている場合はビジネスに影響を与える可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="0a48a-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="0a48a-127">これらの種類の情報は、ほとんどまたは全く保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a48a-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="0a48a-128">これらの同じマーケティング活動は、開発中ですが、組織内でのみ共有される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="0a48a-129">この場合、Teams の既定の共有設定で十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="0a48a-130">開発中の新しい製品に関する情報は、組織内でも機密性が高いと見なされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="0a48a-131">この場合は、より高いレベルの保護が適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="0a48a-132">たとえば、この情報へのアクセスを特定のチームのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="0a48a-133">プロジェクトによっては、ベンダーやパートナー組織など、組織外のユーザーとの共同作業が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="0a48a-134">組織の成功に不可欠な情報や、厳しいセキュリティ要件やコンプライアンス要件を持つ情報には、さらに高いレベルの保護が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a48a-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![リスクスケールを低 (リリース済み) から高 (機密性の高いビジネス データ) に変更しました](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="0a48a-136">上記のすべてのシナリオでは、Microsoft Teams のチームを使用して、情報の保存、共有、共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="0a48a-137">セキュリティで保護されたコラボレーションを構成するには、次の Microsoft 365 の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a48a-137">To configure secure collaboration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="0a48a-138">製品またはコンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a48a-138">Product or component</span></span> | <span data-ttu-id="0a48a-139">機能</span><span class="sxs-lookup"><span data-stu-id="0a48a-139">Capability or feature</span></span> | <span data-ttu-id="0a48a-140">ライセンス</span><span class="sxs-lookup"><span data-stu-id="0a48a-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="0a48a-141">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0a48a-141">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0a48a-142">SPO、OneDrive、Teams の安全な添付ファイル安全なドキュメントTeams の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="0a48a-142">Safe Attachments for SPO, OneDrive and Teams; Safe Documents; Safe Links for Teams</span></span>    | <span data-ttu-id="0a48a-143">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="0a48a-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="0a48a-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a48a-144">SharePoint</span></span>    | <span data-ttu-id="0a48a-145">サイトとファイル共有ポリシー, サイト共有のアクセス許可, リンクの共有, アクセス要求, サイトのゲスト共有の設定</span><span class="sxs-lookup"><span data-stu-id="0a48a-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="0a48a-146">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="0a48a-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="0a48a-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a48a-147">Microsoft Teams</span></span>   | <span data-ttu-id="0a48a-148">ゲスト アクセス、プライベート チーム、プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="0a48a-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="0a48a-149">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="0a48a-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="0a48a-150">Microsoft 365 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="0a48a-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="0a48a-151">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="0a48a-151">Sensitivity labels</span></span>    | <span data-ttu-id="0a48a-152">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="0a48a-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="0a48a-153">あらゆる種類のデータに Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="0a48a-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="0a48a-154">さまざまな機性を持つ情報へのアクセスを管理するために、Teams の 3 つの異なる [層の保護を開発しました](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0a48a-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="0a48a-155">これらの階層は、ニーズやビジネスに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams の論理的なアーキテクチャ ポスターのサムネイル](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="0a48a-157">ベースライン、機密、および機密性の高いこれらの層は、次の表に示すように、過剰な情報の漏えいや潜在的な情報漏洩を防ぐのに役立つ保護を徐々に強化します。 </span><span class="sxs-lookup"><span data-stu-id="0a48a-157">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

|-|<span data-ttu-id="0a48a-158">**ベースライン層**</span><span class="sxs-lookup"><span data-stu-id="0a48a-158">**Baseline tier**</span></span>|<span data-ttu-id="0a48a-159">**機密階層**</span><span class="sxs-lookup"><span data-stu-id="0a48a-159">**Sensitive tier**</span></span>|<span data-ttu-id="0a48a-160">**機密性の高い階層**</span><span class="sxs-lookup"><span data-stu-id="0a48a-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="0a48a-161">パブリック チームまたはプライベート チーム</span><span class="sxs-lookup"><span data-stu-id="0a48a-161">Public or private team</span></span>|<span data-ttu-id="0a48a-162">[Either/リンク/埋め込み]</span><span class="sxs-lookup"><span data-stu-id="0a48a-162">Either</span></span>|<span data-ttu-id="0a48a-163">プライベート</span><span class="sxs-lookup"><span data-stu-id="0a48a-163">Private</span></span>|<span data-ttu-id="0a48a-164">プライベート</span><span class="sxs-lookup"><span data-stu-id="0a48a-164">Private</span></span>|
|<span data-ttu-id="0a48a-165">認証されていない共有</span><span class="sxs-lookup"><span data-stu-id="0a48a-165">Unauthenticated sharing</span></span>|<span data-ttu-id="0a48a-166">Blocked</span><span class="sxs-lookup"><span data-stu-id="0a48a-166">Blocked</span></span>|<span data-ttu-id="0a48a-167">Blocked</span><span class="sxs-lookup"><span data-stu-id="0a48a-167">Blocked</span></span>|<span data-ttu-id="0a48a-168">Blocked</span><span class="sxs-lookup"><span data-stu-id="0a48a-168">Blocked</span></span>|
|<span data-ttu-id="0a48a-169">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="0a48a-169">File sharing</span></span>|<span data-ttu-id="0a48a-170">可</span><span class="sxs-lookup"><span data-stu-id="0a48a-170">Allowed</span></span>|<span data-ttu-id="0a48a-171">可</span><span class="sxs-lookup"><span data-stu-id="0a48a-171">Allowed</span></span>|<span data-ttu-id="0a48a-172">共有できるのはチーム所有者のみです。</span><span class="sxs-lookup"><span data-stu-id="0a48a-172">Only team owners can share.</span></span>|
|<span data-ttu-id="0a48a-173">チーム メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="0a48a-173">Team membership</span></span>|<span data-ttu-id="0a48a-174">誰でもパブリック チームに参加できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-174">Anyone can join public teams.</span></span><br><span data-ttu-id="0a48a-175">プライベート チームに参加するには、チーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="0a48a-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="0a48a-176">参加するにはチーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="0a48a-176">Team owner approval required to join.</span></span>|<span data-ttu-id="0a48a-177">参加するにはチーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="0a48a-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="0a48a-178">ドキュメントの暗号化</span><span class="sxs-lookup"><span data-stu-id="0a48a-178">Document encryption</span></span>|||<span data-ttu-id="0a48a-179">[Sensitivity label] (区別ラベル付き) で使用可能</span><span class="sxs-lookup"><span data-stu-id="0a48a-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="0a48a-180">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="0a48a-180">Guest sharing</span></span>|<span data-ttu-id="0a48a-181">可</span><span class="sxs-lookup"><span data-stu-id="0a48a-181">Allowed</span></span>|<span data-ttu-id="0a48a-182">許可またはブロック可能</span><span class="sxs-lookup"><span data-stu-id="0a48a-182">Can be allowed or blocked</span></span>|<span data-ttu-id="0a48a-183">許可またはブロック可能</span><span class="sxs-lookup"><span data-stu-id="0a48a-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="0a48a-184">非管理対象デバイス</span><span class="sxs-lookup"><span data-stu-id="0a48a-184">Unmanaged devices</span></span>|<span data-ttu-id="0a48a-185">制限なし</span><span class="sxs-lookup"><span data-stu-id="0a48a-185">No restriction</span></span>|<span data-ttu-id="0a48a-186">Web 専用アクセス</span><span class="sxs-lookup"><span data-stu-id="0a48a-186">Web-only access</span></span>|<span data-ttu-id="0a48a-187">Blocked</span><span class="sxs-lookup"><span data-stu-id="0a48a-187">Blocked</span></span>|

<span data-ttu-id="0a48a-188">これらの層を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a48a-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="0a48a-189">ゲスト アクセスとプライベート チャネル用に Teams の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="0a48a-190">内部共有とゲスト共有、アクセス要求、および共有リンク用にチームに関連付けられた SharePoint サイトの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="0a48a-191">機密性の *高* い *層と機密性* の高い層の場合、チームを分類し、管理されていないデバイスからのゲスト共有とアクセスを制御する機密ラベルを構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="0a48a-192">機密性の *高い* 層の場合は、適用するドキュメントを暗号化する機密ラベルを構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="0a48a-193">ベースライン層から始めて、必要に応じて機密性の高い、機密性の高い層を使用するチームを追加して、組織内の情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="0a48a-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="0a48a-194">開始するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a48a-194">See these resources to get started:</span></span>

- [<span data-ttu-id="0a48a-195">ベースライン保護を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="0a48a-196">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="0a48a-197">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="0a48a-198">組織内でも共有からの保護を強化する必要がある機密性の高いプロジェクトがある場合は、独自の機密ラベルを使用してファイルを暗号化するチームを構成して、チーム メンバーだけがファイルを読み取り可能にできます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="0a48a-199">詳細 [については、「セキュリティ分離を使用してチームを構成する](secure-teams-security-isolation.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a48a-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="0a48a-200">組織外のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="0a48a-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="0a48a-201">組織外のユーザー [と任意の感度の情報を共有する必要がある場合があります](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="0a48a-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="0a48a-202">これは、単一のドキュメントを 1 人のユーザーと共有したり、大規模なパートナー組織や世界中の人との主要なプロジェクトで共同作業を行う場合などです。</span><span class="sxs-lookup"><span data-stu-id="0a48a-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="0a48a-203">Microsoft 365 では、この範囲の外部共有は、機密情報の保護に役立つ適切な保護策を使用して、簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="0a48a-204">次のリソースは、組織外のユーザーと共同作業するための環境のセットアップを開始するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="0a48a-205">[ドキュメントで共同作業を行い](collaborate-on-documents.md) 、フォルダーの個々のファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="0a48a-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="0a48a-206">[SharePoint サイトでゲスト](collaborate-in-site.md) と共同作業を行うサイトで共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="0a48a-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="0a48a-207">[チーム内のゲストと](collaborate-as-team.md) 共同作業を行うチームとして共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="0a48a-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="0a48a-208">共有される情報の感度に応じて、過剰な共有を防ぐためのセーフガードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="0a48a-209">これらのリソースは、組織に必要な保護を設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="0a48a-210">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="0a48a-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="0a48a-211">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="0a48a-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="0a48a-212">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="0a48a-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="0a48a-213">パートナー組織に主要なプロジェクトがある場合は、Azure Entitlement Management を使用して、プロジェクトに設定したチーム内の組織のゲストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="0a48a-214">詳細 [については、「管理されたゲストと B2B エクストラネットを作成する」](b2b-extranet.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a48a-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="0a48a-215">セキュリティで保護されたコラボレーション ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="0a48a-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="0a48a-216">このソリューションを展開する準備ができたら、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="0a48a-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="0a48a-217">Teams の [3 つの異なる保護層を構成します](configure-teams-three-tiers-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0a48a-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="0a48a-218">組織外の [ユーザーと任意の感度情報を共有する設定を構成します](collaborate-with-people-outside-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="0a48a-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0a48a-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a48a-219">See also</span></span>

[<span data-ttu-id="0a48a-220">Microsoft 365 のセキュリティに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="0a48a-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="0a48a-221">Microsoft 365 コンプライアンスのドキュメント</span><span class="sxs-lookup"><span data-stu-id="0a48a-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="0a48a-222">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="0a48a-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
