---
title: 管理者の申請
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの送信ポータルを使用して、疑わしいメール、フィッシング詐欺の疑いがあるメール、スパム、その他の有害な可能性のあるメッセージ、URL、ファイルをスキャンのために Microsoft に送信する方法について説明します。
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864950"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="9c61f-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="9c61f-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9c61f-104">Exchange Online にメールボックスがある Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの送信ポータルを使用して、メール メッセージ、URL、および添付ファイルをスキャンのために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="9c61f-105">メールを送信すると、テナントへの受信メールを許可している可能性があるポリシーに関する情報と、メール内の URL と添付ファイルの検査に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="9c61f-106">メールを許可するポリシーには、個々のユーザーの差出人セーフ リストと、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) などのテナント レベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="9c61f-107">電子メール メッセージ、URL、および添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9c61f-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9c61f-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="9c61f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9c61f-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9c61f-110">[提出] ページに直接 **移動するには** 、次のコマンドを使用します <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="9c61f-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="9c61f-111">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c61f-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9c61f-112">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="9c61f-113">Exchange Online **での**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="9c61f-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="9c61f-114">この役割グループのメンバーシップは、この記事で[](#view-user-submissions-to-the-custom-mailbox)後述するように、カスタム メールボックスへのユーザー送信を表示するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9c61f-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="9c61f-115">ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する [」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9c61f-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="9c61f-116">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="9c61f-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="9c61f-117">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリック \> **します**。 </span><span class="sxs-lookup"><span data-stu-id="9c61f-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="9c61f-118">次 **のセクションで** 説明するように、メッセージ、URL、または添付ファイルを送信するために表示される新しい送信のフライアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="9c61f-119">Microsoft に問題があるメールを送信する</span><span class="sxs-lookup"><span data-stu-id="9c61f-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="9c61f-120">[オブジェクトの **種類] セクションで** 、[電子メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="9c61f-121">[提出 **形式] セクション** で、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="9c61f-122">**ネットワーク** メッセージ ID : これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="9c61f-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="9c61f-123">**[ファイル**]: [ファイルの **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="9c61f-124">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c61f-125">Office 365 プラン 1 またはプラン 2 の Defender を使用する管理者は、30 日間の古いメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="9c61f-126">その他の管理者は 7 日間のみ戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c61f-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="9c61f-127">[ **受信者] セクション** で、ポリシー チェックを実行する 1 人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="9c61f-128">ポリシー チェックでは、ユーザーまたは組織のポリシーが原因でメールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="9c61f-129">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9c61f-130">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9c61f-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9c61f-131">**ブロックされている必要があります**: **スパム**、フィッシング **、またはマルウェア** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="9c61f-132">確信が持てない場合は、最善の判断を下してください。</span><span class="sxs-lookup"><span data-stu-id="9c61f-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="9c61f-133">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-133">When you're finished, click the **Submit** button.</span></span>

![URL 送信の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="9c61f-135">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="9c61f-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="9c61f-136">[オブジェクトの **種類] セクションで\*\*\*\*、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="9c61f-137">表示されるボックスに、完全な URL (たとえば) を入力します `https://www.fabrikam.com/marketing.html` 。</span><span class="sxs-lookup"><span data-stu-id="9c61f-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="9c61f-138">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9c61f-139">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9c61f-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9c61f-140">**ブロックされている必要があります**: [フィッシングまたは **マルウェア] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="9c61f-141">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-141">When you're finished, click the **Submit** button.</span></span>

![メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="9c61f-143">疑わしいファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="9c61f-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="9c61f-144">[オブジェクトの **種類] セクションで** 、[添付ファイル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="9c61f-145">[ファイル **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-145">Click **Choose File**.</span></span> <span data-ttu-id="9c61f-146">開いたダイアログで、ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="9c61f-147">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9c61f-148">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9c61f-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9c61f-149">**ブロックされている必要があります**: **マルウェア** だけが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="9c61f-150">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-150">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの送信の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="9c61f-152">管理者の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-152">View admin submissions</span></span>

<span data-ttu-id="9c61f-153">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリック \> **します**。 </span><span class="sxs-lookup"><span data-stu-id="9c61f-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9c61f-154">ページの上部には、開始日、終了日を入力できます。また、既定では、ボックスに値を入力して [更新] ボタンをクリックすることで、提出 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9c61f-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9c61f-155">Update</span><span class="sxs-lookup"><span data-stu-id="9c61f-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9c61f-156">フィルター条件を変更するには **、[Submission ID]** ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="9c61f-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9c61f-157">**Sender**</span></span>
- <span data-ttu-id="9c61f-158">**件名/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="9c61f-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="9c61f-159">**提出者**</span><span class="sxs-lookup"><span data-stu-id="9c61f-159">**Submitted by**</span></span>
- <span data-ttu-id="9c61f-160">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-160">**Submission type**</span></span>
- <span data-ttu-id="9c61f-161">**状態**</span><span class="sxs-lookup"><span data-stu-id="9c61f-161">**Status**</span></span>

![管理者の申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="9c61f-163">結果をエクスポートするには、ページの **上部にある** [エクスポート] をクリックし、[グラフ データ] または [テーブル **]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9c61f-164">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="9c61f-165">グラフの下には、メール (既定)、URL、添付ファイルの 3 つのタブ **があります**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="9c61f-166">管理者のメールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-166">View admin email submissions</span></span>

<span data-ttu-id="9c61f-167">[電子メール **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-167">Click the **Email** tab.</span></span>

<span data-ttu-id="9c61f-168">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9c61f-169">**日付**</span><span class="sxs-lookup"><span data-stu-id="9c61f-169">**Date**</span></span>
- <span data-ttu-id="9c61f-170">**提出 ID**: すべての申請に割り当てられる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="9c61f-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="9c61f-171">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-172">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9c61f-173">**Sender**</span></span>
- <span data-ttu-id="9c61f-174">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9c61f-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-175">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-175">**Submission type**</span></span>
- <span data-ttu-id="9c61f-176">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="9c61f-176">**Delivery reason**</span></span>
- <span data-ttu-id="9c61f-177">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9c61f-178"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="9c61f-179">管理者の提出の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="9c61f-179">Admin submission rescan details</span></span>

<span data-ttu-id="9c61f-180">管理者の提出で送信されたメッセージは再スキャンされ、詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="9c61f-181">配信時に送信者の電子メール認証にエラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="9c61f-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="9c61f-182">メッセージの Verdict に影響を与えた、または上書きした可能性があるポリシー ヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="9c61f-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="9c61f-183">現在の分析結果では、メッセージに含まれる URL またはファイルが悪意のあるものか確認されません。</span><span class="sxs-lookup"><span data-stu-id="9c61f-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="9c61f-184">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="9c61f-184">Feedback from graders.</span></span>

<span data-ttu-id="9c61f-185">オーバーライドが見つかった場合は、数分で再スキャンが完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c61f-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="9c61f-186">メール認証で問題が発生したり、配信が上書きの影響を受けなかったりした場合、成績者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c61f-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="9c61f-187">管理者 URL の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-187">View admin URL submissions</span></span>

<span data-ttu-id="9c61f-188">**[URL] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-188">Click the **URL** tab.</span></span>

<span data-ttu-id="9c61f-189">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9c61f-190">**日付**</span><span class="sxs-lookup"><span data-stu-id="9c61f-190">**Date**</span></span>
- <span data-ttu-id="9c61f-191">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="9c61f-191">**Submission ID**</span></span>
- <span data-ttu-id="9c61f-192">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-193">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9c61f-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-194">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-194">**Submission type**</span></span>
- <span data-ttu-id="9c61f-195">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9c61f-196"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="9c61f-197">管理者の添付ファイルの提出を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-197">View admin attachment submissions</span></span>

<span data-ttu-id="9c61f-198">[添付ファイル **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="9c61f-199">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9c61f-200">**日付**</span><span class="sxs-lookup"><span data-stu-id="9c61f-200">**Date**</span></span>
- <span data-ttu-id="9c61f-201">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="9c61f-201">**Submission ID**</span></span>
- <span data-ttu-id="9c61f-202">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-203">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-204">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-204">**Submission type**</span></span>
- <span data-ttu-id="9c61f-205">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9c61f-206"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="9c61f-207">Microsoft へのユーザー申請を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="9c61f-208">レポート メッセージ アドイン、Report [](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)アドイン、または[Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)で組み込みのレポートを使用しているユーザーを展開した場合は、[ユーザーの送信]タブでユーザーが報告している情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="9c61f-209">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9c61f-210">[ユーザーの **提出] タブを選択** し、[新しい提出] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9c61f-211">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9c61f-212">**送信日**</span><span class="sxs-lookup"><span data-stu-id="9c61f-212">**Submitted on**</span></span>
- <span data-ttu-id="9c61f-213">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-214">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9c61f-215">**Sender**</span></span>
- <span data-ttu-id="9c61f-216">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9c61f-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-217">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-217">**Submission type**</span></span>

<span data-ttu-id="9c61f-218"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="9c61f-219">ページの上部には、開始日、終了日を入力できます。既定では、ボックスに値を入力して [更新] ボタンをクリックすることで Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9c61f-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9c61f-220">Update</span><span class="sxs-lookup"><span data-stu-id="9c61f-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9c61f-221">フィルター条件を変更するには、[送信者]ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="9c61f-222">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c61f-222">**Sender domain**</span></span>
- <span data-ttu-id="9c61f-223">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="9c61f-223">**Subject**</span></span>
- <span data-ttu-id="9c61f-224">**提出者**</span><span class="sxs-lookup"><span data-stu-id="9c61f-224">**Submitted by**</span></span>
- <span data-ttu-id="9c61f-225">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-225">**Submission type**</span></span>
- <span data-ttu-id="9c61f-226">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9c61f-226">**Sender IP**</span></span>

![ユーザー提出のフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="9c61f-228">結果をエクスポートするには、ページの **上部にある** [エクスポート] をクリックし、[グラフ データ] または [テーブル **]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9c61f-229">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="9c61f-230">カスタム メールボックスへのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9c61f-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="9c61f-231">**ユーザー** から報告 [されたメッセージ](user-submission.md) を受信するようにカスタム メールボックスを構成した場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="9c61f-232">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9c61f-233">[カスタム メールボックス **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="9c61f-234">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9c61f-235">**送信日**</span><span class="sxs-lookup"><span data-stu-id="9c61f-235">**Submitted on**</span></span>
- <span data-ttu-id="9c61f-236">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-237">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9c61f-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9c61f-238">**Sender**</span></span>
- <span data-ttu-id="9c61f-239">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9c61f-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9c61f-240">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9c61f-240">**Submission type**</span></span>

<span data-ttu-id="9c61f-241">ページの上部に開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで Submitted でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9c61f-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9c61f-242">Update</span><span class="sxs-lookup"><span data-stu-id="9c61f-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9c61f-243">結果をエクスポートするには、ページの **上部にある** [エクスポート] をクリックし、[グラフ データ] または [テーブル **]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9c61f-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9c61f-244">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="9c61f-245">ユーザーの提出を元に戻す</span><span class="sxs-lookup"><span data-stu-id="9c61f-245">Undo user submissions</span></span>

<span data-ttu-id="9c61f-246">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="9c61f-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="9c61f-247">ユーザーがメールを回復する場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="9c61f-248">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="9c61f-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="9c61f-249">Microsoft にメッセージを送信せずにユーザーから報告されたメッセージを取得するようにカスタム メールボックスを構成した場合は、特定のメッセージを検索して分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="9c61f-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="9c61f-250">これにより、ユーザーの申請が管理者の申請に効果的に移動します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="9c61f-251">[**カスタム メールボックス]** タブで、一覧からメッセージを選択し、[操作] ボタンをクリックして、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c61f-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="9c61f-252">**レポートをクリーンにする**</span><span class="sxs-lookup"><span data-stu-id="9c61f-252">**Report clean**</span></span>
- <span data-ttu-id="9c61f-253">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="9c61f-253">**Report phishing**</span></span>
- <span data-ttu-id="9c61f-254">**マルウェアを報告する**</span><span class="sxs-lookup"><span data-stu-id="9c61f-254">**Report malware**</span></span>
- <span data-ttu-id="9c61f-255">**迷惑メールを報告する**</span><span class="sxs-lookup"><span data-stu-id="9c61f-255">**Report spam**</span></span>

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
