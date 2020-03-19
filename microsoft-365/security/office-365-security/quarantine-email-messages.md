---
title: Office 365 でメール メッセージを検疫する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Office 365 での検疫は、潜在的に危険または不要なメッセージを保持します。 管理者とエンドユーザーは検疫にアクセスできます。
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857311"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="83d59-104">Office 365 での検疫</span><span class="sxs-lookup"><span data-stu-id="83d59-104">Quarantine in Office 365</span></span>

<span data-ttu-id="83d59-105">Exchange Online または exchange online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合、Office 365 をご利用のお客様は、潜在的な危険または不要なメッセージを保持するために検疫を利用できます。</span><span class="sxs-lookup"><span data-stu-id="83d59-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="83d59-106">マルウェア対策ポリシーは、マルウェアが含まれて*いる添付ファイル*が見つかった場合に、自動的にメッセージを検疫します。</span><span class="sxs-lookup"><span data-stu-id="83d59-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="83d59-107">詳細については、「 [Office 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="83d59-108">既定では、スパム対策ポリシーはフィッシングメッセージを検疫し、スパムおよびバルクメールメッセージをユーザーの迷惑メールフォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="83d59-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="83d59-109">ただし、スパムや電子メールメッセージを検疫するスパム対策ポリシーを作成およびカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="83d59-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="83d59-110">詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="83d59-111">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="83d59-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="83d59-112">管理者は、すべてのユーザーに対してすべての種類の検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="83d59-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="83d59-113">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを操作できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="83d59-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="83d59-114">詳細については、「 [Office 365 での管理者としての検疫済みメッセージとファイルの管理](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="83d59-115">メッセージがスパム、バルクメール、または (4 月 2020) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="83d59-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="83d59-116">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="83d59-117">ユーザーが自分で検疫されたフィッシングメッセージを管理できないようにするために、管理者は、スパム対策ポリシーで**フィッシング詐欺メール**フィルター verdict に対して別のアクションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="83d59-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="83d59-118">詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="83d59-119">管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="83d59-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="83d59-120">検疫の詳細については、「検疫に関する[FAQ](quarantine-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83d59-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
