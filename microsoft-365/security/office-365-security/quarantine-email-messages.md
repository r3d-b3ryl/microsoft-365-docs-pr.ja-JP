---
title: 検疫済み電子メールメッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、潜在的な危険または望ましくないメッセージを保持する Exchange Online Protection (EOP) の検疫について知ることができます。
ms.openlocfilehash: 77eea3140fb96faec4fb5a749422c2bd9da85b45
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202473"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="a57a1-103">EOP で検疫された電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="a57a1-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a57a1-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合は、潜在的な危険または望ましくないメッセージを保持するために検疫を利用できます。365</span><span class="sxs-lookup"><span data-stu-id="a57a1-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="a57a1-105">マルウェア対策ポリシーは、マルウェアが含まれて *いる添付ファイル* が見つかった場合に、自動的にメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="a57a1-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="a57a1-106">詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="a57a1-107">既定では、スパム対策ポリシーはフィッシングメッセージを検疫し、スパムおよびバルクメールメッセージをユーザーの迷惑メールフォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="a57a1-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="a57a1-108">ただし、スパムや電子メールメッセージを検疫するスパム対策ポリシーを作成およびカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="a57a1-109">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a57a1-110">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="a57a1-111">管理者は、すべてのユーザーに対してすべての種類の検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="a57a1-112">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを操作できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="a57a1-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a57a1-113">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="a57a1-114">メッセージがスパム、バルクメール、または (2020 年4月の) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを使用して受信することができます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="a57a1-115">詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="a57a1-116">ユーザーが自分で検疫されたフィッシングメッセージを管理できないようにするために、管理者は、スパム対策ポリシーで **フィッシング詐欺メール** フィルター verdict に対して別のアクションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="a57a1-117">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="a57a1-118">管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="a57a1-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="a57a1-119">検疫の詳細については、「検疫に関する [FAQ](quarantine-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a57a1-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
