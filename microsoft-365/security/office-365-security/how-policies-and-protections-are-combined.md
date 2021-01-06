---
title: メール保護の順序と優先順位
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
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
description: 管理者は、Exchange Online Protection (EOP) の保護のアプリケーションの順序、および保護ポリシーの優先度の値によって適用されるポリシーがどのように決定されるのかについて説明します。
ms.openlocfilehash: a18234344e1100f3b6a03c10e970c8195e53e7df
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760568"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="49957-104">メール保護の順序と優先順位</span><span class="sxs-lookup"><span data-stu-id="49957-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="49957-105">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、受信電子メールに複数の形式の保護のフラグが設定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="49957-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="49957-106">たとえば、すべての Microsoft 365 ユーザーが利用できる EOP の組み込みのフィッシング対策ポリシーや、Office 365 のお客様が Microsoft Defender で利用できるより堅牢なフィッシング対策ポリシーなどです。</span><span class="sxs-lookup"><span data-stu-id="49957-106">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="49957-107">メッセージは、マルウェア、スパム、フィッシングなどの複数の検出スキャンも通過します。このすべてのアクティビティを考えると、どのポリシーが適用されるのかについて、混乱が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49957-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="49957-108">一般に、メッセージに適用されるポリシーは **、CAT (Category)** プロパティの **X-Forefront-Antispam-Report** ヘッダーで識別されます。</span><span class="sxs-lookup"><span data-stu-id="49957-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="49957-109">詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49957-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="49957-110">メッセージに適用されるポリシーを決定する主な要因は 2 種類です。</span><span class="sxs-lookup"><span data-stu-id="49957-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="49957-111">**電子メール保護の種類の優先度**: この順序は構成できません。次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="49957-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="49957-112">Priority</span><span class="sxs-lookup"><span data-stu-id="49957-112">Priority</span></span>|<span data-ttu-id="49957-113">電子メール保護</span><span class="sxs-lookup"><span data-stu-id="49957-113">Email protection</span></span>|<span data-ttu-id="49957-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="49957-114">Category</span></span>|<span data-ttu-id="49957-115">管理する場所</span><span class="sxs-lookup"><span data-stu-id="49957-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="49957-116">1 </span><span class="sxs-lookup"><span data-stu-id="49957-116">1</span></span>|<span data-ttu-id="49957-117">マルウェア</span><span class="sxs-lookup"><span data-stu-id="49957-117">Malware</span></span>|<span data-ttu-id="49957-118">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="49957-118">CAT:MALW</span></span>|[<span data-ttu-id="49957-119">EOP でマルウェア対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="49957-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="49957-120">2 </span><span class="sxs-lookup"><span data-stu-id="49957-120">2</span></span>|<span data-ttu-id="49957-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="49957-121">Phishing</span></span>|<span data-ttu-id="49957-122">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="49957-122">CAT:PHSH</span></span>|[<span data-ttu-id="49957-123">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="49957-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="49957-124">3 </span><span class="sxs-lookup"><span data-stu-id="49957-124">3</span></span>|<span data-ttu-id="49957-125">高確度スパム</span><span class="sxs-lookup"><span data-stu-id="49957-125">High confidence spam</span></span>|<span data-ttu-id="49957-126">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="49957-126">CAT:HSPM</span></span>|[<span data-ttu-id="49957-127">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="49957-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="49957-128">4 </span><span class="sxs-lookup"><span data-stu-id="49957-128">4</span></span>|<span data-ttu-id="49957-129">スプーフィング</span><span class="sxs-lookup"><span data-stu-id="49957-129">Spoofing</span></span>|<span data-ttu-id="49957-130">CAT:SPOOF</span><span class="sxs-lookup"><span data-stu-id="49957-130">CAT:SPOOF</span></span>|[<span data-ttu-id="49957-131">EOP でスプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="49957-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="49957-132">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="49957-132">5<sup>\*</sup></span></span>|<span data-ttu-id="49957-133">ユーザー偽装 (保護されたユーザー)</span><span class="sxs-lookup"><span data-stu-id="49957-133">User impersonation (protected users)</span></span>|<span data-ttu-id="49957-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="49957-134">UIMP</span></span>|[<span data-ttu-id="49957-135">Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="49957-135">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="49957-136">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="49957-136">6<sup>\*</sup></span></span>|<span data-ttu-id="49957-137">ドメイン偽装 (保護されたドメイン)</span><span class="sxs-lookup"><span data-stu-id="49957-137">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="49957-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="49957-138">DIMP</span></span>|[<span data-ttu-id="49957-139">Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="49957-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="49957-140">7 </span><span class="sxs-lookup"><span data-stu-id="49957-140">7</span></span>|<span data-ttu-id="49957-141">スパム</span><span class="sxs-lookup"><span data-stu-id="49957-141">Spam</span></span>|<span data-ttu-id="49957-142">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="49957-142">CAT:SPM</span></span>|[<span data-ttu-id="49957-143">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="49957-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="49957-144">8 </span><span class="sxs-lookup"><span data-stu-id="49957-144">8</span></span>|<span data-ttu-id="49957-145">バルク</span><span class="sxs-lookup"><span data-stu-id="49957-145">Bulk</span></span>|<span data-ttu-id="49957-146">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="49957-146">CAT:BULK</span></span>|[<span data-ttu-id="49957-147">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="49957-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="49957-148"><sup>\*</sup> これらの機能は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="49957-148"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="49957-149">ポリシーの **優先度:** 保護の種類 (スパム対策、マルウェア対策、フィッシング対策など) ごとに、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用されるカスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="49957-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="49957-150">各カスタム ポリシーには、ポリシーの適用順序を決定する優先順位の値があります。</span><span class="sxs-lookup"><span data-stu-id="49957-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="49957-151">既定のポリシーは常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="49957-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="49957-152">ユーザーが同じ種類の複数のポリシーで定義されている場合は、優先度が最も高いポリシーだけがポリシーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="49957-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="49957-153">その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。</span><span class="sxs-lookup"><span data-stu-id="49957-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="49957-154">たとえば、同じユーザーに適用される Office 365 用の Microsoft Defender の次のフィッシング対策ポリシーと、ユーザー偽装とスプーフィングの両方として識別されるメッセージについて考えてみることができます。</span><span class="sxs-lookup"><span data-stu-id="49957-154">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="49957-155">[ポリシー名]</span><span class="sxs-lookup"><span data-stu-id="49957-155">Policy name</span></span>|<span data-ttu-id="49957-156">Priority</span><span class="sxs-lookup"><span data-stu-id="49957-156">Priority</span></span>|<span data-ttu-id="49957-157">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="49957-157">User impersonation</span></span>|<span data-ttu-id="49957-158">スプーフィング対策</span><span class="sxs-lookup"><span data-stu-id="49957-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="49957-159">ポリシー A</span><span class="sxs-lookup"><span data-stu-id="49957-159">Policy A</span></span>|<span data-ttu-id="49957-160">1 </span><span class="sxs-lookup"><span data-stu-id="49957-160">1</span></span>|<span data-ttu-id="49957-161">オン</span><span class="sxs-lookup"><span data-stu-id="49957-161">On</span></span>|<span data-ttu-id="49957-162">オフ</span><span class="sxs-lookup"><span data-stu-id="49957-162">Off</span></span>|
  |<span data-ttu-id="49957-163">ポリシー B</span><span class="sxs-lookup"><span data-stu-id="49957-163">Policy B</span></span>|<span data-ttu-id="49957-164">2 </span><span class="sxs-lookup"><span data-stu-id="49957-164">2</span></span>|<span data-ttu-id="49957-165">オフ</span><span class="sxs-lookup"><span data-stu-id="49957-165">Off</span></span>|<span data-ttu-id="49957-166">オン</span><span class="sxs-lookup"><span data-stu-id="49957-166">On</span></span>|
  |

1. <span data-ttu-id="49957-167">スプーフィングはユーザー偽装 (5) よりも優先度 (4) が高いので、メッセージはスプーフィングとしてマークされ、処理されます。</span><span class="sxs-lookup"><span data-stu-id="49957-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="49957-168">ポリシー A はポリシー B よりも優先度が高いので、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="49957-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="49957-169">ポリシー A の設定に基づいて、スプーフィング対策がポリシーでオフになっているため、メッセージに対してアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="49957-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="49957-170">ポリシー処理が停止し、ポリシー B がユーザーに適用されません。</span><span class="sxs-lookup"><span data-stu-id="49957-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="49957-171">同じユーザーが同じ種類の複数のカスタム ポリシーに意図的または意図せず含まれている可能性があります。カスタム ポリシーの設計ガイドラインは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49957-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="49957-172">少ない数のユーザーに適用するポリシーに高い優先度を割り当て、多数のユーザーに適用するポリシーに低い優先度を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="49957-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="49957-173">既定のポリシーは常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="49957-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="49957-174">優先度の高いポリシーを、優先度の低いポリシーよりも厳密な設定またはより特殊な設定に構成します。</span><span class="sxs-lookup"><span data-stu-id="49957-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="49957-175">使用するカスタム ポリシーの数を少なくする (より厳密な設定またはより特殊な設定を必要とするユーザーに対してだけカスタム ポリシーを使用する) の使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="49957-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
