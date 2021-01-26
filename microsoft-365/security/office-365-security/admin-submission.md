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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターの送信ポータルを使用して、疑わしいメール、フィッシング詐欺の疑いがあるメール、スパム、その他の有害な可能性のあるメッセージ、URL、ファイルをスキャンのために Microsoft に送信する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976605"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="20dec-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="20dec-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="20dec-104">Exchange Online にメールボックスがある Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの送信ポータルを使用して、メール メッセージ、URL、および添付ファイルをスキャンのために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="20dec-105">電子メール メッセージを送信すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="20dec-106">**電子メール認証チェック**: メール認証が配信された際に、電子メール認証が通過または失敗したかどうかに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="20dec-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="20dec-107">**ポリシー ヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの条件を上書きします。</span><span class="sxs-lookup"><span data-stu-id="20dec-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="20dec-108">**ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。</span><span class="sxs-lookup"><span data-stu-id="20dec-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="20dec-109">**成績分析**: メッセージが悪意のあるものかどうかを確認するために、人間の成績を確認します。</span><span class="sxs-lookup"><span data-stu-id="20dec-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20dec-110">ペイロード評価/デトレーションとグレードの分析は、すべてのテナントで行われるというではありません。</span><span class="sxs-lookup"><span data-stu-id="20dec-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="20dec-111">データがコンプライアンスの目的でテナントの境界を離れるはずではない場合、情報が組織外に出るのをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="20dec-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="20dec-112">電子メール メッセージ、URL、および添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="20dec-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20dec-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="20dec-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20dec-114"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="20dec-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20dec-115">[提出] ページに直接 **移動するには** 、次のコマンドを使用します <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="20dec-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="20dec-116">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="20dec-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="20dec-117">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="20dec-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="20dec-118">Exchange Online **での**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="20dec-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="20dec-119">この役割グループのメンバーシップは、この記事で[](#view-user-submissions-to-the-custom-mailbox)後述するように、カスタム メールボックスへのユーザー送信を表示するために必要です。</span><span class="sxs-lookup"><span data-stu-id="20dec-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="20dec-120">ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する [」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="20dec-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="20dec-121">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="20dec-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="20dec-122">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリック \> **します**。 </span><span class="sxs-lookup"><span data-stu-id="20dec-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="20dec-123">次 **のセクションで** 説明するように、メッセージ、URL、または添付ファイルを送信するために表示される新しい送信のフライアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="20dec-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="20dec-124">Microsoft に問題があるメールを送信する</span><span class="sxs-lookup"><span data-stu-id="20dec-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="20dec-125">[オブジェクトの **種類] セクションで** 、[電子メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="20dec-126">[提出 **形式] セクション** で、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="20dec-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="20dec-127">**ネットワーク** メッセージ ID : これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="20dec-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="20dec-128">**[ファイル**]: [ファイルの **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20dec-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="20dec-129">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="20dec-130">Office 365 プラン 1 またはプラン 2 の Defender を使用する管理者は、30 日間の古いメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="20dec-131">その他の管理者は 7 日間のみ戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20dec-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="20dec-132">[ **受信者] セクション** で、ポリシー チェックを実行する 1 人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="20dec-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="20dec-133">ポリシー チェックでは、ユーザーまたは組織のポリシーが原因でメールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="20dec-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="20dec-134">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="20dec-135">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="20dec-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="20dec-136">**ブロックされている必要があります**: **スパム**、フィッシング **、またはマルウェア** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="20dec-137">確信が持てない場合は、最善の判断を下してください。</span><span class="sxs-lookup"><span data-stu-id="20dec-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="20dec-138">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-138">When you're finished, click the **Submit** button.</span></span>

   ![URL 送信の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="20dec-140">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="20dec-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="20dec-141">[オブジェクトの **種類] セクションで\*\*\*\*、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="20dec-142">表示されるボックスに、完全な URL (たとえば) を入力します `https://www.fabrikam.com/marketing.html` 。</span><span class="sxs-lookup"><span data-stu-id="20dec-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="20dec-143">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="20dec-144">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="20dec-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="20dec-145">**ブロックされている必要があります**: [フィッシングまたは **マルウェア] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="20dec-146">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-146">When you're finished, click the **Submit** button.</span></span>

   ![メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="20dec-148">疑わしいファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="20dec-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="20dec-149">[オブジェクトの **種類] セクションで** 、[添付ファイル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="20dec-150">[ファイル **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20dec-150">Click **Choose File**.</span></span> <span data-ttu-id="20dec-151">開いたダイアログで、ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="20dec-152">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="20dec-153">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="20dec-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="20dec-154">**ブロックされている必要があります**: **マルウェア** だけが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="20dec-155">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-155">When you're finished, click the **Submit** button.</span></span>

   ![添付ファイルの送信の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="20dec-157">管理者の提出を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-157">View admin submissions</span></span>

<span data-ttu-id="20dec-158">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリックします \> 。  </span><span class="sxs-lookup"><span data-stu-id="20dec-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="20dec-159">ページの上部には、開始日、終了日を入力できます。また、既定では、ボックスに値を入力して [更新] ボタンをクリックすることで、提出 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="20dec-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="20dec-160">Update</span><span class="sxs-lookup"><span data-stu-id="20dec-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="20dec-161">フィルター条件を変更するには **、[Submission ID]** ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="20dec-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="20dec-162">**Sender**</span></span>
- <span data-ttu-id="20dec-163">**件名/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="20dec-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="20dec-164">**提出者**</span><span class="sxs-lookup"><span data-stu-id="20dec-164">**Submitted by**</span></span>
- <span data-ttu-id="20dec-165">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-165">**Submission type**</span></span>
- <span data-ttu-id="20dec-166">**状態**</span><span class="sxs-lookup"><span data-stu-id="20dec-166">**Status**</span></span>

![管理者の申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="20dec-168">結果をエクスポートするには、ページ上部の **[** エクスポート] をクリックし、[グラフ データ] **または** [テーブル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="20dec-169">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="20dec-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="20dec-170">グラフの下には、メール (既定)、URL、添付ファイルの 3 つのタブ **があります**。</span><span class="sxs-lookup"><span data-stu-id="20dec-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="20dec-171">管理者のメールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-171">View admin email submissions</span></span>

<span data-ttu-id="20dec-172">[電子メール **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-172">Click the **Email** tab.</span></span>

<span data-ttu-id="20dec-173">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="20dec-174">**日付**</span><span class="sxs-lookup"><span data-stu-id="20dec-174">**Date**</span></span>
- <span data-ttu-id="20dec-175">**提出 ID**: すべての申請に割り当てられる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="20dec-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="20dec-176">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-177">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="20dec-178">**Sender**</span></span>
- <span data-ttu-id="20dec-179">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="20dec-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-180">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-180">**Submission type**</span></span>
- <span data-ttu-id="20dec-181">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="20dec-181">**Delivery reason**</span></span>
- <span data-ttu-id="20dec-182">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="20dec-183"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="20dec-184">管理者の提出の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="20dec-184">Admin submission rescan details</span></span>

<span data-ttu-id="20dec-185">管理者の提出で送信されたメッセージは再スキャンされ、詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="20dec-186">配信時に送信者の電子メール認証にエラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="20dec-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="20dec-187">メッセージの Verdict に影響を与えた、または上書きした可能性があるポリシー ヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="20dec-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="20dec-188">現在の分析結果では、メッセージに含まれる URL またはファイルが悪意のあるものか確認されません。</span><span class="sxs-lookup"><span data-stu-id="20dec-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="20dec-189">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="20dec-189">Feedback from graders.</span></span>

<span data-ttu-id="20dec-190">オーバーライドが見つかった場合は、数分で再スキャンが完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20dec-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="20dec-191">メール認証で問題が発生したり、配信が上書きの影響を受けなかったりした場合、成績者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20dec-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="20dec-192">管理者 URL の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-192">View admin URL submissions</span></span>

<span data-ttu-id="20dec-193">**[URL] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-193">Click the **URL** tab.</span></span>

<span data-ttu-id="20dec-194">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="20dec-195">**日付**</span><span class="sxs-lookup"><span data-stu-id="20dec-195">**Date**</span></span>
- <span data-ttu-id="20dec-196">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="20dec-196">**Submission ID**</span></span>
- <span data-ttu-id="20dec-197">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-198">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="20dec-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-199">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-199">**Submission type**</span></span>
- <span data-ttu-id="20dec-200">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="20dec-201"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="20dec-202">管理者の添付ファイルの提出を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-202">View admin attachment submissions</span></span>

<span data-ttu-id="20dec-203">[添付ファイル **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="20dec-204">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="20dec-205">**日付**</span><span class="sxs-lookup"><span data-stu-id="20dec-205">**Date**</span></span>
- <span data-ttu-id="20dec-206">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="20dec-206">**Submission ID**</span></span>
- <span data-ttu-id="20dec-207">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-208">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-209">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-209">**Submission type**</span></span>
- <span data-ttu-id="20dec-210">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="20dec-211"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="20dec-212">Microsoft へのユーザー申請を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="20dec-213">レポート メッセージ アドイン、Report [](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)アドイン、または[Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の組み込みレポートを使用しているユーザーを展開した場合は、[ユーザーの送信]タブでユーザーが報告している情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="20dec-214">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="20dec-215">[ユーザーの **提出] タブを選択** し、[新しい提出] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20dec-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="20dec-216">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="20dec-217">**送信日**</span><span class="sxs-lookup"><span data-stu-id="20dec-217">**Submitted on**</span></span>
- <span data-ttu-id="20dec-218">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-219">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="20dec-220">**Sender**</span></span>
- <span data-ttu-id="20dec-221">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="20dec-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-222">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-222">**Submission type**</span></span>

<span data-ttu-id="20dec-223"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20dec-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="20dec-224">ページの上部には、開始日、終了日を入力できます。既定では、ボックスに値を入力して [更新] ボタンをクリックすることで Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="20dec-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="20dec-225">Update</span><span class="sxs-lookup"><span data-stu-id="20dec-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="20dec-226">フィルター条件を変更するには、[送信者]ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="20dec-227">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="20dec-227">**Sender domain**</span></span>
- <span data-ttu-id="20dec-228">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="20dec-228">**Subject**</span></span>
- <span data-ttu-id="20dec-229">**提出者**</span><span class="sxs-lookup"><span data-stu-id="20dec-229">**Submitted by**</span></span>
- <span data-ttu-id="20dec-230">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-230">**Submission type**</span></span>
- <span data-ttu-id="20dec-231">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="20dec-231">**Sender IP**</span></span>

![ユーザー提出のフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="20dec-233">結果をエクスポートするには、ページの **上部にある** [エクスポート] をクリックし、[グラフ データ] または [テーブル **]** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="20dec-234">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="20dec-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="20dec-235">カスタム メールボックスへのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="20dec-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="20dec-236">**ユーザー** から報告 [されたメッセージ](user-submission.md) を受信するようにカスタム メールボックスを構成した場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="20dec-237">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="20dec-238">[カスタム メールボックス **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="20dec-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="20dec-239">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューで列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="20dec-240">**送信日**</span><span class="sxs-lookup"><span data-stu-id="20dec-240">**Submitted on**</span></span>
- <span data-ttu-id="20dec-241">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-242">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="20dec-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="20dec-243">**Sender**</span></span>
- <span data-ttu-id="20dec-244">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="20dec-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="20dec-245">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="20dec-245">**Submission type**</span></span>

<span data-ttu-id="20dec-246">ページの上部に開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで Submitted でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="20dec-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="20dec-247">Update</span><span class="sxs-lookup"><span data-stu-id="20dec-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="20dec-248">結果をエクスポートするには、ページ上部の **[** エクスポート] をクリックし、[グラフ データ] **または** [テーブル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="20dec-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="20dec-249">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="20dec-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="20dec-250">ユーザーの提出を元に戻す</span><span class="sxs-lookup"><span data-stu-id="20dec-250">Undo user submissions</span></span>

<span data-ttu-id="20dec-251">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="20dec-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="20dec-252">ユーザーがメールを回復する場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="20dec-253">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="20dec-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="20dec-254">Microsoft にメッセージを送信せずにユーザーから報告されたメッセージを取得するようにカスタム メールボックスを構成した場合は、特定のメッセージを検索して分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="20dec-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="20dec-255">これにより、ユーザーの申請が管理者の申請に効果的に移動します。</span><span class="sxs-lookup"><span data-stu-id="20dec-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="20dec-256">[**カスタム メールボックス]** タブで、一覧からメッセージを選択し、[操作] ボタンをクリックして、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="20dec-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="20dec-257">**レポートをクリーンにする**</span><span class="sxs-lookup"><span data-stu-id="20dec-257">**Report clean**</span></span>
- <span data-ttu-id="20dec-258">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="20dec-258">**Report phishing**</span></span>
- <span data-ttu-id="20dec-259">**マルウェアを報告する**</span><span class="sxs-lookup"><span data-stu-id="20dec-259">**Report malware**</span></span>
- <span data-ttu-id="20dec-260">**迷惑メールを報告する**</span><span class="sxs-lookup"><span data-stu-id="20dec-260">**Report spam**</span></span>

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
