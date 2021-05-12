---
title: 検疫済み電子メール メッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、潜在的に危険なメッセージや望ましくないメッセージを保持する Exchange Online Protection (EOP) の検疫について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a11f5f9e1e730a3b0cc09625ec8e8cb592d869
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333808"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="fa8bd-103">EOP で検疫された電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="fa8bd-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fa8bd-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fa8bd-104">**Applies to**</span></span>
- [<span data-ttu-id="fa8bd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fa8bd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fa8bd-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fa8bd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fa8bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa8bd-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fa8bd-108">Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、潜在的に危険なメッセージや望ましくないメッセージを保持するために検疫を利用できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="fa8bd-109">マルウェア対策ポリシーは、添付ファイルにマルウェアが含まれていると検出された場合、メッセージを自動的に検疫します。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="fa8bd-110">詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="fa8bd-111">既定では、スパム対策はフィッシング メッセージを検疫し、スパムメッセージとバルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="fa8bd-112">ただし、スパム対策ポリシーを作成およびカスタマイズして、スパムメッセージとバルクメール メッセージを検疫することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="fa8bd-113">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="fa8bd-114">ユーザーと管理者の両方が検疫済みメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="fa8bd-115">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="fa8bd-116">マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージは、管理者だけが処理できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="fa8bd-117">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="fa8bd-118">ユーザーは、メッセージがスパム、バルク メール、または (2020 年 4 月現在) フィッシングとして検疫された場合、受信者である検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="fa8bd-119">詳細については、「EOP で検疫済みメッセージをユーザーとして検索して解放する [」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="fa8bd-120">ユーザーが検疫済みフィッシング メッセージを管理しきれなくするために、管理者はスパム対策ポリシーのフィッシングメール フィルターの評決に対して別のアクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="fa8bd-121">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="fa8bd-122">管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="fa8bd-123">検疫の詳細については、「検疫に関するよく寄せられる質問 [」を参照してください](quarantine-faq.yml)。</span><span class="sxs-lookup"><span data-stu-id="fa8bd-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.yml).</span></span>
