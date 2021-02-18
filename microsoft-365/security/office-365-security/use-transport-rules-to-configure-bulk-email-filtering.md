---
title: メール フロー ルールを使用してバルク メールをフィルター処理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) でメール フロー ルール (トランスポート ルール) を使用してバルク メール (灰色のメール) を識別およびフィルター処理する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8030d21d414cb38769a6831391262fa3798a8838
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287295"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="c8402-103">メール フロー ルールを使用して EOP でバルク メールをフィルタリングする</span><span class="sxs-lookup"><span data-stu-id="c8402-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c8402-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c8402-104">**Applies to**</span></span>
- [<span data-ttu-id="c8402-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c8402-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c8402-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c8402-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c8402-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8402-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c8402-108">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージでスパムおよびバルク メール (グレー メールとも呼ばれる) をスキャンします。</span><span class="sxs-lookup"><span data-stu-id="c8402-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="c8402-109">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8402-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c8402-110">バルク メールをフィルター処理するその他のオプションが必要な場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、バルク メールでよく見られるテキスト パターンや語句を検索し、それらのメッセージをスパムとしてマークできます。</span><span class="sxs-lookup"><span data-stu-id="c8402-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="c8402-111">バルク メールの詳細については、「 [迷惑](what-s-the-difference-between-junk-email-and-bulk-email.md) メールとバルク メールの違い」と EOP のバルク苦情レベル [(BCL) を参照してください](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="c8402-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="c8402-112">このトピックでは、Exchange 管理センター (EAC) と PowerShell でこれらのメール フロー ルールを作成する方法について説明します (Exchange Online にメールボックスがある Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="c8402-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c8402-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c8402-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c8402-114">この記事の手順を実行する前に、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8402-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="c8402-115">具体的には、既定で組織の管理、コンプライアンス管理 **(グローバル** 管理者)、および **レコード** 管理の役割グループに割り当てられるトランスポート ルールの役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8402-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="c8402-116">詳細については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c8402-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="c8402-117">Exchange Online のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c8402-117">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="c8402-118">スタンドアロン EOP のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c8402-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="c8402-119">EAC を使用して役割グループのメンバーの一覧を変更する</span><span class="sxs-lookup"><span data-stu-id="c8402-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="c8402-120">Exchange Online で EAC を開く方法については [、Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="c8402-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="c8402-121">スタンドアロン EOP で EAC を開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="c8402-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="c8402-122">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8402-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c8402-123">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8402-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c8402-124">Exchange Online およびスタンドアロン EOP のメール フロー ルールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8402-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="c8402-125">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="c8402-125">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c8402-126">Exchange Online のメール フロー ルールでの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="c8402-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c8402-127">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="c8402-127">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="c8402-128">例でバルク メールを識別するために使用される単語とテキスト パターンのリストは完全ではありません。必要に応じてエントリを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="c8402-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="c8402-129">ただし、これらは良い開始点です。</span><span class="sxs-lookup"><span data-stu-id="c8402-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="c8402-p107">メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた *後* に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8402-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="c8402-132">次の手順では、バルク メッセージを組織全体のスパムとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="c8402-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="c8402-133">ただし、別の条件を追加してこれらのルールを特定の受信者にのみ適用することができます。そのため、数名の対象を絞り込むユーザーに対して積極的なフィルター処理を使用できます。一方、他のユーザー (ほとんどがサインアップしたバルク メールを受け取るユーザー) は影響を受け取らない状態です。</span><span class="sxs-lookup"><span data-stu-id="c8402-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="c8402-134">EAC を使用してバルク メールをフィルター処理するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c8402-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="c8402-135">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8402-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c8402-136">[追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8402-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="c8402-137">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="c8402-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c8402-138">**[名前**]: ルールのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8402-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="c8402-139">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8402-139">Click **More Options**.</span></span>

   - <span data-ttu-id="c8402-140">**次のいずれかの** 設定を構成して、正規表現 (RegEx) または単語または語句を使用してメッセージ内のコンテンツを検索する場合に、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="c8402-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="c8402-141">**件名または本文** \>**件名** または本文が次のテキスト パターンと一致する: 表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 ![ ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c8402-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="c8402-142">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c8402-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="c8402-143">エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c8402-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="c8402-144">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8402-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="c8402-145">**件名または本文** \>**件名または** 本文に次のいずれかの単語が含まれています:表示される [単語または語句の指定] ダイアログで、次のいずれかの値を入力し、[追加] アイコンをクリックして、すべての値を入力するまで繰り返します。 ![ ](../../media/ITPro-EAC-AddIcon.png)</span><span class="sxs-lookup"><span data-stu-id="c8402-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="c8402-146">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c8402-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="c8402-147">エントリを削除するには、そのエントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c8402-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="c8402-148">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8402-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="c8402-149">**Do the following**: Select **Modify the message properties** set the spam confidence level \> **(SCL)**.</span><span class="sxs-lookup"><span data-stu-id="c8402-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="c8402-150">表示される **[SCL の** 指定] ダイアログで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c8402-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="c8402-151">メッセージをスパムとしてマーク **するには\*\*\*\*、6 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8402-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="c8402-152">スパム対策ポリシーでスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動]**です**)。</span><span class="sxs-lookup"><span data-stu-id="c8402-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="c8402-153">メッセージを信頼度の **高いスパムとしてマークするには\*\*\*\*、9 を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8402-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="c8402-154">スパム対策ポリシーで信頼度の高いスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動]**です)。**</span><span class="sxs-lookup"><span data-stu-id="c8402-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="c8402-155">SCL 値の詳細については [、EOP の「Spam Confidence Level (SCL)」を参照してください](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c8402-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="c8402-156">完了したら、[保存] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="c8402-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="c8402-157">PowerShell を使用してバルク メールをフィルター処理するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="c8402-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="c8402-158">メール フロー ルール (正規表現と単語) の一方または両方を作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8402-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="c8402-159">この例では、トピックの以前の正規表現の同じリストを使用してメッセージをスパムとして設定する、"バルク メール フィルター - RegEx" という名前の新しいルールを作成 **します**。</span><span class="sxs-lookup"><span data-stu-id="c8402-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="c8402-160">この例では、トピックの前の部分と同じ単語の一覧を使用してメッセージを信頼度の高いスパムとして設定する、"バルク メール フィルター - 単語" という名前の新しいルール **を作成します**。</span><span class="sxs-lookup"><span data-stu-id="c8402-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="c8402-161">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8402-161">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c8402-162">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c8402-162">How do you know this worked?</span></span>

<span data-ttu-id="c8402-163">バルク メールをフィルター処理するようにメール フロー ルールが構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c8402-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="c8402-164">EAC で、メール フロー ルールに **移動** し、ルールを選択して編集アイコンをクリックし、 \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8402-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="c8402-165">PowerShell で、ルールの名前に置き換え、次のコマンドを \<Rule Name\> 実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8402-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="c8402-166">外部アカウントから、影響を受ける受信者に、語句またはテキスト パターンのいずれかを含むテスト メッセージを送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="c8402-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
