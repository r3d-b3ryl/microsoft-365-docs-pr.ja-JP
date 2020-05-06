---
title: Office 365 での管理者による送信
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
description: 疑わしいメール、疑わしいフィッシングメール、スパム、およびその他の潜在的に有害なメッセージ、Url、およびその他の潜在的な問題がある電子メールをスキャンのために社内から Microsoft に送信する方法について説明します。
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034202"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="cfd05-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="cfd05-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="cfd05-104">Exchange Online にメールボックスを持つ Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンスセンターの送信ポータルを使用して、電子メールメッセージ、Url、および添付ファイルをスキャン用に Microsoft に提出することができます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="cfd05-105">電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="cfd05-106">メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="cfd05-107">他の方法で電子メールメッセージ、Url、および添付ファイルを Microsoft に提出する方法については、「 [microsoft にメッセージとファイルを報告](report-junk-email-messages-to-microsoft.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd05-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cfd05-108">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="cfd05-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cfd05-109"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cfd05-110">**送信**ページに直接移動するには、 <https://protection.office.com/reportsubmission>を使用します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="cfd05-111">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd05-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="cfd05-112">スパム対策ポリシーを追加、変更、および削除するには、**組織の管理**、**セキュリティ管理者**、または**セキュリティリーダー**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd05-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="cfd05-113">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfd05-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="cfd05-114">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「 [microsoft へのメッセージとファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd05-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="cfd05-115">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="cfd05-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="cfd05-116">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理** \> ] [**管理者の送信メッセージ**を**確認** \>します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="cfd05-117">表示された [**送信**] ページで、[**新しい送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="cfd05-118">次のセクションで説明されているように、メッセージ、URL、または添付ファイルを送信するための**新しい送信**ポップアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="cfd05-119">疑わしいメールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="cfd05-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="cfd05-120">[**オブジェクトの種類**] セクションで、[**電子メール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="cfd05-121">[**提出形式**] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="cfd05-122">**ネットワークメッセージ id**: これは、メッセージ内の、 **Exchange 組織のネットワークメッセージ id**ヘッダーで使用可能な GUID 値になります。</span><span class="sxs-lookup"><span data-stu-id="cfd05-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="cfd05-123">[**ファイル**]: [**ファイルの選択] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="cfd05-124">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="cfd05-125">[**受信者**] セクションで、ポリシーチェックの実行対象となる1人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="cfd05-126">ポリシーチェックは、ユーザーまたは組織のポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="cfd05-127">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="cfd05-128">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="cfd05-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="cfd05-129">**ブロックされている必要があり**ます。 [**スパム**、**フィッシング**、または**マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="cfd05-130">わからない場合は、適切な判断を行ってください。</span><span class="sxs-lookup"><span data-stu-id="cfd05-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="cfd05-131">送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="cfd05-132">1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="cfd05-133">[状態] リンクをクリックすると、送信に関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="cfd05-134">これには、ポリシーチェックの結果と rescan verdict が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="cfd05-135">メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="cfd05-136">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-136">When you're finished, click the **Submit** button.</span></span>

![URL の送信例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="cfd05-138">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="cfd05-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="cfd05-139">[**オブジェクトの種類**] セクションで、[ **URL**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="cfd05-140">表示されるボックスに、完全な URL (たとえば、 <https://www.fabrikam.com/marketing.html>) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="cfd05-141">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="cfd05-142">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="cfd05-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="cfd05-143">**ブロックされている必要があり**ます。 [**フィッシング**または**マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="cfd05-144">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-144">When you're finished, click the **Submit** button.</span></span>

![電子メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="cfd05-146">疑わしいファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="cfd05-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="cfd05-147">[**オブジェクトの種類**] セクションで、[**添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="cfd05-148">[**ファイルの選択] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-148">Click **Choose File**.</span></span> <span data-ttu-id="cfd05-149">開いたダイアログで、ファイルを見つけて選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="cfd05-150">[**送信理由**] セクションで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="cfd05-151">**ブロックされないようにする**</span><span class="sxs-lookup"><span data-stu-id="cfd05-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="cfd05-152">**ブロックされている必要があり**ます。**マルウェア**のみが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="cfd05-153">完了したら、[**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-153">When you're finished, click the **Submit** button.</span></span>

![添付ファイルの提出の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="cfd05-155">管理者の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-155">View admin submissions</span></span>

1. <span data-ttu-id="cfd05-156">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理** \> ] [**管理者の送信メッセージ**を**確認** \>します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="cfd05-157">[**送信**] ページが表示されたら、[**管理者の提出**] タブが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="cfd05-158">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックスに値を入力して [最新の情報に![更新]](../../media/scc-quarantine-refresh.png)ボタンをクリックすることで、**送信 ID**でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="cfd05-159">Update</span><span class="sxs-lookup"><span data-stu-id="cfd05-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="cfd05-160">フィルター条件を変更するには、[**提出 ID** ] ボタンをクリックして、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="cfd05-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="cfd05-161">**Sender**</span></span>
- <span data-ttu-id="cfd05-162">**Subject/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="cfd05-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="cfd05-163">**提出者**</span><span class="sxs-lookup"><span data-stu-id="cfd05-163">**Submitted by**</span></span>
- <span data-ttu-id="cfd05-164">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-164">**Submission type**</span></span>
- <span data-ttu-id="cfd05-165">**状態**</span><span class="sxs-lookup"><span data-stu-id="cfd05-165">**Status**</span></span>

![管理者送信のフィルターオプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="cfd05-167">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="cfd05-168">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="cfd05-169">グラフの下に、[**電子メール**] (既定)、[ **URL**]、および [**添付ファイル**] の3つのタブがあります。</span><span class="sxs-lookup"><span data-stu-id="cfd05-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="cfd05-170">管理者の電子メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-170">View admin email submissions</span></span>

<span data-ttu-id="cfd05-171">[**電子メール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-171">Click the **Email** tab.</span></span>

<span data-ttu-id="cfd05-172">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="cfd05-173">**日付**</span><span class="sxs-lookup"><span data-stu-id="cfd05-173">**Date**</span></span>
- <span data-ttu-id="cfd05-174">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="cfd05-174">**Submission ID**</span></span>
- <span data-ttu-id="cfd05-175">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-176">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="cfd05-177">**Sender**</span></span>
- <span data-ttu-id="cfd05-178">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="cfd05-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-179">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-179">**Submission type**</span></span>
- <span data-ttu-id="cfd05-180">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="cfd05-180">**Delivery reason**</span></span>
- <span data-ttu-id="cfd05-181">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-182">**コントロールの種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-182">**Control type**</span></span>
- <span data-ttu-id="cfd05-183">**コントロールソース**</span><span class="sxs-lookup"><span data-stu-id="cfd05-183">**Control source**</span></span>

  <span data-ttu-id="cfd05-184"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="cfd05-185">管理者 URL の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-185">View admin URL submissions</span></span>

<span data-ttu-id="cfd05-186">[ **URL** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-186">Click the **URL** tab.</span></span>

<span data-ttu-id="cfd05-187">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="cfd05-188">**日付**</span><span class="sxs-lookup"><span data-stu-id="cfd05-188">**Date**</span></span>
- <span data-ttu-id="cfd05-189">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="cfd05-189">**Submission ID**</span></span>
- <span data-ttu-id="cfd05-190">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-191">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="cfd05-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-192">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-192">**Submission type**</span></span>
- <span data-ttu-id="cfd05-193">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="cfd05-194"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="cfd05-195">管理者添付ファイルの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-195">View admin attachment submissions</span></span>

<span data-ttu-id="cfd05-196">[**添付ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="cfd05-197">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="cfd05-198">**日付**</span><span class="sxs-lookup"><span data-stu-id="cfd05-198">**Date**</span></span>
- <span data-ttu-id="cfd05-199">**送信 ID**</span><span class="sxs-lookup"><span data-stu-id="cfd05-199">**Submission ID**</span></span>
- <span data-ttu-id="cfd05-200">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-201">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-202">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-202">**Submission type**</span></span>
- <span data-ttu-id="cfd05-203">**現状**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="cfd05-204"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="cfd05-205">Microsoft へのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="cfd05-206">[レポートメッセージアドイン](enable-the-report-message-add-in.md)を展開した場合、またはユーザーが[Outlook on the web で組み込みのレポート](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)を使用している場合は、[**ユーザーの送信**] タブでどのユーザーがレポートしているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="cfd05-207">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理** \> ] [**管理者の送信メッセージ**を**確認** \>します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="cfd05-208">表示された [**送信**] ページで、[**ユーザーの送信**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="cfd05-209">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="cfd05-210">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="cfd05-210">**Submitted on**</span></span>
- <span data-ttu-id="cfd05-211">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-212">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="cfd05-213">**Sender**</span></span>
- <span data-ttu-id="cfd05-214">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="cfd05-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-215">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-215">**Submission type**</span></span>

<span data-ttu-id="cfd05-216"><sup>\*</sup>この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="cfd05-217">ページの上部に、[開始日]、[終了日]、[(既定)] の順に入力し、ボックス**Sender**に値を入力して [最新の情報![に更新](../../media/scc-quarantine-refresh.png)] ボタンをクリックすることによって、送信者によるフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="cfd05-218">Update</span><span class="sxs-lookup"><span data-stu-id="cfd05-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="cfd05-219">フィルター条件を変更するには、[**送信者**] ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="cfd05-220">**送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cfd05-220">**Sender domain**</span></span>
- <span data-ttu-id="cfd05-221">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="cfd05-221">**Subject**</span></span>
- <span data-ttu-id="cfd05-222">**提出者**</span><span class="sxs-lookup"><span data-stu-id="cfd05-222">**Submitted by**</span></span>
- <span data-ttu-id="cfd05-223">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-223">**Submission type**</span></span>
- <span data-ttu-id="cfd05-224">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="cfd05-224">**Sender IP**</span></span>

![ユーザー送信のフィルターオプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="cfd05-226">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="cfd05-227">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="cfd05-228">カスタムメールボックスへのユーザー送信を表示する</span><span class="sxs-lookup"><span data-stu-id="cfd05-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="cfd05-229">ユーザーが報告したメッセージを受信するように[カスタムメールボックスを構成](user-submission.md)した場合は、レポートメールボックスに配信されたメッセージを表示して送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="cfd05-230">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理** \> ] [**管理者の送信メッセージ**を**確認** \>します] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="cfd05-231">表示された [**送信**] ページで、[**カスタムメールボックス**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfd05-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="cfd05-232">ページの下部にある [**列のオプション**] ボタンをクリックすると、ビューの列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="cfd05-233">**送信されたもの**</span><span class="sxs-lookup"><span data-stu-id="cfd05-233">**Submitted on**</span></span>
- <span data-ttu-id="cfd05-234">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-235">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cfd05-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="cfd05-236">**Sender**</span></span>
- <span data-ttu-id="cfd05-237">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="cfd05-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="cfd05-238">**送信の種類**</span><span class="sxs-lookup"><span data-stu-id="cfd05-238">**Submission type**</span></span>

<span data-ttu-id="cfd05-239">ページの上部に、開始日と終了日を入力し、ボックスに値を入力して [最新**Submitted by**の情報に更新] ボタン![](../../media/scc-quarantine-refresh.png)をクリックすることで、送信によってフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="cfd05-240">Update</span><span class="sxs-lookup"><span data-stu-id="cfd05-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="cfd05-241">結果をエクスポートするには、ページの上部にある [**エクスポート**] をクリックして、[**グラフデータ**] または [**テーブル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="cfd05-242">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cfd05-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="cfd05-243">カスタムメールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="cfd05-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="cfd05-244">ユーザーが報告したメッセージを Microsoft に送信せずに受信するようにカスタムメールボックスを構成した場合は、特定のメッセージを検索して Microsoft に送信して分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="cfd05-245">これにより、ユーザーの送信が管理者の送信に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="cfd05-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="cfd05-246">[**カスタムメールボックス**] タブで、一覧からメッセージを選択し、[**アクション**] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="cfd05-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="cfd05-247">**クリーンなレポート**</span><span class="sxs-lookup"><span data-stu-id="cfd05-247">**Report clean**</span></span>
- <span data-ttu-id="cfd05-248">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="cfd05-248">**Report phishing**</span></span>
- <span data-ttu-id="cfd05-249">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="cfd05-249">**Report malware**</span></span>
- <span data-ttu-id="cfd05-250">**スパムの報告**</span><span class="sxs-lookup"><span data-stu-id="cfd05-250">**Report spam**</span></span>

![[アクション] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
