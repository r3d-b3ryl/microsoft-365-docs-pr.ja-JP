---
title: Office 365 で受信拒否リストを作成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 受信拒否リストのオプションには、Outlook の禁止された送信者、スパム対策送信者/ドメイン禁止リスト、IP 禁止一覧、および Exchange メールフロールール (トランスポートルール) が含まれます。
ms.openlocfilehash: 09a90fce31bd1ed9aea8275e2f01cda3ba816b1b
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572333"
---
# <a name="create-block-sender-lists-in-office-365"></a><span data-ttu-id="0e2d9-103">Office 365 で受信拒否リストを作成する</span><span class="sxs-lookup"><span data-stu-id="0e2d9-103">Create block sender lists in Office 365</span></span>

<span data-ttu-id="0e2d9-104">送信者から不要な電子メールをブロックする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-104">Sometimes it's necessary to block unwanted email from senders.</span></span> <span data-ttu-id="0e2d9-105">複数の方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-105">There are several methods available to choose from.</span></span> <span data-ttu-id="0e2d9-106">これらのオプションには、Outlook のブロックされた送信者、スパム対策送信者/ドメインブロックリスト、IP 禁止一覧、および Exchange メールフロールール (トランスポートルールとも呼ばれる) があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-106">These options include Outlook Blocked Senders, Anti-Spam Sender/Domain Block Lists, IP Block Lists, and Exchange mail flow rules (also known as transport rules).</span></span>

> [!NOTE]
> <span data-ttu-id="0e2d9-107">組織のブロックリストは誤検知 (不在着信) に対処するために使用できますが、これらの候補を分析のために Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-107">While organization block lists can be used to address false negatives (missed spam), those candidates should also be submitted to Microsoft for analysis.</span></span> <span data-ttu-id="0e2d9-108">ブロックリストを使用して誤検知を管理すると、管理オーバーヘッドが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-108">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="0e2d9-109">この目的でブロックリストを使用する場合は、「ready」に記載されているように、[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)する記事も残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-109">If you will use a block list for this purpose, you will need to also keep the article for [submitting spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), at the ready.</span></span>

<span data-ttu-id="0e2d9-110">受信拒否リストを構成する適切な方法は、影響の範囲によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-110">The proper method to configure blocked sender lists varies depending on the scope of the impact.</span></span> <span data-ttu-id="0e2d9-111">単一のユーザーに影響を与える場合、適切なソリューションは、Outlook のブロックされた送信者を使用することもできますが、複数のユーザーまたはすべてのユーザーが影響を受ける場合は、他のいずれかのオプションの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-111">For single user impact, the right solution could be to use Outlook Blocked Senders, but if multiple users or all users are being impacted, one of the other options would be more appropriate.</span></span>

## <a name="options-from-least-to-broadest-scope"></a><span data-ttu-id="0e2d9-112">少なくとも最も広範なスコープからのオプション</span><span class="sxs-lookup"><span data-stu-id="0e2d9-112">Options from least to broadest scope</span></span>

<span data-ttu-id="0e2d9-113">ブロックリストを作成する際には、影響の範囲 (影響を受けるユーザーの数) に基づいて適切な方法を選択することが重要です。これにより、ブロックメソッドの幅広さに一致するようになります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-113">When creating a Block list it's important to pick the appropriate method based on the scope of the impact (how many people will be impacted), so that it matches the breadth of the blocking method.</span></span> <span data-ttu-id="0e2d9-114">次に示すオプションは、範囲と幅の両方でランク付けされます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-114">The options listed below are ranked by both scope and breadth.</span></span> <span data-ttu-id="0e2d9-115">リストは狭い範囲から広くなりますが、詳細については、 *「詳細*」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

- <span data-ttu-id="0e2d9-116">Outlook のブロックされた送信者</span><span class="sxs-lookup"><span data-stu-id="0e2d9-116">Outlook Blocked Senders</span></span>
- <span data-ttu-id="0e2d9-117">スパム対策ポリシー: 送信者/ドメインブロックリスト</span><span class="sxs-lookup"><span data-stu-id="0e2d9-117">Anti-Spam policy: Sender/Domain Block lists</span></span>
- <span data-ttu-id="0e2d9-118">Exchange メールフロールール</span><span class="sxs-lookup"><span data-stu-id="0e2d9-118">Exchange mail flow rules</span></span>
- <span data-ttu-id="0e2d9-119">スパム対策ポリシー: IP 禁止一覧</span><span class="sxs-lookup"><span data-stu-id="0e2d9-119">Anti-Spam policy: IP Block Lists</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="0e2d9-120">Outlook の受信拒否リストを使用する</span><span class="sxs-lookup"><span data-stu-id="0e2d9-120">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="0e2d9-121">影響を受けるユーザーの数が少ない場合、Outlook がブロックされた送信者が使用されるのは、送信されたメールにのみ影響するからです。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-121">When only a small number of users are impacted, that's when Outlook Blocked Senders should be used, because this will only impact mail being sent to them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e2d9-122">不要なメッセージがよく知られ認識可能なソースからのニュースレターである場合は、電子メールからの登録を中止して、ユーザーが今後メールを受信できないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-122">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from getting the emails in the future.</span></span>

<span data-ttu-id="0e2d9-123">この設定手順は、 [outlook on the web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)と[outlook クライアント](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)で異なります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-123">The steps to set this up are different between [Outlook on the web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) and the [Outlook client](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span> <span data-ttu-id="0e2d9-124">受信拒否が原因でメッセージが正常にブロックされると、メッセージがブロックされていることを示す " **fv: BLK" というメッセージがスパム対策に表示され**ます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-124">**When messages are successfully blocked due to Blocked Senders you will see SFV:BLK in the X-Forefront-Antispam-Report** which indicates that the message is being blocked.</span></span>

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a><span data-ttu-id="0e2d9-125">スパム対策ポリシーの送信者/ドメインブロックリストを使用する</span><span class="sxs-lookup"><span data-stu-id="0e2d9-125">Use Anti-Spam Policy Sender/Domain Block lists</span></span>

<span data-ttu-id="0e2d9-126">複数のユーザーが影響を受けている場合、範囲は広くなり、会社全体の送信者/ドメインブロックリストのスパム対策ポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-126">When multiple users are being impacted, the scope is wider, and you need to use a company-wide sender/domain block list Anti-Spam policy.</span></span> <span data-ttu-id="0e2d9-127">詳細な手順については、「[スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-127">The detailed steps can be found in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="0e2d9-128">このメソッドによってブロックされるメッセージはすべて、ポリシーに構成されたスパムアクションに従います。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-128">Any messages blocked through this method will follow the spam action as configured in the policy.</span></span>

<span data-ttu-id="0e2d9-129">これらのリストの最大数は、約1000エントリです。ただし、ポータルには30個のエントリしか入力できません。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-129">The maximum limit for these lists is approximately 1000 entries; although, you will only be able to enter 30 entries into the portal.</span></span> <span data-ttu-id="0e2d9-130">30個を超えるエントリを追加するには、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-130">You must use PowerShell to add more than 30 entries.</span></span>

## <a name="use-exchange-mail-flow-rules-specific-senders"></a><span data-ttu-id="0e2d9-131">Exchange メールフロールール固有の送信者を使用する</span><span class="sxs-lookup"><span data-stu-id="0e2d9-131">Use Exchange mail flow rules specific senders</span></span>

<span data-ttu-id="0e2d9-132">特定のユーザーまたは組織全体でメッセージが送信されないようにブロックする必要がある場合は、メールフロールールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-132">If you need to block messages from being sent to specific users or across the entire organization, you can use mail flow rules.</span></span> <span data-ttu-id="0e2d9-133">メールフロールールは、送信者の電子メールアドレスやドメインだけでなく、メッセージ内の重要な語句やその他のプロパティをトリガーすることができるため、より柔軟になります。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-133">Mail flow rules are more flexible because they can trigger off the sender Email Address or Domain as well as key words and other properties  in the message.</span></span> <span data-ttu-id="0e2d9-134">この柔軟性により、部分的なブロックを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-134">This flexibility will let you create partial- to complete blocks.</span></span> <span data-ttu-id="0e2d9-135">メールフロールールの詳細については、「[メールフロールールを使用したメッセージでの SCL の設定](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-135">For more information about mail flow rules, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e2d9-136">非常にアグレッシブなルールを作成する*のは簡単*です。その結果、使用されている条件が可能な限り固有であることが重要です。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-136">It's easy to create rules that are *overly* aggressive, as a result it's important the criteria being used is as specific as possible.</span></span> <span data-ttu-id="0e2d9-137">また、作成したルールの監査を有効にし、テストを行って、すべてが期待どおりに動作することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-137">Also, be sure that you enable auditing on the rule you create and do testing to ensure everything works as expected.</span></span>

## <a name="use-anti-spam-policy-ip-block-lists"></a><span data-ttu-id="0e2d9-138">スパム対策ポリシーの IP 禁止一覧を使用する</span><span class="sxs-lookup"><span data-stu-id="0e2d9-138">Use Anti-Spam Policy IP Block lists</span></span>

<span data-ttu-id="0e2d9-139">他のオプションのいずれかを使用して*送信者をブロック*することができない場合は、スパム対策ポリシー IP 禁止一覧を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-139">When it's not possible to use one of the other options to block a sender, *then* you can use the Anti-Spam Policy IP Block List.</span></span> <span data-ttu-id="0e2d9-140">詳細については、「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-140">For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> <span data-ttu-id="0e2d9-141">ブロックされている ip の数を最小限に抑えることが重要なので、IP アドレス範囲全体をブロックすることはお勧めし*ません*。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-141">It's important to keep the number of blocked IPs to a minimum, so blocking entire IP address ranges is *not* recommended.</span></span>

<span data-ttu-id="0e2d9-142">*特*に、コンシューマーサービスまたは共有インフラストラクチャに属する ip アドレス範囲の追加を避ける必要があります。また、通常のメンテナンスの一環として、許可された ip アドレスの一覧を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-142">You should *especially* avoid adding IP address ranges that belong to consumer services or shared infrastructures, and also ensure that you review the list of allowed IP addresses as part of regular maintenance.</span></span> <span data-ttu-id="0e2d9-143">**が許可されているため、エントリは攻撃のためにルートを開くことができるので、このリストを詳細に管理して、不要になった許可エントリを定期的に削除する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="0e2d9-143">**Because allows-entries can open up routes for attack, you must closely manage this list and regularly remove the allows-entries that are no longer needed.**</span></span> <span data-ttu-id="0e2d9-144">また、差出人セーフリストを許可する場合は、「 *[Office 365 で安全な送信者のリストを作成](create-safe-sender-lists-in-office-365.md)* する」のリスクと注意事項を必ず読んで理解してください。</span><span class="sxs-lookup"><span data-stu-id="0e2d9-144">Also, if you will make allows in a Safe-Sender list be sure to read and understand the risks and precautions in *[Create Safe-Sender lists in Office 365](create-safe-sender-lists-in-office-365.md)*.</span></span>
