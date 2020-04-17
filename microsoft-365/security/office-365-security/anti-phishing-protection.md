---
title: Office 365 でのフィッシング対策保護
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Office 365 は、既定では、フィッシング攻撃に対するさまざまな保護を提供します。また、Office 365 Advanced Threat Protection (ATP) のその他の機能も利用できます。 このトピックでは、Office 365 でのフィッシング対策のオプションと戦略について学習し、実装するために使用できるオンラインリソースについて説明します。
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537427"
---
# <a name="anti-phishing-protection-in-office-365"></a><span data-ttu-id="3ea78-104">Office 365 でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="3ea78-104">Anti-phishing protection in Office 365</span></span>

<span data-ttu-id="3ea78-105">*フィッシング*正規または信頼された送信者からのメッセージの機密情報を盗もうとする電子メール攻撃。</span><span class="sxs-lookup"><span data-stu-id="3ea78-105">*Phishing* an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="3ea78-106">フィッシングには特定のカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="3ea78-106">There are specific categories of phishing.</span></span> <span data-ttu-id="3ea78-107">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-107">For example:</span></span>

- <span data-ttu-id="3ea78-108">**スピアーフィッシング**は、目的の受信者に特化した、非常に集中的でカスタマイズされたコンテンツを使用します (通常は、攻撃者による受信者の偵察後)。</span><span class="sxs-lookup"><span data-stu-id="3ea78-108">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="3ea78-109">**Whaling**は、組織内のエグゼクティブまたはその他の高価値のターゲットに対して最大の効果を与えるように指示されます。</span><span class="sxs-lookup"><span data-stu-id="3ea78-109">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="3ea78-110">**ビジネスメールの侵害 (BEC)** は、受信者が支払いを承認したり、ファンドを転送したり、顧客データを公開したりするための取り組みで、偽造された信頼できる送信者 (金融責任者、顧客、信頼できるパートナーなど) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-110">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="3ea78-111">データを暗号化し、暗号化を解除するために支払いを要求する**ランサムウェア**は、常にフィッシングメッセージで開始します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-111">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="3ea78-112">フィッシング対策保護は暗号化されたファイルの解読には役立ちませんが、ランサムウェアキャンペーンに関連付けられている最初のフィッシングメッセージを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ea78-112">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="3ea78-113">ランサムウェア攻撃からの回復の詳細については、「 [Office 365 のランサムウェアからの回復](recover-from-ransomware.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-113">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Office 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="3ea78-114">攻撃の複雑さが増すにつれて、熟練したユーザーが高度なフィッシングメッセージを識別することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="3ea78-114">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="3ea78-115">幸いなことに、Exchange Online Protection (EOP) と Office 365 の追加機能により、Advanced Threat Protection (ATP) が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ea78-115">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="3ea78-116">EOP でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="3ea78-116">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="3ea78-117">EOP (つまり、ATP を使用しない Office 365 組織) には、組織をフィッシング脅威から保護するのに役立つ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ea78-117">EOP (that is, Office 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="3ea78-118">**スプーフィングインテリジェンス**: 内部および外部のドメイン内の送信者からのスプーフィングされたメッセージを確認し、それらの送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="3ea78-118">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="3ea78-119">詳細については、「 [Configure スプーフ知能 In Office 365](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-119">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="3ea78-120">**既定のフィッシング対策ポリシー**: スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別を有効または無効にしたり、禁止されたスプーフィング送信者のアクションを指定したり ([迷惑メール] フォルダーまたは検疫に移動) したりします。</span><span class="sxs-lookup"><span data-stu-id="3ea78-120">**Default anti-phishing policy**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="3ea78-121">詳細については、「 [CONFIGURE EOP」の「フィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-121">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="3ea78-122">**暗黙的な電子メール認証**: EOP では、受信電子メールの標準の電子メール認証チェック ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)) を使用して、送信者評価、送信者履歴、受信者履歴、動作分析、その他の高度な手法を使用して偽造された送信者を特定できます。</span><span class="sxs-lookup"><span data-stu-id="3ea78-122">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="3ea78-123">詳細については、「 [Office 365 の電子メール認証](email-validation-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-123">For more information, see [Email authentication in Office 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="3ea78-124">Office 365 ATP の追加のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="3ea78-124">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="3ea78-125">Office 365 ATP には、追加の高度なフィッシング対策機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ea78-125">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="3ea78-126">**ATP のフィッシング対策ポリシー**: 新しいカスタムポリシーを作成し、偽装の設定 (ユーザーとドメインを偽装から保護)、メールボックスインテリジェンスの設定、および詳細なフィッシングしきい値を調整します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-126">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="3ea78-127">詳細については、「 [Office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-127">For more information, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="3ea78-128">フィッシング対策ポリシーと ATP のフィッシング対策ポリシーの相違点の詳細については、「 [Office 365 のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-128">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Office 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="3ea78-129">[**キャンペーンビュー**]: コンピューター学習およびその他のヒューリスティックは、サービスと組織全体に対して、組織的なフィッシング攻撃に関係するメッセージを識別して分析します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-129">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="3ea78-130">詳細については、「[Office 365 ATP のキャンペーン ビュー](campaigns.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-130">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="3ea78-131">**アタックシミュレータ**: 管理者は偽のフィッシングメッセージを作成し、それを教育ツールとして内部ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="3ea78-131">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="3ea78-132">詳細については、「 [Office 365 ATP」の「アタックシミュレータ」](attack-simulator.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ea78-132">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="3ea78-133">その他のフィッシング対策リソース</span><span class="sxs-lookup"><span data-stu-id="3ea78-133">Other anti-phishing resources</span></span>

- <span data-ttu-id="3ea78-134">エンドユーザーの場合:[フィッシング対策やその他の形式のオンライン詐欺から保護](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)します。</span><span class="sxs-lookup"><span data-stu-id="3ea78-134">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546).</span></span>

- <span data-ttu-id="3ea78-135">[Office 365 がフィッシングを防ぐために差出人アドレスを検証する方法](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="3ea78-135">[How Office 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
