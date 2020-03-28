---
title: 分析のためにメッセージを手動で Microsoft に送信する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'ユーザーは、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することができます。 '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032806"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="6963b-103">分析のためにメッセージを手動で Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6963b-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="6963b-104">Office 365 組織の管理者が Exchange Online メールボックスを使用している場合は、Office 365 セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6963b-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="6963b-105">詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="6963b-106">組織内のユーザーが迷惑メール (スパム) またはフィッシングメッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスがかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6963b-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="6963b-107">より正確になるように、スパムフィルターを常に微調整しています。</span><span class="sxs-lookup"><span data-stu-id="6963b-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="6963b-108">この処理を支援するには、誤検知 (不良としてマークされた良好な電子メール)、誤検知 (無効なメールが許可されている)、および Microsoft に対するフィッシングメッセージを分析用に送信します。</span><span class="sxs-lookup"><span data-stu-id="6963b-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="6963b-109">大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6963b-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="6963b-110">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6963b-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="6963b-111">次の手順を使用して誤検知を報告する代わりに、Outlook および web 上の Outlook (旧称 Outlook Web App) のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6963b-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="6963b-112">このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="6963b-113">スパムまたはフィッシングとして識別されたスパムフィルタリングを通過したメッセージを受信した場合は、そのメッセージを Microsoft スパム分析および Microsoft フィッシング分析チームに適宜送信することができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="6963b-114">アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="6963b-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="6963b-115">次のいずれかの受信者を使用して、新しい空の電子メールメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6963b-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="6963b-116">**迷惑メール**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="6963b-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="6963b-117">**フィッシング**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="6963b-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="6963b-118">迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="6963b-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="6963b-119">これにより、迷惑メールまたはフィッシングメッセージは新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6963b-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="6963b-120">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="6963b-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="6963b-121">新しいメッセージに複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="6963b-122">すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6963b-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="6963b-123">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="6963b-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="6963b-124">添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6963b-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="6963b-125">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="6963b-126">管理者は、スパムとして misidentified されている特定のメッセージをブロックするいくつかの方法を用意しています。</span><span class="sxs-lookup"><span data-stu-id="6963b-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="6963b-127">詳細については、「 [Office 365 でブロックされる送信者のリストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="6963b-128">誤検知を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6963b-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="6963b-129">次の手順を使用して誤検知を報告するのではなく、Outlook および web 上の Outlook のユーザーは Microsoft Outlook 用のレポートメッセージアドインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6963b-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="6963b-130">このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="6963b-131">メッセージが誤ってスパムとして識別された場合は、メッセージを Microsoft スパム分析チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="6963b-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="6963b-132">アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整して、メッセージを通過できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="6963b-133">受信者としての`not_junk@office365.microsoft.com`新しい空の電子メールメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6963b-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="6963b-134">Misidentified メッセージを新しいメッセージにドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="6963b-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="6963b-135">これにより、misidentified メッセージは新しいメッセージの添付ファイルとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="6963b-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="6963b-136">メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしないでください (メッセージヘッダーを検査できるように、元のメッセージが必要です)。</span><span class="sxs-lookup"><span data-stu-id="6963b-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="6963b-137">新しいメッセージに複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="6963b-138">すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="6963b-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="6963b-139">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="6963b-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="6963b-140">添付されたメッセージについては、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="6963b-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="6963b-141">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="6963b-142">管理者は、特定のメッセージがスパムフィルタリングをスキップできるようにするいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6963b-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="6963b-143">詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="6963b-144">Microsoft に報告されたメッセージのコピーを受信するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="6963b-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="6963b-145">このトピックで説明する方法を使用して Microsoft に報告された電子メールメッセージを検索するメールフロールール (トランスポートルールとも呼ばれます) を作成し、これらのレポートされたメッセージのコピーを受信するように Bcc 受信者を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="6963b-146">メールフロールールは、Exchange 管理センター (EAC) および PowerShell (Office 365 お客様の場合は Exchange Online PowerShell) で作成できます。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="6963b-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6963b-147">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6963b-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6963b-148">これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6963b-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="6963b-149">具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6963b-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="6963b-150">詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="6963b-151">Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="6963b-152">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6963b-153">スタンドアロンの Exchange Online Protection の PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6963b-154">Exchange Online およびスタンドアロン EOP のメールフロールールの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="6963b-155">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="6963b-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="6963b-156">Exchange Online のメールフロールールの条件と例外 (述語)</span><span class="sxs-lookup"><span data-stu-id="6963b-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="6963b-157">Exchange Online でのメール フロー ルールの処理</span><span class="sxs-lookup"><span data-stu-id="6963b-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="6963b-158">EAC を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="6963b-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="6963b-159">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6963b-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="6963b-160">[追加] アイコン](../../media/ITPro-EAC-AddIcon.png) **をクリックし**、[**新しいルールの作成**] を選択します。 ![</span><span class="sxs-lookup"><span data-stu-id="6963b-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="6963b-161">**[新しいルール]** のページが開いたら、以下の設定を行ってください:</span><span class="sxs-lookup"><span data-stu-id="6963b-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6963b-162">[**名前**]: わかりやすい一意のルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6963b-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="6963b-163">たとえば、Microsoft に報告される Bcc メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6963b-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="6963b-164">[**その他のオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-164">Click **More Options**.</span></span>

   - <span data-ttu-id="6963b-165">[次の**場合にこのルールを適用**する]:**受信者** \> **のアドレスに次のいずれかの単語が含まれ**ます。表示される [**単語または語句の指定**] ダイアログで、次のいずれかの値を入力し、[ ![追加] アイコン](../../media/ITPro-EAC-AddIcon.png)をクリックして、すべての値を入力するまで繰り返します。 **Add**</span><span class="sxs-lookup"><span data-stu-id="6963b-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="6963b-166">エントリを編集するには、エントリを選択し、 **[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="6963b-167">エントリを削除するには、エントリを選択し、 **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="6963b-168">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="6963b-169">**次の手順を実行**します。 [**受信者** \> **を Bcc ボックスに追加する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6963b-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="6963b-170">表示されるダイアログで、追加する受信者を見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="6963b-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="6963b-171">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="6963b-172">ルールを監査したり、ルールをテストしたり、特定の期間にルールをアクティブ化したり、その他の設定を行ったりするには、追加の選択を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6963b-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="6963b-173">ルールを適用する前に、ルールをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6963b-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="6963b-174">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6963b-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="6963b-175">PowerShell を使用して、報告されたメッセージのコピーを受信するメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="6963b-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="6963b-176">この例では、このトピックで説明する方法を使用して Microsoft に報告された電子メールメッセージを検索し、Bcc 受信者としてユーザー laura@contoso.com および julia@contoso.com を追加する Bcc メッセージという名前の新しいメールフロールールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6963b-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="6963b-177">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6963b-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6963b-178">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6963b-178">How do you know this worked?</span></span>

<span data-ttu-id="6963b-179">レポートされたメッセージのコピーを受信するメールフロールールが構成されていることを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6963b-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="6963b-180">EAC で、 \> [**メールフロー** \> **ルール** \> ] に移動し、[**編集]** ![編集](../../media/ITPro-EAC-EditIcon.png)アイコンをクリックして設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6963b-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="6963b-181">PowerShell で、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6963b-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="6963b-182">テストメッセージをレポート電子メールアドレスのいずれかに送信し、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6963b-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
