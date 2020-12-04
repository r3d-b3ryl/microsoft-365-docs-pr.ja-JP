---
title: 管理者による送信
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
description: 管理者は、セキュリティ & コンプライアンスセンターの送信ポータルを使用して、疑わしいメール、疑わしいフィッシングメール、スパム、その他の潜在的な有害なメッセージ、Url、およびその他の潜在的な問題を報告する方法について説明します。
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568592"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="6a509-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="6a509-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6a509-104">Exchange Online のメールボックスを使用する Microsoft 365 の組織では、管理者はセキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、および添付ファイルをスキャン用に Microsoft に提出できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="6a509-105">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="6a509-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="6a509-106">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a509-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="6a509-107">他の方法で電子メールメッセージ、Url、および添付ファイルを Microsoft に提出する方法については、「 [microsoft にメッセージとファイルを報告](report-junk-email-messages-to-microsoft.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a509-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a509-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6a509-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a509-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a509-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6a509-110">**送信** ページに直接移動するには、を使用 <https://protection.office.com/reportsubmission> します。</span><span class="sxs-lookup"><span data-stu-id="6a509-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="6a509-111">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a509-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="6a509-112">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="6a509-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="6a509-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での **組織の管理**。</span><span class="sxs-lookup"><span data-stu-id="6a509-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="6a509-114">このトピックで後述するように [、カスタムメールボックスへのユーザーの送信を表示](#view-user-submissions-to-the-custom-mailbox) するには、この役割グループのメンバーシップが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a509-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="6a509-115">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft へのメッセージとファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a509-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="6a509-116">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="6a509-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="6a509-117">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** の提出] に移動し、[管理者への提出] タブが表示されていることを確認して、 \> **Submissions**[**新しい提出**] をクリックします。 **Admin submissions**</span><span class="sxs-lookup"><span data-stu-id="6a509-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="6a509-118">次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信するための **新しい送信** ポップアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a509-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="6a509-119">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6a509-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="6a509-120">[ **オブジェクトの種類** ] セクションで、[ **電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="6a509-121">[ **提出形式** ] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a509-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="6a509-122">[**ネットワークメッセージ ID**]: この値は、メッセージ内の **Exchange 組織のネットワークメッセージ id** ヘッダー、または検疫されたメッセージの "x-------------------------------------の **相関 id** ヘッダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="6a509-123">[**ファイル**]: [**ファイルの選択] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="6a509-124">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6a509-125">Office 365 プラン1またはプラン2の Defender を使用している管理者は、メッセージを過去30日間として送信することができます。</span><span class="sxs-lookup"><span data-stu-id="6a509-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="6a509-126">他の管理者は、7日間のみ戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="6a509-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="6a509-127">[ **受信者** ] セクションで、ポリシーチェックの実行対象となる1人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a509-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="6a509-128">ポリシーチェックは、ユーザーまたは組織のポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6a509-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="6a509-129">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6a509-130">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="6a509-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6a509-131">**ブロックされている必要があり** ます。 [ **スパム**、 **フィッシング**、または **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="6a509-132">わからない場合は、適切な判断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="6a509-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="6a509-133">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-133">When you're finished, click the **Submit** button.</span></span>

![URL の送信例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="6a509-135">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6a509-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="6a509-136">[ **オブジェクトの種類** ] セクションで、[ **URL**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="6a509-137">表示されるボックスに、完全な URL (たとえば、) を入力し `https://www.fabrikam.com/marketing.html` ます。</span><span class="sxs-lookup"><span data-stu-id="6a509-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="6a509-138">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6a509-139">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="6a509-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6a509-140">**ブロックされている必要があり** ます。 [ **フィッシング** または **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="6a509-141">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-141">When you're finished, click the **Submit** button.</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="6a509-143">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="6a509-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="6a509-144">[ **オブジェクトの種類** ] セクションで、[ **添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="6a509-145">[ **ファイルの選択] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-145">Click **Choose File**.</span></span> <span data-ttu-id="6a509-146">開いたダイアログで、ファイルを見つけて選択し、[ **開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="6a509-147">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6a509-148">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="6a509-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6a509-149">**ブロックされている必要があり** ます。 **マルウェア** のみが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="6a509-150">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-150">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの提出の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="6a509-152">管理者の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-152">View admin submissions</span></span>

<span data-ttu-id="6a509-153">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** の提出] に移動し、[管理者への提出] タブが表示されていることを確認して、 \> **Submissions**[**新しい提出**] をクリックします。 **Admin submissions**</span><span class="sxs-lookup"><span data-stu-id="6a509-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6a509-154">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることにより、 **送信 ID** でフィルター処理できます (既定では、すべての提出物に割り当てられている GUID 値) ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="6a509-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6a509-155">Update</span><span class="sxs-lookup"><span data-stu-id="6a509-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6a509-156">フィルター条件を変更するには、[ **提出 ID** ] ボタンをクリックして、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="6a509-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6a509-157">**Sender**</span></span>
- <span data-ttu-id="6a509-158">**Subject/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="6a509-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="6a509-159">**提出者**</span><span class="sxs-lookup"><span data-stu-id="6a509-159">**Submitted by**</span></span>
- <span data-ttu-id="6a509-160">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-160">**Submission type**</span></span>
- <span data-ttu-id="6a509-161">**状態**</span><span class="sxs-lookup"><span data-stu-id="6a509-161">**Status**</span></span>

![管理者送信のフィルターオプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="6a509-163">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6a509-164">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6a509-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="6a509-165">グラフの下に、[ **電子メール** ] (既定)、[ **URL**]、および [ **添付ファイル**] の3つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="6a509-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="6a509-166">管理者の電子メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-166">View admin email submissions</span></span>

<span data-ttu-id="6a509-167">[ **電子メール** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-167">Click the **Email** tab.</span></span>

<span data-ttu-id="6a509-168">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6a509-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="6a509-169">**Date**</span></span>
- <span data-ttu-id="6a509-170">**送信 ID**: すべての提出物に割り当てられている GUID 値。</span><span class="sxs-lookup"><span data-stu-id="6a509-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="6a509-171">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-172">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6a509-173">**Sender**</span></span>
- <span data-ttu-id="6a509-174">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="6a509-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-175">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-175">**Submission type**</span></span>
- <span data-ttu-id="6a509-176">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="6a509-176">**Delivery reason**</span></span>
- <span data-ttu-id="6a509-177">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6a509-178"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="6a509-179">管理者送信再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="6a509-179">Admin submission rescan details</span></span>

<span data-ttu-id="6a509-180">管理者の送信で送信されたメッセージは、再スキャンと、詳細ポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="6a509-181">送信時に送信者の電子メール認証でエラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="6a509-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="6a509-182">メッセージの verdict に影響を与えたり、上書きされたりする可能性のあるポリシーヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="6a509-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="6a509-183">現在の分析結果は、メッセージに含まれる Url またはファイルが悪意のあるものであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a509-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="6a509-184">Graders からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="6a509-184">Feedback from graders.</span></span>

<span data-ttu-id="6a509-185">上書きが見つかった場合、再スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="6a509-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="6a509-186">電子メールの認証に問題がない場合、または配信が上書きの影響を受けていない場合は、graders からのフィードバックが1日までにかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a509-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="6a509-187">管理者 URL の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-187">View admin URL submissions</span></span>

<span data-ttu-id="6a509-188">[ **URL** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-188">Click the **URL** tab.</span></span>

<span data-ttu-id="6a509-189">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6a509-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="6a509-190">**Date**</span></span>
- <span data-ttu-id="6a509-191">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="6a509-191">**Submission ID**</span></span>
- <span data-ttu-id="6a509-192">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-193">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="6a509-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-194">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-194">**Submission type**</span></span>
- <span data-ttu-id="6a509-195">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6a509-196"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="6a509-197">管理者添付ファイルの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-197">View admin attachment submissions</span></span>

<span data-ttu-id="6a509-198">[ **添付ファイル** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="6a509-199">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6a509-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="6a509-200">**Date**</span></span>
- <span data-ttu-id="6a509-201">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="6a509-201">**Submission ID**</span></span>
- <span data-ttu-id="6a509-202">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-203">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-204">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-204">**Submission type**</span></span>
- <span data-ttu-id="6a509-205">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6a509-206"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="6a509-207">Microsoft へのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="6a509-208">[レポートメッセージアドイン](enable-the-report-message-add-in.md)を展開した場合、またはユーザーが [Outlook on the web で組み込みのレポート](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)を使用している場合は、[**ユーザーの送信**] タブでどのユーザーがレポートしているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="6a509-209">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** の提出] に移動 \> **Submissions** します。</span><span class="sxs-lookup"><span data-stu-id="6a509-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6a509-210">[ **ユーザーの送信** ] タブを選択し、[ **新しい送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a509-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6a509-211">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6a509-212">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="6a509-212">**Submitted on**</span></span>
- <span data-ttu-id="6a509-213">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-214">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6a509-215">**Sender**</span></span>
- <span data-ttu-id="6a509-216">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="6a509-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-217">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-217">**Submission type**</span></span>

<span data-ttu-id="6a509-218"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="6a509-219">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることによって、 **送信者** によるフィルター処理を実行でき ![ ](../../media/scc-quarantine-refresh.png) ます。</span><span class="sxs-lookup"><span data-stu-id="6a509-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6a509-220">Update</span><span class="sxs-lookup"><span data-stu-id="6a509-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6a509-221">フィルター条件を変更するには、[ **送信者** ] ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="6a509-222">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="6a509-222">**Sender domain**</span></span>
- <span data-ttu-id="6a509-223">**Subject**</span><span class="sxs-lookup"><span data-stu-id="6a509-223">**Subject**</span></span>
- <span data-ttu-id="6a509-224">**提出者**</span><span class="sxs-lookup"><span data-stu-id="6a509-224">**Submitted by**</span></span>
- <span data-ttu-id="6a509-225">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-225">**Submission type**</span></span>
- <span data-ttu-id="6a509-226">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="6a509-226">**Sender IP**</span></span>

![ユーザー送信のフィルターオプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="6a509-228">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6a509-229">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6a509-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="6a509-230">カスタムメールボックスへのユーザー送信を表示する</span><span class="sxs-lookup"><span data-stu-id="6a509-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="6a509-231">ユーザーが報告したメッセージを受信するように [カスタムメールボックスを構成](user-submission.md)した **場合** は、レポートメールボックスに配信されたメッセージを表示して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a509-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="6a509-232">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** の提出] に移動 \> **Submissions** します。</span><span class="sxs-lookup"><span data-stu-id="6a509-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6a509-233">[ **カスタムメールボックス** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="6a509-234">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6a509-235">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="6a509-235">**Submitted on**</span></span>
- <span data-ttu-id="6a509-236">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-237">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6a509-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6a509-238">**Sender**</span></span>
- <span data-ttu-id="6a509-239">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="6a509-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6a509-240">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="6a509-240">**Submission type**</span></span>

<span data-ttu-id="6a509-241">ページの上部に、開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで、 **送信** によってフィルター処理を行うことができます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="6a509-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6a509-242">Update</span><span class="sxs-lookup"><span data-stu-id="6a509-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6a509-243">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6a509-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6a509-244">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6a509-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="6a509-245">ユーザー送信の取り消し</span><span class="sxs-lookup"><span data-stu-id="6a509-245">Undo user submissions</span></span>

<span data-ttu-id="6a509-246">ユーザーが疑わしいメールをカスタムメールボックスに送信すると、ユーザーと管理者には送信を取り消すオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="6a509-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="6a509-247">ユーザーがメールを回復したい場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="6a509-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="6a509-248">カスタムメールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="6a509-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="6a509-249">ユーザーが報告したメッセージを Microsoft に送信せずに受信するようにカスタムメールボックスを構成した場合は、特定のメッセージを検索して Microsoft に送信して分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a509-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="6a509-250">これにより、ユーザーの送信が管理者の送信に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="6a509-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="6a509-251">[ **カスタムメールボックス** ] タブで、一覧からメッセージを選択し、[ **アクション** ] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="6a509-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="6a509-252">**クリーンなレポート**</span><span class="sxs-lookup"><span data-stu-id="6a509-252">**Report clean**</span></span>
- <span data-ttu-id="6a509-253">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="6a509-253">**Report phishing**</span></span>
- <span data-ttu-id="6a509-254">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="6a509-254">**Report malware**</span></span>
- <span data-ttu-id="6a509-255">**スパムの報告**</span><span class="sxs-lookup"><span data-stu-id="6a509-255">**Report spam**</span></span>

![[アクション] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
