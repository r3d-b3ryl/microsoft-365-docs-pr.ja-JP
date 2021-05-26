---
title: Microsoft Defender for Identity security alerts in Microsoft 365 Defender
description: Microsoft Defender for Identity が発行したセキュリティ アラートを管理および確認する方法については、「Microsoft Defender」Microsoft 365します。
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657854"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="13ed1-103">Defender for Identity security alerts in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13ed1-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="13ed1-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="13ed1-104">**Applies to:**</span></span>

- <span data-ttu-id="13ed1-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="13ed1-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="13ed1-106">Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="13ed1-106">Defender for Identity</span></span>

<span data-ttu-id="13ed1-107">この記事では、セキュリティ センターで[Microsoft Defender for Identity](/defender-for-identity)セキュリティアラートを操作する方法のMicrosoft 365[説明します](/microsoft-365/security/defender/overview-security-center)。</span><span class="sxs-lookup"><span data-stu-id="13ed1-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="13ed1-108">Defender for Identity alerts は、専用の IDENTITY アラート[ページ形式Microsoft 365セキュリティ](https://security.microsoft.com)センターにネイティブに統合されます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="13ed1-109">これは、Microsoft Defender for Identity エクスペリエンス全体を Defender に導入する最初のステップMicrosoft 365[です](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="13ed1-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="13ed1-110">新しい Identity アラート ページでは、Microsoft Defender for Identity のお客様にクロスドメインシグナルエンリッチメントと新しい自動 ID 応答機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="13ed1-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="13ed1-111">これにより、セキュリティを確保し、セキュリティ操作の効率を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="13ed1-112">Microsoft 365 Defender を使用してアラートを調査する利点の[1](/microsoft-365/security/defender/microsoft-365-defender)つは、Microsoft Defender for Identity アラートがスイート内の他の各製品から取得した情報とさらに関連付けられているという利点があります。</span><span class="sxs-lookup"><span data-stu-id="13ed1-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="13ed1-113">これらの強化されたアラートは、Microsoft Defender for Microsoft 365および Microsoft Defender [for](/microsoft-365/security/office-365-security) Endpoint から発信される他Office 365のアラート形式と[一致しています](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="13ed1-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="13ed1-114">新しいページでは、ID に関連付けられたアラートを調査するために別の製品ポータルに移動する必要が実質的になくされます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="13ed1-115">Defender for Identity から発生したアラートによって、Microsoft 365 Defender の自動調査と応答[(AIR)](/microsoft-365/security/defender/m365d-autoir)機能がトリガーされ、アラートが自動的に修復され、疑わしいアクティビティに寄与する可能性があるツールやプロセスの軽減が可能になります。</span><span class="sxs-lookup"><span data-stu-id="13ed1-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

>[!IMPORTANT]
><span data-ttu-id="13ed1-116">Defender との統合の一環Microsoft 365、いくつかのオプションと詳細が Defender for Identity ポータルの場所から変更されています。</span><span class="sxs-lookup"><span data-stu-id="13ed1-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="13ed1-117">使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。</span><span class="sxs-lookup"><span data-stu-id="13ed1-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="13ed1-118">セキュリティアラートの確認</span><span class="sxs-lookup"><span data-stu-id="13ed1-118">Review security alerts</span></span>

<span data-ttu-id="13ed1-119">アラートには、[アラート] ページ、インシデント ページ、個々のデバイスのページ、高度な検索ページなど、複数の **場所からアクセス** できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="13ed1-120">この例では、[アラート] ページを **確認します**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-120">In this example, we'll review the **Alerts page**.</span></span>  

<span data-ttu-id="13ed1-121">[セキュリティ [センター Microsoft 365インシデント](https://security.microsoft.com/)] に移動し、[&**通知**] に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![[インシデントとアラート] に移動し、[アラート] をクリックします。](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="13ed1-123">Defender for Identity からのアラートを表示するには、上部の[フィルター]を選択し、[サービス ソース] で **[Microsoft Defender for Identity]** を選択し、[適用] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Id イベントの Defender のフィルター](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="13ed1-125">アラートは、アラート名、タグ、**重大度**、**調査** 状態、**状態**、**カテゴリ**、検出ソース、影響を受けた資産、**最初** のアクティビティ、および最後のアクティビティの情報と一緒に **表示されます**。 </span><span class="sxs-lookup"><span data-stu-id="13ed1-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Defender for Identity イベント](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="13ed1-127">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="13ed1-127">Manage alerts</span></span>

<span data-ttu-id="13ed1-128">アラートの **1 つの [アラート名** ] をクリックすると、アラートの詳細が表示されたページに移動します。</span><span class="sxs-lookup"><span data-stu-id="13ed1-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="13ed1-129">左側のウィンドウに、[発生した操作] の概要 **が表示されます**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![アラートで何が起こったか](../../media/defender-identity/what-happened.png)

<span data-ttu-id="13ed1-131">[何が **起こったか]** ボックスの上には、アラートの **アカウント、宛先\*\*\*\*ホスト**、および **送信元ホストの** ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="13ed1-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="13ed1-132">その他のアラートについては、追加のホスト、アカウント、IP アドレス、ドメイン、セキュリティ グループの詳細についてボタンが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="13ed1-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="13ed1-133">関係するエンティティの詳細を取得するには、それらを選択します。</span><span class="sxs-lookup"><span data-stu-id="13ed1-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="13ed1-134">右側のウィンドウに、アラートの詳細が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="13ed1-135">ここでは、詳細を確認し、いくつかのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="13ed1-136">**このアラートを分類** する - ここでは、このアラートを True アラートまたは **False アラート** として **指定できます。**</span><span class="sxs-lookup"><span data-stu-id="13ed1-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![アラートの分類](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="13ed1-138">**アラートの状態** - [ **分類の設定]** で、アラートを True または **False に** 分類 **できます**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="13ed1-139">[ **割り当て** 済み] で、アラートを自分に割り当てたり、割り当てを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![アラートの状態](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="13ed1-141">**アラートの** 詳細 - **[アラート** の詳細] で、特定のアラートに関する詳細情報を確認し、アラートの種類に関するドキュメントへのリンクを参照し、アラートが関連付けられているインシデントを確認し、このアラートの種類にリンクされている自動調査を確認し、影響を受けたデバイスとユーザーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![アラートの詳細](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="13ed1-143">**コメント&履歴** - アラートにコメントを追加し、アラートに関連付けられているすべてのアクションの履歴を確認できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![コメントと履歴](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="13ed1-145">**警告の** 管理 - [警告の **管理] を** 選択すると、次のウィンドウを編集できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="13ed1-146">**[状態**] - [新規 **]、[\*\*\*\*解決済み]、** または [進行中]**を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="13ed1-147">**分類** - [True アラート] **または [False アラート** ] **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="13ed1-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="13ed1-148">**コメント** - アラートに関するコメントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="13ed1-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="13ed1-149">[警告の管理] の横にある 3 つのドットを選択すると、脅威の専門家に相談したり、アラートを Excel ファイルにエクスポートしたり、別のインシデントに **リンク** することができます。 </span><span class="sxs-lookup"><span data-stu-id="13ed1-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![アラートの管理](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    ><span data-ttu-id="13ed1-151">このファイルExcel、使用可能なリンクが 2 つ用意されています **。[Microsoft Defender for Identity** の表示] と [Defender の表示 **] の 2** Microsoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="13ed1-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="13ed1-152">各リンクを使用すると、関連するポータルにアクセスし、そこにアラートに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="13ed1-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ed1-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ed1-153">See also</span></span>

- [<span data-ttu-id="13ed1-154">Defender でアラートをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="13ed1-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
