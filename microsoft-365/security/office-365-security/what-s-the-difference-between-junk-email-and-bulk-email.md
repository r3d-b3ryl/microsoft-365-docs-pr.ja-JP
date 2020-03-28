---
title: 迷惑メールとバルク メールの違い
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: このトピックでは、迷惑メール (スパム) とバルクメールの違い、および Office 365 の関連するコントロールについて説明します。
ms.openlocfilehash: 56e997235a374ee9f56956be96458b46bffcdc21
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033628"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="3450b-103">迷惑メールとバルク メールの違い</span><span class="sxs-lookup"><span data-stu-id="3450b-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="3450b-104">Office 365 exchange online またはスタンドアロン Exchange Online Protection (EOP) のお客様が Exchange online メールボックスを使用していない場合は、「迷惑メールとバルクメールの違いは何ですか」という質問があります。</span><span class="sxs-lookup"><span data-stu-id="3450b-104">Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="3450b-105">このトピックでは、EOP で使用できるコントロールとその違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3450b-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="3450b-106">**迷惑メール**とは、迷惑メールで、未承諾のメッセージ (正しく識別された場合) をいいます。</span><span class="sxs-lookup"><span data-stu-id="3450b-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="3450b-107">既定では、EOP は、送信元の電子メールサーバーの評価に基づいてスパムを拒否します。</span><span class="sxs-lookup"><span data-stu-id="3450b-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="3450b-108">メッセージが送信元 IP 検査に合格した場合は、スパムフィルタリングに送信されます。</span><span class="sxs-lookup"><span data-stu-id="3450b-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="3450b-109">メッセージがスパムフィルター処理によってスパムとして分類されている場合、メッセージは (既定では) 目的の受信者に配信され、その迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="3450b-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="3450b-110">スパムフィルタリング verdicts に対して実行するアクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3450b-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="3450b-111">手順については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3450b-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="3450b-112">スパムフィルター verdict を使用していない場合は、「[レポートメッセージとファイル](report-junk-email-messages-to-microsoft.md)」で説明されているように、スパムとして、または迷惑メールではないと思われるメッセージをいくつかの方法で報告することができます。</span><span class="sxs-lookup"><span data-stu-id="3450b-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="3450b-113">**バルクメール**(_灰色のメール_とも呼ばれます) では、分類がより困難です。</span><span class="sxs-lookup"><span data-stu-id="3450b-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="3450b-114">スパムは常に脅威ですが、バルクメールは1回限りの広告またはマーケティングメッセージであることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="3450b-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="3450b-115">ユーザーによっては、バルクメールメッセージを必要としており (実際には、それらを受信するように故意にサインアップしている)、他のユーザーはバルクメールをスパムと考えています。</span><span class="sxs-lookup"><span data-stu-id="3450b-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="3450b-116">たとえば、一部のユーザーは、Contoso Corporation からの広告メッセージや、サイバーセキュリティに関する今後の会議への招待を受信したいと考えていますが、他のユーザーはこれらの同じメッセージをスパムと考えています。</span><span class="sxs-lookup"><span data-stu-id="3450b-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="3450b-117">バルクメールを識別する方法の詳細については、「 [Office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3450b-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="3450b-118">バルク メールの管理方法</span><span class="sxs-lookup"><span data-stu-id="3450b-118">How to manage bulk email</span></span>

<span data-ttu-id="3450b-119">バルクメールには反力が混在しているため、すべての組織に適用される一般的なガイダンスはありません。</span><span class="sxs-lookup"><span data-stu-id="3450b-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="3450b-120">スパム対策ポリシーには、バルクメールをスパムとして識別するために使用される既定の BCL しきい値があります。</span><span class="sxs-lookup"><span data-stu-id="3450b-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="3450b-121">管理者は、しきい値を増減できます。</span><span class="sxs-lookup"><span data-stu-id="3450b-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="3450b-122">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3450b-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="3450b-123">[Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="3450b-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="3450b-124">EOP スパム対策ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="3450b-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="3450b-125">ユーザーがバルクメールの受信について苦情を受けているのに、EOP でスパムフィルター処理を通過する、よく知られた送信者からのメッセージであるという、見落としやすいもう1つのオプションは、ユーザーが一括メールメッセージの登録解除オプションを確認する必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="3450b-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
