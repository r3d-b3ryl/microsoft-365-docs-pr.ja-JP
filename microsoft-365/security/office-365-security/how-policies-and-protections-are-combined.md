---
title: 電子メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、Microsoft 365 Defender ポータル、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の保護のアプリケーションの順序と、保護ポリシーの優先度の値によって適用されるポリシーがどのように決定されるのかについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9dea01324e37a56fbff049e4e46cd5882f1fabad
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409130"
---
# <a name="order-and-precedence-of-email-protection"></a><span data-ttu-id="1b26b-104">電子メール保護の順序と優先順位</span><span class="sxs-lookup"><span data-stu-id="1b26b-104">Order and precedence of email protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1b26b-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1b26b-105">**Applies to**</span></span>
- [<span data-ttu-id="1b26b-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1b26b-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1b26b-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1b26b-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1b26b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b26b-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1b26b-109">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、受信メールに複数の形式の保護のフラグが設定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b26b-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email may be flagged by multiple forms of protection.</span></span> <span data-ttu-id="1b26b-110">たとえば、すべての Microsoft 365 のお客様が利用できる EOP の組み込みのフィッシング対策ポリシー、および Office 365 のお客様に対して Microsoft Defender が利用できるより堅牢なフィッシング対策ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="1b26b-110">For example, the built-in anti-phishing policies in EOP that are available to all Microsoft 365 customers, and the more robust anti-phishing policies that are available to Microsoft Defender for Office 365 customers.</span></span> <span data-ttu-id="1b26b-111">メッセージは、マルウェア、スパム、フィッシングなどの複数の検出スキャンも通過します。このすべてのアクティビティを考えると、どのポリシーが適用されるのかという混乱が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b26b-111">Messages also pass through multiple detection scans for malware, spam, phishing, etc. Given all this activity, there may be some confusion as to which policy is applied.</span></span>

<span data-ttu-id="1b26b-112">一般に、メッセージに適用されるポリシーは **、CAT (Category)** プロパティの **X-Forefront-Antispam-Report** ヘッダーで識別されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-112">In general, a policy that's applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="1b26b-113">詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b26b-113">For more information, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="1b26b-114">メッセージに適用されるポリシーを決定する主な要因は次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="1b26b-114">There are two major factors that determine which policy is applied to a message:</span></span>

- <span data-ttu-id="1b26b-115">**電子メール保護の種類の優先度**: この順序は構成できません。次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="1b26b-115">**The priority of the email protection type**: This order is not configurable, and is described in the following table:</span></span>

  <br>

  ****

  |<span data-ttu-id="1b26b-116">優先度</span><span class="sxs-lookup"><span data-stu-id="1b26b-116">Priority</span></span>|<span data-ttu-id="1b26b-117">電子メールの保護</span><span class="sxs-lookup"><span data-stu-id="1b26b-117">Email protection</span></span>|<span data-ttu-id="1b26b-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1b26b-118">Category</span></span>|<span data-ttu-id="1b26b-119">管理する場所</span><span class="sxs-lookup"><span data-stu-id="1b26b-119">Where to manage</span></span>|
  |---|---|---|---|
  |<span data-ttu-id="1b26b-120">1</span><span class="sxs-lookup"><span data-stu-id="1b26b-120">1</span></span>|<span data-ttu-id="1b26b-121">マルウェア</span><span class="sxs-lookup"><span data-stu-id="1b26b-121">Malware</span></span>|<span data-ttu-id="1b26b-122">CAT:MALW</span><span class="sxs-lookup"><span data-stu-id="1b26b-122">CAT:MALW</span></span>|[<span data-ttu-id="1b26b-123">EOP でマルウェア対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="1b26b-123">Configure anti-malware policies in EOP</span></span>](configure-anti-malware-policies.md)|
  |<span data-ttu-id="1b26b-124">2</span><span class="sxs-lookup"><span data-stu-id="1b26b-124">2</span></span>|<span data-ttu-id="1b26b-125">フィッシング</span><span class="sxs-lookup"><span data-stu-id="1b26b-125">Phishing</span></span>|<span data-ttu-id="1b26b-126">CAT:PHSH</span><span class="sxs-lookup"><span data-stu-id="1b26b-126">CAT:PHSH</span></span>|[<span data-ttu-id="1b26b-127">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1b26b-127">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1b26b-128">3</span><span class="sxs-lookup"><span data-stu-id="1b26b-128">3</span></span>|<span data-ttu-id="1b26b-129">高確度スパム</span><span class="sxs-lookup"><span data-stu-id="1b26b-129">High confidence spam</span></span>|<span data-ttu-id="1b26b-130">CAT:HSPM</span><span class="sxs-lookup"><span data-stu-id="1b26b-130">CAT:HSPM</span></span>|[<span data-ttu-id="1b26b-131">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1b26b-131">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1b26b-132">4 </span><span class="sxs-lookup"><span data-stu-id="1b26b-132">4</span></span>|<span data-ttu-id="1b26b-133">スプーフィング</span><span class="sxs-lookup"><span data-stu-id="1b26b-133">Spoofing</span></span>|<span data-ttu-id="1b26b-134">CAT:スプーフィング</span><span class="sxs-lookup"><span data-stu-id="1b26b-134">CAT:SPOOF</span></span>|[<span data-ttu-id="1b26b-135">EOP でのスプーフィング インテリジェンスの分析情報</span><span class="sxs-lookup"><span data-stu-id="1b26b-135">Spoof intelligence insight in EOP</span></span>](learn-about-spoof-intelligence.md)|
  |<span data-ttu-id="1b26b-136">5<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b26b-136">5<sup>\*</sup></span></span>|<span data-ttu-id="1b26b-137">ユーザー偽装 (保護されたユーザー)</span><span class="sxs-lookup"><span data-stu-id="1b26b-137">User impersonation (protected users)</span></span>|<span data-ttu-id="1b26b-138">UIMP</span><span class="sxs-lookup"><span data-stu-id="1b26b-138">UIMP</span></span>|[<span data-ttu-id="1b26b-139">Microsoft Defender でフィッシング対策ポリシーを構成Office 365</span><span class="sxs-lookup"><span data-stu-id="1b26b-139">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-mdo-anti-phishing-policies.md)|
  |<span data-ttu-id="1b26b-140">6<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b26b-140">6<sup>\*</sup></span></span>|<span data-ttu-id="1b26b-141">ドメイン偽装 (保護されたドメイン)</span><span class="sxs-lookup"><span data-stu-id="1b26b-141">Domain impersonation (protected domains)</span></span>|<span data-ttu-id="1b26b-142">DIMP</span><span class="sxs-lookup"><span data-stu-id="1b26b-142">DIMP</span></span>|[<span data-ttu-id="1b26b-143">Microsoft Defender でフィッシング対策ポリシーを構成Office 365</span><span class="sxs-lookup"><span data-stu-id="1b26b-143">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>](configure-mdo-anti-phishing-policies.md)|
  |<span data-ttu-id="1b26b-144">7 </span><span class="sxs-lookup"><span data-stu-id="1b26b-144">7</span></span>|<span data-ttu-id="1b26b-145">スパム</span><span class="sxs-lookup"><span data-stu-id="1b26b-145">Spam</span></span>|<span data-ttu-id="1b26b-146">CAT:SPM</span><span class="sxs-lookup"><span data-stu-id="1b26b-146">CAT:SPM</span></span>|[<span data-ttu-id="1b26b-147">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1b26b-147">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |<span data-ttu-id="1b26b-148">8 </span><span class="sxs-lookup"><span data-stu-id="1b26b-148">8</span></span>|<span data-ttu-id="1b26b-149">バルク</span><span class="sxs-lookup"><span data-stu-id="1b26b-149">Bulk</span></span>|<span data-ttu-id="1b26b-150">CAT:BULK</span><span class="sxs-lookup"><span data-stu-id="1b26b-150">CAT:BULK</span></span>|[<span data-ttu-id="1b26b-151">EOP でのスパム対策ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1b26b-151">Configure anti-spam policies in EOP</span></span>](configure-your-spam-filter-policies.md)|
  |

  <span data-ttu-id="1b26b-152"><sup>\*</sup>これらの機能は、Microsoft Defender のフィッシング対策ポリシーでのみOffice 365。</span><span class="sxs-lookup"><span data-stu-id="1b26b-152"><sup>\*</sup> These features are only available in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="1b26b-153">**ポリシー** の優先度 : ポリシーの種類 (スパム対策、マルウェア対策、フィッシング対策など) ごとに、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用されるカスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-153">**The priority of the policy**: For each type of policy (anti-spam, anti-malware, anti-phishing, etc.), there's a default policy that applies to everyone, but you can create custom policies that apply to specific users.</span></span> <span data-ttu-id="1b26b-154">各カスタム ポリシーには、ポリシーが適用される順序を決定する優先度の値があります。</span><span class="sxs-lookup"><span data-stu-id="1b26b-154">Each custom policy has a priority value that determines the order that the policies are applied in.</span></span> <span data-ttu-id="1b26b-155">既定のポリシーは常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-155">The default policy is always applied last.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1b26b-156">ユーザーが同じ種類の複数のポリシーで定義されている場合、優先度が最も高いポリシーだけが適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-156">If a user is defined in multiple policies of the same type, only the policy with the highest priority is applied to them.</span></span> <span data-ttu-id="1b26b-157">その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。</span><span class="sxs-lookup"><span data-stu-id="1b26b-157">Any remaining policies of that type are not evaluated for the user (including the default policy).</span></span>

<span data-ttu-id="1b26b-158">たとえば、同じユーザーに適用される Office 365 の Microsoft Defender の次のフィッシング対策ポリシーと、ユーザー偽装とスプーフィングの両方として識別されるメッセージを検討します。</span><span class="sxs-lookup"><span data-stu-id="1b26b-158">For example, consider the following anti-phishing policies in Microsoft Defender for Office 365 **that apply to the same users**, and a message that's identified as both user impersonation and spoofing:</span></span>

<br>

****

|<span data-ttu-id="1b26b-159">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="1b26b-159">Policy name</span></span>|<span data-ttu-id="1b26b-160">優先度</span><span class="sxs-lookup"><span data-stu-id="1b26b-160">Priority</span></span>|<span data-ttu-id="1b26b-161">ユーザー偽装</span><span class="sxs-lookup"><span data-stu-id="1b26b-161">User impersonation</span></span>|<span data-ttu-id="1b26b-162">スプーフィング対策</span><span class="sxs-lookup"><span data-stu-id="1b26b-162">Anti-spoofing</span></span>|
|---|---|---|---|
|<span data-ttu-id="1b26b-163">ポリシー A</span><span class="sxs-lookup"><span data-stu-id="1b26b-163">Policy A</span></span>|<span data-ttu-id="1b26b-164">1</span><span class="sxs-lookup"><span data-stu-id="1b26b-164">1</span></span>|<span data-ttu-id="1b26b-165">オン</span><span class="sxs-lookup"><span data-stu-id="1b26b-165">On</span></span>|<span data-ttu-id="1b26b-166">オフ</span><span class="sxs-lookup"><span data-stu-id="1b26b-166">Off</span></span>|
|<span data-ttu-id="1b26b-167">ポリシー B</span><span class="sxs-lookup"><span data-stu-id="1b26b-167">Policy B</span></span>|<span data-ttu-id="1b26b-168">2</span><span class="sxs-lookup"><span data-stu-id="1b26b-168">2</span></span>|<span data-ttu-id="1b26b-169">オフ</span><span class="sxs-lookup"><span data-stu-id="1b26b-169">Off</span></span>|<span data-ttu-id="1b26b-170">オン</span><span class="sxs-lookup"><span data-stu-id="1b26b-170">On</span></span>|
|

1. <span data-ttu-id="1b26b-171">スプーフィングの優先度がユーザー偽装 (5) よりも高い (4) ため、メッセージはスプーフィングとしてマークされ、処理されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-171">The message is marked and treated as spoof, because spoofing has a higher priority (4) than user impersonation (5).</span></span>
2. <span data-ttu-id="1b26b-172">ポリシー A はポリシー B よりも優先度が高いので、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-172">Policy A is applied to the users because it has a higher priority than Policy B.</span></span>
3. <span data-ttu-id="1b26b-173">ポリシー A の設定に基づいて、ポリシーでスプーフィング対策がオフになっているため、メッセージに対してアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1b26b-173">Based on the settings in Policy A, no action is taken on the message, because anti-spoofing is turned off in the policy.</span></span>
4. <span data-ttu-id="1b26b-174">ポリシー処理が停止し、ポリシー B はユーザーに適用されません。</span><span class="sxs-lookup"><span data-stu-id="1b26b-174">Policy processing stops, so Policy B is never applied to the users.</span></span>

<span data-ttu-id="1b26b-175">同じユーザーが意図的または意図せずに同じ種類の複数のカスタム ポリシーに含まれている可能性がある場合は、カスタム ポリシーに次の設計ガイドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1b26b-175">Because it's possible that the same users are intentionally or unintentionally included in multiple custom policies of the same type, use the following design guidelines for custom policies:</span></span>

- <span data-ttu-id="1b26b-176">少人数のユーザーに適用されるポリシーに高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先度を低くします。</span><span class="sxs-lookup"><span data-stu-id="1b26b-176">Assign a higher priority to policies that apply to a small number of users, and a lower priority to policies that apply to a large number of users.</span></span> <span data-ttu-id="1b26b-177">既定のポリシーは常に最後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b26b-177">Remember, the default policy is always applied last.</span></span>
- <span data-ttu-id="1b26b-178">優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密な設定またはより特殊な設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="1b26b-178">Configure your higher priority policies to have stricter or more specialized settings than lower priority policies.</span></span>
- <span data-ttu-id="1b26b-179">使用するカスタム ポリシーの数を少なくします (より厳密な設定またはより特殊な設定が必要なユーザーに対してカスタム ポリシーのみを使用してください)。</span><span class="sxs-lookup"><span data-stu-id="1b26b-179">Consider using fewer custom policies (only use custom policies for users who require stricter or more specialized settings).</span></span>
