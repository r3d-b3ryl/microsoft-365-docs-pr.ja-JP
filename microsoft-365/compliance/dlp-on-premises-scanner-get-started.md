---
title: Microsoft 365 Endpoint データ損失防止 (プレビュー) を開始する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 のデータ損失防止のオンプレミス スキャナーを設定する
ms.openlocfilehash: b21474f3a9e045bf353d62ef6c7c8d4174801a1b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623835"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="651c1-103">データ損失防止のオンプレミス スキャナー (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="651c1-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="651c1-104">この記事では、Microsoft 365 データ損失防止オンプレミス スキャナーの前提条件と構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="651c1-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="651c1-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="651c1-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="651c1-106">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="651c1-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="651c1-107">DLP オンプレミス スキャナーの使用を開始する前に、[Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) およびアドオンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="651c1-108">プレビューに参加するには、DLP ルールを設定する管理者アカウントに次のライセンスのいずれかを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="651c1-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="651c1-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="651c1-110">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="651c1-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="651c1-111">Microsoft 365 E5 情報保護およびガバナンス</span><span class="sxs-lookup"><span data-stu-id="651c1-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="651c1-112">ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="651c1-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="651c1-113">Permissions</span></span>


<span data-ttu-id="651c1-114">Endpoint DLP からのデータは、[アクティビティ エクスプローラー](data-classification-activity-explorer.md)で表示します。</span><span class="sxs-lookup"><span data-stu-id="651c1-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="651c1-115">Activity エクスプローラーに権限を付与する役割は4つあります。データへのアクセスに使用するアカウントは、次のいずれかのメンバーでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="651c1-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="651c1-116">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="651c1-116">Global administrator</span></span>
- <span data-ttu-id="651c1-117">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="651c1-117">Compliance administrator</span></span>
- <span data-ttu-id="651c1-118">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="651c1-118">Security administrator</span></span>
- <span data-ttu-id="651c1-119">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="651c1-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="651c1-120">DLP オンプレミス スキャナーの前提条件</span><span class="sxs-lookup"><span data-stu-id="651c1-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="651c1-p103">Azure Information Protection (AIP) スキャナーは、DLP ポリシーの一致とポリシーの適用を実装します。スキャナーは AIP クライアントの一部としてインストールされるため、インストールは AIP、AIP クライアント、および AIP 統合ラベル スキャナーのすべての前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="651c1-123">AIP クライアントとスキャナーを展開します。</span><span class="sxs-lookup"><span data-stu-id="651c1-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="651c1-124">[AIP 統合ラベル クライアントのインストール](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)と [] の詳細については、「[Azure Information Protection 統合ラベルスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="651c1-125">すべての検出ルールが機密情報タイプのみに基づいている場合でも、テナントには少なくとも 1 つのラベルとポリシーが公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="651c1-126">DLP オンプレミス スキャナーを展開する</span><span class="sxs-lookup"><span data-stu-id="651c1-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="651c1-127">[AIP 統合ラベル クライアントのインストール](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="651c1-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="651c1-128">「[Azure Information Protection 統合ラベルスキャナーの構成とインストール](/azure/information-protection/deploy-aip-scanner-configure-install)」の手順に従って、スキャナーのインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="651c1-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="651c1-129">ネットワーク検出ジョブの構成はオプションの手順です。</span><span class="sxs-lookup"><span data-stu-id="651c1-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="651c1-130">これをスキップして、コンテンツ スキャン ジョブでスキャンする特定のリポジトリを定義できます。</span><span class="sxs-lookup"><span data-stu-id="651c1-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="651c1-131">コンテンツ スキャン ジョブを作成し、DLP エンジンによる評価が必要なファイルをホストするリポジトリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="651c1-132">作成したコンテンツ スキャン ジョブで DLP ルールを有効にし、DLP 有効化段階に直接進む場合を除いて、**[有効にする]** オプションを **[オフ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="651c1-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="651c1-p106">コンテンツ スキャン ジョブが適切なクラスターに割り当てられていることを確認します。それでもコンテンツ スキャン ジョブを作成しなかった場合は、新しいジョブを作成して、パブリック プレビュー バージョンを実行するスキャナー ノードを含むクラスターに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="651c1-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="651c1-135">[Azure ポータルの Azure Information Protection](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) 拡張機能に接続し、スキャンを実行するコンテンツ スキャン ジョブにリポジトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="651c1-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="651c1-136">次のいずれかの操作を実行して、スキャンを実行します。 </span><span class="sxs-lookup"><span data-stu-id="651c1-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="651c1-137">スキャナーのスケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="651c1-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="651c1-138">ポータルで手動の **[今すぐスキャン]** オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="651c1-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="651c1-139">または、**Start-AIPScan** PowerShell コマンドレットを実行します</span><span class="sxs-lookup"><span data-stu-id="651c1-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="651c1-140">スキャナーはデフォルトでリポジトリのデルタ スキャンを実行し、ファイルが変更されたか、完全な再スキャンを開始しない限り、前のスキャン サイクルですでにスキャンされたファイルはスキップされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="651c1-141">完全な再スキャンは、UI の **[すべてのファイルを再スキャンする]** オプションを使用するか、**Start-AIPScan-Reset** を実行することで開始できます。</span><span class="sxs-lookup"><span data-stu-id="651c1-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="651c1-142">Microsoft 365 コンプライアンス センターの [[データ損失防止]](https://compliance.microsoft.com/datalossprevention?viewid=policies) ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="651c1-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="651c1-143">**[ポリシーの作成]** を選択し、テスト DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="651c1-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="651c1-144">ポリシーの作成についてサポートが必要な場合は、「[テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="651c1-145">この機能に慣れるまで、必ずテストで実行してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="651c1-146">ポリシーには、次のパラメータを使用します。</span><span class="sxs-lookup"><span data-stu-id="651c1-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="651c1-147">必要に応じて、DLP オンプレミス スキャナー ルールを特定の場所にスコープします。</span><span class="sxs-lookup"><span data-stu-id="651c1-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="651c1-148">**[場所]** のスコープを **[すべて]** に設定すると、スキャナーによってスキャンされたすべてのファイルが DLP ルールの照合と適用の対象になります。</span><span class="sxs-lookup"><span data-stu-id="651c1-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="651c1-149">場所を指定するときは、除外リストまたは包含リストのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="651c1-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="651c1-150">パブリック プレビュー中は、両方を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="651c1-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="651c1-151">ルールは、包含リストにリストされているパターンの 1 つに一致するパスにのみ関連するか、包含リストにリストされているパターンに一致するファイルを除くすべてのファイルに関連するように定義できます。</span><span class="sxs-lookup"><span data-stu-id="651c1-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="651c1-152">ローカル パスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="651c1-152">No local paths are supported.</span></span> <span data-ttu-id="651c1-153">有効なパスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="651c1-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="651c1-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="651c1-154">\\\server\share</span></span>
      - <span data-ttu-id="651c1-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="651c1-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="651c1-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="651c1-156">\*\\folder1</span></span>
      - <span data-ttu-id="651c1-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="651c1-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="651c1-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="651c1-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="651c1-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="651c1-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="651c1-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="651c1-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="651c1-161">許容できない値の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="651c1-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="651c1-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="651c1-162">\*\\a</span></span>
      - <span data-ttu-id="651c1-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="651c1-163">Aaa</span></span>
      - <span data-ttu-id="651c1-164">c:</span><span class="sxs-lookup"><span data-stu-id="651c1-164">c:</span></span>\
      - <span data-ttu-id="651c1-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="651c1-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="651c1-166">除外リストは、包含リストよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="651c1-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="651c1-167">DLP アラート管理ダッシュボードでの DLP オンプレミス スキャナー アラートの表示</span><span class="sxs-lookup"><span data-stu-id="651c1-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="651c1-168">Microsoft 365 コンプライアンス センターの [[データ損失防止]](https://compliance.microsoft.com/datalossprevention?viewid=policies) ページを開き、**[アラート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="651c1-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="651c1-169">エンドポイント DLP ポリシーの警告を表示するには、「[DLP ポリシーの警告を構成および表示する方法](dlp-configure-view-alerts-policies.md)」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="651c1-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="651c1-170">アクティビティ エクスプローラーと監査ログでの DLP オンプレミス スキャナーの表示</span><span class="sxs-lookup"><span data-stu-id="651c1-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="651c1-171">オンプレミス スキャナーでは、監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="651c1-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="651c1-172">Microsoft 365では、監査は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="651c1-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="651c1-173">Microsoft 365 コンプライアンスセンターでドメインの[データ分類ページ](https://compliance.microsoft.com/dataclassification?viewid=overview)を開き、Activity エクスプローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="651c1-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="651c1-174">オンプレミス スキャナーの場所のすべてのデータにアクセスしてフィルタリングするには、「[Activity エクスプローラースタートガイド](data-classification-activity-explorer.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="651c1-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="651c1-175">[[コンプライアンス センターの監査ログ]](https://security.microsoft.com/auditlogsearch) を開きます。</span><span class="sxs-lookup"><span data-stu-id="651c1-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="651c1-176">パブリック プレビューの間、DLP ルールの一致は監査ログ UI で利用可能であるか、[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="651c1-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="651c1-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="651c1-177">Next steps</span></span>
<span data-ttu-id="651c1-178">DLP オンプレミス の場所のテスト ポリシーを展開し、アクティビティ エクスプローラーでアクティビティ データを表示できるようになったので、機密アイテムを保護する DLP ポリシーを作成する次のステップに進む準備ができました。</span><span class="sxs-lookup"><span data-stu-id="651c1-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="651c1-179">オンプレミスでのDLPの使用 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="651c1-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="651c1-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="651c1-180">See also</span></span>

- [<span data-ttu-id="651c1-181">DLP オンプレミス スキャナーの前提条件 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="651c1-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="651c1-182">DLP オンプレミス スキャナーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="651c1-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="651c1-183">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="651c1-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="651c1-184">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="651c1-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="651c1-185">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="651c1-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="651c1-186">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="651c1-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)