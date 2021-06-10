---
title: 既定ではセキュリティで保護Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: セキュリティ保護 (EOP) の既定の設定Exchange Online Protection詳細
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f197556426171b867b49781b38ea5f5116f80aa2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861529"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="e98de-103">既定ではセキュリティで保護Office 365</span><span class="sxs-lookup"><span data-stu-id="e98de-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e98de-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e98de-104">**Applies to**</span></span>
- [<span data-ttu-id="e98de-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e98de-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e98de-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e98de-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e98de-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e98de-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e98de-108">"Secure by default" は、可能な限り最も安全な既定の設定を定義するために使用される用語です。</span><span class="sxs-lookup"><span data-stu-id="e98de-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="e98de-109">ただし、セキュリティと生産性のバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="e98de-110">これには、次の分散が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e98de-110">This can include balancing across:</span></span>

- <span data-ttu-id="e98de-111">**使いやすさ**: 設定の生産性を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="e98de-112">**リスク**: セキュリティが重要なアクティビティをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="e98de-113">**従来の** 設定 : 新しい最新の設定が改善された場合でも、ビジネス上の理由から、古い製品や機能の一部の構成を維持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="e98de-114">Microsoft 365メールボックスを持つ組織は、Exchange Online (EOP) によってExchange Online Protectionされます。</span><span class="sxs-lookup"><span data-stu-id="e98de-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e98de-115">この保護には、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e98de-115">This protection includes:</span></span>

- <span data-ttu-id="e98de-116">マルウェアが疑われるメールは自動的に検疫され、受信者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="e98de-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="e98de-117">[「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e98de-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="e98de-118">信頼度の高いフィッシングと識別された電子メールは、スパム対策ポリシーアクションに従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="e98de-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="e98de-119">[「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e98de-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="e98de-120">EOP の詳細については、「EOP の概要Exchange Online Protection[参照してください](exchange-online-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e98de-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="e98de-121">Microsoft は既定で顧客のセキュリティを維持したいと考えていますので、一部のテナントの上書きはマルウェアや高信頼フィッシングには適用されません。</span><span class="sxs-lookup"><span data-stu-id="e98de-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="e98de-122">これらのオーバーライドには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e98de-122">These overrides include:</span></span>

- <span data-ttu-id="e98de-123">許可された送信者リストまたは許可されたドメイン リスト (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="e98de-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="e98de-124">Outlook セーフ送信者</span><span class="sxs-lookup"><span data-stu-id="e98de-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="e98de-125">IP 許可一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="e98de-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="e98de-126">これらの上書きに関する詳細については、「差出人セーフ リストの作成 [」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e98de-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e98de-127">EOP スパム対策 **ポリシーの** 信頼度の高いフィッシングメールの評決に対して、[メッセージを迷惑メールフォルダーに移動する] アクションは廃止されました。</span><span class="sxs-lookup"><span data-stu-id="e98de-127">We have deprecated the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="e98de-128">信頼度の高いフィッシング メッセージにこのアクションを使用するスパム対策ポリシーは、検疫メッセージに **変換されます**。</span><span class="sxs-lookup"><span data-stu-id="e98de-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="e98de-129">信頼 **度の高いフィッシング メッセージ** の [電子メール アドレスにメッセージをリダイレクトする] アクションは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="e98de-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="e98de-130">既定ではセキュリティで保護は、オンまたはオフにできる設定ではなく、潜在的に危険なメッセージや望ましくないメッセージをメールボックスから守るフィルター処理の仕組みです。</span><span class="sxs-lookup"><span data-stu-id="e98de-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="e98de-131">マルウェアと高信頼のフィッシング メッセージは検疫する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="e98de-132">マルウェアまたは高信頼フィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="e98de-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="e98de-133">詳細については [、「EOP で検疫済みメッセージとファイルを管理者として管理する」を参照してください。](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="e98de-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="e98de-134">これを行う理由の詳細</span><span class="sxs-lookup"><span data-stu-id="e98de-134">More on why we're doing this</span></span>

<span data-ttu-id="e98de-135">既定でセキュリティで保護されるという考え方は、構成された例外がメッセージの配信を許可する場合でも、悪意のあるメッセージを知っていた場合と同じアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e98de-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="e98de-136">これは、マルウェアで常に使用していたのと同じ方法で、この動作を信頼性の高いフィッシング メッセージに拡張しています。</span><span class="sxs-lookup"><span data-stu-id="e98de-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="e98de-137">データは、ユーザーが迷惑メール フォルダー内のメッセージと検疫の悪意のあるリンクをクリックする可能性が 30 倍高い可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="e98de-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="e98de-138">また、信頼度の高いフィッシング メッセージに対する誤検知率 (良いメッセージが悪いとマークされている) が非常に低いことを示し、管理者は管理者の申請で誤検知を解決できます。</span><span class="sxs-lookup"><span data-stu-id="e98de-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="e98de-139">また、Outlook のスパム対策ポリシーと セーフ Senders で許可されている送信者と許可されたドメイン リストが広すぎて、良いよりも害が大きいと判断しました。</span><span class="sxs-lookup"><span data-stu-id="e98de-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="e98de-140">別の言い方をすると、セキュリティ サービスとして、ユーザーが侵害されるのを防ぐために、お客様の代理として行動しています。</span><span class="sxs-lookup"><span data-stu-id="e98de-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="e98de-141">例外</span><span class="sxs-lookup"><span data-stu-id="e98de-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="e98de-142">2021 年 7 月には、既定でセキュリティで保護されたメール フロー Exchange (トランスポート ルールとも呼ばれる) に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="e98de-142">In July 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e98de-143">メール フロー ルールを使用して、サード パーティのフィッシング シミュレーションやセキュリティ操作メールボックスへのフィルター処理されていない配信を許可する場合、最終的には、これらのルールを排除し、[](configure-advanced-delivery.md)機能が利用可能なときに高度な配信ポリシーの使用に切り替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="e98de-144">信頼度の高いフィッシング メッセージがフィルター処理をバイパスできる唯一のオーバーライドは、メール フロー ルールです。</span><span class="sxs-lookup"><span data-stu-id="e98de-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="e98de-145">メール フロー ルールを使用してフィルター処理をバイパスするには、「メール フロー ルールを使用してメッセージに [SCL を設定する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。</span><span class="sxs-lookup"><span data-stu-id="e98de-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="e98de-146">次のシナリオでは、オーバーライドの使用のみを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e98de-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="e98de-147">フィッシング シミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e98de-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="e98de-148">セキュリティ/SecOps メールボックス: フィルター処理されていないメッセージを取得するためにセキュリティ チームが使用する専用のメールボックス (良いメールボックスと悪いメールボックスの両方)。</span><span class="sxs-lookup"><span data-stu-id="e98de-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="e98de-149">Teams、悪意のあるコンテンツが含まれているか確認できます。</span><span class="sxs-lookup"><span data-stu-id="e98de-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="e98de-150">サード パーティ製のフィルター: ドメインの MX レコードがドメインの MX レコードを指していない場合、既定ではセキュリティで保護Office 365。</span><span class="sxs-lookup"><span data-stu-id="e98de-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="e98de-151">誤検知: 管理者の申請を介して Microsoft によって分析されている特定のメッセージを一時的に許可 [する場合があります](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="e98de-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="e98de-152">すべての上書きと同様に、一時的な上書きをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e98de-152">As with all overrides, it is recommended that they are temporary.</span></span>
