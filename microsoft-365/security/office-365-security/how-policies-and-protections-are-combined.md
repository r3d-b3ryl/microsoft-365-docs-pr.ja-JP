---
title: 電子メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
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
description: 管理者は、Exchange Online Protection (EOP) での保護の順序、および保護ポリシーの優先度の値によってどのようなポリシーが適用されるかを調べることができます。
ms.openlocfilehash: 6b17a524fb9dfbf5e33604c2ec26a678befc8834
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600287"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="1326e-104">電子メール保護の順序と優先順位</span><span class="sxs-lookup"><span data-stu-id="1326e-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1326e-105">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合、受信電子メールに複数の形式の保護によるフラグが設定されることがあります。365</span><span class="sxs-lookup"><span data-stu-id="1326e-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="1326e-106">たとえば、Microsoft 365 のすべてのユーザーが使用できる組み込みの EOP フィッシング対策ポリシー、および Office 365 Advanced Threat Protection (Office 365 ATP) のお客様が利用できる、より堅牢な ATP のフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="1326e-106">For example, the built-in EOP anti-phishing policies that are available to all Microsoft 365 customers, and the more robust ATP anti-phishing policies that are also available to Office 365 Advanced Threat Protection (Office 365 ATP) customers.</span></span> <span data-ttu-id="1326e-107">メッセージも、マルウェア、スパム、フィッシングなどの複数の検出スキャンを通過します。このアクティビティがすべて与えられた場合、どのポリシーが適用されるかについて混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="1326e-107">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="1326e-108">一般に、メッセージに適用されるポリシーは、 **CAT (Category)** プロパティの**スパム対策**ヘッダー内で識別されます。</span><span class="sxs-lookup"><span data-stu-id="1326e-108">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="1326e-109">詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1326e-109">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="1326e-110">メッセージに適用されるポリシーを決定する主な要因は2つあります。</span><span class="sxs-lookup"><span data-stu-id="1326e-110">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="1326e-111">**電子メール保護の種類の優先度**: この順序は構成できず、次の表に記載されています。</span><span class="sxs-lookup"><span data-stu-id="1326e-111">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  ****

  |<span data-ttu-id="1326e-112">Priority</span><span class="sxs-lookup"><span data-stu-id="1326e-112">Priority</span></span>|<span data-ttu-id="1326e-113">電子メール保護</span><span class="sxs-lookup"><span data-stu-id="1326e-113">Email protection</span></span>|<span data-ttu-id="1326e-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1326e-114">Category</span></span>|<span data-ttu-id="1326e-115">管理対象</span><span class="sxs-lookup"><span data-stu-id="1326e-115">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="1326e-116">1-d</span><span class="sxs-lookup"><span data-stu-id="1326e-116">1</span></span>|<span data-ttu-id="1326e-117">マルウェア</span><span class="sxs-lookup"><span data-stu-id="1326e-117">Malware</span></span>|<span data-ttu-id="1326e-118">CAT: 男性 W</span><span class="sxs-lookup"><span data-stu-id="1326e-118">CAT:MALW</span></span>|[<span data-ttu-id="1326e-119">EOP でマルウェア対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1326e-119">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="1326e-120">pbm-2</span><span class="sxs-lookup"><span data-stu-id="1326e-120">2</span></span>|<span data-ttu-id="1326e-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="1326e-121">Phishing</span></span>|<span data-ttu-id="1326e-122">CAT: PHSH</span><span class="sxs-lookup"><span data-stu-id="1326e-122">CAT:PHSH</span></span>|[<span data-ttu-id="1326e-123">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1326e-123">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1326e-124">1/3</span><span class="sxs-lookup"><span data-stu-id="1326e-124">3</span></span>|<span data-ttu-id="1326e-125">高確度スパム</span><span class="sxs-lookup"><span data-stu-id="1326e-125">High confidence spam</span></span>|<span data-ttu-id="1326e-126">CAT: HSPM</span><span class="sxs-lookup"><span data-stu-id="1326e-126">CAT:HSPM</span></span>|[<span data-ttu-id="1326e-127">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1326e-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1326e-128">4 </span><span class="sxs-lookup"><span data-stu-id="1326e-128">4</span></span>|<span data-ttu-id="1326e-129">スプーフィング</span><span class="sxs-lookup"><span data-stu-id="1326e-129">Spoofing</span></span>|<span data-ttu-id="1326e-130">CAT: スプーフィング</span><span class="sxs-lookup"><span data-stu-id="1326e-130">CAT:SPOOF</span></span>|[<span data-ttu-id="1326e-131">EOP でスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="1326e-131">Configure spoof intelligence in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="1326e-132">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1326e-132">5<sup>\*</sup></span></span>|<span data-ttu-id="1326e-133">ユーザー偽装 (保護されたドメイン)</span><span class="sxs-lookup"><span data-stu-id="1326e-133">User impersonation (protected domains)</span></span>|<span data-ttu-id="1326e-134">UIMP</span><span class="sxs-lookup"><span data-stu-id="1326e-134">UIMP</span></span>|[<span data-ttu-id="1326e-135">ATP フィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1326e-135">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="1326e-136">シックス<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1326e-136">6<sup>\*</sup></span></span>|<span data-ttu-id="1326e-137">ドメイン偽装 (保護されたユーザー)</span><span class="sxs-lookup"><span data-stu-id="1326e-137">Domain impersonation (protected users)</span></span>|<span data-ttu-id="1326e-138">DIMP</span><span class="sxs-lookup"><span data-stu-id="1326e-138">DIMP</span></span>|[<span data-ttu-id="1326e-139">ATP フィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1326e-139">Configure ATP anti-phishing policies</span></span>](configure-atp-anti-phishing-policies.md)|
  |<span data-ttu-id="1326e-140">7 </span><span class="sxs-lookup"><span data-stu-id="1326e-140">7</span></span>|<span data-ttu-id="1326e-141">スパム</span><span class="sxs-lookup"><span data-stu-id="1326e-141">Spam</span></span>|<span data-ttu-id="1326e-142">CAT: SPM</span><span class="sxs-lookup"><span data-stu-id="1326e-142">CAT:SPM</span></span>|[<span data-ttu-id="1326e-143">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1326e-143">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1326e-144">8 </span><span class="sxs-lookup"><span data-stu-id="1326e-144">8</span></span>|<span data-ttu-id="1326e-145">バルク</span><span class="sxs-lookup"><span data-stu-id="1326e-145">Bulk</span></span>|<span data-ttu-id="1326e-146">CAT: BULK</span><span class="sxs-lookup"><span data-stu-id="1326e-146">CAT:BULK</span></span>|[<span data-ttu-id="1326e-147">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1326e-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="1326e-148"><sup>\*</sup> これらの機能は、ATP のフィッシング対策ポリシーでのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="1326e-148"><sup>\*</sup> These features are only available in ATP anti-phishing policies.</span></span>

- <span data-ttu-id="1326e-149">**ポリシーの優先度**: 各保護の種類 (スパム対策、マルウェア対策、フィッシング詐欺対策など) について、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用するカスタムポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1326e-149">**The priority of the policy**: For each protection type (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="1326e-150">各カスタムポリシーには、ポリシーが適用される順序を決定する優先順位の値があります。</span><span class="sxs-lookup"><span data-stu-id="1326e-150">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="1326e-151">既定のポリシーは常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1326e-151">The default policy is always applied last.</span></span>

  <span data-ttu-id="1326e-152">ユーザーが同じ種類の複数のポリシーで定義されている場合、優先度の高いポリシーのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1326e-152">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="1326e-153">その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。</span><span class="sxs-lookup"><span data-stu-id="1326e-153">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="1326e-154">たとえば、 **同じユーザーに適用される**次の ATP のフィッシング対策ポリシーと、ユーザーの偽装とスプーフィングの両方として識別されるメッセージを考えてみます。</span><span class="sxs-lookup"><span data-stu-id="1326e-154">For example, consider the following ATP anti-phishing policies **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

  ****

  |<span data-ttu-id="1326e-155">ATP のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="1326e-155">ATP anti-phishing policy</span></span>|<span data-ttu-id="1326e-156">Priority</span><span class="sxs-lookup"><span data-stu-id="1326e-156">Priority</span></span>|<span data-ttu-id="1326e-157">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="1326e-157">User impersonation</span></span>|<span data-ttu-id="1326e-158">スプーフィング対策</span><span class="sxs-lookup"><span data-stu-id="1326e-158">Anti-spoofing</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="1326e-159">ポリシー A</span><span class="sxs-lookup"><span data-stu-id="1326e-159">Policy A</span></span>|<span data-ttu-id="1326e-160">1-d</span><span class="sxs-lookup"><span data-stu-id="1326e-160">1</span></span>|<span data-ttu-id="1326e-161">オン</span><span class="sxs-lookup"><span data-stu-id="1326e-161">On</span></span>|<span data-ttu-id="1326e-162">オフ</span><span class="sxs-lookup"><span data-stu-id="1326e-162">Off</span></span>|
  |<span data-ttu-id="1326e-163">ポリシー B</span><span class="sxs-lookup"><span data-stu-id="1326e-163">Policy B</span></span>|<span data-ttu-id="1326e-164">pbm-2</span><span class="sxs-lookup"><span data-stu-id="1326e-164">2</span></span>|<span data-ttu-id="1326e-165">オフ</span><span class="sxs-lookup"><span data-stu-id="1326e-165">Off</span></span>|<span data-ttu-id="1326e-166">オン</span><span class="sxs-lookup"><span data-stu-id="1326e-166">On</span></span>|
  |

1. <span data-ttu-id="1326e-167">スプーフィングは、ユーザー偽装 (8) よりも優先度が高いため、メッセージはスプーフィングとしてマークされ、スプーフィングとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="1326e-167">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (8).</span></span>
2. <span data-ttu-id="1326e-168">ポリシー A は、ポリシー B よりも優先度が高いため、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1326e-168">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="1326e-169">ポリシーでスプーフィング対策がオフになっているため、ポリシー A の設定に基づいて、メッセージに対してアクションは何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="1326e-169">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="1326e-170">ポリシーの処理は停止するため、ポリシー B がユーザーに適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="1326e-170">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="1326e-171">同じユーザーが同じ種類の複数のカスタムポリシーに故意または誤って含まれている可能性があるので、次のようなカスタムポリシーの設計ガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1326e-171">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="1326e-172">少数のユーザーに適用されるポリシーにより高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先順位を低くします。</span><span class="sxs-lookup"><span data-stu-id="1326e-172">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="1326e-173">既定のポリシーは常に最後に適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1326e-173">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="1326e-174">より優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密に特殊化された設定にします。</span><span class="sxs-lookup"><span data-stu-id="1326e-174">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="1326e-175">より少ないカスタムポリシーを使用することを検討してください (厳密な設定を必要とするユーザーにはカスタムポリシーのみを使用します)。</span><span class="sxs-lookup"><span data-stu-id="1326e-175">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
