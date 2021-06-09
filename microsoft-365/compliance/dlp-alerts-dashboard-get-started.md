---
title: データ損失防止の警告ダッシュボードを開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: データ損失防止ポリシーのアラートの定義と管理について説明します。
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843868"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="9e3a2-103">データ損失防止の警告ダッシュボードを開始する</span><span class="sxs-lookup"><span data-stu-id="9e3a2-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="9e3a2-104">データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐための保護措置を取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="9e3a2-105">機密性の高いアイテムに対してアクションが実行された場合は、DLP のアラートを構成することで通知を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="9e3a2-106">この記事では、データ損失防止 (DLP) ポリシーにリンクされているリッチ アラート ポリシーを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="9e3a2-107">DLP ポリシー違反のアラート、イベント、および関連するメタデータを[](https://compliance.microsoft.com/)表示するには、Microsoft 365 コンプライアンス センターで[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)アラート管理ダッシュボードを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="9e3a2-108">DLP アラートを使用する場合は、「データ損失防止アラート ダッシュボードについて [」を確認する必要があります。](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="9e3a2-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9e3a2-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="9e3a2-109">Before you begin</span></span>

<span data-ttu-id="9e3a2-110">開始する前に、必要な前提条件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="9e3a2-111">DLP アラート管理ダッシュボードのライセンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="9e3a2-112">アラート構成オプションのライセンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="9e3a2-113">Roles</span><span class="sxs-lookup"><span data-stu-id="9e3a2-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="9e3a2-114">DLP アラート管理ダッシュボードのライセンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="9e3a2-115">DLP の対象となるテナントOffice 365 DLP アラート管理ダッシュボードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="9e3a2-116">開始するには、オンライン、オンライン、およびOffice 365の DLP のExchange Online対象SharePoint必要OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="9e3a2-117">OFFICE 365 DLP のライセンス要件の詳細については、「どのライセンスがユーザーにサービスの恩恵を受ける権利を提供するか」[を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="9e3a2-118">Teams [DLP](dlp-microsoft-teams.md)の対象となるエンドポイント[DLP](endpoint-dlp-learn-about.md)を使用しているお客様は、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="9e3a2-119">コンテンツ **プレビュー機能は** 、次のライセンスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="9e3a2-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="9e3a2-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="9e3a2-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="9e3a2-121">Office 365 (E5)</span></span>
- <span data-ttu-id="9e3a2-122">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="9e3a2-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="9e3a2-123">Microsoft 365 E5/A5 情報保護とガバナンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="9e3a2-124">Microsft 365 E5/A5 コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="9e3a2-125">アラート構成オプションのライセンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="9e3a2-126">**単** 一イベントアラートの構成: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生する度にアラートがトリガーされる場合にのみアラート ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="9e3a2-127">**集約アラート構成**: しきい値に基づいて集約アラート ポリシーを構成するには、次のいずれかのライセンス構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="9e3a2-128">E5 または G5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="9e3a2-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="9e3a2-129">E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="9e3a2-130">Office 365 Advanced Threat Protection プラン 2</span><span class="sxs-lookup"><span data-stu-id="9e3a2-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="9e3a2-131">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="9e3a2-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="9e3a2-132">Microsoft 365証拠開示と監査アドオン ライセンス</span><span class="sxs-lookup"><span data-stu-id="9e3a2-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="9e3a2-133">Roles</span><span class="sxs-lookup"><span data-stu-id="9e3a2-133">Roles</span></span>


<span data-ttu-id="9e3a2-134">DLP アラート管理ダッシュボードを表示する場合、または DLP ポリシーでアラート構成オプションを編集する場合は、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="9e3a2-135">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="9e3a2-135">Compliance Administrator</span></span>
- <span data-ttu-id="9e3a2-136">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="9e3a2-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="9e3a2-137">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="9e3a2-137">Security Administrator</span></span>
- <span data-ttu-id="9e3a2-138">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="9e3a2-138">Security Operator</span></span>
- <span data-ttu-id="9e3a2-139">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="9e3a2-139">Security Reader</span></span>

<span data-ttu-id="9e3a2-140">DLP アラート管理ダッシュボードにアクセスするには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="9e3a2-141">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="9e3a2-141">Manage alerts</span></span>

<span data-ttu-id="9e3a2-142">と、次の 2 つの役割のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-142">and either of these two roles:</span></span>

- <span data-ttu-id="9e3a2-143">DLP コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="9e3a2-143">DLP Compliance Management</span></span>
- <span data-ttu-id="9e3a2-144">View-Only DLP コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="9e3a2-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="9e3a2-145">コンテンツ プレビュー機能と一致した機密コンテンツおよびコンテキスト機能にアクセスするには、次のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="9e3a2-146">コンテンツ エクスプローラー コンテンツ ビューアーの役割グループ</span><span class="sxs-lookup"><span data-stu-id="9e3a2-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="9e3a2-147">データ分類コンテンツ ビューアーの役割が事前に割り当てられている。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="9e3a2-148">DLP アラート構成</span><span class="sxs-lookup"><span data-stu-id="9e3a2-148">DLP alert configuration</span></span>

<span data-ttu-id="9e3a2-149">DLP ポリシーでアラートを構成する方法については、「データ損失防止の開始場所」 [を参照してください](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="9e3a2-150">集計イベントアラートの構成</span><span class="sxs-lookup"><span data-stu-id="9e3a2-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="9e3a2-151">組織に集約アラート構成オプションの[](#licensing-for-alert-configuration-options)ライセンスが設定されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集約されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

<span data-ttu-id="9e3a2-153">この構成を使用すると、アクティビティがポリシー条件に一致するか、アクティビティの数に基づいて、または削除されたデータの量に基づいて、特定のしきい値を超えた場合にアラートを生成するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="9e3a2-154">単一イベントアラートの構成</span><span class="sxs-lookup"><span data-stu-id="9e3a2-154">Single event alert configuration</span></span>

<span data-ttu-id="9e3a2-155">組織に単一イベントアラート構成[](#licensing-for-alert-configuration-options)オプションのライセンスが適用されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="9e3a2-156">DLP ルールの一致が発生する度に発生するアラートを作成するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="単一イベントアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="9e3a2-158">DLP アラートの調査</span><span class="sxs-lookup"><span data-stu-id="9e3a2-158">Investigate a DLP alert</span></span>

<span data-ttu-id="9e3a2-159">DLP アラート管理ダッシュボードを操作するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="9e3a2-160">コンプライアンス センター [Microsoft 365、](https://www.compliance.microsoft.com)データ損失防止 **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="9e3a2-161">[アラート] **タブを** 選択して、DLP アラート ダッシュボードを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="9e3a2-162">アラートを選択して詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

4. <span data-ttu-id="9e3a2-164">[イベント **] タブを** 選択して、アラートに関連付けられているすべてのイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="9e3a2-165">特定のイベントを選択して、その詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="9e3a2-166">使用可能なイベントの詳細の一覧については、「データ損失防止アラート ダッシュボードについて」 [を参照してください](dlp-alerts-dashboard-learn.md)。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="9e3a2-167">[詳細 **] を** 選択して、 **アラートの [概要** ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="9e3a2-168">概要ページには、次の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="9e3a2-169">何が起こったかの</span><span class="sxs-lookup"><span data-stu-id="9e3a2-169">of what happened</span></span>
    1. <span data-ttu-id="9e3a2-170">ポリシーの一致を引き起こしたアクションを実行したユーザー</span><span class="sxs-lookup"><span data-stu-id="9e3a2-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="9e3a2-171">一致するポリシーに関する情報など</span><span class="sxs-lookup"><span data-stu-id="9e3a2-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="9e3a2-172">[イベント] **タブを** 選択して、次の情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="9e3a2-173">関連するコンテンツ</span><span class="sxs-lookup"><span data-stu-id="9e3a2-173">content involved</span></span>
    1. <span data-ttu-id="9e3a2-174">一致する機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="9e3a2-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="9e3a2-175">metadata</span><span class="sxs-lookup"><span data-stu-id="9e3a2-175">metadata</span></span>

7. <span data-ttu-id="9e3a2-176">[機密情報 **の種類] タブを** 選択して、コンテンツで検出された機密情報の種類に関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="9e3a2-177">詳細には、信頼度、カウント、および機密情報の種類に一致するコンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="9e3a2-178">アラートを調査した後、[概要]タブに戻り、トリアージを管理し、アラートの処理を管理し、コメントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="9e3a2-179">ワークフロー管理の履歴を表示するには、[管理ログ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="9e3a2-180">アラートに必要なアクションを実行した後、アラートの状態を [解決済み] **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="9e3a2-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e3a2-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e3a2-181">See also</span></span>

- [<span data-ttu-id="9e3a2-182">データ損失防止アラートとアラート ダッシュボードの詳細</span><span class="sxs-lookup"><span data-stu-id="9e3a2-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="9e3a2-183">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="9e3a2-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)