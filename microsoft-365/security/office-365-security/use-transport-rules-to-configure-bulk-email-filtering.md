---
title: メール フロー ルールを使用してバルク メールをフィルター処理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、メール フロー ルール (トランスポート ルール) を使用して Exchange Online Protection (EOP) でバルク メールを識別してフィルター処理する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfe841d3e80efc50d6ffbc702faefa1c9a971b13
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826755"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="5e9b0-103">メール フロー ルールを使用して EOP でバルク メールをフィルタリングする</span><span class="sxs-lookup"><span data-stu-id="5e9b0-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="5e9b0-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、スパムまたはバルク メール (グレー メールとしても知られています) の受信メッセージをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="5e9b0-105">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5e9b0-106">バルク メールをフィルター処理する他のオプションを使用する場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、バルク メールでよく見られるテキスト パターンや語句を検索し、それらのメッセージにスパムのマークを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="5e9b0-107">バルク メールの詳細については、迷惑メールとバルク メールの違 [い](what-s-the-difference-between-junk-email-and-bulk-email.md) 、および EOP のバルク メール [(BCL) の違いを参照してください](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="5e9b0-108">このトピックでは、Exchange 管理センター (EAC) および PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用 Exchange Online PowerShell; Exchange Online メールボックスを使用している組織用のスタンドアロン EOP PowerShell) でこれらのメール フロー ルールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5e9b0-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5e9b0-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5e9b0-110">これらの手順を実行する場合は、あかじにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="5e9b0-111">Exchange Online では、Exchange Online の機能アクセス許可の「メール [フロー」エントリを参照してください](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="5e9b0-112">スタンドアロン EOP では、トランスポート ルールの役割が必要です。この役割は、既定で OrganizationManagement、ComplianceManagement、および RecordsManagement の役割に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="5e9b0-113">詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="5e9b0-114">Exchange Online の EAC を開くには、「Exchange Online [の Exchange 管理センター」を参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="5e9b0-115">スタンドアロン EOP の EAC を開くには、「スタンドアロン EOP [の Exchange 管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5e9b0-116">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5e9b0-117">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5e9b0-118">Exchange Online でのメール フロー ルールとスタンドアロン EOP のメール フロー ルールの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="5e9b0-119">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="5e9b0-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="5e9b0-120">Exchange Online のメール フロー ルールでの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="5e9b0-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="5e9b0-121">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="5e9b0-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="5e9b0-122">例のバルク メールを識別するための単語とテキスト パターンのリストは、すべてが拡張的ではありません。必要に応じて、エントリの追加や削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="5e9b0-123">それでも、それらは出点として優れており、どうならいかもしれないわけです。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="5e9b0-p107">メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた*後*に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="5e9b0-126">以下の手順では、バルク メッセージを組織全体のスパムとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="5e9b0-127">ただし、別の条件を追加することでこれらのルールを特定の受信者にのみ適用できるため、少数の高い対象ユーザーに集中的なフィルター処理を使用できます。それに対しては、他のユーザー (受信するもののほとんどが登録したバルク メール) には影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="5e9b0-128">EAC を使用してバルク メールをフィルター処理するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="5e9b0-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="5e9b0-129">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="5e9b0-130">[追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="5e9b0-131">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="5e9b0-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="5e9b0-132">**名前**: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="5e9b0-133">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-133">Click **More Options**.</span></span>

   - <span data-ttu-id="5e9b0-134">**正規表現**(RegEx) または単語または語句を使用してメッセージ内のコンテンツを検索するには、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="5e9b0-135">**件名または本文** \>**次のテキスト パターンと一致する**件名または本文。表示**される [単語または語句を**指定してください] ダイアログで、次の値のいずれかを入力して [**追加** ![ ] アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="5e9b0-136">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="5e9b0-137">エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="5e9b0-138">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="5e9b0-139">**件名または本文** \>**件名または本文に次の単語のいずれかを含めます**。表示される [単語または語**句**の指定] ダイアログで、次の値のいずれかを入力して [**追加]** ![ アイコンをクリック ](../../media/ITPro-EAC-AddIcon.png) し、すべての値を入力するまで繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="5e9b0-140">エントリを編集するには、エントリを選択し、[編集] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-EditIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="5e9b0-141">エントリを削除するには、エントリを選択し、[削除] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-DeleteIcon.png) 。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="5e9b0-142">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="5e9b0-143">**次の手順**を **行います。メッセージプロパティを** \> **変更すると、SCL (Spam Confidence Level) が設定されます**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="5e9b0-144">表示される **SCL の** 指定ダイアログで、以下のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="5e9b0-145">メッセージをスパムとしてマーク **するには、6**を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="5e9b0-146">スパム対策ポリシーでスパム フィルター **の確認について** 構成したアクションは、メッセージに適用されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="5e9b0-147">メッセージに高信頼 **スパムのマークを付け、9** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="5e9b0-148">スパム対策ポリシーで **高** 精度スパム対策フィルターの確認に構成したアクションが、そのメッセージに適用されます (既定値は **[迷惑メール フォルダーにメッセージを移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="5e9b0-149">SCL 値の詳細については、EOP の [Spam Confidence Level (SCL) を参照してください](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="5e9b0-150">完了したら、[保存] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="5e9b0-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="5e9b0-151">PowerShell を使用してバルク メールをフィルター処理するメール フロー ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="5e9b0-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="5e9b0-152">次の構文を使用して、1 つまたは両方のメール フロー ルール (正規表現と単語) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="5e9b0-153">この例では、メッセージをスパムとして設定するために、このトピックで前述した正規表現の同じリストを使用する「Bulk email filtering - RegEx」という名前の新しいルールを **作成します**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="5e9b0-154">この例では、メッセージを「高信頼スパム」として設定するために、このトピックで前述した単語のリストと同じものを使用する「バルク メール フィルター - 語 **句」という名前の新しいルールを作成します**。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="5e9b0-155">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5e9b0-156">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5e9b0-156">How do you know this worked?</span></span>

<span data-ttu-id="5e9b0-157">バルク メールをフィルター処理するようにメール フロー ルールが構成されていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="5e9b0-158">EAC で、[メール フロー ルール]**に移動し** \> **Rules** \> 、[編集] アイコン \> をクリック**Edit** ![ して ](../../media/ITPro-EAC-EditIcon.png) 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="5e9b0-159">PowerShell で、ルールの \<Rule Name\> 名前を置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="5e9b0-160">外部アカウントから、影響を受ける受信者にテスト メッセージ (語句またはテキスト パターンのいずれか 1 つを含む) を送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e9b0-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
