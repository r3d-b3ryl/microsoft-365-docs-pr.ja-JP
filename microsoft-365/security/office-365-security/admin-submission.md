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
description: 管理者は、Microsoft 365 セキュリティ センターの Submits ポータルを使用して、不審なメール、フィッシングメール、スパム、その他有害な可能性のあるメッセージ、URL、および電子メールの添付ファイルを Microsoft に提出して再スキャンする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878690"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="fda48-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="fda48-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fda48-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fda48-104">**Applies to**</span></span>
- [<span data-ttu-id="fda48-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fda48-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fda48-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fda48-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="fda48-107">Exchange Online のメールボックスを持つ組織では、管理者はセキュリティ & コンプライアンス センターの申請ポータルを使用して、電子メール メッセージ、URL、添付ファイルを Microsoft に送信してスキャンできます。 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fda48-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="fda48-108">電子メール メッセージを送信すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="fda48-109">**電子メール認証チェック**: 電子メール認証が配信された際に合格または失敗したかどうかの詳細。</span><span class="sxs-lookup"><span data-stu-id="fda48-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="fda48-110">**ポリシーヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの評決を上書きします。</span><span class="sxs-lookup"><span data-stu-id="fda48-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="fda48-111">**ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。</span><span class="sxs-lookup"><span data-stu-id="fda48-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="fda48-112">**Grader 分析**: メッセージが悪意のあるかどうかを確認するために、人間の採点者が行うレビュー。</span><span class="sxs-lookup"><span data-stu-id="fda48-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fda48-113">ペイロード評価/デトナレーションおよび採点者分析は、すべてのテナントで行われるという問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="fda48-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="fda48-114">データがコンプライアンスの目的でテナント境界から離れるはずではない場合、情報は組織外に出るのをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fda48-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="fda48-115">電子メール メッセージ、URL、添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="fda48-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fda48-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="fda48-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fda48-117">[セキュリティ センター] Microsoft 365開きます <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="fda48-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fda48-118">[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="fda48-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="fda48-119">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fda48-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="fda48-120">**セキュリティ センター** の **組織** の管理 [またはMicrosoft 365リーダー](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fda48-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="fda48-121">**[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="fda48-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="fda48-122">この記事で後述するように、カスタム メールボックスへの[](#view-user-submissions-to-the-custom-mailbox)ユーザー申請を表示するには、この役割グループのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="fda48-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="fda48-123">ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="fda48-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="fda48-124">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="fda48-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="fda48-125">[セキュリティ [Microsoft 365]](../defender/overview-security-center.md)で、[申請]に移動し、[分析用に送信]タブに移動し、[確認のために Microsoft に送信する]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="fda48-126">次の **セクションで説明するように** 、メッセージ、URL、または電子メールの添付ファイルを送信するために表示される [Microsoft に送信する] を使用して、確認の飛び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="fda48-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="fda48-127">疑いがある電子メールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="fda48-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="fda48-128">[申請 **の種類の選択] セクションで** 、[メール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="fda48-129">[ネットワーク **メッセージ ID の追加または電子メール** ファイルのアップロード] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fda48-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="fda48-130">電子メール ネットワーク メッセージ **ID** を追加する: これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="fda48-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="fda48-131">**アップロードを開く: [** ファイルの参照]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="fda48-132">開いたダイアログで、.eml ファイルまたは .msg ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fda48-133">30 日という古いメッセージを送信する機能は、ユーザーのユーザーに対して Defender Office 365されています。</span><span class="sxs-lookup"><span data-stu-id="fda48-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="fda48-134">管理者は 7 日間だけ戻って行くことができます。</span><span class="sxs-lookup"><span data-stu-id="fda48-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="fda48-135">[問題 **を持っていた受信者の選択** ] セクションで、ポリシー チェックを実行する受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="fda48-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="fda48-136">ポリシー チェックは、ユーザーまたは組織のポリシーが原因で電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="fda48-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="fda48-137">[Microsoft **に提出する理由の選択] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="fda48-138">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="fda48-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fda48-139">**ブロックされている必要があります**: [スパム **]、[\*\*\*\*フィッシング]、または [マルウェア]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="fda48-140">不明な場合は、最善の判断を下してください。</span><span class="sxs-lookup"><span data-stu-id="fda48-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="fda48-141">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="fda48-141">When you're finished, click the **Submit** button.</span></span>

   ![新しい URL 申請の例](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="fda48-143">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="fda48-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="fda48-144">[申請 **の種類の選択] セクションで\*\*\*\*、[URL] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="fda48-145">表示されるボックスに、完全な URL (たとえば) を入力 `https://www.fabrikam.com/marketing.html` します。</span><span class="sxs-lookup"><span data-stu-id="fda48-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="fda48-146">[申請 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fda48-147">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="fda48-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fda48-148">**ブロックされている必要があります**: [フィッシング] または [**マルウェア] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="fda48-149">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="fda48-149">When you're finished, click the **Submit** button.</span></span>

   ![新しいメール送信の例](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="fda48-151">疑わしいメール添付ファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="fda48-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="fda48-152">[申請 **の種類の選択] セクションで** 、[電子メールの添付ファイル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="fda48-153">[ファイル **の選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-153">Click **Choose File**.</span></span> <span data-ttu-id="fda48-154">開いたダイアログで、ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="fda48-155">[申請 **の理由] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="fda48-156">**ブロックされていない必要があります**</span><span class="sxs-lookup"><span data-stu-id="fda48-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="fda48-157">**ブロックされている必要があります:\*\*\*\*マルウェア** だけが選択され、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="fda48-158">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="fda48-158">When you're finished, click the **Submit** button.</span></span>

   ![新しい添付ファイルの申請の例](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="fda48-160">分析のために提出されたアイテムの表示</span><span class="sxs-lookup"><span data-stu-id="fda48-160">View items Submitted for analysis</span></span>

<span data-ttu-id="fda48-161">セキュリティ センター Microsoft 365に移動し、[送信済み分析] タブに移動して、自分が [送信済み]**分析タブに表示されているのを確認** します。</span><span class="sxs-lookup"><span data-stu-id="fda48-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="fda48-162">ページの中央にあるコマンド バーで、開始日、終了日、および (既定で) ボックスに値を入力し、[更新] ボタンをクリックして、申請 **ID** (すべての申請に割り当てられている GUID 値) でフィルター処理できます。 ![ ](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="fda48-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fda48-163">Update</span><span class="sxs-lookup"><span data-stu-id="fda48-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fda48-164">フィルター条件を変更するには、[フィルター] ボタン **をクリック** し、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="fda48-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fda48-165">**Sender**</span></span>
- <span data-ttu-id="fda48-166">**件名/URL/ファイル名**</span><span class="sxs-lookup"><span data-stu-id="fda48-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="fda48-167">**提出者**</span><span class="sxs-lookup"><span data-stu-id="fda48-167">**Submitted by**</span></span>
- <span data-ttu-id="fda48-168">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-168">**Submission type**</span></span>
- <span data-ttu-id="fda48-169">**状態**</span><span class="sxs-lookup"><span data-stu-id="fda48-169">**Status**</span></span>

![管理者申請の新しいフィルター オプション](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="fda48-171">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fda48-172">表示されるダイアログで、ファイルを保存.csvします。</span><span class="sxs-lookup"><span data-stu-id="fda48-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="fda48-173">グラフの下には、メール **(既定\*\*\*\*)、URL、およびメール** 添付ファイルの 3 つの **タブがあります**。</span><span class="sxs-lookup"><span data-stu-id="fda48-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="fda48-174">管理メールの送信を表示する</span><span class="sxs-lookup"><span data-stu-id="fda48-174">View admin email submissions</span></span>

<span data-ttu-id="fda48-175">ページの下部にある **[列のカスタマイズ** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fda48-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="fda48-176">**Date**</span></span>
- <span data-ttu-id="fda48-177">**申請 ID**: すべての申請に割り当てられている GUID 値。</span><span class="sxs-lookup"><span data-stu-id="fda48-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="fda48-178">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-179">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-180">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fda48-180">**Sender**</span></span>
- <span data-ttu-id="fda48-181">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fda48-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-182">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-182">**Submission type**</span></span>
- <span data-ttu-id="fda48-183">**配信理由**</span><span class="sxs-lookup"><span data-stu-id="fda48-183">**Delivery reason**</span></span>
- <span data-ttu-id="fda48-184">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fda48-185"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="fda48-186">管理者申請の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="fda48-186">Admin submission rescan details</span></span>

<span data-ttu-id="fda48-187">管理者の申請で送信されたメッセージは再スキャンされ、提出の詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="fda48-188">配信時に送信者のメール認証に失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="fda48-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="fda48-189">メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="fda48-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="fda48-190">現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="fda48-191">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="fda48-191">Feedback from graders.</span></span>

<span data-ttu-id="fda48-192">上書きが見つかった場合、再スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="fda48-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="fda48-193">メール認証や配信に問題が発生しない場合は、上書きによって影響を受けなかった場合、採点者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fda48-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="fda48-194">管理者 URL の申請を表示する</span><span class="sxs-lookup"><span data-stu-id="fda48-194">View admin URL submissions</span></span>

<span data-ttu-id="fda48-195">**[URL] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="fda48-195">Click the **URL** tab.</span></span>

<span data-ttu-id="fda48-196">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fda48-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="fda48-197">**Date**</span></span>
- <span data-ttu-id="fda48-198">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="fda48-198">**Submission ID**</span></span>
- <span data-ttu-id="fda48-199">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-200">[**URL**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fda48-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-201">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-201">**Submission type**</span></span>
- <span data-ttu-id="fda48-202">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fda48-203"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="fda48-204">メール添付ファイルの申請を表示する</span><span class="sxs-lookup"><span data-stu-id="fda48-204">View email attachment submissions</span></span>

<span data-ttu-id="fda48-205">[添付ファイル **] タブを** クリックします。</span><span class="sxs-lookup"><span data-stu-id="fda48-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="fda48-206">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fda48-207">**Date**</span><span class="sxs-lookup"><span data-stu-id="fda48-207">**Date**</span></span>
- <span data-ttu-id="fda48-208">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="fda48-208">**Submission ID**</span></span>
- <span data-ttu-id="fda48-209">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-210">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-211">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-211">**Submission type**</span></span>
- <span data-ttu-id="fda48-212">**状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="fda48-213"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="fda48-214">Microsoft へのユーザー申請の表示</span><span class="sxs-lookup"><span data-stu-id="fda48-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="fda48-215">レポート メッセージ アドイン、レポート[](enable-the-report-message-add-in.md)フィッシング アドイン、またはユーザー[](enable-the-report-phish-add-in.md)が web 上[の Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)で組み込みのレポートを使用している場合は、[ユーザーの申請] タブでユーザーが報告している情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="fda48-216">セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fda48-217">[ユーザー申請 **] タブを選択** し、[新しい申請] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fda48-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="fda48-218">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fda48-219">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="fda48-219">**Submitted on**</span></span>
- <span data-ttu-id="fda48-220">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-221">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-222">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fda48-222">**Sender**</span></span>
- <span data-ttu-id="fda48-223">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fda48-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-224">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-224">**Submission type**</span></span>

<span data-ttu-id="fda48-225"><sup>\*</sup> この値をクリックすると、詳細情報がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="fda48-226">ページの上部付近では、開始日、終了日、および (既定で) ボックスに値を入力し、[更新]ボタンをクリックして Sender でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="fda48-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fda48-227">Update</span><span class="sxs-lookup"><span data-stu-id="fda48-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fda48-228">フィルター条件を変更するには、[送信者] ボタン **を** クリックし、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="fda48-229">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="fda48-229">**Sender domain**</span></span>
- <span data-ttu-id="fda48-230">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="fda48-230">**Subject**</span></span>
- <span data-ttu-id="fda48-231">**提出者**</span><span class="sxs-lookup"><span data-stu-id="fda48-231">**Submitted by**</span></span>
- <span data-ttu-id="fda48-232">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-232">**Submission type**</span></span>
- <span data-ttu-id="fda48-233">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="fda48-233">**Sender IP**</span></span>

![ユーザー申請の新しいフィルター オプション](../../media/user-submissions-filter-options.png)

<span data-ttu-id="fda48-235">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fda48-236">表示されるダイアログで、ファイルを保存.csvします。</span><span class="sxs-lookup"><span data-stu-id="fda48-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="fda48-237">カスタム メールボックスへのユーザー申請の表示</span><span class="sxs-lookup"><span data-stu-id="fda48-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="fda48-238">**ユーザー** が報告した [メッセージを](user-submission.md) 受信するようにカスタム メールボックスを構成している場合は、レポート メールボックスに配信されたメッセージを表示および送信できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="fda48-239">セキュリティ 管理コンプライアンス センター&、脅威管理 **の申請に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="fda48-240">[カスタム メールボックス **] タブを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="fda48-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="fda48-241">ページの下部にある **[列のオプション** ] ボタンをクリックすると、ビューに列を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="fda48-242">**送信済み**</span><span class="sxs-lookup"><span data-stu-id="fda48-242">**Submitted on**</span></span>
- <span data-ttu-id="fda48-243">**提出者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-244">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fda48-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="fda48-245">**Sender**</span></span>
- <span data-ttu-id="fda48-246">[**Sender IP (送信者の IP)**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="fda48-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="fda48-247">**申請の種類**</span><span class="sxs-lookup"><span data-stu-id="fda48-247">**Submission type**</span></span>

<span data-ttu-id="fda48-248">ページの上部の近くに開始日、終了日を入力し、ボックスに値を入力し、[更新]ボタンをクリックして[送信済み] でフィルター ![ 処理できます ](../../media/scc-quarantine-refresh.png) 。</span><span class="sxs-lookup"><span data-stu-id="fda48-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="fda48-249">Update</span><span class="sxs-lookup"><span data-stu-id="fda48-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="fda48-250">結果をエクスポートするには、ページの上部 **にある [エクスポート** ] をクリックし、[グラフ データ] または [ **テーブル** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fda48-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="fda48-251">表示されるダイアログで、ファイルを保存.csvします。</span><span class="sxs-lookup"><span data-stu-id="fda48-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="fda48-252">組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="fda48-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="fda48-253">ユーザー申請の元に戻す</span><span class="sxs-lookup"><span data-stu-id="fda48-253">Undo user submissions</span></span>

<span data-ttu-id="fda48-254">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すオプションを使用できません。</span><span class="sxs-lookup"><span data-stu-id="fda48-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="fda48-255">ユーザーが電子メールを回復する場合は、削除済みアイテムまたは迷惑メール フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="fda48-256">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="fda48-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="fda48-257">Microsoft にメッセージを送信せずにユーザーが報告したメッセージを傍受するようにカスタム メールボックスを構成している場合は、特定のメッセージを見つけて分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="fda48-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="fda48-258">これにより、ユーザーの申請が管理者申請に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="fda48-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="fda48-259">[ユーザー **が報告したメッセージ**] タブで、一覧でメッセージを選択し、[アクション] ボタンをクリックして、次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="fda48-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="fda48-260">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="fda48-260">**Report clean**</span></span>
- <span data-ttu-id="fda48-261">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="fda48-261">**Report phishing**</span></span>
- <span data-ttu-id="fda48-262">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="fda48-262">**Report malware**</span></span>
- <span data-ttu-id="fda48-263">**スパムを報告する**</span><span class="sxs-lookup"><span data-stu-id="fda48-263">**Report spam**</span></span>

![[アクション] ボタンの [新しいオプション]](../../media/user-submission-custom-mailbox-action-button.png)
