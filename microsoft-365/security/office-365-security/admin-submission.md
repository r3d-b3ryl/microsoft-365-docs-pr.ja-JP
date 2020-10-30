---
title: 管理者による送信
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.openlocfilehash: 5d4123acaf3c9891f9aeb8028173f3071c260935
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806762"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="e5054-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="e5054-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e5054-104">Exchange Online のメールボックスを使用する Microsoft 365 の組織では、管理者はセキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、および添付ファイルをスキャン用に Microsoft に提出できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="e5054-105">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="e5054-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="e5054-106">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5054-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="e5054-107">他の方法で電子メールメッセージ、Url、および添付ファイルを Microsoft に提出する方法については、「 [microsoft にメッセージとファイルを報告](report-junk-email-messages-to-microsoft.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5054-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e5054-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e5054-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e5054-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5054-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e5054-110">**送信** ページに直接移動するには、を使用 <https://protection.office.com/reportsubmission> します。</span><span class="sxs-lookup"><span data-stu-id="e5054-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="e5054-111">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5054-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="e5054-112">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。</span><span class="sxs-lookup"><span data-stu-id="e5054-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="e5054-113">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での **組織の管理** 。</span><span class="sxs-lookup"><span data-stu-id="e5054-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="e5054-114">このトピックで後述するように [、カスタムメールボックスへのユーザーの送信を表示](#view-user-submissions-to-the-custom-mailbox) するには、この役割グループのメンバーシップが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5054-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="e5054-115">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft へのメッセージとファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5054-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="e5054-116">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="e5054-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="e5054-117">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** の提出] に移動し、[管理者への提出] タブが表示されていることを確認して、 \> **Submissions** [ **新しい提出** ] をクリックします。 **Admin submissions**</span><span class="sxs-lookup"><span data-stu-id="e5054-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission** .</span></span>

2. <span data-ttu-id="e5054-118">次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信するための **新しい送信** ポップアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5054-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e5054-119">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="e5054-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="e5054-120">[ **オブジェクトの種類** ] セクションで、[ **電子メール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-120">In the **Object type** section, select **Email** .</span></span> <span data-ttu-id="e5054-121">[ **提出形式** ] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5054-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="e5054-122">**ネットワークメッセージ id** : これは、メッセージ内の、 **Exchange 組織のネットワークメッセージ id** ヘッダーで使用可能な GUID 値になります。</span><span class="sxs-lookup"><span data-stu-id="e5054-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="e5054-123">[ **ファイル** ]: [ **ファイルの選択] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-123">**File** : Click **Choose file** .</span></span> <span data-ttu-id="e5054-124">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[ **開く** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open** .</span></span>

2. <span data-ttu-id="e5054-125">[ **受信者** ] セクションで、ポリシーチェックの実行対象となる1人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5054-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="e5054-126">ポリシーチェックは、ユーザーまたは組織のポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e5054-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="e5054-127">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5054-128">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="e5054-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5054-129">**ブロックされている必要があり** ます。 [ **スパム** 、 **フィッシング** 、または **マルウェア** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware** .</span></span> <span data-ttu-id="e5054-130">わからない場合は、適切な判断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="e5054-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="e5054-131">送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="e5054-132">1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="e5054-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="e5054-133">[状態] リンクをクリックすると、送信に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="e5054-134">これには、ポリシーチェックの結果と rescan verdict が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5054-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="e5054-135">メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="e5054-136">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-136">When you're finished, click the **Submit** button.</span></span>

![URL の送信例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e5054-138">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="e5054-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="e5054-139">[ **オブジェクトの種類** ] セクションで、[ **URL** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-139">In the **Object type** section, select **URL** .</span></span> <span data-ttu-id="e5054-140">表示されるボックスに、完全な URL (たとえば、) を入力し `https://www.fabrikam.com/marketing.html` ます。</span><span class="sxs-lookup"><span data-stu-id="e5054-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="e5054-141">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5054-142">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="e5054-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5054-143">**ブロックされている必要があり** ます。 [ **フィッシング** または **マルウェア** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-143">**Should have been blocked** : Select **Phishing** or **Malware** .</span></span>

3. <span data-ttu-id="e5054-144">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-144">When you're finished, click the **Submit** button.</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="e5054-146">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="e5054-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="e5054-147">[ **オブジェクトの種類** ] セクションで、[ **添付ファイル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-147">In the **Object type** section, select **Attachment** .</span></span>

2. <span data-ttu-id="e5054-148">[ **ファイルの選択] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-148">Click **Choose File** .</span></span> <span data-ttu-id="e5054-149">開いたダイアログで、ファイルを見つけて選択し、[ **開く** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-149">In the dialog that opens, find and select the file, and then click **Open** .</span></span>

3. <span data-ttu-id="e5054-150">[ **送信理由** ] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="e5054-151">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="e5054-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="e5054-152">**ブロックされている必要があり** ます。 **マルウェア** のみが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="e5054-153">完了したら、[ **送信** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-153">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの提出の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="e5054-155">管理者の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-155">View admin submissions</span></span>

<span data-ttu-id="e5054-156">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** の提出] に移動し、[管理者への提出] タブが表示されていることを確認して、 \> **Submissions** [ **新しい提出** ] をクリックします。 **Admin submissions**</span><span class="sxs-lookup"><span data-stu-id="e5054-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission** .</span></span>

<span data-ttu-id="e5054-157">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることにより、 **送信 ID** でフィルター処理できます (既定では、すべての提出物に割り当てられている GUID 値) ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e5054-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5054-158">Update</span><span class="sxs-lookup"><span data-stu-id="e5054-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5054-159">フィルター条件を変更するには、[ **提出 ID** ] ボタンをクリックして、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="e5054-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e5054-160">**Sender**</span></span>
- <span data-ttu-id="e5054-161">**Subject/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="e5054-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="e5054-162">**提出者**</span><span class="sxs-lookup"><span data-stu-id="e5054-162">**Submitted by**</span></span>
- <span data-ttu-id="e5054-163">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-163">**Submission type**</span></span>
- <span data-ttu-id="e5054-164">**状態**</span><span class="sxs-lookup"><span data-stu-id="e5054-164">**Status**</span></span>

![管理者送信のフィルターオプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="e5054-166">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="e5054-167">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5054-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="e5054-168">グラフの下に、[ **電子メール** ] (既定)、[ **URL** ]、および [ **添付ファイル** ] の3つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="e5054-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment** .</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="e5054-169">管理者の電子メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-169">View admin email submissions</span></span>

<span data-ttu-id="e5054-170">[ **電子メール** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-170">Click the **Email** tab.</span></span>

<span data-ttu-id="e5054-171">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5054-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5054-172">**Date**</span></span>
- <span data-ttu-id="e5054-173">**送信 ID** : すべての提出物に割り当てられている GUID 値。</span><span class="sxs-lookup"><span data-stu-id="e5054-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="e5054-174">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-175">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e5054-176">**Sender**</span></span>
- <span data-ttu-id="e5054-177">[ **Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="e5054-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-178">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-178">**Submission type**</span></span>
- <span data-ttu-id="e5054-179">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="e5054-179">**Delivery reason**</span></span>
- <span data-ttu-id="e5054-180">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-181">**コントロールの種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-181">**Control type**</span></span>
- <span data-ttu-id="e5054-182">**コントロールソース**</span><span class="sxs-lookup"><span data-stu-id="e5054-182">**Control source**</span></span>

  <span data-ttu-id="e5054-183"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="e5054-184">管理者 URL の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-184">View admin URL submissions</span></span>

<span data-ttu-id="e5054-185">[ **URL** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-185">Click the **URL** tab.</span></span>

<span data-ttu-id="e5054-186">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5054-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5054-187">**Date**</span></span>
- <span data-ttu-id="e5054-188">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="e5054-188">**Submission ID**</span></span>
- <span data-ttu-id="e5054-189">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-190">[ **URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="e5054-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-191">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-191">**Submission type**</span></span>
- <span data-ttu-id="e5054-192">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e5054-193"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="e5054-194">管理者添付ファイルの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-194">View admin attachment submissions</span></span>

<span data-ttu-id="e5054-195">[ **添付ファイル** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="e5054-196">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5054-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="e5054-197">**Date**</span></span>
- <span data-ttu-id="e5054-198">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="e5054-198">**Submission ID**</span></span>
- <span data-ttu-id="e5054-199">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-200">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-201">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-201">**Submission type**</span></span>
- <span data-ttu-id="e5054-202">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="e5054-203"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="e5054-204">Microsoft へのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="e5054-205">[レポートメッセージアドイン](enable-the-report-message-add-in.md)を展開した場合、またはユーザーが [Outlook on the web で組み込みのレポート](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)を使用している場合は、[ **ユーザーの送信** ] タブでどのユーザーがレポートしているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="e5054-206">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** の提出] に移動 \> **Submissions** します。</span><span class="sxs-lookup"><span data-stu-id="e5054-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions** .</span></span>

2. <span data-ttu-id="e5054-207">[ **ユーザーの送信** ] タブを選択し、[ **新しい送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5054-207">Select the **User submissions** tab, and then click **New submission** .</span></span>

<span data-ttu-id="e5054-208">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5054-209">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="e5054-209">**Submitted on**</span></span>
- <span data-ttu-id="e5054-210">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-211">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e5054-212">**Sender**</span></span>
- <span data-ttu-id="e5054-213">[ **Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="e5054-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-214">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-214">**Submission type**</span></span>

<span data-ttu-id="e5054-215"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="e5054-216">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることによって、 **送信者** によるフィルター処理を実行でき ![ ](../../media/scc-quarantine-refresh.png) ます。</span><span class="sxs-lookup"><span data-stu-id="e5054-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5054-217">Update</span><span class="sxs-lookup"><span data-stu-id="e5054-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5054-218">フィルター条件を変更するには、[ **送信者** ] ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="e5054-219">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="e5054-219">**Sender domain**</span></span>
- <span data-ttu-id="e5054-220">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="e5054-220">**Subject**</span></span>
- <span data-ttu-id="e5054-221">**提出者**</span><span class="sxs-lookup"><span data-stu-id="e5054-221">**Submitted by**</span></span>
- <span data-ttu-id="e5054-222">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-222">**Submission type**</span></span>
- <span data-ttu-id="e5054-223">[ **Sender IP (送信者の IP)** ]</span><span class="sxs-lookup"><span data-stu-id="e5054-223">**Sender IP**</span></span>

![ユーザー送信のフィルターオプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="e5054-225">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="e5054-226">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5054-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="e5054-227">カスタムメールボックスへのユーザー送信を表示する</span><span class="sxs-lookup"><span data-stu-id="e5054-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="e5054-228">ユーザーが報告したメッセージを受信するように [カスタムメールボックスを構成](user-submission.md)した **場合** は、レポートメールボックスに配信されたメッセージを表示して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5054-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="e5054-229">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** の提出] に移動 \> **Submissions** します。</span><span class="sxs-lookup"><span data-stu-id="e5054-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions** .</span></span>

2. <span data-ttu-id="e5054-230">[ **カスタムメールボックス** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="e5054-231">ページの下部にある [ **列のオプション** ] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="e5054-232">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="e5054-232">**Submitted on**</span></span>
- <span data-ttu-id="e5054-233">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-234">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e5054-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e5054-235">**Sender**</span></span>
- <span data-ttu-id="e5054-236">[ **Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="e5054-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="e5054-237">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="e5054-237">**Submission type**</span></span>

<span data-ttu-id="e5054-238">ページの上部に、開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで、 **送信** によってフィルター処理を行うことができます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="e5054-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="e5054-239">Update</span><span class="sxs-lookup"><span data-stu-id="e5054-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="e5054-240">結果をエクスポートするには、ページの上部にある [ **エクスポート** ] をクリックして、[ **グラフデータ** ] または [ **テーブル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5054-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table** .</span></span> <span data-ttu-id="e5054-241">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e5054-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="e5054-242">ユーザー送信の取り消し</span><span class="sxs-lookup"><span data-stu-id="e5054-242">Undo user submissions</span></span>

<span data-ttu-id="e5054-243">ユーザーが疑わしいメールをカスタムメールボックスに送信すると、ユーザーと管理者には送信を取り消すオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="e5054-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="e5054-244">ユーザーがメールを回復したい場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="e5054-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="e5054-245">カスタムメールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="e5054-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="e5054-246">ユーザーが報告したメッセージを Microsoft に送信せずに受信するようにカスタムメールボックスを構成した場合は、特定のメッセージを検索して Microsoft に送信して分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5054-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="e5054-247">これにより、ユーザーの送信が管理者の送信に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="e5054-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="e5054-248">[ **カスタムメールボックス** ] タブで、一覧からメッセージを選択し、[ **アクション** ] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="e5054-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="e5054-249">**クリーンなレポート**</span><span class="sxs-lookup"><span data-stu-id="e5054-249">**Report clean**</span></span>
- <span data-ttu-id="e5054-250">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="e5054-250">**Report phishing**</span></span>
- <span data-ttu-id="e5054-251">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="e5054-251">**Report malware**</span></span>
- <span data-ttu-id="e5054-252">**スパムの報告**</span><span class="sxs-lookup"><span data-stu-id="e5054-252">**Report spam**</span></span>

![[アクション] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
