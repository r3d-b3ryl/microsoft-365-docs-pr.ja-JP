---
title: 迷惑 &apos; メールとバルク メールの違いは何ですか?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、迷惑メール (スパム) とバルク メール (グレー メール) の違いについて、電子メール (EOP) Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206975"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="1ff37-103">EOP での迷惑メールとバルク メールの違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="1ff37-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ff37-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1ff37-104">**Applies to**</span></span>
- [<span data-ttu-id="1ff37-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ff37-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ff37-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1ff37-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ff37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ff37-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1ff37-108">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、顧客は「迷惑メールとバルク メールの違いは何ですか」と尋ねる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ff37-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="1ff37-109">このトピックでは、その違いと、EOP で使用できるコントロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1ff37-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="1ff37-110">**迷惑メール** はスパムです。これは、迷惑なメッセージで、普遍的に必要とされないメッセージ (正常に識別される) です。</span><span class="sxs-lookup"><span data-stu-id="1ff37-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="1ff37-111">既定では、EOP は、ソースメールサーバーの評価に基づいてスパムを拒否します。</span><span class="sxs-lookup"><span data-stu-id="1ff37-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="1ff37-112">メッセージが送信元 IP の検査を通過した場合は、スパムフィルタリングに送信されます。</span><span class="sxs-lookup"><span data-stu-id="1ff37-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="1ff37-113">迷惑メールフィルターによってメッセージがスパムとして分類された場合、メッセージは (既定では) 対象の受信者に配信されて、[迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ff37-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="1ff37-114">迷惑メールフィルター の判定を実行するアクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ff37-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="1ff37-115">手順については [、「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ff37-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="1ff37-116">また、スパム分類の判定に同意できない場合は、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」に記載されているように、いくつかの方法でスパムまたは非スパムであると思われるメッセージを Microsoft に報告することができます。</span><span class="sxs-lookup"><span data-stu-id="1ff37-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="1ff37-117">**バルクメール** (_グレーメール_ としても知られています) は、もう少し分類が困難です。</span><span class="sxs-lookup"><span data-stu-id="1ff37-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="1ff37-118">迷惑メールは常に脅威であるのに対し、多くの場合、バルクメールは1回限りの広告、またはマーケティングメッセージです。</span><span class="sxs-lookup"><span data-stu-id="1ff37-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="1ff37-119">バルクメールメッセージを必要としている (実際に、あえてサインアップしてバルクメールを受信する）ユーザもいます。一方、バルクメールをスパムだと感じるユーザもいます。</span><span class="sxs-lookup"><span data-stu-id="1ff37-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="1ff37-120">たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはこれらのメッセージをスパムと見なしている場合です。</span><span class="sxs-lookup"><span data-stu-id="1ff37-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="1ff37-121">バルク メールの識別方法の詳細については、「EOP のバルク 苦情レベル [(BCL)」を参照してください](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="1ff37-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="1ff37-122">バルク メールの管理方法</span><span class="sxs-lookup"><span data-stu-id="1ff37-122">How to manage bulk email</span></span>

<span data-ttu-id="1ff37-123">バルクメールへの反応が多様であるため、すべての組織に適用される汎用的なガイダンスはありません。</span><span class="sxs-lookup"><span data-stu-id="1ff37-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="1ff37-124">スパム対策ポリシーには、バルクメールを迷惑メールとして識別するために使用される既定の BCL しきい値があります。</span><span class="sxs-lookup"><span data-stu-id="1ff37-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="1ff37-125">管理者はしきい値を増減できます。</span><span class="sxs-lookup"><span data-stu-id="1ff37-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="1ff37-126">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ff37-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="1ff37-127">[EOP でスパム対策ポリシーを構成します](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1ff37-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1ff37-128">「[EOP のスパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」</span><span class="sxs-lookup"><span data-stu-id="1ff37-128">[EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span></span>

<span data-ttu-id="1ff37-129">見落としがちなもう１つの対策オプションとして、ユーザーがバルクメールを受信することについて苦情をしていても、スパムフィルタリングを通過する信頼できる送信者からのメッセージを EOP にしている場合は、ユーザーはバルクメールのメッセージに配信停止オプションがあるかどうかを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1ff37-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
