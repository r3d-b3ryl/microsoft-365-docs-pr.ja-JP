---
title: メールフロールールを使用して Office 365 でバルクメールをフィルター処理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) のメールフロールールを使用してバルクメールフィルターを適用する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43a10951a24ac76108fb0531f9e2c205c3fc9047
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034976"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="a50af-103">メールフロールールを使用して Office 365 でバルクメールをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a50af-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="a50af-104">Exchange Online または exchange online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Microsoft 365 顧客の場合、EOP はスパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) を使用して、スパムおよびバルクメール (灰色のメール) の受信メッセージをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="a50af-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="a50af-105">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a50af-106">バルクメールをフィルター処理するためのその他のオプションが必要な場合は、メールフロールール (トランスポートルールとも呼ばれる) を作成して、バルクメールでよく見られるテキストパターンや語句を検索し、それらのメッセージをスパムとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a50af-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="a50af-107">バルクメールの詳細については、Office 365 の「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」および「[バルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="a50af-108">このトピックでは、Exchange 管理センター (EAC) と PowerShell (Microsoft 365 お客様向けの Exchange Online PowerShell) でこれらのメールフロールールを作成する方法について説明します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="a50af-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a50af-109">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a50af-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a50af-110">これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a50af-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="a50af-111">具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a50af-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="a50af-112">詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="a50af-113">Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="a50af-114">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a50af-115">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a50af-116">Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="a50af-117">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="a50af-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="a50af-118">Exchange Online のメールフロールールの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="a50af-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="a50af-119">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="a50af-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="a50af-120">この例では、バルクメールを識別するために使用される単語とテキストパターンの一覧は完全ではありません。必要に応じて、エントリを追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="a50af-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="a50af-121">ただし、開始点として適しています。</span><span class="sxs-lookup"><span data-stu-id="a50af-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="a50af-p106">メッセージ内の件名または他のヘッダー フィールドでの単語またはテキスト パターンの検索は、SMTP サーバー間で ASCII テキスト内のバイナリ メッセージ送信に使用された MIME コンテンツ転送エンコーディング方式に基づいてメッセージがデコードされた*後*に行われます。条件または例外を使用して、メッセージ内の件名または他のヘッダー フィールドの未加工 (通常は Base64) のエンコード値を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="a50af-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="a50af-124">次の手順では、組織全体に対してバルクメッセージをスパムとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="a50af-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="a50af-125">ただし、これらのルールを特定の受信者にのみ適用する別の条件を追加することができます。そのため、一部の高度な対象ユーザーに対して積極的にフィルターを適用することができます。ただし、ユーザーの残りの部分 (頻繁に使用するバルクメールを取得する場合) は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a50af-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="a50af-126">EAC を使用して、バルクメールをフィルター処理するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="a50af-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="a50af-127">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="a50af-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a50af-128">[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) **をクリックし**、[**新しいルールの作成**] を選択します。 ![</span><span class="sxs-lookup"><span data-stu-id="a50af-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a50af-129">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="a50af-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a50af-130">[**名前**]: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a50af-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="a50af-131">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-131">Click **More Options**.</span></span>

   - <span data-ttu-id="a50af-132">[次の**場合、このルールを適用**する]: 正規表現 (RegEx) または単語または語句を使用したメッセージのコンテンツを検索するには、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a50af-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="a50af-133">**件名** \>または本文が次の**テキストパターンと一致**する場合: 表示された [**単語または語句の指定**] ダイアログボックスで、次のいずれ](../../media/ITPro-EAC-AddIcon.png)かの値を入力し **、[** ![追加] アイコンをクリックして、すべての値を入力するまで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a50af-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="a50af-134">エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="a50af-135">エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="a50af-136">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="a50af-137">**件名** \>または本文に次**のいずれかの単語が含ま**れている場合: 表示される [**単語または語句の指定**] ダイアログボックスで、次](../../media/ITPro-EAC-AddIcon.png)のいずれかの値を入力し **、[** ![追加] アイコンをクリックして、すべての値を入力するまで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a50af-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="a50af-138">エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="a50af-139">エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="a50af-140">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="a50af-141">**次の操作を行い**ます。 [ \> **メッセージのプロパティを変更する**] [**スパム信頼レベル (SCL) を設定**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a50af-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="a50af-142">表示される [ **SCL の指定**] ダイアログで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a50af-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="a50af-143">メッセージを**スパム**としてマークするには、[ **6**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a50af-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="a50af-144">スパム対策ポリシーで verdicts**スパム**フィルター処理用に構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="a50af-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="a50af-145">メッセージを**高精度のスパム**としてマークするには、[ **9**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a50af-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="a50af-146">迷惑メール対策ポリシーで、**高信頼度の高いスパム**フィルター処理に対して構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**] です)。</span><span class="sxs-lookup"><span data-stu-id="a50af-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="a50af-147">SCL 値の詳細については、「 [Office 365 のスパム信頼レベル (SCL)](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="a50af-148">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a50af-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="a50af-149">PowerShell を使用してバルクメールをフィルター処理するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="a50af-149">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="a50af-150">次の構文を使用して、1つまたは両方のメールフロールール (正規表現と単語の比較) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a50af-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="a50af-151">この例では、メッセージを**スパム**として設定するために、前述したものと同じ正規表現のリストを使用する "バルクメールフィルター-RegEx" という名前の新しいルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a50af-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="a50af-152">この例では、「バルクメールフィルター-単語」という名前の新しいルールを作成して、このトピックの前の部分と同じ単語リストを使用して、メッセージを**高精度のスパム**として設定します。</span><span class="sxs-lookup"><span data-stu-id="a50af-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="a50af-153">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a50af-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a50af-154">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a50af-154">How do you know this worked?</span></span>

<span data-ttu-id="a50af-155">バルクメールをフィルター処理するようにメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a50af-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="a50af-156">EAC で、 \> [**メールフロー** \> **ルール** \> ] に移動し、[**編集]** ![編集](../../media/ITPro-EAC-EditIcon.png)アイコンをクリックして設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a50af-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="a50af-157">PowerShell で、rule \<name\>をルールの名前に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a50af-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="a50af-158">外部アカウントから、語句またはテキストパターンの1つを含む、影響を受ける受信者にテストメッセージを送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="a50af-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
