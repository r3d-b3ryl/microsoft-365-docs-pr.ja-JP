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
description: 管理者は、セキュリティ & コンプライアンス センターの Submits ポータルを使用して、疑わしいメール、フィッシングメール、スパム、その他有害な可能性のあるメッセージ、URL、ファイルを Microsoft に送信してスキャンする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e0975d5b6c2d29c94a30f7bbc703221b80217761
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599877"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="7ea3e-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7ea3e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-104">**Applies to**</span></span>
- [<span data-ttu-id="7ea3e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7ea3e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7ea3e-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7ea3e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="7ea3e-107">Exchange Online のメールボックスを持つ Microsoft 365 組織では、管理者はセキュリティ & コンプライアンス センターの Submits ポータルを使用して、電子メール メッセージ、URL、添付ファイルをスキャンのために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="7ea3e-108">電子メール メッセージを送信すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="7ea3e-109">**電子メール認証チェック**: 電子メール認証が配信された際に合格または失敗したかどうかの詳細。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="7ea3e-110">**ポリシーヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの評決を上書きします。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="7ea3e-111">**ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="7ea3e-112">**Grader 分析**: メッセージが悪意のあるかどうかを確認するために、人間の採点者が行うレビュー。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ea3e-113">ペイロード評価/デトナレーションおよび採点者分析は、すべてのテナントで行われるという問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="7ea3e-114">データがコンプライアンスの目的でテナント境界から離れるはずではない場合、情報は組織外に出るのをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="7ea3e-115">電子メール メッセージ、URL、添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ea3e-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7ea3e-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ea3e-117"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7ea3e-118">[申請] ページに直接 **移動するには** 、 を使用します <https://protection.office.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="7ea3e-119">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="7ea3e-120">**セキュリティ センター** の **組織の** 管理 [またはセキュリティ &リーダー](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="7ea3e-121">Exchange **Online の**[組織の管理](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="7ea3e-122">この記事で後述するように、カスタム メールボックスへの[](#view-user-submissions-to-the-custom-mailbox)ユーザー申請を表示するには、この役割グループのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="7ea3e-123">ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="7ea3e-124">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="7ea3e-125">[セキュリティ & コンプライアンス センター] で、[脅威管理の申請] に移動し、[管理者の申請] タブで [新しい申請] をクリックします \> 。  </span><span class="sxs-lookup"><span data-stu-id="7ea3e-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="7ea3e-126">次 **のセクションで** 説明するように、メッセージ、URL、または添付ファイルを送信するために表示される新しい申請フライアウトを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="7ea3e-127">疑いがある電子メールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="7ea3e-128">[オブジェクトの **種類] セクションで** 、[メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="7ea3e-129">[提出 **形式] セクション** で、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="7ea3e-130">**ネットワーク メッセージ ID**: これは、メッセージの **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="7ea3e-131">**ファイル**: [ファイルの **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="7ea3e-132">開いたダイアログで、.eml ファイルまたは .msg ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7ea3e-133">30 日間の古いメッセージを送信する機能は、365 人のユーザーに対して Defender Office中断されています。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="7ea3e-134">管理者は 7 日間だけ戻って行くことができます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="7ea3e-135">[受信者 **] セクション** で、ポリシー チェックを実行する 1 つ以上の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="7ea3e-136">ポリシー チェックは、ユーザーまたは組織のポリシーが原因で電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="7ea3e-137">[申請 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ea3e-138">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ea3e-139">**ブロックされている必要があります**: [スパム **]、[\*\*\*\*フィッシング]、または [マルウェア]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="7ea3e-140">不明な場合は、最善の判断を下してください。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="7ea3e-141">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-141">When you're finished, click the **Submit** button.</span></span>

   ![URL 申請の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="7ea3e-143">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="7ea3e-144">[オブジェクトの **種類] セクションで\*\*\*\*、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="7ea3e-145">表示されるボックスに、完全な URL (たとえば) を入力 `https://www.fabrikam.com/marketing.html` します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="7ea3e-146">[申請 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ea3e-147">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ea3e-148">**ブロックされている必要があります**: [フィッシング] または [**マルウェア] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="7ea3e-149">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-149">When you're finished, click the **Submit** button.</span></span>

   ![電子メール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="7ea3e-151">疑わしいファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="7ea3e-152">[オブジェクトの **種類] セクションで** 、[添付ファイル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="7ea3e-153">[ファイル **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-153">Click **Choose File**.</span></span> <span data-ttu-id="7ea3e-154">開いたダイアログで、ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="7ea3e-155">[申請 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7ea3e-156">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7ea3e-157">**ブロックされている必要があります:\*\*\*\*マルウェア** だけが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="7ea3e-158">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-158">When you're finished, click the **Submit** button.</span></span>

   ![添付ファイルの提出例](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="7ea3e-160">分析のために提出されたアイテムの表示</span><span class="sxs-lookup"><span data-stu-id="7ea3e-160">View items Submitted for analysis</span></span>

<span data-ttu-id="7ea3e-161">[セキュリティ & コンプライアンス センター] で、[脅威管理の申請] に移動し、[送信済み分析] \> **タブに移動している必要があります**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="7ea3e-162">ページの上部付近では、開始日、終了日、および (既定で) ボックスに値を入力し、[更新] ボタンをクリックして、申請 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます。 ![ ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="7ea3e-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ea3e-163">Update</span><span class="sxs-lookup"><span data-stu-id="7ea3e-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ea3e-164">フィルター条件を変更するには、[申請 **ID]** ボタンをクリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="7ea3e-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-165">**Sender**</span></span>
- <span data-ttu-id="7ea3e-166">**件名/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="7ea3e-167">**提出者**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-167">**Submitted by**</span></span>
- <span data-ttu-id="7ea3e-168">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-168">**Submission type**</span></span>
- <span data-ttu-id="7ea3e-169">**状態**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-169">**Status**</span></span>

![管理者申請のフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="7ea3e-171">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ea3e-172">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="7ea3e-173">グラフの下には、メール **(既定\*\*\*\*)、URL、** 添付ファイルの 3 つのタブ **があります**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="7ea3e-174">管理メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-174">View admin email submissions</span></span>

<span data-ttu-id="7ea3e-175">[メール] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-175">Click the **Email** tab.</span></span>

<span data-ttu-id="7ea3e-176">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ea3e-177">**日付**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-177">**Date**</span></span>
- <span data-ttu-id="7ea3e-178">**申請 ID**: すべての申請に割り当てられている GUID 値。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="7ea3e-179">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-180">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-181">**Sender**</span></span>
- <span data-ttu-id="7ea3e-182">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-183">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-183">**Submission type**</span></span>
- <span data-ttu-id="7ea3e-184">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-184">**Delivery reason**</span></span>
- <span data-ttu-id="7ea3e-185">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7ea3e-186"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="7ea3e-187">管理者申請の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="7ea3e-187">Admin submission rescan details</span></span>

<span data-ttu-id="7ea3e-188">管理者の申請で送信されたメッセージは再スキャンされ、詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="7ea3e-189">配信時に送信者のメール認証に失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="7ea3e-190">メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="7ea3e-191">現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="7ea3e-192">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-192">Feedback from graders.</span></span>

<span data-ttu-id="7ea3e-193">上書きが見つかった場合、再スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="7ea3e-194">メール認証や配信に問題が発生しない場合は、上書きによって影響を受けなかった場合、採点者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="7ea3e-195">管理者 URL の申請を表示する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-195">View admin URL submissions</span></span>

<span data-ttu-id="7ea3e-196">**[URL] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-196">Click the **URL** tab.</span></span>

<span data-ttu-id="7ea3e-197">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ea3e-198">**日付**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-198">**Date**</span></span>
- <span data-ttu-id="7ea3e-199">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-199">**Submission ID**</span></span>
- <span data-ttu-id="7ea3e-200">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-201">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-202">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-202">**Submission type**</span></span>
- <span data-ttu-id="7ea3e-203">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7ea3e-204"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="7ea3e-205">管理者の添付ファイルの申請を表示する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-205">View admin attachment submissions</span></span>

<span data-ttu-id="7ea3e-206">[添付ファイル **] タブを** クリックします。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="7ea3e-207">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ea3e-208">**日付**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-208">**Date**</span></span>
- <span data-ttu-id="7ea3e-209">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-209">**Submission ID**</span></span>
- <span data-ttu-id="7ea3e-210">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-211">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-212">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-212">**Submission type**</span></span>
- <span data-ttu-id="7ea3e-213">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7ea3e-214"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="7ea3e-215">Microsoft へのユーザー申請の表示</span><span class="sxs-lookup"><span data-stu-id="7ea3e-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="7ea3e-216">レポート メッセージ アドイン、レポート[](enable-the-report-message-add-in.md)フィッシング アドイン、またはユーザー[](enable-the-report-phish-add-in.md)が[Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)で組み込みのレポートを使用している場合は、[ユーザーの申請] タブでユーザーが報告している情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="7ea3e-217">セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7ea3e-218">[ユーザー申請 **] タブを選択** し、[新しい申請] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="7ea3e-219">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ea3e-220">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-220">**Submitted on**</span></span>
- <span data-ttu-id="7ea3e-221">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-222">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-223">**Sender**</span></span>
- <span data-ttu-id="7ea3e-224">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-225">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-225">**Submission type**</span></span>

<span data-ttu-id="7ea3e-226"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="7ea3e-227">ページの上部付近では、開始日、終了日、および (既定で) ボックスに値を入力し、[更新]ボタンをクリックして Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ea3e-228">Update</span><span class="sxs-lookup"><span data-stu-id="7ea3e-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ea3e-229">フィルター条件を変更するには、[送信者] ボタン **を** クリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="7ea3e-230">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-230">**Sender domain**</span></span>
- <span data-ttu-id="7ea3e-231">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-231">**Subject**</span></span>
- <span data-ttu-id="7ea3e-232">**提出者**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-232">**Submitted by**</span></span>
- <span data-ttu-id="7ea3e-233">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-233">**Submission type**</span></span>
- <span data-ttu-id="7ea3e-234">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-234">**Sender IP**</span></span>

![ユーザー申請のフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="7ea3e-236">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ea3e-237">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="7ea3e-238">カスタム メールボックスへのユーザー申請の表示</span><span class="sxs-lookup"><span data-stu-id="7ea3e-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="7ea3e-239">**ユーザー** が報告した [メッセージを](user-submission.md) 受信するようにカスタム メールボックスを構成している場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="7ea3e-240">セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7ea3e-241">[カスタム メールボックス **] タブを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="7ea3e-242">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7ea3e-243">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-243">**Submitted on**</span></span>
- <span data-ttu-id="7ea3e-244">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-245">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ea3e-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-246">**Sender**</span></span>
- <span data-ttu-id="7ea3e-247">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="7ea3e-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7ea3e-248">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-248">**Submission type**</span></span>

<span data-ttu-id="7ea3e-249">ページの上部の近くに開始日、終了日を入力し、ボックスに値を入力し、[更新]ボタンをクリックして[送信済み] でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7ea3e-250">Update</span><span class="sxs-lookup"><span data-stu-id="7ea3e-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7ea3e-251">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7ea3e-252">表示されるダイアログで、.csv ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="7ea3e-253">組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="7ea3e-254">ユーザー申請の元に戻す</span><span class="sxs-lookup"><span data-stu-id="7ea3e-254">Undo user submissions</span></span>

<span data-ttu-id="7ea3e-255">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すオプションを使用できません。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="7ea3e-256">ユーザーが電子メールを回復する場合は、削除済みアイテムまたは迷惑メール フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="7ea3e-257">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="7ea3e-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="7ea3e-258">Microsoft にメッセージを送信せずにユーザーが報告したメッセージを傍受するようにカスタム メールボックスを構成している場合は、特定のメッセージを見つけて分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="7ea3e-259">これにより、ユーザーの申請が管理者申請に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="7ea3e-260">[カスタム **メールボックス] タブ** で、一覧でメッセージを選択し、[アクション] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="7ea3e-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="7ea3e-261">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-261">**Report clean**</span></span>
- <span data-ttu-id="7ea3e-262">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-262">**Report phishing**</span></span>
- <span data-ttu-id="7ea3e-263">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-263">**Report malware**</span></span>
- <span data-ttu-id="7ea3e-264">**スパムを報告する**</span><span class="sxs-lookup"><span data-stu-id="7ea3e-264">**Report spam**</span></span>

![[操作] ボタンのオプション](../../media/user-submission-custom-mailbox-action-button.png)
