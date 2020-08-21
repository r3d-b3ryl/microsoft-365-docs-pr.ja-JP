---
title: メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) における保護のアプリケーションの順序について学習できます。また、保護ポリシーの優先順位の値で、どのポリシーが適用されるかがどのように決定されるかについて学習できます。
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827411"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="86854-104">メール保護の順序と優先順位</span><span class="sxs-lookup"><span data-stu-id="86854-104">Order and precedence of email protection</span></span>

<span data-ttu-id="86854-105">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信電子メールに複数の保護が設定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="86854-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="86854-106">たとえば、組み込みの EOP フィッシング対策ポリシー (すべての Microsoft 365 ユーザーが利用可能) と、より堅牢な ATP フィッシング対策ポリシー (Office 365 Advanced Threat Protection (Office 365 ATP) ユーザーも利用できます。</span><span class="sxs-lookup"><span data-stu-id="86854-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="86854-107">また、メッセージはマルウェア、スパム、フィッシングなどについて複数の検出スキャンにパスします。このアクティビティをすべて完了すると、どのポリシーが適用されるかについて、多く問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86854-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="86854-108">通常、メッセージに適用されるポリシーは **、X-Forefront-Antispam-Report** ヘッダーの **CAT (Category) プロパティで特定** できます。</span><span class="sxs-lookup"><span data-stu-id="86854-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="86854-109">詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86854-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="86854-110">メッセージに適用されるポリシーを決定する主な要因は 2 つです。</span><span class="sxs-lookup"><span data-stu-id="86854-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="86854-111">**電子メール保護タイプの優先度**: この順序は構成できません。次の表に、その順序を示します。</span><span class="sxs-lookup"><span data-stu-id="86854-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="86854-112">優先度</span><span class="sxs-lookup"><span data-stu-id="86854-112">Priority</span></span>|<span data-ttu-id="86854-113">電子メール保護</span><span class="sxs-lookup"><span data-stu-id="86854-113">Email protection</span></span>|<span data-ttu-id="86854-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="86854-114">Category</span></span>|<span data-ttu-id="86854-115">管理する場所</span><span class="sxs-lookup"><span data-stu-id="86854-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="86854-116">1 </span><span class="sxs-lookup"><span data-stu-id="86854-116">1</span></span>|<span data-ttu-id="86854-117">マルウェア</span><span class="sxs-lookup"><span data-stu-id="86854-117">Malware</span></span>|<span data-ttu-id="86854-118">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="86854-118">CAT:MALW</span></span>|[<span data-ttu-id="86854-119">EOP でマルウェア対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="86854-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="86854-120">2 </span><span class="sxs-lookup"><span data-stu-id="86854-120">2</span></span>|<span data-ttu-id="86854-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="86854-121">Phishing</span></span>|<span data-ttu-id="86854-122">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="86854-122">CAT:PHSH</span></span>|[<span data-ttu-id="86854-123">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="86854-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="86854-124">3 </span><span class="sxs-lookup"><span data-stu-id="86854-124">3</span></span>|<span data-ttu-id="86854-125">高確度スパム</span><span class="sxs-lookup"><span data-stu-id="86854-125">High confidence spam</span></span>|<span data-ttu-id="86854-126">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="86854-126">CAT:HSPM</span></span>|[<span data-ttu-id="86854-127">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="86854-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="86854-128">4 </span><span class="sxs-lookup"><span data-stu-id="86854-128">4</span></span>|<span data-ttu-id="86854-129">スプーフィング</span><span class="sxs-lookup"><span data-stu-id="86854-129">Spoofing</span></span>|<span data-ttu-id="86854-130">CAT:SPOOF</span><span class="sxs-lookup"><span data-stu-id="86854-130">CAT:SPOOF</span></span>|[<span data-ttu-id="86854-131">EOP でスプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="86854-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="86854-132">5 </span><span class="sxs-lookup"><span data-stu-id="86854-132">5</span></span>|<span data-ttu-id="86854-133">スパム</span><span class="sxs-lookup"><span data-stu-id="86854-133">Spam</span></span>|<span data-ttu-id="86854-134">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="86854-134">CAT:SPM</span></span>|[<span data-ttu-id="86854-135">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="86854-135">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="86854-136">6 </span><span class="sxs-lookup"><span data-stu-id="86854-136">6</span></span>|<span data-ttu-id="86854-137">バルク</span><span class="sxs-lookup"><span data-stu-id="86854-137">Bulk</span></span>|<span data-ttu-id="86854-138">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="86854-138">CAT:BULK</span></span>|[<span data-ttu-id="86854-139">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="86854-139">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="86854-140">7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86854-140">7<sup>\*</sup></span></span>|<span data-ttu-id="86854-141">ドメイン偽装 (保護されたユーザー)</span><span class="sxs-lookup"><span data-stu-id="86854-141">Domain impersonation (protected users)</span></span>|<span data-ttu-id="86854-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="86854-142">DIMP</span></span>|[<span data-ttu-id="86854-143">ATP フィッシング詐欺対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="86854-143">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="86854-144">8<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="86854-144">8<sup>\*</sup></span></span>|<span data-ttu-id="86854-145">ユーザー偽装 (保護されたドメイン)</span><span class="sxs-lookup"><span data-stu-id="86854-145">User impersonation (protected domains)</span></span>|<span data-ttu-id="86854-146">UIMP</span><span class="sxs-lookup"><span data-stu-id="86854-146">UIMP</span></span>|[<span data-ttu-id="86854-147">ATP フィッシング詐欺対策ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="86854-147">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |

  <span data-ttu-id="86854-148"><sup>\*</sup> これらの機能は、ATP フィッシング対策ポリシーでのみ使用可能です。</span><span class="sxs-lookup"><span data-stu-id="86854-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="86854-149">**ポリシーの優先度**: 各保護の種類 (スパム対策、マルウェア対策、フィッシング対策など) ごとに、すべてのユーザーに適用される既定のポリシーが用意されていますが、特定のユーザーに適用されるカスタム ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="86854-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="86854-150">各カスタム ポリシーには、ポリシーの適用順序を決定する優先順位の値があります。</span><span class="sxs-lookup"><span data-stu-id="86854-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="86854-151">既定のポリシーは、常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="86854-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="86854-152">ユーザーが同じ種類の複数のポリシーで定義されている場合は、最も優先度の高いポリシーのみがポリシーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="86854-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="86854-153">その種類の残りのポリシーはユーザーには評価されません (既定のポリシーを含む)。</span><span class="sxs-lookup"><span data-stu-id="86854-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="86854-154">たとえば、同じユーザーに適用される次の ATP フィ**that apply to the same users**ッシング対策ポリシーと、ユーザー偽装およびスプーフィングとして識別されるメッセージについて検討します。</span><span class="sxs-lookup"><span data-stu-id="86854-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="86854-155">ATP フィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="86854-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="86854-156">優先度</span><span class="sxs-lookup"><span data-stu-id="86854-156">Priority</span></span>|<span data-ttu-id="86854-157">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="86854-157">User impersonation</span></span>|<span data-ttu-id="86854-158">スプーフィング対策</span><span class="sxs-lookup"><span data-stu-id="86854-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="86854-159">ポリシー A</span><span class="sxs-lookup"><span data-stu-id="86854-159">Policy A</span></span>|<span data-ttu-id="86854-160">1 </span><span class="sxs-lookup"><span data-stu-id="86854-160">1</span></span>|<span data-ttu-id="86854-161">オン</span><span class="sxs-lookup"><span data-stu-id="86854-161">On</span></span>|<span data-ttu-id="86854-162">オフ</span><span class="sxs-lookup"><span data-stu-id="86854-162">Off</span></span>|
  |<span data-ttu-id="86854-163">ポリシー B</span><span class="sxs-lookup"><span data-stu-id="86854-163">Policy B</span></span>|<span data-ttu-id="86854-164">2 </span><span class="sxs-lookup"><span data-stu-id="86854-164">2</span></span>|<span data-ttu-id="86854-165">オフ</span><span class="sxs-lookup"><span data-stu-id="86854-165">Off</span></span>|<span data-ttu-id="86854-166">オン</span><span class="sxs-lookup"><span data-stu-id="86854-166">On</span></span>|
  |

1. <span data-ttu-id="86854-167">スプーフィングはユーザー偽装より優先度が高い (4) ため、メッセージはスプーフィングとしてマークおよび処理されます。</span><span class="sxs-lookup"><span data-stu-id="86854-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="86854-168">ポリシー B よりも高い優先順位を持つポリシー A がユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="86854-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="86854-169">ポリシー A の設定に基づいて、ポリシーでスプーフィング対策がオフになっているため、メッセージに対してアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="86854-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="86854-170">ポリシーの処理が停止されるため、ポリシー B はユーザーに一度も適用されません。</span><span class="sxs-lookup"><span data-stu-id="86854-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="86854-171">同じユーザーが、同じ種類の複数のカスタム ポリシーに意図的または意図的に含まれている可能性があるため、カスタム ポリシーに関しては以下の設計ガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="86854-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="86854-172">割り当てる優先度を割り当てるには、ユーザーの数を小さくし、多数のユーザーに適用するポリシーには低い優先度を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="86854-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="86854-173">既定のポリシーは常に最後に適用されますので注意してください。</span><span class="sxs-lookup"><span data-stu-id="86854-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="86854-174">優先度の高いポリシーを、優先度の低いポリシーよりも厳密かつ特殊な設定を設定する構成。</span><span class="sxs-lookup"><span data-stu-id="86854-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="86854-175">より少ないカスタム ポリシーの使用を検討します (より高くてすみ、またはより高い特殊な設定が必要なユーザーに対してのみカスタム ポリシーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="86854-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
