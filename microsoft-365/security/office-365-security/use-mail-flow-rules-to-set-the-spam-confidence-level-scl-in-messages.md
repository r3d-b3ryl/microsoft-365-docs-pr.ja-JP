---
title: メッセージ内の SCL にメールフロールールを使用する
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
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: メールフロールール (トランスポートルール) を作成してメッセージを識別し、Exchange Online Protection でメッセージのスパム信頼レベル (SCL) を設定する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 223e676579c99eca7db641146d3a1b6bd22f9ca2
ms.sourcegitcommit: 1f3101326e8a54b9bda4ba0324eae00fafcf5e7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44405121"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="29f45-103">メールフロールールを使用して、EOP のメッセージでスパム信頼レベル (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="29f45-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

<span data-ttu-id="29f45-104">Exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内のメールボックスを持つ Microsoft 365 組織では、EOP はスパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) を使用して、スパムの受信メッセージをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="29f45-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="29f45-105">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="29f45-106">特定のメッセージをスパムフィルターによってもスキャンされる前に、スパムとしてマークしたり、スパムフィルター処理をスキップするようメッセージをマークしたりするには、メールフロールール (トランスポートルールとも呼ばれます) を作成して、メッセージを識別し、スパム信頼レベル (SCL) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="29f45-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="29f45-107">SCL の詳細については、「 [EOP」の「スパム信頼レベル (scl)](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="29f45-108">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="29f45-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="29f45-109">これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="29f45-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="29f45-110">具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29f45-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="29f45-111">詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="29f45-112">Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="29f45-113">Exchange Online のメールフロールールの詳細については、「[メールフロールール (トランスポートルール) (Exchange online)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="29f45-114">EAC を使用して、メッセージの SCL を設定するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="29f45-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="29f45-115">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="29f45-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="29f45-116">[追加] アイコン**をクリックし**、[ ![ ](../../media/ITPro-EAC-AddIcon.png) **新しいルールの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f45-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="29f45-117">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="29f45-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="29f45-118">[**名前**]: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="29f45-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="29f45-119">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29f45-119">Click **More Options**.</span></span>

   - <span data-ttu-id="29f45-120">[次の**場合、このルールを適用**する]: メッセージを識別する1つまたは複数の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f45-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="29f45-121">詳細については、「 [Exchange Online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="29f45-122">**次の操作を行い**ます。 [**メッセージのプロパティを変更する**] [ \> **スパム信頼レベル (SCL) を設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f45-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="29f45-123">表示される [ **SCL の指定**] ダイアログで、次のいずれかの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="29f45-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="29f45-124">**スパムフィルターをバイパス**する: メッセージはスパムフィルタリングをスキップします。</span><span class="sxs-lookup"><span data-stu-id="29f45-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="29f45-125">メッセージでスパムフィルターをスキップすることについて慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="29f45-126">攻撃者はこの脆弱性を利用して、フィッシングやその他の悪意のあるメッセージを組織に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="29f45-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="29f45-127">メールフロールールには、送信者の電子メールアドレスまたはドメインだけではなく、より多くの情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="29f45-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="29f45-128">詳細については、「 [EOP での安全な送信者リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29f45-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="29f45-129">**0 ~ 4**: メッセージは、スパムフィルタリングを介して送信され、追加の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="29f45-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="29f45-130">**5 または 6**: メッセージは**スパム**としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="29f45-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="29f45-131">スパム対策ポリシーで verdicts**スパム**フィルター処理用に構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="29f45-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="29f45-132">**7 ~ 9**: メッセージは、**信頼度の高いスパム**としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="29f45-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="29f45-133">迷惑メール対策ポリシーで、**高信頼度の高いスパム**フィルター処理に対して構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**] です)。</span><span class="sxs-lookup"><span data-stu-id="29f45-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="29f45-134">ルールに必要な追加のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="29f45-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="29f45-135">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29f45-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="29f45-136">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="29f45-136">How do you know this worked?</span></span>

<span data-ttu-id="29f45-137">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="29f45-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="29f45-138">たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="29f45-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="29f45-139">ただし、**スパム信頼レベル (SCL)** を**9**に設定し、適用されるスパム対策ポリシーに対して**信頼度の高いスパム**アクションがメッセージを迷惑メールフォルダーに移動する場合は、指定された受信者の迷惑メールフォルダーにメッセージを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29f45-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
