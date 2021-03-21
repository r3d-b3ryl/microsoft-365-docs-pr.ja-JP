---
title: メッセージで SCL にメール フロー ルールを使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: メッセージを識別し、Exchange Online Protection でメッセージのスパム信頼レベル (SCL) を設定するメール フロー ルール (トランスポート ルール) を作成する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921134"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="f3748-103">メール フロー ルールを使用して EOP のメッセージのスパム信頼レベル (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="f3748-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3748-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f3748-104">**Applies to**</span></span>
- [<span data-ttu-id="f3748-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3748-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3748-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f3748-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f3748-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3748-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f3748-108">Exchange Online メールボックスのないメールボックスまたはスタンドアロンの Exchange Online Protection (EOP) 組織を持つ Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージをスキャンしてスパムを検出します。</span><span class="sxs-lookup"><span data-stu-id="f3748-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="f3748-109">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3748-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f3748-110">特定のメッセージをスパム フィルターでスキャンする前にスパムとしてマークする場合や、スパム フィルター処理をスキップするメッセージをマークする場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを識別し、スパム信頼レベル (SCL) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f3748-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="f3748-111">SCL の詳細については、「EOP の [スパム信頼レベル (SCL)」を参照してください](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="f3748-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f3748-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f3748-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f3748-113">この記事の手順を実行するには、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3748-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f3748-114">具体的には、既定では、組織の管理、コンプライアンス管理 **(グローバル** 管理者)、レコード管理の役割グループに割り当てられているトランスポート ルールの役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="f3748-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="f3748-115">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f3748-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="f3748-116">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3748-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="f3748-117">スタンドアロン EOP のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3748-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="f3748-118">役割グループ内のメンバーの一覧を変更する EAC を使用する</span><span class="sxs-lookup"><span data-stu-id="f3748-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="f3748-119">Exchange Online で EAC を開く方法については、「Exchange Online [の Exchange 管理センター」を参照してください](/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="f3748-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="f3748-120">スタンドアロン EOP で EAC を開く方法については、「 [スタンドアロン EOP の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="f3748-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f3748-121">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3748-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f3748-122">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3748-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f3748-123">Exchange Online および Exchange Online Protection のメール フロー ルールの詳細については、「Exchange Online のメール フロー [ルール (トランスポート ルール)」を参照してください。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="f3748-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="f3748-124">EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f3748-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="f3748-125">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3748-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f3748-126">[追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルール **の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3748-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="f3748-127">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="f3748-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f3748-128">**名前**: ルールの一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3748-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="f3748-129">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3748-129">Click **More Options**.</span></span>

   - <span data-ttu-id="f3748-130">**[ メッセージを識別する** 1 つ以上の条件を選択する] の場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="f3748-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="f3748-131">詳細については [、「Exchange Online のメール フロー ルールの条件と例外 (述語)」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="f3748-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="f3748-132">**[メッセージのプロパティを** 変更 **する] を選択** \> **して、スパム信頼レベル (SCL) を設定します**。</span><span class="sxs-lookup"><span data-stu-id="f3748-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="f3748-133">表示される **[SCL の指定** ] ダイアログで、次のいずれかの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="f3748-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="f3748-134">**[スパム フィルターのバイパス**] : メッセージはスパム フィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="f3748-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="f3748-135">メッセージでスパム フィルター処理をスキップできるように注意してください。</span><span class="sxs-lookup"><span data-stu-id="f3748-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="f3748-136">攻撃者はこの脆弱性を利用して、フィッシングなどの悪意のあるメッセージを組織に送信できます。</span><span class="sxs-lookup"><span data-stu-id="f3748-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="f3748-137">メール フロー ルールには、送信者の電子メール アドレスまたはドメイン以上の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3748-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="f3748-138">詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f3748-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="f3748-139">**0 ~ 4**: メッセージはスパム フィルターを介して送信され、追加の処理が行います。</span><span class="sxs-lookup"><span data-stu-id="f3748-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="f3748-140">**5 または 6**: メッセージはスパムとしてマーク **されます**。</span><span class="sxs-lookup"><span data-stu-id="f3748-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="f3748-141">スパム対策ポリシーでスパム フィルターの評決に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です**)。</span><span class="sxs-lookup"><span data-stu-id="f3748-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="f3748-142">**7 ~ 9**: メッセージは高信頼スパム **としてマークされます**。</span><span class="sxs-lookup"><span data-stu-id="f3748-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="f3748-143">スパム対策ポリシーで信頼度の高いスパム フィルターの評決を構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動 **する]** です)。</span><span class="sxs-lookup"><span data-stu-id="f3748-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="f3748-144">ルールに必要な追加のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3748-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="f3748-145">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3748-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f3748-146">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="f3748-146">How do you know this worked?</span></span>

<span data-ttu-id="f3748-147">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f3748-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="f3748-148">たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3748-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="f3748-149">ただし、スパム信頼レベル **(SCL)** を **9** に設定し、該当するスパム対策ポリシーの [高信頼スパム] アクションが [迷惑メール] フォルダーにメッセージを移動する場合は、メッセージを指定した受信者の迷惑メール フォルダーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3748-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>