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
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) および Microsoft Defender for Office 365 のフィッシング対策保護機能について学ぶことができます。
ms.openlocfilehash: 5b175a252f95c62a40348a78e694628ee58488bd
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614993"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a><span data-ttu-id="b0793-103">Microsoft 365 でのフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="b0793-103">Anti-phishing protection in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b0793-104">*フィッシング* は、正当または信頼された送信者から送られたように見えるメッセージで、機密情報を盗もうとする電子メール攻撃です。</span><span class="sxs-lookup"><span data-stu-id="b0793-104">*Phishing* is an email attack that tries to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b0793-105">フィッシングには特定のカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="b0793-105">There are specific categories of phishing.</span></span> <span data-ttu-id="b0793-106">例:</span><span class="sxs-lookup"><span data-stu-id="b0793-106">For example:</span></span>

- <span data-ttu-id="b0793-107">**スピアーフィッシング** は、対象の受信者に特化した、優先されるカスタマイズされたコンテンツを使用します (通常は、受信者が攻撃者による偵察後に行います)。</span><span class="sxs-lookup"><span data-stu-id="b0793-107">**Spear phishing** uses focused, customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="b0793-108">**Whaling** は、組織内のエグゼクティブまたはその他の高価値のターゲットに対して最大の効果を与えるように指示されます。</span><span class="sxs-lookup"><span data-stu-id="b0793-108">**Whaling** is directed at executives or other high value targets within an organization for maximum effect.</span></span>

- <span data-ttu-id="b0793-109">**ビジネスメールの侵害 (BEC)** は、偽造された信頼できる送信者 (金融責任者、顧客、信頼できるパートナーなど) を使用して、顧客に対して支払いの承認、預金の移管、顧客データの開示を行います。</span><span class="sxs-lookup"><span data-stu-id="b0793-109">**Business email compromise (BEC)** uses forged trusted senders (financial officers, customers, trusted partners, etc.) to trick recipients into approving payments, transferring funds, or revealing customer data.</span></span>

- <span data-ttu-id="b0793-110">データを暗号化し、暗号化を解除するために支払いを要求する **ランサムウェア** は、常にフィッシングメッセージで開始します。</span><span class="sxs-lookup"><span data-stu-id="b0793-110">**Ransomware** that encrypts your data and demands payment to decrypt it almost always starts out in phishing messages.</span></span> <span data-ttu-id="b0793-111">フィッシング対策保護は暗号化されたファイルの解読には役立ちませんが、ランサムウェアキャンペーンに関連付けられている最初のフィッシングメッセージを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b0793-111">Anti-phishing protection can't help you decrypt encrypted files, but it can help detect the initial phishing messages that are associated with the ransomware campaign.</span></span> <span data-ttu-id="b0793-112">ランサムウェア攻撃からの回復の詳細については、「 [Microsoft 365 のランサムウェアからの回復](recover-from-ransomware.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-112">For more information about recovering from a ransomware attack, see [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).</span></span>

<span data-ttu-id="b0793-113">攻撃の複雑さが増すにつれて、熟練したユーザーが高度なフィッシングメッセージを識別することが困難になります。</span><span class="sxs-lookup"><span data-stu-id="b0793-113">With the growing complexity of attacks, it's even difficult for trained users to identify sophisticated phishing messages.</span></span> <span data-ttu-id="b0793-114">幸いなことに、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 の追加機能は役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="b0793-114">Fortunately, Exchange Online Protection (EOP) and the additional features in Microsoft Defender for Office 365 can help.</span></span>

## <a name="anti-phishing-protection-in-eop"></a><span data-ttu-id="b0793-115">EOP のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="b0793-115">Anti-phishing protection in EOP</span></span>

<span data-ttu-id="b0793-116">EOP (つまり、microsoft Defender for Office 365 を使用しない Microsoft 365 組織) には、組織をフィッシング脅威から保護するのに役立つ機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0793-116">EOP (that is, Microsoft 365 organizations without Microsoft Defender for Office 365) contains features that can help protect your organization from phishing threats:</span></span>

- <span data-ttu-id="b0793-117">**スプーフィング インテリジェンス**: 内部および外部ドメインの送信者からのスプーフィングされたメッセージを確認し、その送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="b0793-117">**Spoof intelligence**: Review spoofed messages from senders in internal and external domains, and allow or block those senders.</span></span> <span data-ttu-id="b0793-118">詳細については、「 [Configure スプーフ知能 IN EOP」](learn-about-spoof-intelligence.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-118">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="b0793-119">**EOP のフィッシング対策ポリシー**: スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別を有効または無効にしたり、ブロックされた送信者に対するアクションを指定したりします ([迷惑メール] フォルダーまたは検疫に移動)。</span><span class="sxs-lookup"><span data-stu-id="b0793-119">**Anti-phishing policies in EOP**: Turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and specify the action for blocked spoofed senders (move to Junk Email folder or quarantine).</span></span> <span data-ttu-id="b0793-120">詳細については、「 [CONFIGURE EOP」の「フィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-120">For more information, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="b0793-121">**暗黙的な電子メール認証**: EOP では、受信電子メールの標準の電子メール認証チェック ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、 [DMARC](use-dmarc-to-validate-email.md)) を使用して、送信者評価、送信者履歴、受信者履歴、動作分析、その他の高度な手法を使用して偽造された送信者を特定できます。</span><span class="sxs-lookup"><span data-stu-id="b0793-121">**Implicit email authentication**: EOP enhances standard email authentication checks for inbound email ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)) with sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques to help identify forged senders.</span></span> <span data-ttu-id="b0793-122">詳細については、「[Microsoft 365 でのメール認証](email-validation-and-authentication.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0793-122">For more information, see [Email authentication in Microsoft 365](email-validation-and-authentication.md).</span></span>

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b0793-123">Microsoft Defender for Office 365 のその他のフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="b0793-123">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b0793-124">Microsoft Defender for Office 365 には、追加の高度なフィッシング対策機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0793-124">Microsoft Defender for Office 365 contains additional and more advanced anti-phishing features:</span></span>

- <span data-ttu-id="b0793-125">**Microsoft Defender For Office 365 のフィッシング対策ポリシー**: 新しいカスタムポリシーを作成し、偽装設定 (ユーザーおよびドメインを偽装から保護)、メールボックスインテリジェンス設定、および調整可能な高度なフィッシングしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="b0793-125">**Anti-phishing policies in Microsoft Defender for Office 365**: Create new custom policies, configure anti-impersonation settings (protect users and domains from impersonation), mailbox intelligence settings, and adjustable advanced phishing thresholds.</span></span> <span data-ttu-id="b0793-126">詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-126">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span> <span data-ttu-id="b0793-127">Office 365 の Defender での EOP とフィッシング詐欺対策ポリシーの相違点の詳細については、「 [Microsoft 365 のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-127">For more information about the differences between anti-phishing policies in EOP and anti-phishing policies in Defender for Office 365, see [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="b0793-128">[**キャンペーンビュー**]: コンピューター学習およびその他のヒューリスティックは、サービスと組織全体に対して、組織的なフィッシング攻撃に関係するメッセージを識別して分析します。</span><span class="sxs-lookup"><span data-stu-id="b0793-128">**Campaign Views**: Machine learning and other heuristics identify and analyze messages that are involved in coordinated phishing attacks against the entire service and your organization.</span></span> <span data-ttu-id="b0793-129">詳細については、「 [Microsoft Defender For Office 365](campaigns.md)」の「キャンペーンビュー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-129">For more information, see [Campaign Views in Microsoft Defender for Office 365](campaigns.md).</span></span>

- <span data-ttu-id="b0793-130">**アタックシミュレータ**: 管理者は偽のフィッシングメッセージを作成し、それを教育ツールとして内部ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="b0793-130">**Attack simulator**: Admins can create fake phishing messages and send them to internal users as an education tool.</span></span> <span data-ttu-id="b0793-131">詳細については、「 [Microsoft Defender For Office 365](attack-simulator.md)」の「アタックシミュレータ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0793-131">For more information, see [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="other-anti-phishing-resources"></a><span data-ttu-id="b0793-132">その他のフィッシング対策リソース</span><span class="sxs-lookup"><span data-stu-id="b0793-132">Other anti-phishing resources</span></span>

- <span data-ttu-id="b0793-133">エンドユーザーの場合: [フィッシング対策やその他の形式のオンライン詐欺から保護](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)します。</span><span class="sxs-lookup"><span data-stu-id="b0793-133">For end users: [Protect yourself from phishing schemes and other forms of online fraud](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).</span></span>

- <span data-ttu-id="b0793-134">[Microsoft 365 がフィッシングを防ぐために差出人アドレスを検証する方法](how-office-365-validates-the-from-address.md)。</span><span class="sxs-lookup"><span data-stu-id="b0793-134">[How Microsoft 365 validates the From address to prevent phishing](how-office-365-validates-the-from-address.md).</span></span>
