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
description: 機密情報に基づいてデータを保護するために Teams でセキュリティで保護されたコンテンツコラボレーションをセットアップする方法について説明します。
ms.openlocfilehash: f65657125fef8b8cf7e4e229d70d8fe211153392
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613586"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a><span data-ttu-id="3aa9e-103">Microsoft 365 とセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-103">Set up secure collaboration with Microsoft 365</span></span>

<span data-ttu-id="3aa9e-104">情報を適切な人と簡単に共有できるようにする一方で、過剰な共有が組織の成功にとって重要であることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-104">Being able to easily share information with the right people while preventing oversharing is key to an organization's success.</span></span> <span data-ttu-id="3aa9e-105">これには、機密データをアクセスする必要があるユーザーに対してのみ安全に共有できることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-105">This includes being able to share sensitive data safely with only those who should have access to it.</span></span> <span data-ttu-id="3aa9e-106">プロジェクトによっては、機密データを組織外のユーザーと共有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-106">Depending on the project, this might include sharing sensitive data with people outside your organization.</span></span>

<span data-ttu-id="3aa9e-107">このコラボレーションソリューションのガイダンスには、次のような2つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-107">This collaboration solution guidance includes two components to help you:</span></span>
- <span data-ttu-id="3aa9e-108">各プロジェクトの適切なレベルの保護を使用して Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-108">Deploy Microsoft Teams with the right level of protection for each project</span></span>
- <span data-ttu-id="3aa9e-109">プロジェクトごとに適切なセキュリティ設定を使用して外部共有を構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-109">Configure external sharing with appropriate security settings for each project</span></span>

![適切な保護を使用して Teams を展開し、適切なセキュリティ設定を使用して外部共有を構成する](..\media\solutions-architecture-center\secure-collaboration-overview.png)

<span data-ttu-id="3aa9e-111">多目的で使いやすいコンテンツコラボレーションツールを使用できない場合、ユーザーはメールでドキュメントを送信して共同作業することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-111">If versatile and easy-to-use content collaboration tools aren't available, users will often collaborate by emailing documents.</span></span> <span data-ttu-id="3aa9e-112">これは、単調でエラーが発生しやすいコラボレーションの方法であり、情報が不適切に共有されるリスクを高めることができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-112">This is a tedious and error-prone method of collaboration, and can increase the risk of inappropriate sharing of information.</span></span> <span data-ttu-id="3aa9e-113">ユーザーが情報を共有することが困難すぎる場合は、その情報が管理されていないコンシューマー製品の使用に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-113">If people find sharing information too difficult, they could revert to using consumer products that are not governed by IT.</span></span> <span data-ttu-id="3aa9e-114">これにより、さらに大きなリスクが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-114">This can pose an even greater risk.</span></span>

<span data-ttu-id="3aa9e-115">Microsoft 365 では、次のようなさまざまな構成を使用して Teams を展開できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-115">With Microsoft 365, you can deploy Teams with a variety of configurations that help:</span></span>

- <span data-ttu-id="3aa9e-116">知的所有権を保護する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-116">Protect your intellectual property</span></span>
- <span data-ttu-id="3aa9e-117">簡単にコラボレーションを有効にする</span><span class="sxs-lookup"><span data-stu-id="3aa9e-117">Enable easy collaboration</span></span>
- <span data-ttu-id="3aa9e-118">セキュリティと操作性のバランスを確立して、ユーザーの満足度を上げ、シャドウを考慮するリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-118">Create a balance between security and usability that increases user satisfaction and reduces the risk of shadow IT</span></span>

<span data-ttu-id="3aa9e-119">ほとんどの組織にはさまざまな情報があり、機密度が異なり、情報が適切に共有されていない場合にはさまざまなビジネスへの影響があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-119">Most organizations have a variety of information, with varying degrees of sensitivity and varying degrees of business impact if the information is inappropriately shared.</span></span> <span data-ttu-id="3aa9e-120">特定の情報の機密性に応じて、次のような共有を許可することができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-120">Depending on the sensitivity of a given piece of information, you may want to allow sharing with:</span></span>

- <span data-ttu-id="3aa9e-121">すべてのユーザー (認証されていない)</span><span class="sxs-lookup"><span data-stu-id="3aa9e-121">Anyone (unauthenticated)</span></span>
- <span data-ttu-id="3aa9e-122">組織内のユーザー</span><span class="sxs-lookup"><span data-stu-id="3aa9e-122">People inside the organization</span></span>
- <span data-ttu-id="3aa9e-123">組織内の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="3aa9e-123">Specific people inside the organization</span></span>
- <span data-ttu-id="3aa9e-124">組織の内部および外部の特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="3aa9e-124">Specific people inside and outside the organization</span></span>

<span data-ttu-id="3aa9e-125">マーケティングパンフレットなどの情報は、組織外での共有を目的としています。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-125">Information such as marketing brochures are meant for sharing broadly outside the organization.</span></span> <span data-ttu-id="3aa9e-126">カフェテリアのメニューなどの情報は、外部共有を目的としたものではありませんが、外部で共有されている場合はビジネスへの影響はありません。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-126">Information such as cafeteria menus aren't meant for external sharing, but would have no business impact if they were shared externally.</span></span> <span data-ttu-id="3aa9e-127">これらの種類の情報は、ほとんどまたはまったく保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-127">These types of information need little or no protection.</span></span>

<span data-ttu-id="3aa9e-128">開発中の同じマーケティングパンフレットは、組織内でのみ共有することができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-128">Those same marketing brochures, while under development, might only be shared inside the organization.</span></span> <span data-ttu-id="3aa9e-129">この場合は、Teams の既定の共有設定で十分です。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-129">In this case, the default sharing settings in Teams may be sufficient.</span></span>

<span data-ttu-id="3aa9e-130">開発中の新しい製品に関する情報は、組織内であっても機密であると見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-130">Information about a new product that is under development might be considered sensitive, even within the organization.</span></span> <span data-ttu-id="3aa9e-131">この場合は、より高いレベルの保護が適している場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-131">A greater degree of protection might be appropriate in this case.</span></span> <span data-ttu-id="3aa9e-132">たとえば、特定のチームのメンバーに対するこの情報へのアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-132">You could restrict access to this information to members of a specific team, for example.</span></span> <span data-ttu-id="3aa9e-133">プロジェクトによっては、ベンダーやパートナー組織などの組織外のユーザーと共同作業が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-133">Depending on the project, you may need to collaborate with people outside your organization, such as a vendor or partner organization.</span></span>

<span data-ttu-id="3aa9e-134">組織の成功にとって重要な情報、またはセキュリティやコンプライアンスに関する厳しい要件がある場合は、より高いレベルの保護が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-134">Information that is critical to your organization's success, or has stringent security or compliance requirements might require even greater levels of protection.</span></span>

![低 (リリースパンフレット) から高 (機密性の高いビジネスデータ) までのリスクスケール](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

<span data-ttu-id="3aa9e-136">上記のすべてのシナリオでは、Microsoft Teams の teams を使用して、情報を格納、共有、および共同作業することができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-136">For all the scenarios noted above, you can use teams in Microsoft Teams to store, share, and collaborate on the information.</span></span> 

<span data-ttu-id="3aa9e-137">セキュリティで保護されたグループ作業を構成するには、次の Microsoft 365 の機能と機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-137">To configure secure collaboration, you use these Microsoft 365 capabilities and features.</span></span>

| <span data-ttu-id="3aa9e-138">製品またはコンポーネント</span><span class="sxs-lookup"><span data-stu-id="3aa9e-138">Product or component</span></span> | <span data-ttu-id="3aa9e-139">機能</span><span class="sxs-lookup"><span data-stu-id="3aa9e-139">Capability or feature</span></span> | <span data-ttu-id="3aa9e-140">ライセンス</span><span class="sxs-lookup"><span data-stu-id="3aa9e-140">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="3aa9e-141">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="3aa9e-141">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="3aa9e-142">SPO、OneDrive、Teams の安全な添付ファイル。安全なドキュメント。Teams の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="3aa9e-142">Safe Attachments for SPO, OneDrive and Teams; Safe Documents; Safe Links for Teams</span></span>    | <span data-ttu-id="3aa9e-143">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="3aa9e-143">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="3aa9e-144">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3aa9e-144">SharePoint</span></span>    | <span data-ttu-id="3aa9e-145">サイトとファイルの共有のポリシー、サイトの共有のアクセス許可、共有リンク、アクセスの要求、サイトのゲスト共有設定</span><span class="sxs-lookup"><span data-stu-id="3aa9e-145">Site and file sharing policies, Site sharing permissions, Sharing links, Access requests, Site guest sharing settings</span></span> | <span data-ttu-id="3aa9e-146">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="3aa9e-146">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="3aa9e-147">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3aa9e-147">Microsoft Teams</span></span>   | <span data-ttu-id="3aa9e-148">ゲストアクセス、プライベートチーム、プライベートチャネル</span><span class="sxs-lookup"><span data-stu-id="3aa9e-148">Guest access, private teams, private channels</span></span> | <span data-ttu-id="3aa9e-149">Microsoft 365 E1、E3、E5</span><span class="sxs-lookup"><span data-stu-id="3aa9e-149">Microsoft 365 E1, E3 and E5</span></span> |
| <span data-ttu-id="3aa9e-150">Microsoft 365 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="3aa9e-150">Microsoft 365 Compliance</span></span>  | <span data-ttu-id="3aa9e-151">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="3aa9e-151">Sensitivity labels</span></span>    | <span data-ttu-id="3aa9e-152">Microsoft 365 E3、E5</span><span class="sxs-lookup"><span data-stu-id="3aa9e-152">Microsoft 365 E3 and E5</span></span> |

### <a name="using-teams-for-all-kinds-of-data"></a><span data-ttu-id="3aa9e-153">すべての種類のデータに Teams を使用する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-153">Using Teams for all kinds of data</span></span>

<span data-ttu-id="3aa9e-154">さまざまな反応を持つ情報へのアクセスを管理するために、 [Teams に対して3つの異なる保護レベル](configure-teams-three-tiers-protection.md)を開発しました。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-154">To manage access to information with different sensitivities, we've developed [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span> <span data-ttu-id="3aa9e-155">これらの層のいずれかをカスタマイズして、ニーズやビジネスに適したものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-155">You can customize any of these tiers to better address the needs or your business.</span></span> 

![Teams の論理的なアーキテクチャ ポスターのサムネイル](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


<span data-ttu-id="3aa9e-157">次の表に示すよう *に、これら* の *階層によって、過度\*\*な共有* や情報漏洩を防止するための保護が徐々に増加します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-157">These tiers - *baseline*, *sensitive*, and *highly sensitive* - gradually increase the protections that help prevent oversharing and potential information leakage, as shown in the following table.</span></span>

|-|<span data-ttu-id="3aa9e-158">**ベースライン層**</span><span class="sxs-lookup"><span data-stu-id="3aa9e-158">**Baseline tier**</span></span>|<span data-ttu-id="3aa9e-159">**機密層**</span><span class="sxs-lookup"><span data-stu-id="3aa9e-159">**Sensitive tier**</span></span>|<span data-ttu-id="3aa9e-160">**非常に機密性の高い層**</span><span class="sxs-lookup"><span data-stu-id="3aa9e-160">**Highly sensitive tier**</span></span>|
|:--|:-----------|:------------|:-------------------|
|<span data-ttu-id="3aa9e-161">パブリックまたはプライベートチーム</span><span class="sxs-lookup"><span data-stu-id="3aa9e-161">Public or private team</span></span>|<span data-ttu-id="3aa9e-162">[Either/リンク/埋め込み]</span><span class="sxs-lookup"><span data-stu-id="3aa9e-162">Either</span></span>|<span data-ttu-id="3aa9e-163">Kirkland</span><span class="sxs-lookup"><span data-stu-id="3aa9e-163">Private</span></span>|<span data-ttu-id="3aa9e-164">Kirkland</span><span class="sxs-lookup"><span data-stu-id="3aa9e-164">Private</span></span>|
|<span data-ttu-id="3aa9e-165">認証されていない共有</span><span class="sxs-lookup"><span data-stu-id="3aa9e-165">Unauthenticated sharing</span></span>|<span data-ttu-id="3aa9e-166">Blocked</span><span class="sxs-lookup"><span data-stu-id="3aa9e-166">Blocked</span></span>|<span data-ttu-id="3aa9e-167">Blocked</span><span class="sxs-lookup"><span data-stu-id="3aa9e-167">Blocked</span></span>|<span data-ttu-id="3aa9e-168">Blocked</span><span class="sxs-lookup"><span data-stu-id="3aa9e-168">Blocked</span></span>|
|<span data-ttu-id="3aa9e-169">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="3aa9e-169">File sharing</span></span>|<span data-ttu-id="3aa9e-170">可</span><span class="sxs-lookup"><span data-stu-id="3aa9e-170">Allowed</span></span>|<span data-ttu-id="3aa9e-171">可</span><span class="sxs-lookup"><span data-stu-id="3aa9e-171">Allowed</span></span>|<span data-ttu-id="3aa9e-172">チーム所有者のみが共有できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-172">Only team owners can share.</span></span>|
|<span data-ttu-id="3aa9e-173">チームメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="3aa9e-173">Team membership</span></span>|<span data-ttu-id="3aa9e-174">すべてのユーザーがパブリックチームに参加できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-174">Anyone can join public teams.</span></span><br><span data-ttu-id="3aa9e-175">チーム所有者の承認は、プライベートチームに参加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-175">Team owner approval required to join private teams.</span></span>|<span data-ttu-id="3aa9e-176">参加するには、チーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-176">Team owner approval required to join.</span></span>|<span data-ttu-id="3aa9e-177">参加するには、チーム所有者の承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-177">Team owner approval required to join.</span></span>|
|<span data-ttu-id="3aa9e-178">ドキュメントの暗号化</span><span class="sxs-lookup"><span data-stu-id="3aa9e-178">Document encryption</span></span>|||<span data-ttu-id="3aa9e-179">機密ラベルで使用可能</span><span class="sxs-lookup"><span data-stu-id="3aa9e-179">Available with sensitivity label</span></span>|
|<span data-ttu-id="3aa9e-180">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="3aa9e-180">Guest sharing</span></span>|<span data-ttu-id="3aa9e-181">可</span><span class="sxs-lookup"><span data-stu-id="3aa9e-181">Allowed</span></span>|<span data-ttu-id="3aa9e-182">許可またはブロックできる</span><span class="sxs-lookup"><span data-stu-id="3aa9e-182">Can be allowed or blocked</span></span>|<span data-ttu-id="3aa9e-183">許可またはブロックできる</span><span class="sxs-lookup"><span data-stu-id="3aa9e-183">Can be allowed or blocked</span></span>|
|<span data-ttu-id="3aa9e-184">非管理対象デバイス</span><span class="sxs-lookup"><span data-stu-id="3aa9e-184">Unmanaged devices</span></span>|<span data-ttu-id="3aa9e-185">制限なし</span><span class="sxs-lookup"><span data-stu-id="3aa9e-185">No restriction</span></span>|<span data-ttu-id="3aa9e-186">Web 専用アクセス</span><span class="sxs-lookup"><span data-stu-id="3aa9e-186">Web-only access</span></span>|<span data-ttu-id="3aa9e-187">Blocked</span><span class="sxs-lookup"><span data-stu-id="3aa9e-187">Blocked</span></span>|

<span data-ttu-id="3aa9e-188">これらの層の構成には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-188">Configuring these tiers involves:</span></span>

- <span data-ttu-id="3aa9e-189">Teams でゲストアクセスおよびプライベートチャネルの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-189">Configuring settings in Teams for guest access and private channels</span></span>
- <span data-ttu-id="3aa9e-190">内部およびゲストの共有、アクセスの要求、および共有リンクについて、チームの関連付けられた SharePoint サイトの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-190">Configuring settings in a team's associated SharePoint site for internal and guest sharing, access requests, and sharing links</span></span>
- <span data-ttu-id="3aa9e-191">*機密性* の *高い機密* 層に対して、チームを分類するための機密ラベルを構成し、管理されていないデバイスからゲストの共有とアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-191">For the *sensitive* and *highly sensitive* tiers, configuring sensitivity labels to classify the teams, and control guest sharing and access from unmanaged devices</span></span>
- <span data-ttu-id="3aa9e-192">非常に *機密性の高い* 層の場合は、機密ラベルを構成して、適用されるドキュメントを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-192">For the *highly sensitive* tier, configuring a sensitivity label to encrypt the documents to which it is applied</span></span>

<span data-ttu-id="3aa9e-193">ベースライン層から始め、必要に応じて *機密* および *機密性の高い* 階層を使用する teams を追加して、組織内の情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-193">Start with the baseline tier, and then add teams that use the *sensitive* and *highly sensitive* tiers as needed to help protect the information in your organization.</span></span> <span data-ttu-id="3aa9e-194">開始するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-194">See these resources to get started:</span></span>

- [<span data-ttu-id="3aa9e-195">ベースライン保護を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-195">Configure teams with baseline protection</span></span>](configure-teams-baseline-protection.md)
- [<span data-ttu-id="3aa9e-196">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-196">Configure teams with protection for sensitive data</span></span>](configure-teams-sensitive-protection.md)
- [<span data-ttu-id="3aa9e-197">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-197">Configure teams with protection for highly sensitive data</span></span>](configure-teams-highly-sensitive-protection.md)

<span data-ttu-id="3aa9e-198">組織内でも、共有に対する追加の保護を必要とする非常に機密性の高いプロジェクトがある場合は、チームのメンバーだけがファイルを読むことができるように、独自の機密ラベルを使用してファイルを暗号化するようにチームを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-198">If you have a highly sensitive project that requires additional protection from sharing even within your organization, you can configure a team that uses its own sensitivity label to encrypt files so that only team members can read them.</span></span> <span data-ttu-id="3aa9e-199">詳細について [は、「セキュリティの分離を使用してチームを構成](secure-teams-security-isolation.md) する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-199">See [Configure a team with security isolation](secure-teams-security-isolation.md) for details.</span></span>

### <a name="sharing-with-people-outside-your-organization"></a><span data-ttu-id="3aa9e-200">組織外のユーザーとの共有</span><span class="sxs-lookup"><span data-stu-id="3aa9e-200">Sharing with people outside your organization</span></span>

<span data-ttu-id="3aa9e-201">[組織外のユーザーとの秘密度の情報を共有](collaborate-with-people-outside-your-organization.md)する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-201">You may need to [share information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span> <span data-ttu-id="3aa9e-202">これは、単一のドキュメントを1人のユーザーと共有することから、世界中の大規模なパートナー組織またはフリーランサーを持つ主要なプロジェクトで共同作業を行うことまで多岐に沿っています。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-202">This could range from sharing a single document with a single person to collaborating on a major project with a large partner organization or freelancers from around the world.</span></span> <span data-ttu-id="3aa9e-203">Microsoft 365 では、機密情報を保護するための適切な保護対策を使用して、この範囲の外部共有を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-203">In Microsoft 365, this range of external sharing can be done easily and with the appropriate safeguards to help protect your sensitive information.</span></span>

<span data-ttu-id="3aa9e-204">これらのリソースは、組織外のユーザーと共同作業するための環境のセットアップを開始するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-204">These resources will help you get started with setting up your environment for collaborating with people outside your organization:</span></span>

- <span data-ttu-id="3aa9e-205">フォルダーの個々のファイルを共有するために[ドキュメントで共同作業](collaborate-on-documents.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-205">[Collaborate on documents](collaborate-on-documents.md) for sharing individual files of folders.</span></span>
- <span data-ttu-id="3aa9e-206">SharePoint サイトのゲストと共同作業するために[サイトで共同作業](collaborate-in-site.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-206">[Collaborate in a site](collaborate-in-site.md) for collaborating with guests in a SharePoint site.</span></span>
- <span data-ttu-id="3aa9e-207">チーム内のゲストと共同作業を行う[チームとして共同作業](collaborate-as-team.md)を行います。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-207">[Collaborate as a team](collaborate-as-team.md) for collaborating with guests in a team.</span></span>

<span data-ttu-id="3aa9e-208">共有されている情報の機密性に応じて、保護を追加して、過度の共有を防止できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-208">Depending on the sensitivity of the information being shared, you can add safeguards to help prevent oversharing.</span></span> <span data-ttu-id="3aa9e-209">次のリソースは、組織に必要な保護を設定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-209">These resources will help you set up the protections that you need for your organization:</span></span>

- [<span data-ttu-id="3aa9e-210">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="3aa9e-210">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)
- [<span data-ttu-id="3aa9e-211">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-211">Limit accidental exposure to files when sharing with people outside your organization</span></span>](share-limit-accidental-exposure.md)
- [<span data-ttu-id="3aa9e-212">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-212">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

<span data-ttu-id="3aa9e-213">パートナー組織との主要なプロジェクトがある場合は、プロジェクトに対して設定したチームで、Azure の資格管理を使用してその組織からゲストを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-213">If you have a major project with a partner organization, you can use Azure Entitlement Management to manage the guests from that organization in a team that you set up for the project.</span></span> <span data-ttu-id="3aa9e-214">詳細について [は、「管理されたゲストでの B2B エクストラネットの作成](b2b-extranet.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-214">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="deploy-the-secure-collaboration-solution"></a><span data-ttu-id="3aa9e-215">セキュリティで保護されたコラボレーションソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="3aa9e-215">Deploy the secure collaboration solution</span></span>

<span data-ttu-id="3aa9e-216">このソリューションを展開する準備ができたら、次の手順を続行します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-216">When you're ready to deploy this solution, continue with these steps:</span></span>
1. <span data-ttu-id="3aa9e-217">[Teams の3つの異なる保護層](configure-teams-three-tiers-protection.md)を構成します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-217">Configure the [three different tiers of protection for Teams](configure-teams-three-tiers-protection.md).</span></span>
2. <span data-ttu-id="3aa9e-218">[組織外の人との秘密度の情報を共有](collaborate-with-people-outside-your-organization.md)するための設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3aa9e-218">Configure settings for [sharing information of any sensitivity with people outside your organization](collaborate-with-people-outside-your-organization.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3aa9e-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="3aa9e-219">See also</span></span>

[<span data-ttu-id="3aa9e-220">Microsoft 365 のセキュリティに関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="3aa9e-220">Microsoft 365 security documentation</span></span>](https://docs.microsoft.com/microsoft-365/security)

[<span data-ttu-id="3aa9e-221">Microsoft 365 コンプライアンスのドキュメント</span><span class="sxs-lookup"><span data-stu-id="3aa9e-221">Microsoft 365 compliance documentation</span></span>](https://docs.microsoft.com/microsoft-365/compliance)

[<span data-ttu-id="3aa9e-222">Microsoft Teams にようこそ</span><span class="sxs-lookup"><span data-stu-id="3aa9e-222">Welcome to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
