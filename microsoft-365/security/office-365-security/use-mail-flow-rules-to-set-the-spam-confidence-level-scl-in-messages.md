---
title: メッセージ内の SCL にメール フロー ルールを使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: メール フロー ルール (トランスポート ルール) を作成してメッセージを特定し、Exchange Online Protection でそのメッセージの Spam Confidence Level (SCL) を設定する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827375"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="0a426-103">メール フロー ルールを使用して、EOP のメッセージの Spam Confidence Level (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="0a426-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

<span data-ttu-id="0a426-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、スパムがないか受信メッセージをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="0a426-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="0a426-105">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a426-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="0a426-106">特定のメッセージがスパム フィルターによってスキャンされる前にスパムとしてマークする、またはスパム フィルター処理を省略してメッセージにマージするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを特定して Spam Confidence Level (SCL) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0a426-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="0a426-107">SCL の詳細については、EOP の [Spam Confidence Level (SCL) を参照してください](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="0a426-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0a426-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0a426-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0a426-109">これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a426-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="0a426-110">特に、組織管理、コンプライアンス管理、**およびレコード**管理の各役割に既定で**Organization Management**割り当てられる **、** トランスポート ルールの**役割を割り**当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a426-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="0a426-111">詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a426-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="0a426-112">Exchange Online の EAC を開くには、「Exchange Online [の Exchange 管理センター」を参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0a426-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="0a426-113">Exchange Online でのメール フロー ルールの詳細については、Exchange Online の「 [メール フロー ルール (トランスポート ルール)」を参照してください。](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="0a426-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="0a426-114">EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="0a426-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="0a426-115">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0a426-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="0a426-116">[追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0a426-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="0a426-117">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="0a426-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="0a426-118">**名前**: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0a426-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="0a426-119">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a426-119">Click **More Options**.</span></span>

   - <span data-ttu-id="0a426-120">**メッセージを識別する条件を**1 つ以上選択した場合に、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="0a426-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="0a426-121">詳細については [、Exchange Online のメール フロー ルールの条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="0a426-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="0a426-122">**次の手順**を **行います。メッセージプロパティを** \> **変更すると、SCL (Spam Confidence Level) が設定されます**。</span><span class="sxs-lookup"><span data-stu-id="0a426-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="0a426-123">表示される **SCL の** 指定ダイアログで、次のいずれかの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="0a426-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="0a426-124">**スパム フィルター処理をバイパス**する: メッセージはスパム フィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="0a426-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="0a426-125">メッセージがスパム フィルタリングをスキップできるのを非常に大きく行ってください。</span><span class="sxs-lookup"><span data-stu-id="0a426-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="0a426-126">攻撃者は、この脆弱性を使用して、フィッシングやその他の悪意のあるメッセージを組織に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0a426-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="0a426-127">メール フロー ルールには、送信者のメール アドレスまたはドメインだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="0a426-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="0a426-128">詳細については、「EOP で差出 [人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0a426-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="0a426-129">**0 ~ 4:** 追加の処理に関してメッセージがスパム フィルタリングによって送信されます。</span><span class="sxs-lookup"><span data-stu-id="0a426-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="0a426-130">**5 または 6:** メッセージはスパムとしてマーク **されます**。</span><span class="sxs-lookup"><span data-stu-id="0a426-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="0a426-131">スパム対策ポリシーでスパム フィルター **の確認に** 構成したアクションが、メッセージに適用されます (既定値は **、メッセージを [迷惑メール フォルダーに移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="0a426-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="0a426-132">**7 ~ 9:** メッセージは高信頼 **スパムとしてマークされます**。</span><span class="sxs-lookup"><span data-stu-id="0a426-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="0a426-133">スパム対策ポリシーで **高** 信頼スパム対策フィルターの確認に構成したアクションが、メッセージに適用されます (既定値は **[迷惑メール フォルダーにメッセージを移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="0a426-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="0a426-134">ルールに必要なその他のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a426-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="0a426-135">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a426-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0a426-136">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0a426-136">How do you know this worked?</span></span>

<span data-ttu-id="0a426-137">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a426-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="0a426-138">たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a426-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="0a426-139">ただし **、SCL (Spam Confidence Level)** を **9**に設定し、該当するスパム対策ポリシーに **対する高信頼** スパム対策アクションがメッセージを迷惑メール フォルダーに移動する場合、メッセージは指定された受信者の迷惑メール フォルダーに送る必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a426-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
