---
title: 検疫済み電子メールメッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
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
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208284"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="33163-103">EOP で検疫された電子メールメッセージ</span><span class="sxs-lookup"><span data-stu-id="33163-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="33163-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合は、潜在的な危険または望ましくないメッセージを保持するために検疫を利用できます。365</span><span class="sxs-lookup"><span data-stu-id="33163-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="33163-105">マルウェア対策ポリシーは、マルウェアが含まれて*いる添付ファイル*が見つかった場合に、自動的にメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="33163-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="33163-106">詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="33163-107">既定では、スパム対策ポリシーはフィッシングメッセージを検疫し、スパムおよびバルクメールメッセージをユーザーの迷惑メールフォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="33163-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="33163-108">ただし、スパムや電子メールメッセージを検疫するスパム対策ポリシーを作成およびカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="33163-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="33163-109">詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="33163-110">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="33163-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="33163-111">管理者は、すべてのユーザーに対してすべての種類の検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="33163-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="33163-112">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを操作できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="33163-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="33163-113">詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="33163-114">メッセージがスパム、バルクメール、または (2020 年4月の) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを使用して受信することができます。</span><span class="sxs-lookup"><span data-stu-id="33163-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="33163-115">詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="33163-116">ユーザーが自分で検疫されたフィッシングメッセージを管理できないようにするために、管理者は、スパム対策ポリシーで**フィッシング詐欺メール**フィルター verdict に対して別のアクションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="33163-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="33163-117">詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="33163-118">管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="33163-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="33163-119">検疫の詳細については、「検疫に関する[FAQ](quarantine-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33163-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
