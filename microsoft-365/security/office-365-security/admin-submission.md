---
title: Office 365、O365 提出、Office 365 スパムの問題、O365 誤検出、office 365 での送信フィッシング、office 365 での電子メールの送信、メールの送信、メールをスキャン、フィッシングに関する Microsoft scan を使用している、microsoft scan for スパム、送信電子メール、電子メールの送信、dodgy メール、誤ったアクターメール、疑わしい、信頼できないメール、レポートフィッシング電子メール、microsoft への電子メールの報告、詐欺メールを microsoft に報告する、microsoft への電子メールの報告、microsoft への電子メールの報告、スパム受信トレイ内のメール office 365、電子メール office のウイルス365
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
ms.collection:
- M365-security-compliance
description: 疑わしいメール、疑わしいフィッシングメール、スパム、およびその他の潜在的に有害なメッセージ、Url、およびその他の潜在的な問題のあるメールを、Office 365 テナントから Microsoft にスキャンするために提出する方法について説明します。
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033616"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c1830-103">管理者提出を使用して、疑いのあるスパム、フィッシング、Url、およびファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="c1830-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="c1830-104">Exchange Online のメールボックスを使用する Office 365 組織の管理者である場合は、Office 365 セキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、添付ファイルをスキャン用に Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="c1830-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c1830-105">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="c1830-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="c1830-106">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1830-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="c1830-107">その他の方法で、電子メールメッセージ、Url、添付ファイルを Microsoft に提出する方法については、</span><span class="sxs-lookup"><span data-stu-id="c1830-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c1830-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c1830-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c1830-109">セキュリティ & コンプライアンスセンターに<https://protection.office.com/>表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1830-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c1830-110">**送信**ページに直接移動するには、 <https://protection.office.com/reportsubmission>を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1830-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c1830-111">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1830-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c1830-112">スタンドアロンの Exchange Online Protection の PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1830-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c1830-113">これらの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1830-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c1830-114">スパム対策ポリシーを追加、変更、および削除するには、**組織の管理**、**セキュリティ管理者**、または**セキュリティリーダー**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1830-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="c1830-115">セキュリティ & コンプライアンスセンターの役割グループの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1830-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c1830-116">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft にレポートメッセージとファイルを](report-junk-email-messages-to-microsoft.md)送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1830-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="c1830-117">Office 365 スキャンに対して疑わしいコンテンツを Microsoft に送信する方法</span><span class="sxs-lookup"><span data-stu-id="c1830-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="c1830-118">Microsoft にコンテンツを送信するには、送信ページの左上にある [**新しい送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1830-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="c1830-119">ページの右側にあるポップアップが表示され、電子メール、URL、またはファイルのいずれかを送信するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1830-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c1830-120">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="c1830-120">Submit a questionable email to Microsoft</span></span>

![電子メール送信の例](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="c1830-122">電子メールを送信するには、[**電子**メール] を選択し、電子メール**ネットワークのメッセージ ID**を指定するか、電子メールファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c1830-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="c1830-123">ポリシーチェックの実行対象となる受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="c1830-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="c1830-124">ポリシーチェックは、ユーザーまたはテナントレベルのポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c1830-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="c1830-125">電子メールがブロックされているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1830-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="c1830-126">メールがブロックされている必要がある場合は、スパム、フィッシング、またはマルウェアとしてブロックされているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1830-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="c1830-127">可能な種類がわからない場合は、最適な判断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="c1830-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="c1830-128">送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1830-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="c1830-129">1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="c1830-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="c1830-130">[状態] リンクをクリックすると、送信に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1830-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="c1830-131">これには、ポリシーチェックの結果と rescan verdict が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c1830-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="c1830-132">メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c1830-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="c1830-133">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1830-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c1830-134">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="c1830-134">Send a suspect URL to Microsoft</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

1. <span data-ttu-id="c1830-136">URL を送信するには、ポップアップから [ **url** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1830-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="c1830-137">プロトコル (**https://**) を含む完全な URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1830-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="c1830-138">[**フィルター済み**] を選択した場合は、URL がフィッシングまたはマルウェアであるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c1830-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="c1830-139">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1830-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c1830-140">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="c1830-140">Submit a suspected file to Microsoft</span></span>

![電子メール送信の例](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="c1830-142">ファイルを送信するには、ポップアップ**からファイルを選択し**、スキャンしたいファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c1830-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="c1830-143">[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1830-143">Click the **Submit** button.</span></span>
