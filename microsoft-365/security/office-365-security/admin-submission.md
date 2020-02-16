---
title: Office 365、O365 提出、Office 365 スパムの問題、O365 誤検出、office 365 での送信フィッシング、office 365 での電子メールの送信、メールの送信、メールをスキャン、フィッシングに関する Microsoft scan を使用している、microsoft scan for スパム、送信電子メール、電子メールの送信、dodgy メール、誤ったアクターメール、疑わしい、信頼できないメール、レポートフィッシング電子メール、microsoft への電子メールの報告、詐欺メールを microsoft に報告する、microsoft への電子メールの報告、microsoft への電子メールの報告、スパム受信トレイ内のメール office 365、電子メール office のウイルス365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 疑わしいメール、疑わしいフィッシングメール、スパム、およびその他の潜在的に有害なメッセージ、Url、およびその他の潜在的な問題のあるメールを、Office 365 テナントから Microsoft にスキャンするために提出する方法について説明します。
ms.openlocfilehash: b123aef485628728df9db27875117b47295975ad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083637"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="499fb-103">フィッシングの疑いのあるスパム、、Url、およびファイルを Microsoft for Office 365 スキャンに提出する方法</span><span class="sxs-lookup"><span data-stu-id="499fb-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="499fb-104">管理者は、Microsoft が Office 365 でスキャンするファイルまたはネットワークメッセージ ID、Url、ファイルを使用して、メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="499fb-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span>
<span data-ttu-id="499fb-105">更新された提出物セクションには、ユーザーが報告したメッセージと、EOP を使用しているすべてのお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="499fb-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="499fb-106">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="499fb-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="499fb-107">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="499fb-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="499fb-108">Office 365 スキャンに対して疑わしいコンテンツを Microsoft に送信する方法</span><span class="sxs-lookup"><span data-stu-id="499fb-108">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="499fb-109">Microsoft にコンテンツを送信するには、送信ページの左上にある [**新しい送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="499fb-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="499fb-110">ページの右側にあるポップアップが表示され、電子メール、URL、またはファイルのいずれかを送信するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="499fb-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="499fb-111">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="499fb-111">Submit a questionable email to Microsoft</span></span>

![電子メール送信の例](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="499fb-113">電子メールを送信するには、[**電子**メール] を選択し、電子メール**ネットワークのメッセージ ID**を指定するか、電子メールファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="499fb-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="499fb-114">ポリシーチェックの実行対象となる受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="499fb-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="499fb-115">ポリシーチェックは、ユーザーまたはテナントレベルのポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="499fb-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="499fb-116">電子メールがブロックされているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="499fb-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="499fb-117">メールがブロックされている必要がある場合は、スパム、フィッシング、またはマルウェアとしてブロックされているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="499fb-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="499fb-118">可能な種類がわからない場合は、最適な judgement を使用してください。</span><span class="sxs-lookup"><span data-stu-id="499fb-118">If you are not sure what type it might be, use your best judgement.</span></span>

   - <span data-ttu-id="499fb-119">送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="499fb-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="499fb-120">1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="499fb-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="499fb-121">[状態] リンクをクリックすると、送信に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="499fb-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="499fb-122">これには、ポリシーチェックの結果と rescan verdict が含まれます。</span><span class="sxs-lookup"><span data-stu-id="499fb-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="499fb-123">メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="499fb-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="499fb-124">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="499fb-124">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="499fb-125">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="499fb-125">Send a suspect URL to Microsoft</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

1. <span data-ttu-id="499fb-127">URL を送信するには、ポップアップから [ **url** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="499fb-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="499fb-128">プロトコル (**https://**) を含む完全な URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="499fb-128">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="499fb-129">[**フィルター済み**] を選択した場合は、URL がフィッシングまたはマルウェアであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="499fb-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="499fb-130">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="499fb-130">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="499fb-131">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="499fb-131">Submit a suspected file to Microsoft</span></span>

![電子メール送信の例](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="499fb-133">ファイルを送信するには、ポップアップ**からファイルを選択し**、スキャンしたいファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="499fb-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="499fb-134">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="499fb-134">Click the **Submit** button.</span></span>

## <a name="related-topics"></a><span data-ttu-id="499fb-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="499fb-135">Related topics</span></span>

[<span data-ttu-id="499fb-136">Office 365 Advanced Threat Protection プラン 2</span><span class="sxs-lookup"><span data-stu-id="499fb-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)

[<span data-ttu-id="499fb-137">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="499fb-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="499fb-138">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="499fb-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
