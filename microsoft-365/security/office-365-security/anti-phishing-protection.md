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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) および Office 365 Advanced Threat Protection (Office 365 ATP) のフィッシング対策保護機能について学習できます。
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827447"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="1bf9d-103">Microsoft 365 でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="1bf9d-103">Anti-phishing protection in Microsoft 365</span></span>

<span data-ttu-id="1bf9d-104">*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="1bf9d-105">フィッシングには、特定のカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-105">There are specific categories of phishing.</span></span> <span data-ttu-id="1bf9d-106">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-106">For example:</span></span>

- <span data-ttu-id="1bf9d-107">**スピア フィッシングでは、** 特にターゲットとなる受信者にカスタマイズされた (通常は、攻撃者による受信者の再調整後) にカスタマイズした、非常に焦点を置かれてカスタマイズされたコンテンツを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-107">**Spear phishing** uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="1bf9d-108">**Whaling は** 、最大効果をもつ組織内のエグゼクティブまたはその他の価値の高いターゲットに向けられます。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="1bf9d-109">**ビジネス メールが侵害された業者 (BEC)** は、取り組みを取り入れてパートナーを本人が業者に取り入れて、顧客データの承認、行使いの促金を取り入れ、取り入れないように取り組むために取り組む目的で、業務上の信頼できる送信者 (BEC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) in an effort to trick the recipient into approving payments, transferring funds, or disclosing customer data.</span></span>

- <span data-ttu-id="1bf9d-110">**ほとんどの場合、データを暗号化** し支払いを要求するランスパンダウェアは、ほとんどの場合、フィッシング メッセージで開始します。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="1bf9d-111">フィッシング対策保護は、暗号化されたファイルの暗号化を解除する上では役立ちますが、ランサムウェア キャンペーンに関連付けられている最初のフィッシング メッセージを検出する上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="1bf9d-112">ランムウェア攻撃からの回復の詳細については [、「Microsoft 365 のランスムウェア攻撃からの回復」を参照してください](recover-from-ransomware.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="1bf9d-113">攻撃の複雑さが増すと、トレーニング済みユーザーはさらに複雑なフィッシング メッセージを識別するのは難しいものになります。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="1bf9d-114">Exchange Online Protection (EOP) と Office 365 Advanced Threat Protection (Office 365 ATP) の追加機能が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Office 365 Advanced Threat Protection (Office 365 ATP) can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="1bf9d-115">EOP のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="1bf9d-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="1bf9d-116">EOP (つまり、ATP を使用しない Microsoft 365 組織) には、フィッシングの脅威から組織を保護するために役立つ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-116">EOP (that is, Microsoft 365 organizations without ATP) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="1bf9d-117">**スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="1bf9d-118">詳細については、「EOP でス [プーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="1bf9d-119">**EOP のフィッシング対策**ポリシー: スプーフィング インテリジェンスを有効または無効にし、Outlook で認証されていない送信者識別情報をオンまたはオフにして、スプーフィングされた送信者 ([迷惑メール] フォルダーまたは検疫に移動) のアクションを指定する。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="1bf9d-120">詳細については [、「EOP でフィッシング対策ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="1bf9d-121">**暗黙的なメール認証**: EOP は、送信者評価、送信者履歴、受信者履歴、行きの分析、およびその他の高度な手法を使用して、受信メール (SPF、DKIM、DMARC) の電子メール認証チェックを強化して、偽の送信者を識別します。[SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md) [DMARC](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="1bf9d-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="1bf9d-122">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a><span data-ttu-id="1bf9d-123">Office 365 ATP の追加のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="1bf9d-123">Additional anti-phishing protection in Office 365 ATP</span></span>

<span data-ttu-id="1bf9d-124">Office 365 ATP には、次のより高度なフィッシング対策機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-124">Office 365 ATP contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="1bf9d-125">**ATP フィッシング対策**ポリシー: 新しいカスタム ポリシーを作成、偽装対策設定 (偽装からユーザーとドメインを保護)、メールボックス インテリジェンスの設定、および調整可能な高度なフィッシングしきい値。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-125">**ATP anti-phishing policies**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="1bf9d-126">詳細については [、「Microsoft 365 で ATP フィッシング対策ポリシーを構成する」を参照してください](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-126">For more information, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="1bf9d-127">フィッシング対策ポリシーと ATP フィッシング対策ポリシーの違いの詳細については、Microsoft 365 のフィッシ [ング対策ポリシーを参照してください](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-127">For more information about the differences between anti-phishing policies and ATP anti-phishing policies, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="1bf9d-128">**キャンペーン ビュー**: 機械学習とその他のヒューリスティックは、サービス全体および組織に対する調整されたフィッシング攻撃に関係するメッセージを特定して分析します。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="1bf9d-129">詳細については、「[Office 365 ATP のキャンペーン ビュー](campaigns.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-129">For more information, see [Campaign Views in Office 365 ATP](campaigns.md).</span></span>

- <span data-ttu-id="1bf9d-130">**攻撃シミュレータ**: 管理者は偽のフィッシング メッセージを作成し、教育ツールとして内部ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="1bf9d-131">詳細については [、「Office 365 ATP」の「攻撃シミュレータ」を参照してください](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-131">For more information, see [Attack Simulator in Office 365 ATP](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="1bf9d-132">その他のフィッシング対策リソース</span><span class="sxs-lookup"><span data-stu-id="1bf9d-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="1bf9d-133">エンド ユーザー向け: [フィッシング スキームや](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)オンライン切り取りから自分を保護します。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-133">For end-users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="1bf9d-134">[Microsoft 365 がフィッシングを防止するために From アドレスを検証する方法](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf9d-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
