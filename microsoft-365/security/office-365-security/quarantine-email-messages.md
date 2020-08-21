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
description: 管理者は、危害を行う可能性のあるメッセージや望ましくないメッセージを保持する Exchange Online Protection (EOP) の検疫について学習できます。
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826803"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="c14b5-103">EOP の検疫済み電子メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="c14b5-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="c14b5-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、検疫を利用して危害を行う可能性のあるメッセージや望ましくないメッセージを保持できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="c14b5-105">マルウェア対策ポリシーは、マルウェアを含む添付ファイルが見つ *かった場合* 、メッセージを自動的に検疫します。</span><span class="sxs-lookup"><span data-stu-id="c14b5-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="c14b5-106">詳細については [、EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c14b5-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="c14b5-107">既定では、スパム対策ポリシーはフィッシング メッセージを検疫して、スパム メッセージとバルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。</span><span class="sxs-lookup"><span data-stu-id="c14b5-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="c14b5-108">しかし、スパムおよびバルク メール メッセージを検疫するスパム対策ポリシーを作成し、カスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="c14b5-109">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14b5-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c14b5-110">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="c14b5-111">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="c14b5-112">マルウェア、高度フィッシング、メール フロー ルール (別名: トランスポート ルール) の結果として検疫されたメッセージに対してのみ管理者が操作できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c14b5-113">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14b5-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="c14b5-114">メッセージがスパム、バルク メール、(2020 年 4 月の後) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを受信者とし、操作できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="c14b5-115">詳細については、「EOP でユーザーとして [検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c14b5-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="c14b5-116">ユーザーが独自の検疫済みフィッシング メッセージを管理できないようにするために、管理者は、フィッシング **メール** フィルターの詳細に対する別のアクションをスパム対策ポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="c14b5-117">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c14b5-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="c14b5-118">管理者とユーザーは、検疫で誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="c14b5-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="c14b5-119">検疫の詳細については、「検疫 [」FAQ を参照してください](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="c14b5-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
