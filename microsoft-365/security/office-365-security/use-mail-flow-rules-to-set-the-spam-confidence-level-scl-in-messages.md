---
title: メッセージ内の SCL へのメール フロー ルールの使用
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
description: Exchange Online Protection でメッセージを識別し、メッセージの SCL (Spam Confidence Level) を設定するメール フロー ルール (トランスポート ルール) を作成する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287559"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="4f400-103">メール フロー ルールを使用して EOP 内のメッセージの Spam Confidence Level (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="4f400-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4f400-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4f400-104">**Applies to**</span></span>
- [<span data-ttu-id="4f400-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4f400-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4f400-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4f400-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4f400-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f400-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4f400-108">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージにスパムがないかスキャンします。</span><span class="sxs-lookup"><span data-stu-id="4f400-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="4f400-109">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f400-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="4f400-110">特定のメッセージをスパム フィルターでスキャンする前にスパムとしてマークする場合や、スパム フィルター処理をスキップするメッセージをマークする場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを識別し、Spam Confidence Level (SCL) を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4f400-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="4f400-111">SCL の詳細については [、EOP の「Spam Confidence Level (SCL)」を参照してください](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="4f400-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f400-112">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4f400-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4f400-113">この記事の手順を実行する前に、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f400-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="4f400-114">具体的には、既定で組織の管理、コンプライアンス管理 **(グローバル** 管理者)、および **レコード** 管理の役割グループに割り当てられるトランスポート ルールの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="4f400-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="4f400-115">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f400-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="4f400-116">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4f400-116">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="4f400-117">スタンドアロン EOP のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4f400-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="4f400-118">EAC を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="4f400-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="4f400-119">Exchange Online で EAC を開く方法については [、Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="4f400-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="4f400-120">スタンドアロン EOP で EAC を開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="4f400-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4f400-121">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f400-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4f400-122">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f400-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4f400-123">Exchange Online および Exchange Online Protection のメール フロー ルールの詳細については、「Exchange Online のメール フロー ルール[(トランスポート ルール)」を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="4f400-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="4f400-124">EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="4f400-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="4f400-125">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4f400-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4f400-126">[追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4f400-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="4f400-127">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="4f400-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4f400-128">**[名前**]: ルールのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f400-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="4f400-129">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f400-129">Click **More Options**.</span></span>

   - <span data-ttu-id="4f400-130">**次の場合にこのルールを適用** します。メッセージを識別する 1 つ以上の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f400-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="4f400-131">詳細については [、Exchange Online のメール フロー ルールの条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。</span><span class="sxs-lookup"><span data-stu-id="4f400-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="4f400-132">**Do the following**: Select **Modify the message properties** set the spam confidence level \> **(SCL)**.</span><span class="sxs-lookup"><span data-stu-id="4f400-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="4f400-133">表示される **[SCL の** 指定] ダイアログで、次のいずれかの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="4f400-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="4f400-134">**スパム フィルターをバイパス** する : メッセージはスパム フィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="4f400-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="4f400-135">メッセージがスパム フィルタリングをスキップすることを許可することを十分に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4f400-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="4f400-136">攻撃者はこの脆弱性を利用して、フィッシング詐欺などの悪意のあるメッセージを組織に送信できます。</span><span class="sxs-lookup"><span data-stu-id="4f400-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="4f400-137">メール フロー ルールには、送信者の電子メール アドレスまたはドメイン以外の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="4f400-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="4f400-138">詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4f400-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="4f400-139">**0 ~ 4**: メッセージはスパム フィルターを使用して送信され、追加の処理が行されます。</span><span class="sxs-lookup"><span data-stu-id="4f400-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="4f400-140">**5 または 6**: メッセージはスパムとしてマーク **されます**。</span><span class="sxs-lookup"><span data-stu-id="4f400-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="4f400-141">スパム対策ポリシーでスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です**)。</span><span class="sxs-lookup"><span data-stu-id="4f400-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="4f400-142">**7 ~ 9:** メッセージは信頼度の高いスパム **としてマークされます**。</span><span class="sxs-lookup"><span data-stu-id="4f400-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="4f400-143">スパム対策ポリシーで信頼度の高いスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です)。**</span><span class="sxs-lookup"><span data-stu-id="4f400-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="4f400-144">ルールに必要な追加のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f400-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="4f400-145">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f400-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4f400-146">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="4f400-146">How do you know this worked?</span></span>

<span data-ttu-id="4f400-147">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f400-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="4f400-148">たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f400-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="4f400-149">ただし **、Spam Confidence Level (SCL)** を **9** に設定し、適用可能なスパム対策ポリシーの信頼度の高いスパムアクションがメッセージを [迷惑メール] フォルダーに移動する場合、メッセージは指定した受信者の迷惑メール フォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f400-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
