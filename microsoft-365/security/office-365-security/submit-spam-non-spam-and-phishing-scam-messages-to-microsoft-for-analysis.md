---
title: スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する
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
ms.openlocfilehash: 6ca4c99d5e8803fdf7f41ff00cc2a5e65ab38049
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238434"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a><span data-ttu-id="1699e-103">スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="1699e-103">Submit spam, non-spam, and phishing scam messages to Microsoft for analysis</span></span>

<span data-ttu-id="1699e-104">組織内のユーザーが迷惑メール (スパム) またはフィッシング詐欺メッセージを受信トレイで受信する場合や、迷惑メールとしてマークされているために正当な電子メールメッセージを受信しない場合は、ストレスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1699e-104">It can be frustrating when users in your organization receive junk messages (spam) or phishing scam messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="1699e-105">より正確になるように、スパムフィルターを常に微調整しています。</span><span class="sxs-lookup"><span data-stu-id="1699e-105">We're constantly fine-tuning our spam filters to be more accurate.</span></span> <span data-ttu-id="1699e-106">この処理は、誤検出および誤検知のスパムメッセージを分析のために Microsoft に送信することによって、ユーザーが支援します。</span><span class="sxs-lookup"><span data-stu-id="1699e-106">You and your users can help this process by submitting false negative and false positive spam messages to Microsoft for analysis.</span></span> <span data-ttu-id="1699e-107">"誤負" は、スパムとして識別されていないものの、スパムメッセージであることを示します。</span><span class="sxs-lookup"><span data-stu-id="1699e-107">A "false negative" is a spam message that should have been but was not identified as spam.</span></span> <span data-ttu-id="1699e-108">"偽陽性" は、誤ってスパムとして識別された正当な電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="1699e-108">A "false positive" is a legitimate email message that was incorrectly identified as spam.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1699e-109">大量の送信が送信されるため、分析のすべての要求に応答できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1699e-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span> 

<span data-ttu-id="1699e-110">管理者は、電子メール、url、添付ファイルをレビュー用に Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="1699e-110">Admins can send email, url, and attachments to Microsoft for review.</span></span> <span data-ttu-id="1699e-111">「 [Office 365 ATP」の「管理者の提出」を](admin-submission.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-111">See [Admin submissions in Office 365 ATP](admin-submission.md).</span></span>
  
## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a><span data-ttu-id="1699e-112">スパム フィルターを通過した迷惑メールまたはフィッシング詐欺メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="1699e-112">Submit junk or phishing messages that passed through the spam filters</span></span>
<span data-ttu-id="1699e-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1699e-113"></span></span>

<span data-ttu-id="1699e-114">スパムフィルターを通過して、迷惑メールまたはフィッシング詐欺メールとして分類されるメッセージを受信した場合は、必要に応じて Microsoft スパム分析チームと Microsoft のフィッシング分析チームに "偽否定的" メッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="1699e-114">If you receive a message that passed through the spam filters that and should be classified as junk or a phishing scam, you can submit the "false negative" message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams, as appropriate.</span></span> <span data-ttu-id="1699e-115">アナリストはメッセージを確認し、分類基準を満たす場合は、サービス全体のフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="1699e-115">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span> 
  
<span data-ttu-id="1699e-116">組織全体に適用されるスパム設定について詳しくは、「[検出漏れ問題を防ぐために Office 365 スパム フィルターで迷惑メールをブロックする](reduce-spam-email.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1699e-116">For more spam settings that apply to the whole organization, see [Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md).</span></span> <span data-ttu-id="1699e-117">この記事には、誤検知を防止するためのヒントが記載されています。</span><span class="sxs-lookup"><span data-stu-id="1699e-117">This article contains tips to help prevent false negatives.</span></span>
  
<span data-ttu-id="1699e-118">迷惑メール メッセージを送信するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1699e-118">You can submit junk email messages in the following ways:</span></span>
  
- <span data-ttu-id="1699e-119">Outlook および web 上の Outlook では、Microsoft Outlook 用のレポートメッセージアドインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1699e-119">For Outlook and Outlook on the web users, use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="1699e-120">このツールをインストールして使用する方法については、「[レポートメッセージアドインを有効](enable-the-report-message-add-in.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-120">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
        
- <span data-ttu-id="1699e-121">次の手順で説明するように、電子メールを使用して、迷惑メールまたはフィッシング詐欺として分類されるメッセージを Microsoft に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1699e-121">You can also use email to submit messages to Microsoft that should be classified as junk or phishing scams, as described in the following procedure.</span></span>
    
### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a><span data-ttu-id="1699e-122">メールを使用して Microsoft に迷惑メール (スパム) またはフィッシング詐欺メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="1699e-122">Use email to submit junk (spam) or phishing scam messages to Microsoft</span></span>
<span data-ttu-id="1699e-123"><a name="Useemailtosubmitjunkspamorphishingscammessages"> </a></span><span class="sxs-lookup"><span data-stu-id="1699e-123"></span></span>

<span data-ttu-id="1699e-124">Microsoft に迷惑メールまたはフィッシング詐欺メッセージを送信するには:</span><span class="sxs-lookup"><span data-stu-id="1699e-124">To submit a junk or phishing scam message to Microsoft:</span></span>
  
1. <span data-ttu-id="1699e-125">空の電子メールメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1699e-125">Create a blank email message.</span></span>
    
2. <span data-ttu-id="1699e-126">次のように、メッセージをレビューする Microsoft チームにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1699e-126">Address the message to the Microsoft team that reviews messages, as follows:</span></span> 
    
  - <span data-ttu-id="1699e-127">迷惑メールメッセージの場合: junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1699e-127">For junk messages: junk@office365.microsoft.com</span></span>
    
  - <span data-ttu-id="1699e-128">フィッシング詐欺メッセージの場合: phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1699e-128">For phishing scam messages: phish@office365.microsoft.com</span></span>
    
3. <span data-ttu-id="1699e-129">迷惑メールまたはフィッシング詐欺メッセージをコピーして、新しいメッセージに添付ファイルとして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1699e-129">Copy and paste the junk or phishing scam message into the new message as an attachment.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="1699e-130">•新しいメッセージに複数のメッセージを添付することができます。</span><span class="sxs-lookup"><span data-stu-id="1699e-130">• You can attach multiple messages in the new message.</span></span> <span data-ttu-id="1699e-131">すべてのメッセージが同じ種類であることを確認してください。フィッシング詐欺メッセージまたは迷惑メールメッセージのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="1699e-131">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span> <br/><br/><span data-ttu-id="1699e-132">•新しいメッセージの本文を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="1699e-132">• Leave the body of the new message empty.</span></span> <br/><br/><span data-ttu-id="1699e-133">•添付されたメッセージの場合は、.msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web format) の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="1699e-133">• Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span>
  
4. <span data-ttu-id="1699e-134">[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1699e-134">Click **Send**.</span></span>
    
## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a><span data-ttu-id="1699e-135">通過が許可されるはずだったのに迷惑メールとタグ付けされたメッセージを提出する</span><span class="sxs-lookup"><span data-stu-id="1699e-135">Submit messages that were tagged as junk but should have been allowed through</span></span>
<span data-ttu-id="1699e-136"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="1699e-136"></span></span>

<span data-ttu-id="1699e-137">メッセージが誤って迷惑メールとして識別された場合は、「偽陽性」メッセージを Microsoft スパム分析チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="1699e-137">If a message was incorrectly identified as junk, you can submit the "false positive" message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="1699e-138">アナリストは、メッセージの評価と分析を行います。</span><span class="sxs-lookup"><span data-stu-id="1699e-138">The analysts will evaluate and analyze the message.</span></span> <span data-ttu-id="1699e-139">分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1699e-139">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
  
<span data-ttu-id="1699e-140">管理者は、組織全体に適用されるその他のスパム設定情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1699e-140">Administrators can review more spam setting information that applies to a whole organization.</span></span> <span data-ttu-id="1699e-141">[メッセージがスパムとしてマークされないようにする方法に](prevent-email-from-being-marked-as-spam.md)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="1699e-141">See [How to help ensure that a message isn't marked as spam](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="1699e-142">管理者レベルの制御権限を持っている場合に誤検出防止に役立つ情報を記載しています。</span><span class="sxs-lookup"><span data-stu-id="1699e-142">This information is helpful if you have administrator-level control and you want to prevent false positives.</span></span>
  
<span data-ttu-id="1699e-143">スパムではないメッセージを送信するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1699e-143">You can submit non-spam messages in the following ways:</span></span>
  
- <span data-ttu-id="1699e-144">コンテンツフィルターを構成するときに **[迷惑メールフォルダーにメッセージを移動**する] アクションを使用すると (これが既定の動作です)、ユーザーは、outlook または web 上の outlook (旧称 Outlook web App) の迷惑メールフォルダーにある誤検知メッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="1699e-144">If you use the **Move message to Junk Email folder** action when you configure your content filters (this is the default action), users can release false positive messages in their Outlook or Outlook on the web (formerly known as Outlook Web App) Junk Email folder.</span></span> 
    
  - <span data-ttu-id="1699e-145">Outlook ユーザーは、**迷惑メール**ではない右クリックメニューオプションを使用して誤検知メッセージを解放できます。</span><span class="sxs-lookup"><span data-stu-id="1699e-145">Outlook users can release false positive messages by using the **Not Junk** right-click menu option.</span></span> <span data-ttu-id="1699e-146">ただし、この記事の手順に示されているように、電子メールでメッセージを Microsoft に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1699e-146">However, they must submit the message to Microsoft through email, as shown in the procedure in this article.</span></span> 
    
  - <span data-ttu-id="1699e-147">Outlook on the web ユーザーは、偽陽性のメッセージを解放して、**迷惑メールではないとしてマーク**を付けて、分析のために Microsoft に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="1699e-147">Outlook on the web users can release false positive messages and submit them to Microsoft for analysis using the **Mark as not junk** action.</span></span> <span data-ttu-id="1699e-148">これを行う方法の詳細については、「 [Outlook on the web で迷惑メールとフィッシング詐欺を報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-148">For more information about how to do this, see [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span>
    
- <span data-ttu-id="1699e-149">コンテンツフィルターを構成するときに、 **[迷惑メールフォルダーにメッセージを移動**する] アクションの代わりに [メッセージの**検疫**] アクションを使用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1699e-149">If you use the **Quarantine message** action instead of the **Move message to Junk Email folder** action when you configure your content filters:</span></span> 
    
  - <span data-ttu-id="1699e-p112">管理者はスパムとして隔離されたメッセージを解放し、そのメッセージを誤検知メッセージとして Exchange 管理センターから報告できます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-p112">Administrators can release spam-quarantined messages and report them as false positives from the Exchange admin center. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
    
  - <span data-ttu-id="1699e-152">ユーザーは、次のチャネルを使用して、自分のスパム検疫済みメッセージを解放し、誤検知として報告することができます。</span><span class="sxs-lookup"><span data-stu-id="1699e-152">Users can release their own spam-quarantined messages and report them as false positives through the following channels:</span></span> 
    
  - <span data-ttu-id="1699e-153">Exchange 管理センター (EAC) ユーザー インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="1699e-153">The Exchange admin center (EAC) user interface.</span></span> <span data-ttu-id="1699e-154">詳細については、「[Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-154">For more information, see [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md).</span></span>
    
  - <span data-ttu-id="1699e-155">エンドユーザー スパム通知メッセージ (管理者が有効にしている場合)。</span><span class="sxs-lookup"><span data-stu-id="1699e-155">End-user spam notification messages (if they're enabled by your administrator).</span></span> 
    
- <span data-ttu-id="1699e-156">スパムとして分類されるべきでないメッセージを Microsoft にメールで送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1699e-156">You can also use email to submit messages to Microsoft that should not be classified as spam.</span></span> <span data-ttu-id="1699e-157">その場合は、以下の手順を必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="1699e-157">When you do this, make sure that you use the steps in the following procedure.</span></span>
    
### <a name="use-email-to-submit-false-positive-messages"></a><span data-ttu-id="1699e-158">電子メールで誤検知メッセージを提出する</span><span class="sxs-lookup"><span data-stu-id="1699e-158">Use email to submit false positive messages</span></span>

<span data-ttu-id="1699e-159">「[メールを使用して迷惑 (スパム) またはフィッシング詐欺メッセージを Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)」に記載されているものと同じ手順を使用します。ただし、メッセージを not_junk@office365.microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="1699e-159">Use the same procedure as described in the "[Use email to submit junk (spam) or phishing scam messages to Microsoft ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md#Useemailtosubmitjunkspamorphishingscammessages)," but send the message to not_junk@office365.microsoft.com.</span></span>
  
## <a name="spam-evaluation-and-rules-deployment"></a><span data-ttu-id="1699e-160">スパム評価とルールの展開</span><span class="sxs-lookup"><span data-stu-id="1699e-160">Spam evaluation and rules deployment</span></span>
<span data-ttu-id="1699e-161"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="1699e-161"></span></span>

<span data-ttu-id="1699e-162">スパム分析チームは、送信したメッセージを調査し、今後の迷惑メールを防ぐためにスパムフィルターを調整します。</span><span class="sxs-lookup"><span data-stu-id="1699e-162">The spam analysis team examines messages that you submit, and adjusts the spam filters to prevent future junk mail.</span></span> <span data-ttu-id="1699e-163">そのため、Office 365 スパムフィルターは常に見直されています。</span><span class="sxs-lookup"><span data-stu-id="1699e-163">As a result, Office 365 spam filters areconstantly refined.</span></span> <span data-ttu-id="1699e-164">提出されたすべてのアイテムは、ネットワーク規模のレベルで評価されます。</span><span class="sxs-lookup"><span data-stu-id="1699e-164">Any submitted items are evaluated at the network-wide level.</span></span> <span data-ttu-id="1699e-165">False 肯定提出は、スパムフィルターを通過できるようになる可能性があるルールの調整を調査および評価します。</span><span class="sxs-lookup"><span data-stu-id="1699e-165">False positive submissions are examined and assessed for possible rule adjustment to allow future messages through the spam filters.</span></span> <span data-ttu-id="1699e-166">そのため、サービスに誤検知と、偽の否定 (迷惑メールではない) について通知することは、自分やグローバルネットワークを使用するすべてのお客様にとって有益です。</span><span class="sxs-lookup"><span data-stu-id="1699e-166">Therefore, notifying the service of false positives and also false negatives (unfiltered spam) is advantageous for you and all customers who use the global network.</span></span> <span data-ttu-id="1699e-167">スパムチームは、送信された各メッセージ内の次のようなインジケーターをチェックします。</span><span class="sxs-lookup"><span data-stu-id="1699e-167">The spam team examines indicators within each submitted message, such as the following:</span></span>
  
- <span data-ttu-id="1699e-168">送信元アドレス</span><span class="sxs-lookup"><span data-stu-id="1699e-168">From address</span></span>
    
- <span data-ttu-id="1699e-169">送信 IP アドレス</span><span class="sxs-lookup"><span data-stu-id="1699e-169">Sending IP address</span></span>
    
- <span data-ttu-id="1699e-170">キーワード</span><span class="sxs-lookup"><span data-stu-id="1699e-170">Keywords</span></span>
    
- <span data-ttu-id="1699e-171">語句</span><span class="sxs-lookup"><span data-stu-id="1699e-171">Phrases</span></span>
    
- <span data-ttu-id="1699e-172">送信頻度</span><span class="sxs-lookup"><span data-stu-id="1699e-172">Frequency of transmission</span></span>
    
- <span data-ttu-id="1699e-173">その他の傾向やパターン</span><span class="sxs-lookup"><span data-stu-id="1699e-173">Other trends and patterns</span></span>
    
<span data-ttu-id="1699e-174">この情報を確認した後、スパムチームは、サービスのスパムフィルタリングレイヤーに変更を加える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1699e-174">After they review this information, the spam team might make changes to the service's spam filtering layers.</span></span> <span data-ttu-id="1699e-175">スパムチームの詳細については、次の英語のみのビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1699e-175">For more information about the spam team, you can watch the following English-only video:</span></span>
  
[<span data-ttu-id="1699e-176">Microsoft Exchange スパムチームビデオ</span><span class="sxs-lookup"><span data-stu-id="1699e-176">Microsoft Exchange Spam team video</span></span>](https://youtu.be/-TpX_-GMC7o?hd=1)
  
<span data-ttu-id="1699e-p117">スパム評価は、スパムの発信元の言語や文字セットに関係なく適用される継続的なプロセスです。スパム メッセージはあいまいであったり、件名やメッセージ本文のテキストがないことがあるため、スパム チームは、その他のメッセージの特性を使用してフィルター処理を行います。つまり、スパム チームが特定のメッセージをスパムとして設定し、そのルール ベースに必要な変更を行った場合、メッセージの特徴がフィルターを回避できるほど大きく変わらない限り、メッセージはブロックされます。新しいスパム ルールは継続的にデプロイされます。個々の提出についてルールがデプロイされる時期は、提出の量と質によって異なります。新しいスパム ルールはすべてのユーザーに対してグローバルに設定されるため、個々のスパムの提出が必ずしも新しいスパム ルールになるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1699e-p117">Spam evaluation is an ongoing process that applies regardless of the originating language or character set. Because a spam message can be vague or even lack text in the subject or message body, the spam team relies on other message characteristics to perform filtering. This means that after the spam team flags a given message as spam and makes the necessary changes to its rule base, that message will be blocked in the future until its characteristics have been modified enough to avoid our filters. New spam rules are deployed continuously. Time frames for rules on individual submissions vary depending on the quantity and quality of submissions. Because new spam rules are set globally for all customers, not all individual spam submissions will result in a new spam rule.</span></span>
   
## <a name="for-more-information"></a><span data-ttu-id="1699e-183">関連情報</span><span class="sxs-lookup"><span data-stu-id="1699e-183">For more information</span></span>
<span data-ttu-id="1699e-184"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="1699e-184"></span></span>

[<span data-ttu-id="1699e-185">スパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="1699e-185">Anti-spam and anti-malware protection</span></span>](anti-spam-and-anti-malware-protection.md)
  
[<span data-ttu-id="1699e-186">メッセージがスパムとしてマークされないようにする方法</span><span class="sxs-lookup"><span data-stu-id="1699e-186">How to help ensure that a message isn't marked as spam</span></span>](prevent-email-from-being-marked-as-spam.md)
  
[<span data-ttu-id="1699e-187">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="1699e-187">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
  

