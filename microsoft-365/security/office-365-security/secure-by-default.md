---
title: Office 365 でセキュリティ保護
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
description: Exchange Online Protection (EOP) の既定のセキュリティ設定の詳細
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8af609b8ed50b0bfacb7d9f5397fab4c4726927
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040546"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="c1b4e-103">Office 365 でセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c1b4e-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c1b4e-104">"既定でセキュリティ保護" は、できる限り安全な既定の設定を定義するために使用される用語です。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="c1b4e-105">ただし、セキュリティと生産性のバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="c1b4e-106">これには、次の間のバランス調整が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-106">This can include balancing across:</span></span>

- <span data-ttu-id="c1b4e-107">**使いやすさ**: 設定がユーザーの生産性を得る方法を取り入れるべきではありません。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="c1b4e-108">**リスク**: セキュリティによって重要なアクティビティがブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="c1b4e-109">**従来の** 設定 : 新しい最新の設定が改善された場合でも、ビジネス上の理由から、古い製品や機能の一部の構成を維持する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="c1b4e-110">Exchange Online にメールボックスがある Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="c1b4e-111">この保護には以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-111">This protection includes:</span></span>

- <span data-ttu-id="c1b4e-112">マルウェアの疑いがあるメールは自動的に検疫され、受信者に通知されます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="c1b4e-113">[「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="c1b4e-114">信頼度の高いフィッシングとして識別された電子メールは、スパム対策ポリシーアクションに従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="c1b4e-115">[「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c1b4e-116">EOP の詳細については [、「Exchange Online Protection の概要」を参照してください](exchange-online-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-116">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="c1b4e-117">Microsoft は既定でお客様のセキュリティを維持したいと考えていますので、一部のテナントのオーバーライドはマルウェアや信頼度の高いフィッシングには適用されません。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="c1b4e-118">これらのオーバーライドには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-118">These overrides include:</span></span>

- <span data-ttu-id="c1b4e-119">許可された送信者リストまたは許可されたドメイン一覧 (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="c1b4e-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="c1b4e-120">Outlook の差出人セーフ リスト</span><span class="sxs-lookup"><span data-stu-id="c1b4e-120">Outlook Safe Senders</span></span>
- <span data-ttu-id="c1b4e-121">IP 許可一覧 (接続フィルター)</span><span class="sxs-lookup"><span data-stu-id="c1b4e-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="c1b4e-122">これらのオーバーライドの詳細については、「差出人セーフ リストの作成 [」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-122">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c1b4e-123">EOP スパム対策ポリシーの信頼度の高いフィッシングメールの検出に関する[迷惑メール フォルダーにメッセージを移動する] アクションを廃止中です。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-123">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="c1b4e-124">信頼度の高いフィッシング メッセージに対してこのアクションを使用するスパム対策ポリシーは、検疫メッセージに **変換されます**。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-124">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="c1b4e-125">信頼 **度の高いフィッシング メッセージに** 対する電子メール アドレスへのリダイレクト アクションは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-125">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="c1b4e-126">既定では、セキュリティ保護はオンまたはオフにできる設定ではありません。ただし、このフィルター処理は、危険なメッセージや不要なメッセージをメールボックスから送信し続ける方法です。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-126">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="c1b4e-127">マルウェアと信頼度の高いフィッシング メッセージは検疫する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-127">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="c1b4e-128">管理者だけが、マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できます。また、そこから Microsoft に誤検知を報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-128">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="c1b4e-129">詳細については [、「EOP で管理者として検疫済みメッセージとファイルを管理する」を参照してください。](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="c1b4e-129">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="c1b4e-130">これを行う理由の詳細</span><span class="sxs-lookup"><span data-stu-id="c1b4e-130">More on why we're doing this</span></span>

<span data-ttu-id="c1b4e-131">既定でセキュリティ保護されているという問題は、構成済みの例外によってメッセージの配信が許可される場合でも、悪意のあるメッセージを知っていた場合と同じアクションをメッセージに対して実行します。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-131">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="c1b4e-132">これは、マルウェアに対して常に使用していたアプローチと同じであり、現在は、この同じ動作を信頼度の高いフィッシング メッセージに拡張しています。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-132">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="c1b4e-133">このデータは、ユーザーが迷惑メール フォルダー内のメッセージ内の悪意のあるリンクをクリックする可能性が検疫の 30 倍高い可能性を示しています。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-133">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="c1b4e-134">また、弊社のデータは、信頼度の高いフィッシング メッセージに対する誤検知率 (良いメッセージが悪いとマークされている) が非常に低いことを示し、管理者は管理者の送信で誤検知を解決できます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-134">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="c1b4e-135">また、スパム対策ポリシーおよび Outlook の差出人セーフ リストの許可された送信者と許可されたドメインリストが広すぎて、良い問題よりも多くの害を引き起こしている、と判断しました。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-135">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="c1b4e-136">言い方をすると、セキュリティ サービスとして、ユーザーが侵害されるのを防ぐために、お客様の代わりに弊社が行動します。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-136">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="c1b4e-137">例外</span><span class="sxs-lookup"><span data-stu-id="c1b4e-137">Exceptions</span></span>

<span data-ttu-id="c1b4e-138">信頼度の高いフィッシング メッセージがフィルター処理をバイパスできる唯一のオーバーライドは、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-138">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c1b4e-139">メール フロー ルールを使用してフィルター処理をバイパスするには、「メール フロー ルールを使用してメッセージの SCL を設定する」 [を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-139">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="c1b4e-140">次のシナリオでは、オーバーライドの使用のみを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-140">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="c1b4e-141">フィッシング シミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-141">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="c1b4e-142">Security/SecOps メールボックス: セキュリティ チームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好と不良の両方)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-142">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="c1b4e-143">その後、Teams は悪意のあるコンテンツが含まれているか確認できます。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-143">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="c1b4e-144">サード パーティ製フィルター: ドメインの MX レコードが 365 を指していない場合、既定ではセキュリティで保護Office適用されません。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-144">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="c1b4e-145">誤検知: 管理者の提出によって Microsoft によってまだ分析されている特定のメッセージを一 [時的に許可したい場合があります](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-145">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="c1b4e-146">すべてのオーバーライドと同様に、これらは一時的なものとしてお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1b4e-146">As with all overrides, it is recommended that they are temporary.</span></span>
