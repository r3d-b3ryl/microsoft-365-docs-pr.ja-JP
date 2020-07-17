---
title: 管理者による送信
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターの送信ポータルを使用して、疑わしいメール、疑わしいフィッシングメール、スパム、その他の潜在的な有害なメッセージ、Url、およびその他の潜在的な問題を報告する方法について説明します。
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726850"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5dd46-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="5dd46-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="5dd46-104">Exchange Online のメールボックスを使用する Microsoft 365 の組織では、管理者はセキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、および添付ファイルをスキャン用に Microsoft に提出できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5dd46-105">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="5dd46-106">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="5dd46-107">他の方法で電子メールメッセージ、Url、および添付ファイルを Microsoft に提出する方法については、「 [microsoft にメッセージとファイルを報告](report-junk-email-messages-to-microsoft.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd46-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5dd46-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5dd46-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5dd46-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5dd46-110">**送信**ページに直接移動するには、を使用 <https://protection.office.com/reportsubmission> します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="5dd46-111">このトピックの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd46-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="5dd46-112">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd46-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="5dd46-113">[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**組織管理**または**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="5dd46-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="5dd46-114">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**または**検疫の管理**。</span><span class="sxs-lookup"><span data-stu-id="5dd46-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="5dd46-115">送信ポータルへの読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dd46-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="5dd46-116">[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**セキュリティリーダ**。</span><span class="sxs-lookup"><span data-stu-id="5dd46-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="5dd46-117">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**表示のみの組織の管理**。</span><span class="sxs-lookup"><span data-stu-id="5dd46-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="5dd46-118">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft へのメッセージとファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd46-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5dd46-119">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="5dd46-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5dd46-120">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**] [ \> **Review** \> **管理者の送信メッセージ**を確認します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="5dd46-121">表示された [**送信**] ページで、[**新しい送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="5dd46-122">次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信するための**新しい送信**ポップアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5dd46-123">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="5dd46-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5dd46-124">[**オブジェクトの種類**] セクションで、[**電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="5dd46-125">[**提出形式**] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="5dd46-126">**ネットワークメッセージ id**: これは、メッセージ内の、 **Exchange 組織のネットワークメッセージ id**ヘッダーで使用可能な GUID 値になります。</span><span class="sxs-lookup"><span data-stu-id="5dd46-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="5dd46-127">[**ファイル**]: [**ファイルの選択] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="5dd46-128">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="5dd46-129">[**受信者**] セクションで、ポリシーチェックの実行対象となる1人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="5dd46-130">ポリシーチェックは、ユーザーまたは組織のポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="5dd46-131">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5dd46-132">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="5dd46-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5dd46-133">**ブロックされている必要があり**ます。 [**スパム**、**フィッシング**、または**マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="5dd46-134">わからない場合は、適切な判断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="5dd46-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="5dd46-135">送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="5dd46-136">1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="5dd46-137">[状態] リンクをクリックすると、送信に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="5dd46-138">これには、ポリシーチェックの結果と rescan verdict が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="5dd46-139">メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="5dd46-140">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-140">When you're finished, click the **Submit** button.</span></span>

![URL の送信例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5dd46-142">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="5dd46-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5dd46-143">[**オブジェクトの種類**] セクションで、[ **URL**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="5dd46-144">表示されるボックスに、完全な URL (たとえば、) を入力し <https://www.fabrikam.com/marketing.html> ます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="5dd46-145">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5dd46-146">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="5dd46-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5dd46-147">**ブロックされている必要があり**ます。 [**フィッシング**または**マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="5dd46-148">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-148">When you're finished, click the **Submit** button.</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="5dd46-150">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="5dd46-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="5dd46-151">[**オブジェクトの種類**] セクションで、[**添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="5dd46-152">[**ファイルの選択] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-152">Click **Choose File**.</span></span> <span data-ttu-id="5dd46-153">開いたダイアログで、ファイルを見つけて選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5dd46-154">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5dd46-155">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="5dd46-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5dd46-156">**ブロックされている必要があり**ます。**マルウェア**のみが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="5dd46-157">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-157">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの提出の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="5dd46-159">管理者の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-159">View admin submissions</span></span>

1. <span data-ttu-id="5dd46-160">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**] [ \> **Review** \> **管理者の送信メッセージ**を確認します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="5dd46-161">[**送信**] ページが表示されたら、[**管理者の提出**] タブが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="5dd46-162">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで、**送信 ID**でフィルター処理でき ![ ](../../media/scc-quarantine-refresh.png) ます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5dd46-163">Update</span><span class="sxs-lookup"><span data-stu-id="5dd46-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5dd46-164">フィルター条件を変更するには、[**提出 ID** ] ボタンをクリックして、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="5dd46-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dd46-165">**Sender**</span></span>
- <span data-ttu-id="5dd46-166">**Subject/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="5dd46-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="5dd46-167">**提出者**</span><span class="sxs-lookup"><span data-stu-id="5dd46-167">**Submitted by**</span></span>
- <span data-ttu-id="5dd46-168">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-168">**Submission type**</span></span>
- <span data-ttu-id="5dd46-169">**状態**</span><span class="sxs-lookup"><span data-stu-id="5dd46-169">**Status**</span></span>

![管理者送信のフィルターオプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="5dd46-171">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5dd46-172">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="5dd46-173">グラフの下に、[**電子メール**] (既定)、[ **URL**]、および [**添付ファイル**] の3つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="5dd46-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="5dd46-174">管理者の電子メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-174">View admin email submissions</span></span>

<span data-ttu-id="5dd46-175">[**電子メール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-175">Click the **Email** tab.</span></span>

<span data-ttu-id="5dd46-176">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5dd46-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dd46-177">**Date**</span></span>
- <span data-ttu-id="5dd46-178">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="5dd46-178">**Submission ID**</span></span>
- <span data-ttu-id="5dd46-179">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-180">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dd46-181">**Sender**</span></span>
- <span data-ttu-id="5dd46-182">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5dd46-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-183">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-183">**Submission type**</span></span>
- <span data-ttu-id="5dd46-184">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="5dd46-184">**Delivery reason**</span></span>
- <span data-ttu-id="5dd46-185">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-186">**コントロールの種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-186">**Control type**</span></span>
- <span data-ttu-id="5dd46-187">**コントロールソース**</span><span class="sxs-lookup"><span data-stu-id="5dd46-187">**Control source**</span></span>

  <span data-ttu-id="5dd46-188"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="5dd46-189">管理者 URL の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-189">View admin URL submissions</span></span>

<span data-ttu-id="5dd46-190">[ **URL** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-190">Click the **URL** tab.</span></span>

<span data-ttu-id="5dd46-191">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5dd46-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dd46-192">**Date**</span></span>
- <span data-ttu-id="5dd46-193">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="5dd46-193">**Submission ID**</span></span>
- <span data-ttu-id="5dd46-194">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-195">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5dd46-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-196">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-196">**Submission type**</span></span>
- <span data-ttu-id="5dd46-197">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5dd46-198"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="5dd46-199">管理者添付ファイルの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-199">View admin attachment submissions</span></span>

<span data-ttu-id="5dd46-200">[**添付ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="5dd46-201">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5dd46-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dd46-202">**Date**</span></span>
- <span data-ttu-id="5dd46-203">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="5dd46-203">**Submission ID**</span></span>
- <span data-ttu-id="5dd46-204">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-205">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-206">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-206">**Submission type**</span></span>
- <span data-ttu-id="5dd46-207">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5dd46-208"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5dd46-209">Microsoft へのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="5dd46-210">[レポートメッセージアドイン](enable-the-report-message-add-in.md)を展開した場合、またはユーザーが[Outlook on the web で組み込みのレポート](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)を使用している場合は、[**ユーザーの送信**] タブでどのユーザーがレポートしているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="5dd46-211">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**] [ \> **Review** \> **管理者の送信メッセージ**を確認します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="5dd46-212">表示された [**送信**] ページで、[**ユーザーの送信**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="5dd46-213">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5dd46-214">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="5dd46-214">**Submitted on**</span></span>
- <span data-ttu-id="5dd46-215">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-216">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dd46-217">**Sender**</span></span>
- <span data-ttu-id="5dd46-218">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5dd46-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-219">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-219">**Submission type**</span></span>

<span data-ttu-id="5dd46-220"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="5dd46-221">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることによって、**送信者**によるフィルター処理を実行でき ![ ](../../media/scc-quarantine-refresh.png) ます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5dd46-222">Update</span><span class="sxs-lookup"><span data-stu-id="5dd46-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5dd46-223">フィルター条件を変更するには、[**送信者**] ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="5dd46-224">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dd46-224">**Sender domain**</span></span>
- <span data-ttu-id="5dd46-225">**件名**</span><span class="sxs-lookup"><span data-stu-id="5dd46-225">**Subject**</span></span>
- <span data-ttu-id="5dd46-226">**提出者**</span><span class="sxs-lookup"><span data-stu-id="5dd46-226">**Submitted by**</span></span>
- <span data-ttu-id="5dd46-227">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-227">**Submission type**</span></span>
- <span data-ttu-id="5dd46-228">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="5dd46-228">**Sender IP**</span></span>

![ユーザー送信のフィルターオプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="5dd46-230">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5dd46-231">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="5dd46-232">カスタムメールボックスへのユーザー送信を表示する</span><span class="sxs-lookup"><span data-stu-id="5dd46-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="5dd46-233">ユーザーが報告したメッセージを受信するように[カスタムメールボックスを構成](user-submission.md)した場合は、レポートメールボックスに配信されたメッセージを表示して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="5dd46-234">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**] [ \> **Review** \> **管理者の送信メッセージ**を確認します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="5dd46-235">表示された [**送信**] ページで、[**カスタムメールボックス**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dd46-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="5dd46-236">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5dd46-237">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="5dd46-237">**Submitted on**</span></span>
- <span data-ttu-id="5dd46-238">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-239">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dd46-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dd46-240">**Sender**</span></span>
- <span data-ttu-id="5dd46-241">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="5dd46-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5dd46-242">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="5dd46-242">**Submission type**</span></span>

<span data-ttu-id="5dd46-243">ページの上部に、開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで、**送信**によってフィルター処理を行うことができます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="5dd46-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5dd46-244">Update</span><span class="sxs-lookup"><span data-stu-id="5dd46-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5dd46-245">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5dd46-246">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5dd46-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5dd46-247">カスタムメールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="5dd46-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5dd46-248">ユーザーが報告したメッセージを Microsoft に送信せずに受信するようにカスタムメールボックスを構成した場合は、特定のメッセージを検索して Microsoft に送信して分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5dd46-249">これにより、ユーザーの送信が管理者の送信に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="5dd46-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5dd46-250">[**カスタムメールボックス**] タブで、一覧からメッセージを選択し、[**アクション**] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="5dd46-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="5dd46-251">**クリーンなレポート**</span><span class="sxs-lookup"><span data-stu-id="5dd46-251">**Report clean**</span></span>
- <span data-ttu-id="5dd46-252">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="5dd46-252">**Report phishing**</span></span>
- <span data-ttu-id="5dd46-253">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="5dd46-253">**Report malware**</span></span>
- <span data-ttu-id="5dd46-254">**スパムの報告**</span><span class="sxs-lookup"><span data-stu-id="5dd46-254">**Report spam**</span></span>

![[アクション] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
