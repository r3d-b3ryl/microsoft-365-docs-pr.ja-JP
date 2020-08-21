---
title: 管理者の送信
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの申請ポータルを使用して、不審なメール、必要なフィッシング メール、スパム、スキャンのために Microsoft に有害な可能性のあるメッセージ、URL、ファイルを送信する方法を学習できます。
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845968"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="0487f-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="0487f-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="0487f-104">Exchange Online にメールボックスがある Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの提出ポータルを使用して、スキャンのメール メッセージ、URL、および添付ファイルを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0487f-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="0487f-105">メールを送信すると、受信メールをテナントに許可した可能性のあるポリシーに関する情報の他に、メール内の URL や添付ファイルが調べられます。</span><span class="sxs-lookup"><span data-stu-id="0487f-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="0487f-106">メールが許可されている場合があるポリシーには、個々のユーザーの差出人セーフ リストや、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) などのテナント レベル ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0487f-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="0487f-107">電子メール メッセージ、URL、および添付ファイルを Microsoft に送信するその他の方法については、「レポート [メッセージとファイルを Microsoft に送信する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="0487f-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0487f-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0487f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0487f-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0487f-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0487f-110">[Submission] (提出) ページに **直接移動するには** 、次を使用します <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="0487f-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="0487f-111">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0487f-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="0487f-112">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0487f-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0487f-113">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="0487f-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0487f-114">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="0487f-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0487f-115">提出ポータルに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0487f-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0487f-116">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="0487f-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0487f-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="0487f-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="0487f-118">ユーザーがメッセージおよびファイルを Microsoft に送信する方法の詳細については、「レポート メッセージと [ファイルを Microsoft に送信する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="0487f-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="0487f-119">不審な内容を Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="0487f-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="0487f-120">セキュリティ/コンプライアンス &で、[脅威**Threat management**の管理 \> **の送信] に移動**し、管理者の [送信]**タブで送信中であることを確認**し、[新規送信] を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0487f-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="0487f-121">表示 **される新しい** 申請ポップアップを使用して、次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="0487f-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="0487f-122">問題のないメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="0487f-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="0487f-123">[Object **Type] セクションで\*\*\*\*、[Email] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="0487f-124">[Submission **format] (提出の** 形式) セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0487f-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="0487f-125">**ネットワーク メッセージ ID:** これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id ヘッダー内で取得** できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="0487f-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="0487f-126">**[File]:**[Choose **file] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0487f-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="0487f-127">開いたダイアログで,.eml ファイルまたは .msg ファイルを探して選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="0487f-128">[受信者 **]** セクションで、ポリシー チェックの実行に対して 1 名以上の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="0487f-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="0487f-129">ポリシー チェックでは、ユーザー ポリシーまたは組織ポリシーに合格したメールのバイパスが確認されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="0487f-130">[送信 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="0487f-131">**ブロックされていないべきか**</span><span class="sxs-lookup"><span data-stu-id="0487f-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="0487f-132">**スパム、フィッシ\*\*\*\*ング、** マルウェア**を**選択**します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="0487f-133">不満の場合は、最善のジュージングを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0487f-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="0487f-134">提出時にポリシーが必要なためフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="0487f-135">1 つ以上のポリシーが渡されないためにフィルターがバイパスしなかった場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="0487f-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="0487f-136">[状態] リンクをクリックすると、提出に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="0487f-137">これには、ポリシー チェックの結果と、再スキャンの確認結果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0487f-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="0487f-138">Office 365 ATP フル フィルター スタックを介した電子メールは再度実行されませんが、メール、URL、ファイルの特定の属性に基づいて部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="0487f-139">完了したら、送信ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="0487f-139">When you're finished, click the **Submit** button.</span></span>

![URL の送信の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="0487f-141">Microsoft に対する必要な URL の送信</span><span class="sxs-lookup"><span data-stu-id="0487f-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="0487f-142">[ **オブジェクトの種類] セクション** で **、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="0487f-143">表示されるボックスに、完全な URL (たとえば、) を入力します <https://www.fabrikam.com/marketing.html> 。</span><span class="sxs-lookup"><span data-stu-id="0487f-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="0487f-144">[送信 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="0487f-145">**ブロックされていないべきか**</span><span class="sxs-lookup"><span data-stu-id="0487f-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="0487f-146">**ブロックされる: フィ**ッ **シングまたはマルウェアを** 選 **います**。</span><span class="sxs-lookup"><span data-stu-id="0487f-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="0487f-147">完了したら、送信ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="0487f-147">When you're finished, click the **Submit** button.</span></span>

![メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="0487f-149">Microsoft に対して必要なファイルを提出する</span><span class="sxs-lookup"><span data-stu-id="0487f-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="0487f-150">[Object **Type] セクションで\*\*\*\*、[Attachment] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="0487f-151">[ **ファイルの選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0487f-151">Click **Choose File**.</span></span> <span data-ttu-id="0487f-152">開いたダイアログで、ファイルを検索して選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="0487f-153">[送信 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="0487f-154">**ブロックされていないべきか**</span><span class="sxs-lookup"><span data-stu-id="0487f-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="0487f-155">**ブロックされている必要があるのは、\*\*\*\*マルウェアが**この選択肢の 1 つで、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="0487f-156">完了したら、送信ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="0487f-156">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの送信の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="0487f-158">管理者の申請を表示する</span><span class="sxs-lookup"><span data-stu-id="0487f-158">View admin submissions</span></span>

<span data-ttu-id="0487f-159">セキュリティ/コンプライアンス &で、[脅威**Threat management**の管理 \> **の送信] に移動**し、管理者の [送信]**タブで送信中であることを確認**し、[新規送信] を**クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0487f-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="0487f-160">ページの上部で、開始日、終了日を入力できます。(既定では) [サブミッション **ID]** (各提出に割り当てられている GUID 値) でフィルター処理するには、ボックスに値を入力して ![ [更新] ボタンをクリックします ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="0487f-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="0487f-161">Update</span><span class="sxs-lookup"><span data-stu-id="0487f-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="0487f-162">フィルター条件を変更するには、[Submission **ID] ボタンをクリック** し、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="0487f-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0487f-163">**Sender**</span></span>
- <span data-ttu-id="0487f-164">**サブジェクト/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="0487f-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="0487f-165">**送信元**</span><span class="sxs-lookup"><span data-stu-id="0487f-165">**Submitted by**</span></span>
- <span data-ttu-id="0487f-166">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-166">**Submission type**</span></span>
- <span data-ttu-id="0487f-167">**状態**</span><span class="sxs-lookup"><span data-stu-id="0487f-167">**Status**</span></span>

![管理者の申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="0487f-169">結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="0487f-170">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0487f-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="0487f-171">グラフの下には、電子メール (既定 **)、URL、\*\*\*\*添付**ファイルの 3 つのタブ**があります**。</span><span class="sxs-lookup"><span data-stu-id="0487f-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="0487f-172">管理者メールの提出を表示する</span><span class="sxs-lookup"><span data-stu-id="0487f-172">View admin email submissions</span></span>

<span data-ttu-id="0487f-173">[電子メール **] タブを** クリックします。</span><span class="sxs-lookup"><span data-stu-id="0487f-173">Click the **Email** tab.</span></span>

<span data-ttu-id="0487f-174">ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0487f-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="0487f-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="0487f-175">**Date**</span></span>
- <span data-ttu-id="0487f-176">**提出 ID**: 各申請に割り当てられる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="0487f-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="0487f-177">**送信元**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-178">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0487f-179">**Sender**</span></span>
- <span data-ttu-id="0487f-180">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="0487f-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-181">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-181">**Submission type**</span></span>
- <span data-ttu-id="0487f-182">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="0487f-182">**Delivery reason**</span></span>
- <span data-ttu-id="0487f-183">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-184">**コントロールの種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-184">**Control type**</span></span>
- <span data-ttu-id="0487f-185">**コントロール ソース**</span><span class="sxs-lookup"><span data-stu-id="0487f-185">**Control source**</span></span>

  <span data-ttu-id="0487f-186"><sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="0487f-187">管理 URL の提出の表示</span><span class="sxs-lookup"><span data-stu-id="0487f-187">View admin URL submissions</span></span>

<span data-ttu-id="0487f-188">**[URL] タブを**クリックします。</span><span class="sxs-lookup"><span data-stu-id="0487f-188">Click the **URL** tab.</span></span>

<span data-ttu-id="0487f-189">ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0487f-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="0487f-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="0487f-190">**Date**</span></span>
- <span data-ttu-id="0487f-191">**Submission ID**</span><span class="sxs-lookup"><span data-stu-id="0487f-191">**Submission ID**</span></span>
- <span data-ttu-id="0487f-192">**送信元**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-193">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="0487f-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-194">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-194">**Submission type**</span></span>
- <span data-ttu-id="0487f-195">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="0487f-196"><sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="0487f-197">管理者の添付ファイルの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="0487f-197">View admin attachment submissions</span></span>

<span data-ttu-id="0487f-198">[添付ファイル **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0487f-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="0487f-199">ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0487f-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="0487f-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="0487f-200">**Date**</span></span>
- <span data-ttu-id="0487f-201">**Submission ID**</span><span class="sxs-lookup"><span data-stu-id="0487f-201">**Submission ID**</span></span>
- <span data-ttu-id="0487f-202">**送信元**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-203">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-204">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-204">**Submission type**</span></span>
- <span data-ttu-id="0487f-205">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="0487f-206"><sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="0487f-207">Microsoft へのユーザーの申請を表示する</span><span class="sxs-lookup"><span data-stu-id="0487f-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="0487f-208">迷惑メール報告アドインを展開 [した場合、またはユーザーが](enable-the-report-message-add-in.md)Outlook on the web の組み込みのレポートを使用している [場合は](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)、[ユーザーの送信] タブで、どのユーザーが報告を **行うかを確認** できます。</span><span class="sxs-lookup"><span data-stu-id="0487f-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="0487f-209">セキュリティ コンプライアンス センター&、[脅威管理 **の送信]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="0487f-210">[User **submissions] (ユーザーの提出) タブを** 選び、[New submission] (新 **しい申請) をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0487f-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="0487f-211">ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0487f-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="0487f-212">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="0487f-212">**Submitted on**</span></span>
- <span data-ttu-id="0487f-213">**送信元**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-214">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0487f-215">**Sender**</span></span>
- <span data-ttu-id="0487f-216">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="0487f-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-217">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-217">**Submission type**</span></span>

<span data-ttu-id="0487f-218"><sup>\*</sup> この値をクリックすると、詳細な情報がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="0487f-219">ページの上部に表示されているのは、開始日、終了日を入力できます。また、(既定の場合) ボックスに **値を入力して** [更新] ボタンをクリックすると、送信者 ![ によってフィルター処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="0487f-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="0487f-220">Update</span><span class="sxs-lookup"><span data-stu-id="0487f-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="0487f-221">フィルター条件を変更するには、[送信者] **ボタンをクリック** し、次の値のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="0487f-222">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0487f-222">**Sender domain**</span></span>
- <span data-ttu-id="0487f-223">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0487f-223">**Subject**</span></span>
- <span data-ttu-id="0487f-224">**送信元**</span><span class="sxs-lookup"><span data-stu-id="0487f-224">**Submitted by**</span></span>
- <span data-ttu-id="0487f-225">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-225">**Submission type**</span></span>
- <span data-ttu-id="0487f-226">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="0487f-226">**Sender IP**</span></span>

![ユーザー申請のフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="0487f-228">結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="0487f-229">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0487f-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="0487f-230">カスタム メールボックスへのユーザー送信を表示する</span><span class="sxs-lookup"><span data-stu-id="0487f-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="0487f-231">ユーザーから報告された [メッセージを受信するように](user-submission.md) カスタム メールボックスを構成した場合は、レポート メールボックスに配信されたメッセージを表示して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="0487f-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="0487f-232">セキュリティ コンプライアンス センター&、[脅威管理 **の送信]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="0487f-233">[カスタム メールボックス **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="0487f-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="0487f-234">ページの下部 **にある [列]** オプション ボタンをクリックして、ビューで列を追加したり、ビューから列を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0487f-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="0487f-235">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="0487f-235">**Submitted on**</span></span>
- <span data-ttu-id="0487f-236">**送信元**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-237">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0487f-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0487f-238">**Sender**</span></span>
- <span data-ttu-id="0487f-239">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="0487f-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="0487f-240">**提出の種類**</span><span class="sxs-lookup"><span data-stu-id="0487f-240">**Submission type**</span></span>

<span data-ttu-id="0487f-241">ページの上部で、開始日、終了日を入力できます。また、[更新] ボタンをクリックして **[送信** 日] に値を ![ 入力することでフィルター処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="0487f-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="0487f-242">Update</span><span class="sxs-lookup"><span data-stu-id="0487f-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="0487f-243">結果をエクスポートするには、ページの **上** 部にある [エクスポート] をクリックし、[グラフ データまたは **テーブル] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0487f-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="0487f-244">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0487f-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="0487f-245">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="0487f-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="0487f-246">Microsoft にメッセージを送信せずにユーザーから報告されたメッセージを取得するようにカスタム メールボックスを構成した場合は、特定のメッセージを検索して分析用に Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0487f-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="0487f-247">これにより、ユーザーの申請が効率的に管理者の申請に移動されます。</span><span class="sxs-lookup"><span data-stu-id="0487f-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="0487f-248">カスタム メールボックス **タブで** 、一覧からメッセージを選択し、[ **操作]** ボタンをクリックして、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0487f-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="0487f-249">**レポートのクリーンなレポート**</span><span class="sxs-lookup"><span data-stu-id="0487f-249">**Report clean**</span></span>
- <span data-ttu-id="0487f-250">**レポート フィッシング**</span><span class="sxs-lookup"><span data-stu-id="0487f-250">**Report phishing**</span></span>
- <span data-ttu-id="0487f-251">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="0487f-251">**Report malware**</span></span>
- <span data-ttu-id="0487f-252">**迷惑メール報告**</span><span class="sxs-lookup"><span data-stu-id="0487f-252">**Report spam**</span></span>

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
