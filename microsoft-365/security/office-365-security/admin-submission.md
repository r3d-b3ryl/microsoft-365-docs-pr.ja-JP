---
title: 管理者の申請
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
ms.openlocfilehash: 7b4e6dfcb5900ed41ad3ab0b44fada93599f0b4b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288791"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="9be5a-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="9be5a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9be5a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="9be5a-104">**Applies to**</span></span>
- [<span data-ttu-id="9be5a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9be5a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9be5a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="9be5a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)


<span data-ttu-id="9be5a-107">Exchange Online にメールボックスがある Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの送信ポータルを使用して、メール メッセージ、URL、および添付ファイルをスキャンのために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="9be5a-108">電子メール メッセージを送信すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="9be5a-109">**電子メール認証チェック**: メール認証が配信された際に、電子メール認証が合格または失敗したかどうかに関する詳細。</span><span class="sxs-lookup"><span data-stu-id="9be5a-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="9be5a-110">**ポリシー ヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの条件を上書きします。</span><span class="sxs-lookup"><span data-stu-id="9be5a-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="9be5a-111">**ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。</span><span class="sxs-lookup"><span data-stu-id="9be5a-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="9be5a-112">**成績分析**: メッセージが悪意のあるものかどうかを確認するために、人間の成績を確認します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9be5a-113">ペイロード評価/デトレーションとグレードの分析は、すべてのテナントで行われるというではありません。</span><span class="sxs-lookup"><span data-stu-id="9be5a-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="9be5a-114">データがコンプライアンスの目的でテナントの境界を離れるはずではない場合、情報が組織外に出るのをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="9be5a-115">電子メール メッセージ、URL、および添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9be5a-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9be5a-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="9be5a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9be5a-117"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9be5a-118">[提出] ページに直接 **移動するには、** 次のコマンドを使用します <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="9be5a-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="9be5a-119">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be5a-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9be5a-120">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="9be5a-121">Exchange Online **での**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="9be5a-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="9be5a-122">この役割グループのメンバーシップは、この記事で[](#view-user-submissions-to-the-custom-mailbox)後述するように、カスタム メールボックスへのユーザー送信を表示するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9be5a-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="9be5a-123">ユーザーがメッセージやファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="9be5a-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="9be5a-124">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="9be5a-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="9be5a-125">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリックします \> 。  </span><span class="sxs-lookup"><span data-stu-id="9be5a-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="9be5a-126">次 **のセクションで** 説明するように、メッセージ、URL、または添付ファイルを送信するために表示される新しい申請のフライアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="9be5a-127">Microsoft に問題があるメールを送信する</span><span class="sxs-lookup"><span data-stu-id="9be5a-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="9be5a-128">[オブジェクトの **種類] セクションで** 、[電子メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="9be5a-129">[ **提出形式] セクション** で、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="9be5a-130">**ネットワーク** メッセージ ID : これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="9be5a-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="9be5a-131">**[ファイル**]: [ファイルの **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="9be5a-132">開いたダイアログで、.eml または .msg ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9be5a-133">Defender for Office 365 プラン 1 またはプラン 2 の管理者は、30 日間の古いメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="9be5a-134">その他の管理者は 7 日間のみ戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be5a-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="9be5a-135">[ **受信者] セクション** で、ポリシー チェックを実行する 1 人または複数の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="9be5a-136">ポリシー チェックでは、ユーザーまたは組織のポリシーが原因でメールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="9be5a-137">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9be5a-138">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9be5a-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9be5a-139">**ブロックされている必要があります**: **スパム**、フィッシング **、またはマルウェア** を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="9be5a-140">確信が持てない場合は、最善の判断を下してください。</span><span class="sxs-lookup"><span data-stu-id="9be5a-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="9be5a-141">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-141">When you're finished, click the **Submit** button.</span></span>

   ![URL 送信の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="9be5a-143">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="9be5a-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="9be5a-144">[オブジェクトの **種類] セクションで\*\*\*\*、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="9be5a-145">表示されるボックスに、完全な URL (たとえば) を入力します `https://www.fabrikam.com/marketing.html` 。</span><span class="sxs-lookup"><span data-stu-id="9be5a-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="9be5a-146">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9be5a-147">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9be5a-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9be5a-148">**ブロックされている必要があります**: [フィッシングまたは **マルウェア] を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="9be5a-149">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-149">When you're finished, click the **Submit** button.</span></span>

   ![メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="9be5a-151">疑わしいファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="9be5a-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="9be5a-152">[オブジェクトの **種類] セクションで** 、[添付ファイル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="9be5a-153">[ファイル **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-153">Click **Choose File**.</span></span> <span data-ttu-id="9be5a-154">開いたダイアログで、ファイルを見つけて選択し、[開く] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="9be5a-155">[申請 **理由] セクションで** 、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9be5a-156">**ブロックされていない**</span><span class="sxs-lookup"><span data-stu-id="9be5a-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9be5a-157">**ブロックされている必要があります**: **マルウェア** だけが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="9be5a-158">完了したら、[送信] ボタンを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-158">When you're finished, click the **Submit** button.</span></span>

   ![添付ファイルの送信の例](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="9be5a-160">管理者の提出の表示</span><span class="sxs-lookup"><span data-stu-id="9be5a-160">View admin submissions</span></span>

<span data-ttu-id="9be5a-161">セキュリティ & コンプライアンス センターで、[脅威の管理の提出] に移動し、[管理者の提出] タブに移動し、[新しい提出] をクリックします \> 。  </span><span class="sxs-lookup"><span data-stu-id="9be5a-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9be5a-162">ページの上部には、開始日、終了日を入力できます。また、(既定では) ボックスに値を入力して [更新] ボタンをクリックすることで、提出 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます ![ ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9be5a-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9be5a-163">Update</span><span class="sxs-lookup"><span data-stu-id="9be5a-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9be5a-164">フィルター条件を変更するには **、[Submission ID]** ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="9be5a-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9be5a-165">**Sender**</span></span>
- <span data-ttu-id="9be5a-166">**件名/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="9be5a-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="9be5a-167">**提出者**</span><span class="sxs-lookup"><span data-stu-id="9be5a-167">**Submitted by**</span></span>
- <span data-ttu-id="9be5a-168">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-168">**Submission type**</span></span>
- <span data-ttu-id="9be5a-169">**状態**</span><span class="sxs-lookup"><span data-stu-id="9be5a-169">**Status**</span></span>

![管理者の申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="9be5a-171">結果をエクスポートするには、ページ上部の **[** エクスポート] をクリックし、[グラフ データ] **または** [テーブル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9be5a-172">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="9be5a-173">グラフの下には、メール (既定)、URL、添付ファイルの 3 つのタブ **があります**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="9be5a-174">管理者のメールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9be5a-174">View admin email submissions</span></span>

<span data-ttu-id="9be5a-175">[電子メール **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-175">Click the **Email** tab.</span></span>

<span data-ttu-id="9be5a-176">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9be5a-177">**日付**</span><span class="sxs-lookup"><span data-stu-id="9be5a-177">**Date**</span></span>
- <span data-ttu-id="9be5a-178">**提出 ID**: すべての申請に割り当てられる GUID 値。</span><span class="sxs-lookup"><span data-stu-id="9be5a-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="9be5a-179">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-180">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9be5a-181">**Sender**</span></span>
- <span data-ttu-id="9be5a-182">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9be5a-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-183">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-183">**Submission type**</span></span>
- <span data-ttu-id="9be5a-184">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="9be5a-184">**Delivery reason**</span></span>
- <span data-ttu-id="9be5a-185">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9be5a-186"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="9be5a-187">管理者の申請の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="9be5a-187">Admin submission rescan details</span></span>

<span data-ttu-id="9be5a-188">管理者の提出で送信されたメッセージは再スキャンされ、詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="9be5a-189">配信時に送信者の電子メール認証にエラーが発生した場合。</span><span class="sxs-lookup"><span data-stu-id="9be5a-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="9be5a-190">メッセージの Verdict に影響を与えた、または上書きした可能性があるポリシーヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="9be5a-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="9be5a-191">現在の分析結果では、メッセージに含まれる URL またはファイルが悪意のあるものか確認されません。</span><span class="sxs-lookup"><span data-stu-id="9be5a-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="9be5a-192">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="9be5a-192">Feedback from graders.</span></span>

<span data-ttu-id="9be5a-193">オーバーライドが見つかった場合は、数分で再スキャンが完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be5a-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="9be5a-194">メール認証で問題が発生したり、配信が上書きの影響を受けなかったりした場合、成績者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be5a-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="9be5a-195">管理者 URL の送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9be5a-195">View admin URL submissions</span></span>

<span data-ttu-id="9be5a-196">**[URL] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-196">Click the **URL** tab.</span></span>

<span data-ttu-id="9be5a-197">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9be5a-198">**日付**</span><span class="sxs-lookup"><span data-stu-id="9be5a-198">**Date**</span></span>
- <span data-ttu-id="9be5a-199">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="9be5a-199">**Submission ID**</span></span>
- <span data-ttu-id="9be5a-200">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-201">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9be5a-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-202">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-202">**Submission type**</span></span>
- <span data-ttu-id="9be5a-203">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9be5a-204"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="9be5a-205">管理者の添付ファイルの提出を表示する</span><span class="sxs-lookup"><span data-stu-id="9be5a-205">View admin attachment submissions</span></span>

<span data-ttu-id="9be5a-206">[添付ファイル **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="9be5a-207">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9be5a-208">**日付**</span><span class="sxs-lookup"><span data-stu-id="9be5a-208">**Date**</span></span>
- <span data-ttu-id="9be5a-209">**提出 ID**</span><span class="sxs-lookup"><span data-stu-id="9be5a-209">**Submission ID**</span></span>
- <span data-ttu-id="9be5a-210">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-211">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-212">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-212">**Submission type**</span></span>
- <span data-ttu-id="9be5a-213">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9be5a-214"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="9be5a-215">Microsoft へのユーザー申請を表示する</span><span class="sxs-lookup"><span data-stu-id="9be5a-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="9be5a-216">レポート メッセージ アドイン、Report [](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)アドイン、または[Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の組み込みレポートを使用しているユーザーを展開した場合は、[ユーザーの送信]タブでユーザーが報告している情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="9be5a-217">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9be5a-218">[ユーザーの **提出] タブを選択** し、[新しい提出] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9be5a-219">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9be5a-220">**送信日**</span><span class="sxs-lookup"><span data-stu-id="9be5a-220">**Submitted on**</span></span>
- <span data-ttu-id="9be5a-221">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-222">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9be5a-223">**Sender**</span></span>
- <span data-ttu-id="9be5a-224">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9be5a-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-225">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-225">**Submission type**</span></span>

<span data-ttu-id="9be5a-226"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="9be5a-227">ページの上部には、開始日、終了日を入力できます。既定では、ボックスに値を入力して [更新] ボタンをクリックすることで Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9be5a-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9be5a-228">Update</span><span class="sxs-lookup"><span data-stu-id="9be5a-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9be5a-229">フィルター条件を変更するには、[送信者]ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="9be5a-230">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9be5a-230">**Sender domain**</span></span>
- <span data-ttu-id="9be5a-231">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="9be5a-231">**Subject**</span></span>
- <span data-ttu-id="9be5a-232">**提出者**</span><span class="sxs-lookup"><span data-stu-id="9be5a-232">**Submitted by**</span></span>
- <span data-ttu-id="9be5a-233">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-233">**Submission type**</span></span>
- <span data-ttu-id="9be5a-234">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9be5a-234">**Sender IP**</span></span>

![ユーザー提出のフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="9be5a-236">結果をエクスポートするには、ページ上部の **[** エクスポート] をクリックし、[グラフ データ] **または** [テーブル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9be5a-237">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="9be5a-238">カスタム メールボックスへのユーザーの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="9be5a-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="9be5a-239">**ユーザー** から報告 [されたメッセージ](user-submission.md) を受信するようにカスタム メールボックスを構成した場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="9be5a-240">セキュリティ/コンプライアンス センター&、脅威管理の提出 **に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9be5a-241">[カスタム メールボックス **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="9be5a-242">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9be5a-243">**送信日**</span><span class="sxs-lookup"><span data-stu-id="9be5a-243">**Submitted on**</span></span>
- <span data-ttu-id="9be5a-244">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-245">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9be5a-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9be5a-246">**Sender**</span></span>
- <span data-ttu-id="9be5a-247">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="9be5a-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9be5a-248">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="9be5a-248">**Submission type**</span></span>

<span data-ttu-id="9be5a-249">ページの上部に開始日と終了日を入力し、ボックスに値を入力して [最新の情報に更新] ボタンをクリックすることで **Submitted** でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="9be5a-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9be5a-250">Update</span><span class="sxs-lookup"><span data-stu-id="9be5a-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9be5a-251">結果をエクスポートするには、ページ上部の **[** エクスポート] をクリックし、[グラフ データ] **または** [テーブル] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="9be5a-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9be5a-252">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="9be5a-253">ユーザーの提出を元に戻す</span><span class="sxs-lookup"><span data-stu-id="9be5a-253">Undo user submissions</span></span>

<span data-ttu-id="9be5a-254">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すことができません。</span><span class="sxs-lookup"><span data-stu-id="9be5a-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="9be5a-255">ユーザーがメールを回復する場合は、[削除済みアイテム] フォルダーまたは [迷惑メール] フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="9be5a-256">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="9be5a-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="9be5a-257">Microsoft にメッセージを送信せずにユーザーから報告されたメッセージを取得するようにカスタム メールボックスを構成した場合は、特定のメッセージを検索して分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="9be5a-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="9be5a-258">これにより、ユーザーの申請が管理者の申請に効果的に移動します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="9be5a-259">[**カスタム メールボックス]** タブで、一覧からメッセージを選択し、[操作] ボタンをクリックして、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9be5a-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="9be5a-260">**レポートをクリーンにする**</span><span class="sxs-lookup"><span data-stu-id="9be5a-260">**Report clean**</span></span>
- <span data-ttu-id="9be5a-261">**フィッシングを報告する**</span><span class="sxs-lookup"><span data-stu-id="9be5a-261">**Report phishing**</span></span>
- <span data-ttu-id="9be5a-262">**マルウェアを報告する**</span><span class="sxs-lookup"><span data-stu-id="9be5a-262">**Report malware**</span></span>
- <span data-ttu-id="9be5a-263">**迷惑メールを報告する**</span><span class="sxs-lookup"><span data-stu-id="9be5a-263">**Report spam**</span></span>

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
