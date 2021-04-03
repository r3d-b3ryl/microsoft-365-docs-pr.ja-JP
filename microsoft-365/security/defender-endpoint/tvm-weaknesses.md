---
title: 組織の脆弱性 - 脅威と脆弱性の管理
description: 組織で実行されているソフトウェアで見つかった脆弱性の一般的な脆弱性と露出 (CVE) ID を一覧表示します。 Microsoft Defender ATP の脅威と脆弱性管理機能によって検出されました。
keywords: mdatp の脅威&脆弱性管理、脅威と脆弱性管理、mdatp tvm の弱点ページ、tvm、tvm の脆弱性リスト、tvm の脆弱性の詳細を使用して弱点を見つける
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 775592cd2ed9c29df79b04e07cb53efb7bea82d6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501244"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="f65b2-105">組織の脆弱性 - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="f65b2-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f65b2-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f65b2-106">**Applies to:**</span></span>
- [<span data-ttu-id="f65b2-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f65b2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f65b2-108">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="f65b2-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f65b2-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f65b2-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f65b2-110">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f65b2-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f65b2-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f65b2-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="f65b2-112">脅威と脆弱性の管理では、Defender for Endpoint のエンドポイント保護で同じシグナルを使用して、脆弱性をスキャンおよび検出します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="f65b2-113">[ **弱点] ページには** 、共通の脆弱性と露出 (CVE) ID を一覧表示して、デバイスが公開されるソフトウェアの脆弱性が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="f65b2-114">重大度、一般的な脆弱性スコアリング システム (CVSS) の評価、組織での普及率、対応する侵害、脅威の分析情報なども表示できます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="f65b2-115">脆弱性に割り当てられた公式の CVE-ID がない場合、脆弱性名は脅威と脆弱性の管理によって割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="f65b2-116">新しい脆弱性イベントに関する電子メールを取得するには [、「Configure vulnerability email notifications in Microsoft Defender for Endpoint」を参照してください。](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="f65b2-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="f65b2-117">[弱点] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="f65b2-118">[弱点] ページにアクセスするには、次に示すいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f65b2-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="f65b2-119">Microsoft Defender **セキュリティ センター** の [脅威と脆弱性管理] ナビゲーション メニューから [ [弱点] を選択する](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f65b2-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="f65b2-120">グローバル検索</span><span class="sxs-lookup"><span data-stu-id="f65b2-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="f65b2-121">ナビゲーション メニュー</span><span class="sxs-lookup"><span data-stu-id="f65b2-121">Navigation menu</span></span>

<span data-ttu-id="f65b2-122">[脅威と脆弱性の管理] ナビゲーション メニューに移動し、[弱点] を選択 **して** CVEs の一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="f65b2-123">グローバル検索の脆弱性</span><span class="sxs-lookup"><span data-stu-id="f65b2-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="f65b2-124">グローバル検索ドロップダウン メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="f65b2-125">[ **脆弱性と** キーイン] を選択し、探している共通の脆弱性と露出 (CVE) ID を選択し、検索アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="f65b2-126">[ **弱点] ページ** が開き、探している CVE 情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="f65b2-127">![ドロップダウン オプション "脆弱性" が選択されたグローバル検索ボックスと CVE の例。](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="f65b2-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="f65b2-128">CVE を選択して、脆弱性の説明、詳細、脅威の分析情報、公開されたデバイスなど、詳細情報を含むフライアウト パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="f65b2-129">[弱点] ページで残りの脆弱性を確認するには、「CVE」と入力し、[検索] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="f65b2-130">弱点の概要</span><span class="sxs-lookup"><span data-stu-id="f65b2-130">Weaknesses overview</span></span>

<span data-ttu-id="f65b2-131">公開されているデバイスの脆弱性を修復して、資産と組織のリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="f65b2-132">[ **公開されたデバイス] 列** に 0 が表示されている場合は、危険にさらされません。</span><span class="sxs-lookup"><span data-stu-id="f65b2-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![ランディング ページの弱点。](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="f65b2-134">侵害と脅威に関する分析情報</span><span class="sxs-lookup"><span data-stu-id="f65b2-134">Breach and threat insights</span></span>

<span data-ttu-id="f65b2-135">アイコンが赤に色付けされている場合は、[ **脅威** ] 列に関連する侵害と脅威の分析情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="f65b2-136">継続的な脅威に関連付けられている推奨事項の優先順位を常に設定します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="f65b2-137">これらの推奨事項には、脅威の分析情報アイコン赤いバグの簡単 ![ な描画がマークされています。](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="f65b2-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="f65b2-138">と侵害インサイト アイコン ![ ターゲットに当たる矢印の簡単な描画。 ](images/tvm_alert_icon.png)</span><span class="sxs-lookup"><span data-stu-id="f65b2-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="f65b2-139">侵害の分析情報アイコンは、組織に脆弱性が見つかった場合に強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="f65b2-140">![アイコンの上にカーソルを置くと表示される可能性がある侵害インサイト テキストの例。</span><span class="sxs-lookup"><span data-stu-id="f65b2-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="f65b2-141">この 1 つは、「アクティブなアラートの可能性は、この推奨事項に関連付けられている可能性があります。](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="f65b2-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="f65b2-142">組織で見つかった脆弱性に関連する悪用がある場合は、脅威の分析情報アイコンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="f65b2-143">アイコンにカーソルを合わせると、脅威がエクスプロイト キットの一部かどうか、または特定の高度な永続的なキャンペーンやアクティビティ グループに接続されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="f65b2-144">利用可能な場合は、ゼロデイの悪用ニュース、開示、または関連するセキュリティ アドバイザリを含む Threat Analytics レポートへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="f65b2-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![アイコンにカーソルを合わせると表示される可能性がある脅威の分析情報テキスト。](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="f65b2-147">脆弱性に関する分析情報を取得する</span><span class="sxs-lookup"><span data-stu-id="f65b2-147">Gain vulnerability insights</span></span>

<span data-ttu-id="f65b2-148">CVE を選択すると、フライアウト パネルが開き、脆弱性の説明、詳細、脅威の分析情報、公開されたデバイスなどの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="f65b2-149">"OS 機能" カテゴリは、関連するシナリオで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="f65b2-150">公開されているデバイスを使用して、すべての CVE の関連するセキュリティ推奨事項に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![弱点の飛び出しの例。](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="f65b2-152">サポートされていないソフトウェア</span><span class="sxs-lookup"><span data-stu-id="f65b2-152">Software that isn't supported</span></span>

<span data-ttu-id="f65b2-153">脆弱性管理の脅威によって現在サポートされていないソフトウェア&の CVEs は、引き続き [弱点] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="f65b2-154">ソフトウェアはサポートされていないので、使用できるデータは限られています。</span><span class="sxs-lookup"><span data-stu-id="f65b2-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="f65b2-155">公開されているデバイス情報は、サポートされていないソフトウェアの CVEs では使用できません。</span><span class="sxs-lookup"><span data-stu-id="f65b2-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="f65b2-156">[公開されたデバイス] セクションで [使用できない] オプションを選択して、サポートされていないソフトウェアでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![公開されているデバイス フィルター。](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="f65b2-158">他の場所で一般的な脆弱性と露出 (CVE) エントリを表示する</span><span class="sxs-lookup"><span data-stu-id="f65b2-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="f65b2-159">ダッシュボードの脆弱なソフトウェアの上位</span><span class="sxs-lookup"><span data-stu-id="f65b2-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="f65b2-160">脅威と脆弱性 [の管理ダッシュボードに移動](tvm-dashboard-insights.md) し、脆弱なソフトウェアのトップ ウィジェット **までスクロール** ダウンします。</span><span class="sxs-lookup"><span data-stu-id="f65b2-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="f65b2-161">各ソフトウェアで見つかった脆弱性の数と、脅威情報、デバイスの露出の詳細なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![ソフトウェア、弱点、脅威、公開されたデバイスの 4 つの列を持つ、脆弱なソフトウェア カードの上位。](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="f65b2-163">調査するソフトウェアを選択してドリルダウン ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="f65b2-164">[検出された **脆弱性] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="f65b2-165">脆弱性の詳細については、調査する脆弱性を選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Windows Server 2019 のドリルダウンの概要。](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="f65b2-167">デバイス ページで脆弱性を検出する</span><span class="sxs-lookup"><span data-stu-id="f65b2-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="f65b2-168">デバイス ページに関連する弱点情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="f65b2-169">Microsoft Defender Security Center ナビゲーション メニュー バーに移動し、デバイス アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="f65b2-170">[ **デバイス] リスト ページ** が開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="f65b2-171">[デバイス **] リスト ページ** で、調査するデバイス名を選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![調査するデバイスが選択されているデバイスの一覧。](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="f65b2-173">[デバイス] ページが開き、調査するデバイスの詳細と応答オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="f65b2-174">[検出 **された脆弱性] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f65b2-174">Select **Discovered vulnerabilities**.</span></span>

    ![詳細と応答オプションを含むデバイス ページ。](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="f65b2-176">調査する脆弱性を選択して、CVE の詳細 (脆弱性の説明、脅威の分析情報、検出ロジックなど) を含むフライアウト パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="f65b2-177">CVE 検出ロジック</span><span class="sxs-lookup"><span data-stu-id="f65b2-177">CVE Detection logic</span></span>

<span data-ttu-id="f65b2-178">ソフトウェアの証拠と同様に、デバイスに適用した検出ロジックが表示され、脆弱性が確認されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="f65b2-179">新しいセクションは "Detection Logic" (デバイス ページで検出された脆弱性) と呼ばれ、検出ロジックとソースを示します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="f65b2-180">"OS 機能" カテゴリは、関連するシナリオにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="f65b2-181">CVE は、特定の OS コンポーネントが有効になっている場合にのみ、脆弱な OS を実行するデバイスに影響します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="f65b2-182">たとえば、Windows Server 2019 の DNS コンポーネントに脆弱性が存在するとします。</span><span class="sxs-lookup"><span data-stu-id="f65b2-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="f65b2-183">この新機能では、この CVE を WINDOWS Server 2019 デバイスにのみ接続し、DNS 機能を OS で有効にします。</span><span class="sxs-lookup"><span data-stu-id="f65b2-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![デバイスと KB で検出されたソフトウェアを一覧表示する検出ロジックの例。](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="f65b2-185">レポートの不正確さ</span><span class="sxs-lookup"><span data-stu-id="f65b2-185">Report inaccuracy</span></span>

<span data-ttu-id="f65b2-186">あいまいな情報、不正確な情報、または不完全な情報が表示された場合は、誤検知を報告します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="f65b2-187">既に修復済みのセキュリティ推奨事項について報告できます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="f65b2-188">[弱点] ページで CVE を開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="f65b2-189">[ **不正確なレポート] を選択すると、** フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="f65b2-190">ドロップダウン メニューから不正確なカテゴリを選択し、メール アドレスと不正確な詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="f65b2-191">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f65b2-191">Select **Submit**.</span></span> <span data-ttu-id="f65b2-192">フィードバックは、脅威と脆弱性管理の専門家に直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f65b2-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f65b2-193">関連記事</span><span class="sxs-lookup"><span data-stu-id="f65b2-193">Related articles</span></span>

- [<span data-ttu-id="f65b2-194">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="f65b2-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f65b2-195">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="f65b2-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="f65b2-196">ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="f65b2-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="f65b2-197">ダッシュボード インサイト</span><span class="sxs-lookup"><span data-stu-id="f65b2-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="f65b2-198">Microsoft Defender for Endpoint Devices リストの表示と整理</span><span class="sxs-lookup"><span data-stu-id="f65b2-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
