---
title: フィッシング対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、フィッシング対策の保護機能について、Exchange Online Protection (EOP) と Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e1539153282f14a13ddd9066350cbcdca2a074a
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029239"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="05503-103">アプリ内のフィッシング対策Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="05503-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="05503-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="05503-104">**Applies to**</span></span>
- [<span data-ttu-id="05503-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="05503-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="05503-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="05503-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="05503-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05503-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="05503-108">*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。</span><span class="sxs-lookup"><span data-stu-id="05503-108">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="05503-109">フィッシングには特定のカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="05503-109">There are specific categories of phishing.</span></span> <span data-ttu-id="05503-110">例:</span><span class="sxs-lookup"><span data-stu-id="05503-110">For example:</span></span>

- <span data-ttu-id="05503-111">**スピアフィッシング** では、対象となる受信者に合わせて特別にカスタマイズされた、フォーカスのあるカスタマイズされたコンテンツを使用します (通常、攻撃者による受信者の偵察後)。</span><span class="sxs-lookup"><span data-stu-id="05503-111">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="05503-112">**捕鯨は** 、組織内の幹部または他の高価値ターゲットに対して、最大限の効果を得る方向に向けられる。</span><span class="sxs-lookup"><span data-stu-id="05503-112">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="05503-113">ビジネス メール侵害 **(BEC)** は、偽造された信頼できる送信者 (財務担当者、顧客、信頼できるパートナーなど) を使用して、受信者をだまして支払いの承認、資金の転送、顧客データの公開を行います。</span><span class="sxs-lookup"><span data-stu-id="05503-113">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span> <span data-ttu-id="05503-114">[このビデオ](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)を見て詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="05503-114">Learn more by watching [this video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).</span></span>

- <span data-ttu-id="05503-115">**データ** を暗号化し、暗号化解除するための支払いを要求するランサムウェアは、ほとんどの場合、フィッシング メッセージから始まります。</span><span class="sxs-lookup"><span data-stu-id="05503-115">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="05503-116">フィッシング対策保護は、暗号化されたファイルの暗号化を解除するのに役立ちますが、ランサムウェア キャンペーンに関連付けられている最初のフィッシング メッセージを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05503-116">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="05503-117">ランサムウェア攻撃からの回復の詳細については、「ランサムウェア攻撃から回復する」を参照[Microsoft 365。](recover-from-ransomware.md)</span><span class="sxs-lookup"><span data-stu-id="05503-117">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="05503-118">攻撃が複雑化する中、訓練を受けたユーザーが高度なフィッシング メッセージを識別することはさらに困難です。</span><span class="sxs-lookup"><span data-stu-id="05503-118">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="05503-119">幸い、Exchange Online Protection (EOP) と Microsoft Defender for microsoft Defender の追加機能Office 365役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05503-119">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="05503-120">EOP のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="05503-120">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="05503-121">EOP (つまり、microsoft Defender Microsoft 365を使用しない組織Office 365) には、フィッシングの脅威から組織を保護するのに役立つ機能が含まれている。</span><span class="sxs-lookup"><span data-stu-id="05503-121">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="05503-122">**スプーフィン** グ インテリジェンス: スプーフィング インテリジェンスインサイトを使用して、外部ドメインおよび内部ドメインからのメッセージで検出されたスプーフィングされた送信者を確認し、検出された送信者を手動で許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="05503-122">**Spoof intelligence**: Use the spoof intelligence insight to review detected spoofed senders in messages from external and internal domains, and manually allow or block those detected senders.</span></span> <span data-ttu-id="05503-123">詳細については、「[EOP でのスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05503-123">For more information, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="05503-124">**EOP** のフィッシング対策ポリシー : スプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者 ID をオンまたはオフにし、ブロックされたスプーフィングされた送信者のアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="05503-124">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders.</span></span> <span data-ttu-id="05503-125">詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="05503-125">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="05503-126">**テナント許可/ブロック リストでなりすましされた送信者を許可またはブロックする**: スプーフィング インテリジェンス分析の判定を上書きすると、なりすましされた送信者は、手動で許可またはブロックするエントリとなり、「テナント許可/ブロックリスト」の **[なりすまし]** タブにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="05503-126">**Allow or block spoofed senders in the Tenant Allow/Block List**: When you override the verdict in the spoof intelligence insight, the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="05503-127">また、スプーフィング インテリジェンスで検出される前に、手動でなりすまし送信者の許可またはブロック エントリを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="05503-127">You can also manually create allow or block entries for spoof senders before they're detected by spoof intelligence.</span></span> <span data-ttu-id="05503-128">詳細については、「[EOP でテナント許可/ブロック リストを管理する](tenant-allow-block-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05503-128">For more information, see [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).</span></span>

- <span data-ttu-id="05503-129">**暗黙的な** 電子メール認証 : EOP は、送信者評価、送信者履歴、受信者の履歴、行動分析などの高度な手法を使用して、受信メール [(SPF、DKIM、](set-up-spf-in-office-365-to-help-prevent-spoofing.md)および [DMARC)](use-dmarc-to-validate-email.md)の標準的な電子メール認証チェックを強化し、偽造された送信者を識別するのに役立ちます。 [](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="05503-129">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="05503-130">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="05503-130">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="05503-131">Microsoft Defender for Office 365 の追加のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="05503-131">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="05503-132">Microsoft Defender for Office 365 には、次のより高度なフィッシング対策機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05503-132">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="05503-133">**microsoft Defender for Office 365** のフィッシング対策ポリシー: 特定のメッセージ送信者と送信者ドメイン、メールボックス インテリジェンス設定、および調整可能な高度なフィッシングしきい値に対する偽装保護設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="05503-133">**Anti-phishing policies in Microsoft Defender for Office 365**: Configure impersonation protection settings for specific message senders and sender domains, mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="05503-134">詳細については[、「Microsoft Defender でフィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md)を構成する」を参照Office 365。</span><span class="sxs-lookup"><span data-stu-id="05503-134">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span> <span data-ttu-id="05503-135">EOP のフィッシング対策ポリシーと Office 365 用 Defender のフィッシング対策ポリシーの違いの詳細については、「Microsoft 365 のフィッシング対策ポリシー」[を参照してください](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="05503-135">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="05503-136">**キャンペーン ビュー**: 機械学習などのヒューリスティックは、サービス全体と組織に対する協調フィッシング攻撃に関連するメッセージを特定して分析します。</span><span class="sxs-lookup"><span data-stu-id="05503-136">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="05503-137">詳細については[、「Microsoft Defender for microsoft Defender のキャンペーン ビュー」を参照Office 365。](campaigns.md)</span><span class="sxs-lookup"><span data-stu-id="05503-137">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="05503-138">**攻撃シミュレーター**: 管理者は、偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="05503-138">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="05503-139">詳細については[、「Attack Simulator in Microsoft Defender for microsoft Defender for Office 365」 を参照してください](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="05503-139">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="05503-140">その他のフィッシング対策リソース</span><span class="sxs-lookup"><span data-stu-id="05503-140">Other anti-phishing resources</span></span>

- <span data-ttu-id="05503-141">エンド ユーザーの場合: フィッシング詐欺などのオンライン詐欺から身 [を守ります](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)。</span><span class="sxs-lookup"><span data-stu-id="05503-141">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="05503-142">[フィッシングMicrosoft 365防止するために From アドレスを](how-office-365-validates-the-from-address.md)検証する方法。</span><span class="sxs-lookup"><span data-stu-id="05503-142">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
