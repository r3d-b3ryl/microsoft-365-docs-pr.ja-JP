---
title: エンドポイント ASR ルールの Microsoft Defender のレポートとトラブルシューティング
description: このトピックでは、Microsoft Defender for Endpoint ASR ルールを報告およびトラブルシューティングする方法について説明します。
keywords: 攻撃表面の縮小ルール、asr、hips、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、エンドポイント用 microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246146"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a><span data-ttu-id="02086-104">ATP ASR ルールの Microsoft Defender のレポートとトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02086-104">Report and troubleshoot Microsoft Defender for ATP ASR Rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02086-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="02086-105">**Applies to:**</span></span>

- [<span data-ttu-id="02086-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02086-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="02086-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02086-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="02086-108">セキュリティ Microsoft 365は、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および管理するための新しいインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="02086-108">The Microsoft 365 security center is the new interface for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span> <span data-ttu-id="02086-109">ここでは組織のセキュリティの健全性を簡単に表示したり、デバイス、ユーザー、アプリを構成したり、不審なアクティビティのアラートを取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="02086-109">Here you can easily view the security health of your organization, act to configure devices, users, and apps, and get alerts for suspicious activity.</span></span> <span data-ttu-id="02086-110">Microsoft 365 セキュリティ センターは、セキュリティ管理者とセキュリティ運用チームが組織をより適切に管理および保護することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="02086-110">The Microsoft 365 security center is intended for security admins and security operations teams to better manage and protect their organization.</span></span> <span data-ttu-id="02086-111">で、Microsoft 365セキュリティ センターにアクセスします https://security.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="02086-111">Visit the Microsoft 365 security center at https://security.microsoft.com.</span></span>
<span data-ttu-id="02086-112">セキュリティ Microsoft 365では、現在の ASR ルールの構成と、資産内のイベントを完全に確認できます。</span><span class="sxs-lookup"><span data-stu-id="02086-112">In Microsoft 365 security center, we offer you a complete look at the current ASR rules configuration and events in your estate.</span></span> <span data-ttu-id="02086-113">これらのレポートを設定するには、デバイスを Microsoft Defender for Endpoint サービスにオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02086-113">Note that your devices must be onboarded into the Microsoft Defender for Endpoint service for these reports to be populated.</span></span>
<span data-ttu-id="02086-114">セキュリティ センターのスクリーンショットを次に示Microsoft 365レポート デバイス攻撃表面の縮小]  >    >  **の下に示します**。</span><span class="sxs-lookup"><span data-stu-id="02086-114">Here's a screenshot from the Microsoft 365 security center (under **Reports** > **Devices** > **Attack surface reduction**).</span></span> <span data-ttu-id="02086-115">デバイス レベルで、[攻撃表面 **縮小ルール]** ウィンドウ **から [構成] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="02086-115">At the device level, select **Configuration** from the **Attack surface reduction rules** pane.</span></span> <span data-ttu-id="02086-116">次の画面が表示され、特定のデバイスを選択し、個々の ASR ルール構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="02086-116">The following screen is displayed, where you can select a specific device and check its individual ASR rule configuration.</span></span>

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR ルール画面":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a><span data-ttu-id="02086-118">エンドポイント向け Microsoft Defender – 高度な検索</span><span class="sxs-lookup"><span data-stu-id="02086-118">Microsoft Defender for Endpoint – Advanced hunting</span></span>

<span data-ttu-id="02086-119">Microsoft Defender for Endpoint の最も強力な機能の 1 つは、高度な検索です。</span><span class="sxs-lookup"><span data-stu-id="02086-119">One of the most powerful features of Microsoft Defender for Endpoint is advanced hunting.</span></span> <span data-ttu-id="02086-120">高度な狩猟に慣れていない場合は、高度な狩猟で脅威を積極的 [に探す方法を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="02086-120">If you're unfamiliar with advanced hunting, refer [proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

<span data-ttu-id="02086-121">高度な検索はクエリ ベース (Kusto Query Language) の脅威検索ツールで、MDE エンドポイント検出と応答 (EDR) がすべてのコンピューターから収集する、キャプチャされた (生の) データの最大 30 日間を探索できます。</span><span class="sxs-lookup"><span data-stu-id="02086-121">Advanced hunting is a query-based (Kusto Query Language) threat-hunting tool that lets you explore up to 30 days of the captured (raw) data, that MDE Endpoint Detection and Response (EDR) collects from all your machines.</span></span> <span data-ttu-id="02086-122">高度な検索を通じて、イベントを積極的に検査して、興味深いインジケーターとエンティティを見つけ出します。</span><span class="sxs-lookup"><span data-stu-id="02086-122">Through advanced hunting, you can proactively inspect events to locate interesting indicators and entities.</span></span> <span data-ttu-id="02086-123">データへの柔軟なアクセスは、既知の脅威と潜在的な脅威の両方に対する抑制されていない検出に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02086-123">The flexible access to data helps unconstrained hunting for both known and potential threats.</span></span>

<span data-ttu-id="02086-124">高度な検索を通じて、ASR ルール情報を抽出し、レポートを作成し、特定の ASR ルール監査またはブロック イベントのコンテキストに関する詳細な情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="02086-124">Through advanced hunting, it's possible to extract ASR rules information, create reports, and get in-depth information on the context of a given ASR rule audit or block event.</span></span>

<span data-ttu-id="02086-125">ASR ルール イベントは、デバイス の詳細な検索セクションの DeviceEvents テーブルからクエリを実行Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="02086-125">ASR rules events are available to be queried from the DeviceEvents table in the advanced hunting section of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="02086-126">たとえば、次のような単純なクエリは、過去 30 日間、ASR ルールをデータ ソースとして持つすべてのイベントをレポートし、アクションタイプカウントで集計します。この場合は ASR ルールの実際のコード名になります。</span><span class="sxs-lookup"><span data-stu-id="02086-126">For example, a simple query such as the one below can report all the events that have ASR rules as data source, for the last 30 days, and will summarize them by the ActionType count, that in this case it will be the actual codename of the ASR rule.</span></span>

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高度な検索クエリ":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="高度なハンティング画面":::

<span data-ttu-id="02086-129">高度な検索を使用すると、個別のコンピューターで何かを特定するか、環境全体から分析情報を抽出するかに関係なく、何が起こっているかを確認するために、好みでクエリを形成できます。</span><span class="sxs-lookup"><span data-stu-id="02086-129">With advanced hunting you can shape the queries to your liking, so that you can see what is happening, regardless of whether you want to pinpoint something on an individual machine, or you want to extract insights from your entire environment.</span></span>

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a><span data-ttu-id="02086-130">Microsoft Defender for Endpoint machine Timeline</span><span class="sxs-lookup"><span data-stu-id="02086-130">Microsoft Defender for Endpoint machine timeline</span></span>

<span data-ttu-id="02086-131">高度な検索に代わる方法ですが、スコープが狭い場合は、Microsoft Defender for Endpoint マシンのタイムラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="02086-131">An alternative to advanced hunting, but with a narrower scope, is the Microsoft Defender for Endpoint machine timeline.</span></span> <span data-ttu-id="02086-132">Microsoft Defender セキュリティ センター の過去 6 か月間、デバイスのすべての収集イベントを表示するには、[コンピューター] リストに移動し、特定のコンピューターを選択し、[タイムライン] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02086-132">You can view all the collected events of a device, for the past six months, in the Microsoft Defender Security Center, by going to the Machines list, select a given machine, and then click on the Timeline tab.</span></span>

<span data-ttu-id="02086-133">次の図は、特定のエンドポイントでこれらのイベントのタイムライン ビューのスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="02086-133">Pictured below is a screenshot of the Timeline view of these events on a given endpoint.</span></span>  <span data-ttu-id="02086-134">このビューから、右側のウィンドウに沿ったイベント グループに基づいてイベント リストをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="02086-134">From this view, you can filter the events list based on any of the Event Groups along the right-side pane.</span></span> <span data-ttu-id="02086-135">アラートを表示したり、履歴タイムラインをスクロールしたりしながら、フラグ付きイベントと詳細イベントを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="02086-135">You can also enable or disable Flagged and Verbose events while viewing alerts and scrolling through the historical timeline.</span></span>

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="microsoft Defender セキュリティ センターのタイムライン":::

## <a name="how-to-troubleshoot-asr-rules"></a><span data-ttu-id="02086-137">ASR ルールのトラブルシューティング方法</span><span class="sxs-lookup"><span data-stu-id="02086-137">How to troubleshoot ASR rules?</span></span>

<span data-ttu-id="02086-138">最初の方法と最も直接的な方法は、powerShell コマンドレットを使用して、ASR ルールが有効になっている (およびそれらの構成) Windows デバイスでローカルで確認する方法です。</span><span class="sxs-lookup"><span data-stu-id="02086-138">The first and most immediate way is to check locally, on a Windows device, which ASR rules are enabled (and their configuration) is by using the PowerShell cmdlets.</span></span>

<span data-ttu-id="02086-139">ASR ルールの影響と運用をトラブルシューティングするために、Windows提供するその他の情報源を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02086-139">Here are a few other sources of information that Windows offers, to troubleshoot ASR rules’ impact and operation.</span></span>

### <a name="querying-which-rules-are-active"></a><span data-ttu-id="02086-140">アクティブなルールのクエリ</span><span class="sxs-lookup"><span data-stu-id="02086-140">Querying which rules are active</span></span>
<span data-ttu-id="02086-141">ASR ルールが既に有効になっているかどうかを判断する最も簡単な方法の 1 つは、PowerShell コマンドレット Get-MpPreference です。</span><span class="sxs-lookup"><span data-stu-id="02086-141">One of the easiest ways to determine if ASR rules are already enabled—and, is through a PowerShell cmdlet, Get-MpPreference.</span></span>
<span data-ttu-id="02086-142">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="02086-142">Here's an example:</span></span>

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference スクリプトを取得する":::

<span data-ttu-id="02086-144">複数の ASR ルールがアクティブで、構成されたアクションが異なります。</span><span class="sxs-lookup"><span data-stu-id="02086-144">There are multiple ASR rules active, with different configured actions.</span></span>

<span data-ttu-id="02086-145">ASR ルールに関する上記の情報を展開するには、ASR ルールのプロパティAttackSurfaceReductionRules_Idsおよび/**または\*\*\*\*AttackSurfaceReductionRules_Actions。**</span><span class="sxs-lookup"><span data-stu-id="02086-145">To expand the above information on ASR rules, you can use the properties **AttackSurfaceReductionRules_Ids** and/or **AttackSurfaceReductionRules_Actions**.</span></span>

<span data-ttu-id="02086-146">例:</span><span class="sxs-lookup"><span data-stu-id="02086-146">Example:</span></span>

<span data-ttu-id="02086-147">*Get-MPPreference |Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span><span class="sxs-lookup"><span data-stu-id="02086-147">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Ids*</span></span>

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference の例を取得する":::

<span data-ttu-id="02086-149">上記は、0 (Not Configured) とは異なる設定を持つ ASR ルールのすべての ID を示しています。</span><span class="sxs-lookup"><span data-stu-id="02086-149">The above shows all the IDs for ASR rules that have a setting different from 0 (Not Configured).</span></span>

<span data-ttu-id="02086-150">次に、各ルールが構成されている実際のアクション (ブロックまたは監査) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="02086-150">The next step is then to list the actual actions (Block or Audit) that each rule is configured with.</span></span> 

<span data-ttu-id="02086-151">*Get-MPPreference |Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span><span class="sxs-lookup"><span data-stu-id="02086-151">*Get-MPPreference | Select-Object -ExpandProperty\*\*AttackSurfaceReductionRules_Actions*</span></span>

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference の例 2 を取得する":::

### <a name="querying-blocking-and-auditing-events"></a><span data-ttu-id="02086-153">ブロックイベントと監査イベントのクエリ</span><span class="sxs-lookup"><span data-stu-id="02086-153">Querying blocking and auditing events</span></span>
<span data-ttu-id="02086-154">ASR ルール イベントは、ログ内でWindows Defenderできます。</span><span class="sxs-lookup"><span data-stu-id="02086-154">ASR rule events can be viewed within the Windows Defender log.</span></span>

<span data-ttu-id="02086-155">アクセスするには、イベント ビューアー Windows開き、[アプリケーションとサービスログ] Microsoft Windows Windows Defender  >    >    >    >  **を参照します**。</span><span class="sxs-lookup"><span data-stu-id="02086-155">To access it, open Windows Event Viewer, and browse to **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational**.</span></span>

:::image type="content" source="images/eventviewerscrnew.png" alt-text="イベント ビューアー scr":::

## <a name="microsoft-defender-malware-protection-logs"></a><span data-ttu-id="02086-157">Microsoft Defender マルウェア保護ログ</span><span class="sxs-lookup"><span data-stu-id="02086-157">Microsoft Defender Malware Protection Logs</span></span>
<span data-ttu-id="02086-158">また、必要に応じてタスクを管理および構成および自動化するために使用できる、Microsoft Defender ウイルス対策 専用のコマンド ライン ツールを使用してルール イベント `*mpcmdrun.exe*` を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="02086-158">You can also view rule events through the Microsoft Defender Antivirus dedicated command-line tool, called `*mpcmdrun.exe*`, that can be used to manage and configure, and automate tasks if needed.</span></span>

<span data-ttu-id="02086-159">このユーティリティは *、%ProgramFiles%\Windows Defender\MpCmdRun.exeにあります*。</span><span class="sxs-lookup"><span data-stu-id="02086-159">You can find this utility in *%ProgramFiles%\Windows Defender\MpCmdRun.exe*.</span></span> <span data-ttu-id="02086-160">管理者特権のコマンド プロンプト (管理者として実行) から実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02086-160">You must run it from an elevated command prompt (that is, run as Admin).</span></span>

<span data-ttu-id="02086-161">サポート情報を生成するには *、-getfilesMpCmdRun.exeを入力します*。</span><span class="sxs-lookup"><span data-stu-id="02086-161">To generate the support information, type *MpCmdRun.exe -getfiles*.</span></span> <span data-ttu-id="02086-162">しばらくすると、いくつかのログがアーカイブ (MpSupportFiles.cab) にパッケージ化され *、C:\ProgramData\Microsoft\Windows Defender\Support で使用できます*。</span><span class="sxs-lookup"><span data-stu-id="02086-162">After a while, several logs will be packaged into an archive (MpSupportFiles.cab) and made available in *C:\ProgramData\Microsoft\Windows Defender\Support*.</span></span>

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="マルウェア保護ログ":::

<span data-ttu-id="02086-164">そのアーカイブを抽出すると、トラブルシューティングの目的で多くのファイルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="02086-164">Extract that archive and you'll have many files available for troubleshooting purposes.</span></span>

<span data-ttu-id="02086-165">最も関連性の高いファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02086-165">The most relevant files are as follows:</span></span>

- <span data-ttu-id="02086-166">**MPOperationalEvents.txt** - このファイルには、イベント ビューアーの運用ログに関する同Windows Defenderが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02086-166">**MPOperationalEvents.txt** - This file contains same level of information found in Event Viewer for Windows Defender’s Operational log.</span></span>
- <span data-ttu-id="02086-167">**MPRegistry.txt** – このファイルでは、サポート ログがキャプチャされた時点から、現在Windows Defender構成を分析できます。</span><span class="sxs-lookup"><span data-stu-id="02086-167">**MPRegistry.txt** – In this file you will can analyze all the current Windows Defender configurations, from the moment the support logs were captured.</span></span>
- <span data-ttu-id="02086-168">**MPLog.txt** – このログには、サーバーのすべてのアクション/操作に関する詳細な情報がWindows Defender。</span><span class="sxs-lookup"><span data-stu-id="02086-168">**MPLog.txt** – This log contains more verbose information about all the actions/operations of the Windows Defender.</span></span>
