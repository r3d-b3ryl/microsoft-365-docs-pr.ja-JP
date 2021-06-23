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
description: 管理者は、Microsoft 365 Defender ポータルの Submits ポータルを使用して、不審なメール、フィッシングメール、スパム、その他有害な可能性のあるメッセージ、URL、および電子メールの添付ファイルを Microsoft に提出して再スキャンする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab25757c79b7978400e98fa36d48163e1681e7c1
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062012"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="601ec-103">管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する</span><span class="sxs-lookup"><span data-stu-id="601ec-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="601ec-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="601ec-104">**Applies to**</span></span>
- [<span data-ttu-id="601ec-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="601ec-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="601ec-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="601ec-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="601ec-107">Exchange Online メールボックスを持つ組織では、管理者は Microsoft 365 Defender ポータルの Submits ポータルを使用して、電子メール メッセージ、URL、添付ファイルを Microsoft に送信してスキャンできます。 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="601ec-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="601ec-108">電子メール メッセージを送信すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="601ec-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="601ec-109">**電子メール認証チェック**: 電子メール認証が配信された際に合格または失敗したかどうかの詳細。</span><span class="sxs-lookup"><span data-stu-id="601ec-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="601ec-110">**ポリシーヒット**: テナントへの受信メールを許可またはブロックした可能性があるポリシーに関する情報で、サービス フィルターの評決を上書きします。</span><span class="sxs-lookup"><span data-stu-id="601ec-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="601ec-111">**ペイロード評価/デトレーション**: メッセージ内の URL と添付ファイルの検査。</span><span class="sxs-lookup"><span data-stu-id="601ec-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="601ec-112">**Grader 分析**: メッセージが悪意のあるかどうかを確認するために、人間の採点者が行うレビュー。</span><span class="sxs-lookup"><span data-stu-id="601ec-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="601ec-113">ペイロード評価/デトナレーションおよび採点者分析は、すべてのテナントで行われるという問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="601ec-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="601ec-114">データがコンプライアンスの目的でテナント境界から離れるはずではない場合、情報は組織外に出るのをブロックされます。</span><span class="sxs-lookup"><span data-stu-id="601ec-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="601ec-115">電子メール メッセージ、URL、添付ファイルを Microsoft に送信するその他の方法については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="601ec-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="601ec-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="601ec-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="601ec-117"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="601ec-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="601ec-118">[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="601ec-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="601ec-119">メッセージとファイルを Microsoft に送信するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="601ec-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="601ec-120">\*\*[組織の管理\*\*\*\*] または [セキュリティ\*\*[リーダー] をMicrosoft 365 Defenderします](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="601ec-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="601ec-121">**[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="601ec-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="601ec-122">この記事で後述するように、カスタム メールボックスへの[](#view-user-submissions-to-microsoft)ユーザー申請を表示するには、この役割グループのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="601ec-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="601ec-123">ユーザーがメッセージとファイルを Microsoft に送信する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="601ec-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="601ec-124">疑わしいコンテンツを Microsoft に報告する</span><span class="sxs-lookup"><span data-stu-id="601ec-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="601ec-125">[ポータル] Microsoft 365 Defender[メール]**に移動し、[&]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="601ec-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="601ec-126">[申請 **] ページで**、[分析用に送信済み] タブが選択されているのを確認し、[分析のために Microsoft に送信する] の [広告] アイコン ![ ](../../media/m365-cc-sc-create-icon.png) **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="601ec-127">次の **セクションで説明するように** 、メッセージ、URL、または電子メールの添付ファイルを送信するために表示される [Microsoft に送信する] を使用して、確認の飛び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="601ec-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="601ec-128">疑いがある電子メールを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="601ec-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="601ec-129">[申請 **の種類の選択** ] ボックスで、ドロップダウン リスト **で [メール** ] が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="601ec-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="601ec-130">[ネットワーク **メッセージ ID の追加または電子メール** ファイルのアップロード] セクションで、次のいずれかのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="601ec-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="601ec-131">電子メール ネットワーク メッセージ **ID** を追加する: これは、メッセージ内の **X-MS-Exchange-Organization-Network-Message-Id** ヘッダー、または検疫済みメッセージの **X-MS-Office365-Filtering-Correlation-Id** ヘッダーで使用できる GUID 値です。</span><span class="sxs-lookup"><span data-stu-id="601ec-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="601ec-132">**アップロード ファイル (.msg または .eml)** をクリックします。[ファイルの参照]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="601ec-133">開いたダイアログで、.eml ファイルまたは .msg ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="601ec-134">30 日という古いメッセージを送信する機能は、ユーザーのユーザーに対して Defender Office 365されています。</span><span class="sxs-lookup"><span data-stu-id="601ec-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="601ec-135">管理者は 7 日間だけ戻って行くことができます。</span><span class="sxs-lookup"><span data-stu-id="601ec-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="601ec-136">[問題 **が発生した受信者の選択** ] ボックスで、ポリシー チェックを実行する受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="601ec-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="601ec-137">ポリシー チェックは、ユーザーまたは組織のポリシーが原因で電子メールがスキャンをバイパスしたかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="601ec-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="601ec-138">[Microsoft **に提出する理由の選択] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="601ec-139">**ブロックされていない必要があります (誤検知)**</span><span class="sxs-lookup"><span data-stu-id="601ec-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="601ec-140">**ブロックされている必要** があります: 電子メールが表示されるセクションに分類されている必要があります。次のいずれかの値を選択します (不明な場合は、最適な判断を使用してください)。</span><span class="sxs-lookup"><span data-stu-id="601ec-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="601ec-141">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="601ec-141">**Phish**</span></span>
     - <span data-ttu-id="601ec-142">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="601ec-142">**Spam**</span></span>
     - <span data-ttu-id="601ec-143">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="601ec-143">**Malware**</span></span>

5. <span data-ttu-id="601ec-144">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="601ec-144">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="601ec-145">![新しい URL 申請の例](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-145">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="601ec-146">疑わしい URL を Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="601ec-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="601ec-147">[申請 **の種類の選択] ボックス** で、 **ドロップダウン リストから [URL]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="601ec-148">表示される **URL** ボックスに、完全な URL (たとえば) を入力 `https://www.fabrikam.com/marketing.html` します。</span><span class="sxs-lookup"><span data-stu-id="601ec-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="601ec-149">[Microsoft **に提出する理由の選択] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="601ec-150">**ブロックされていない必要があります (誤検知)**</span><span class="sxs-lookup"><span data-stu-id="601ec-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="601ec-151">**ブロックされている必要があります**: [この **URL** は表示されるセクションとして分類されている必要があります] セクションで、[フィッシング] または [マルウェア] **を** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="601ec-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="601ec-152">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="601ec-152">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="601ec-153">![新しいメール送信の例](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-153">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="601ec-154">疑わしいメール添付ファイルを Microsoft に送信する</span><span class="sxs-lookup"><span data-stu-id="601ec-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="601ec-155">[申請 **の種類の選択] ボックス** で、ドロップダウン リスト **から [** ファイル] を選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="601ec-156">表示される **[ファイル]** セクションで、[ファイルの参照] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="601ec-157">開いたダイアログで、ファイルを見つけて選択し、[開く] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="601ec-158">[Microsoft **に提出する理由の選択] セクション** で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="601ec-159">**ブロックされていない必要があります (誤検知)**</span><span class="sxs-lookup"><span data-stu-id="601ec-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="601ec-160">**ブロックされている必要があります**:この **URL** は表示されるセクションとして分類されている必要があります、 **マルウェア** は唯一の選択肢であり、自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="601ec-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="601ec-161">完了したら、[送信] ボタン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="601ec-161">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="601ec-162">![新しい添付ファイルの申請の例](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-162">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="601ec-163">Microsoft への管理者申請の表示</span><span class="sxs-lookup"><span data-stu-id="601ec-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="601ec-164">[ポータル] Microsoft 365 Defender[メール]**に移動し、[&]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="601ec-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="601ec-165">[申請 **] ページで** 、[分析用に送信 **済み] タブ** が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="601ec-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="601ec-166">使用可能な列ヘッダーをクリックすると、エントリを並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="601ec-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="601ec-167">[列 **のカスタマイズ] を** クリックして、最大 7 列を表示します。</span><span class="sxs-lookup"><span data-stu-id="601ec-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="601ec-168">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="601ec-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="601ec-169">**申請名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-170">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-171">**提出日**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-172">**申請の種類**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-173">**提出の理由**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-174">**再スキャンの状態**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-175">**再スキャンの結果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-176">**フィルターの評決**</span><span class="sxs-lookup"><span data-stu-id="601ec-176">**Filter verdict**</span></span>
     - <span data-ttu-id="601ec-177">**配信/ブロックの理由**</span><span class="sxs-lookup"><span data-stu-id="601ec-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="601ec-178">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-178">**Submission ID**</span></span>
     - <span data-ttu-id="601ec-179">**ネットワーク メッセージ ID/オブジェクト ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="601ec-180">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="601ec-180">**Direction**</span></span>
     - <span data-ttu-id="601ec-181">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="601ec-181">**Sender IP**</span></span>
     - <span data-ttu-id="601ec-182">**バルク準拠レベル (BCL)**</span><span class="sxs-lookup"><span data-stu-id="601ec-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="601ec-183">**宛先**</span><span class="sxs-lookup"><span data-stu-id="601ec-183">**Destination**</span></span>
     - <span data-ttu-id="601ec-184">**ポリシー アクション**</span><span class="sxs-lookup"><span data-stu-id="601ec-184">**Policy action**</span></span>
     - <span data-ttu-id="601ec-185">**提出者**</span><span class="sxs-lookup"><span data-stu-id="601ec-185">**Submitted by**</span></span>

     <span data-ttu-id="601ec-186">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="601ec-187">エントリをフィルターするには、[フィルター] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="601ec-188">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="601ec-188">The available filters are:</span></span>
     - <span data-ttu-id="601ec-189">**提出日**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="601ec-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="601ec-190">**申請の種類**:**電子メール\*\*\*\*、URL、** または **ファイルです**。</span><span class="sxs-lookup"><span data-stu-id="601ec-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="601ec-191">**申請 ID**: すべての申請に割り当てられている GUID 値。</span><span class="sxs-lookup"><span data-stu-id="601ec-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="601ec-192">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-192">**Network Message ID**</span></span>
     - <span data-ttu-id="601ec-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="601ec-193">**Sender**</span></span>

     <span data-ttu-id="601ec-194">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-194">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="601ec-195">![管理者申請の新しいフィルター オプション](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-195">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="601ec-196">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="601ec-197">**なし**</span><span class="sxs-lookup"><span data-stu-id="601ec-197">**None**</span></span>
     - <span data-ttu-id="601ec-198">**種類**</span><span class="sxs-lookup"><span data-stu-id="601ec-198">**Type**</span></span>
     - <span data-ttu-id="601ec-199">**理由**</span><span class="sxs-lookup"><span data-stu-id="601ec-199">**Reason**</span></span>
     - <span data-ttu-id="601ec-200">**状態**</span><span class="sxs-lookup"><span data-stu-id="601ec-200">**Status**</span></span>
     - <span data-ttu-id="601ec-201">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="601ec-201">**Rescan result**</span></span>

   - <span data-ttu-id="601ec-202">エントリをエクスポートするには、[エクスポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="601ec-203">表示されるダイアログで、ファイルを保存.csvします。</span><span class="sxs-lookup"><span data-stu-id="601ec-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="601ec-204">管理者申請の再スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="601ec-204">Admin submission rescan details</span></span>

<span data-ttu-id="601ec-205">管理者の申請で送信されたメッセージは確認され、提出の詳細フライアウトに結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="601ec-205">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="601ec-206">配信時に送信者のメール認証に失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="601ec-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="601ec-207">メッセージのセキュリティ判定に影響を与える、または上書きされる可能性があるポリシー ヒットに関する情報。</span><span class="sxs-lookup"><span data-stu-id="601ec-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="601ec-208">現在の爆発的な結果により、メッセージに含まれる URL またはファイルが悪意のあるものかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="601ec-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="601ec-209">成績者からのフィードバック。</span><span class="sxs-lookup"><span data-stu-id="601ec-209">Feedback from graders.</span></span>

<span data-ttu-id="601ec-210">上書きが見つかった場合、再スキャンは数分で完了します。</span><span class="sxs-lookup"><span data-stu-id="601ec-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="601ec-211">メール認証や配信に問題が発生しない場合は、上書きによって影響を受けなかった場合、採点者からのフィードバックは最大で 1 日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="601ec-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="601ec-212">Microsoft へのユーザー申請の表示</span><span class="sxs-lookup"><span data-stu-id="601ec-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="601ec-213">レポート メッセージ アドイン、レポート [](enable-the-report-message-add-in.md)フィッシング アドイン、またはユーザー [](enable-the-report-phish-add-in.md)が [Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の組み込みレポートを使用している場合は、[ユーザーが報告したメッセージ] タブでユーザーが報告している情報を **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="601ec-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="601ec-214">[ポータル] Microsoft 365 Defender[メール]**に移動し、[&]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="601ec-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="601ec-215">[申請 **] ページで** 、[ユーザーが報告した **メッセージ] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="601ec-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="601ec-216">使用可能な列ヘッダーをクリックすると、エントリを並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="601ec-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="601ec-217">[列 **のカスタマイズ] を** クリックして、最大 7 列を表示します。</span><span class="sxs-lookup"><span data-stu-id="601ec-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="601ec-218">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="601ec-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="601ec-219">**メールの件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-220">**報告者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-221">**報告日**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-222">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-223">**報告された理由**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-224">**再スキャンの結果**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="601ec-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="601ec-225">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-225">**Message reported ID**</span></span>
     - <span data-ttu-id="601ec-226">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-226">**Network Message ID**</span></span>
     - <span data-ttu-id="601ec-227">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="601ec-227">**Sender IP**</span></span>
     - <span data-ttu-id="601ec-228">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="601ec-228">**Phish simulation**</span></span>

     <span data-ttu-id="601ec-229">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="601ec-230">エントリをフィルターするには、[フィルター] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="601ec-231">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="601ec-231">The available filters are:</span></span>
     - <span data-ttu-id="601ec-232">**報告日**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="601ec-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="601ec-233">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="601ec-233">**Reported by**</span></span>
     - <span data-ttu-id="601ec-234">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="601ec-234">**Email subject**</span></span>
     - <span data-ttu-id="601ec-235">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-235">**Message reported ID**</span></span>
     - <span data-ttu-id="601ec-236">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="601ec-236">**Network Message ID**</span></span>
     - <span data-ttu-id="601ec-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="601ec-237">**Sender**</span></span>
     - <span data-ttu-id="601ec-238">**報告された理由**:**迷惑メール、\*\*\*\*フィッシング、スパム\*\*\*\*ではありません**。</span><span class="sxs-lookup"><span data-stu-id="601ec-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="601ec-239">**フィッシングシミュレーション**:**はいまたは\*\*\*\*いいえ**</span><span class="sxs-lookup"><span data-stu-id="601ec-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="601ec-240">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-240">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="601ec-241">![ユーザー申請の新しいフィルター オプション](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-241">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="601ec-242">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="601ec-243">**なし**</span><span class="sxs-lookup"><span data-stu-id="601ec-243">**None**</span></span>
     - <span data-ttu-id="601ec-244">**理由**</span><span class="sxs-lookup"><span data-stu-id="601ec-244">**Reason**</span></span>
     - <span data-ttu-id="601ec-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="601ec-245">**Sender**</span></span>
     - <span data-ttu-id="601ec-246">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="601ec-246">**Reported by**</span></span>
     - <span data-ttu-id="601ec-247">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="601ec-247">**Rescan result**</span></span>
     - <span data-ttu-id="601ec-248">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="601ec-248">**Phish simulation**</span></span>

   - <span data-ttu-id="601ec-249">エントリをエクスポートするには、[エクスポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="601ec-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="601ec-250">表示されるダイアログで、ファイルを保存.csvします。</span><span class="sxs-lookup"><span data-stu-id="601ec-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="601ec-251">組織がユーザー報告メッセージをカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="601ec-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="601ec-252">ユーザー申請の元に戻す</span><span class="sxs-lookup"><span data-stu-id="601ec-252">Undo user submissions</span></span>

<span data-ttu-id="601ec-253">ユーザーが不審なメールをカスタム メールボックスに送信すると、ユーザーと管理者は申請を元に戻すオプションを使用できません。</span><span class="sxs-lookup"><span data-stu-id="601ec-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="601ec-254">ユーザーが電子メールを回復する場合は、削除済みアイテムまたは迷惑メール フォルダーで回復できます。</span><span class="sxs-lookup"><span data-stu-id="601ec-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="601ec-255">カスタム メールボックスから Microsoft にメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="601ec-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="601ec-256">Microsoft にメッセージを送信せずにユーザーが報告したメッセージを傍受するようにカスタム メールボックスを構成している場合は、特定のメッセージを見つけて分析のために Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="601ec-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="601ec-257">これにより、ユーザーの申請が管理者申請に効果的に移動されます。</span><span class="sxs-lookup"><span data-stu-id="601ec-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="601ec-258">[ユーザー **報告メッセージ** ] タブで、一覧でメッセージを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="601ec-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="601ec-259">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="601ec-259">**Report clean**</span></span>
- <span data-ttu-id="601ec-260">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="601ec-260">**Report phishing**</span></span>
- <span data-ttu-id="601ec-261">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="601ec-261">**Report malware**</span></span>
- <span data-ttu-id="601ec-262">**スパムを報告する**</span><span class="sxs-lookup"><span data-stu-id="601ec-262">**Report spam**</span></span>
- <span data-ttu-id="601ec-263">**トリガー調査**</span><span class="sxs-lookup"><span data-stu-id="601ec-263">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="601ec-264">![[アクション] ボタンの [新しいオプション]](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="601ec-264">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
