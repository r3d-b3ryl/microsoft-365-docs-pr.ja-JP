---
title: 脅威と脆弱性管理のソフトウェア インベントリ
description: Microsoft Defender for Endpoint の脅威と脆弱性管理のソフトウェア インベントリ ページには、ソフトウェアで検出された脆弱性と脆弱性の数が表示されます。
keywords: 脅威と脆弱性の管理、エンドポイント用 Microsoft Defender、エンドポイント ソフトウェア インベントリ用 Microsoft Defender、mdatp 脅威 & 脆弱性管理、mdatp 脅威 & 脆弱性管理ソフトウェア インベントリ、mdatp tvm ソフトウェア インベントリ、tvm ソフトウェア インベントリ
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
ms.openlocfilehash: a4ceb7cc4d39dbddbb4cd325491c16f4503bfc52
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689379"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="f1f36-104">ソフトウェア インベントリ - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="f1f36-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1f36-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f1f36-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1f36-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1f36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f1f36-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="f1f36-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1f36-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1f36-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f1f36-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f1f36-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f1f36-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f1f36-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="f1f36-111">脅威と脆弱性管理のソフトウェア インベントリは、公式の共通プラットフォーム列挙 [(CPE)](https://nvd.nist.gov/products/cpe)を持つ組織内の既知のソフトウェアの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f1f36-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="f1f36-112">公式 CPE のないソフトウェア製品には、脆弱性が公開されません。</span><span class="sxs-lookup"><span data-stu-id="f1f36-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="f1f36-113">また、ベンダーの名前、弱点の数、脅威、公開されているデバイスの数などの詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1f36-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="f1f36-114">メカニズム</span><span class="sxs-lookup"><span data-stu-id="f1f36-114">How it works</span></span>

<span data-ttu-id="f1f36-115">検出の分野では [、Microsoft Defender for Endpoint](overview-endpoint-detection-response.md)の検出および応答機能の検出と脆弱性評価を担当するシグナルの同じセットを活用しています。</span><span class="sxs-lookup"><span data-stu-id="f1f36-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="f1f36-116">リアルタイムで、数分で、脆弱性情報が発見されるのを見る事が可能です。</span><span class="sxs-lookup"><span data-stu-id="f1f36-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="f1f36-117">エンジンは、複数のセキュリティ フィードから情報を自動的に取得します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="f1f36-118">実際には、特定のソフトウェアがライブ脅威キャンペーンに接続されている場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="f1f36-119">また、利用可能な脅威分析レポートへのリンクもすぐに提供されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="f1f36-120">[ソフトウェア インベントリ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="f1f36-121">Microsoft Defender セキュリティ センターの[脅威と脆弱性管理] ナビゲーション メニューから [ソフトウェア インベントリ] を選択して、[ソフトウェア インベントリ][ページにアクセスします](portal-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f36-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="f1f36-122">デバイスリストから個々のデバイス ページ内の特定のデバイス上のソフトウェア [を表示します](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f1f36-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="f1f36-123">Microsoft Defender for Endpoint グローバル検索を使用してソフトウェアを検索する場合は、スペースの代わりにアンダースコアを付けなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f1f36-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="f1f36-124">たとえば、最適な検索結果については、「Windows 10」ではなく「windows_10」と記述します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="f1f36-125">ソフトウェア インベントリの概要</span><span class="sxs-lookup"><span data-stu-id="f1f36-125">Software inventory overview</span></span>

<span data-ttu-id="f1f36-126">[ **ソフトウェア インベントリ]** ページが開き、ネットワークにインストールされているソフトウェアの一覧 (ベンダー名、見つかった弱点、関連する脅威、公開されたデバイス、露出スコアへの影響、タグなど) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="f1f36-127">リスト ビューは、ソフトウェアで見つかった弱点、関連付けられた脅威、およびソフトウェアがサポートの終了に達したかどうかのようなタグに基づいてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![ソフトウェア インベントリのランディング ページの例。](images/tvm-software-inventory.png)

<span data-ttu-id="f1f36-129">調査するソフトウェアを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="f1f36-130">フライアウト パネルが開き、ページ上の情報がコンパクトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="f1f36-131">調査を深く掘り下げ、[ソフトウェアページを開く] を選択するか、[不正確なレポート] を選択して技術的な不整合にフラグ **を設定します**。</span><span class="sxs-lookup"><span data-stu-id="f1f36-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="f1f36-132">サポートされていないソフトウェア</span><span class="sxs-lookup"><span data-stu-id="f1f36-132">Software that isn't supported</span></span>

<span data-ttu-id="f1f36-133">脅威と脆弱性管理で現在サポート&ソフトウェアは、[ソフトウェア インベントリ] ページに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1f36-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="f1f36-134">サポートされていないので、限られたデータしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="f1f36-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="f1f36-135">[弱さ] セクションの [使用できない] オプションを使用して、サポートされていないソフトウェアでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![サポートされていないソフトウェア フィルター。](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="f1f36-137">以下は、ソフトウェアがサポートされていない状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="f1f36-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="f1f36-138">[弱点] フィールドには [使用できません] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="f1f36-139">[公開されたデバイス] フィールドにダッシュが表示される</span><span class="sxs-lookup"><span data-stu-id="f1f36-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="f1f36-140">サイド パネルとソフトウェア ページに追加された情報テキスト</span><span class="sxs-lookup"><span data-stu-id="f1f36-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="f1f36-141">ソフトウェア ページには、セキュリティに関する推奨事項、検出された脆弱性、またはイベント タイムライン セクションが表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1f36-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="f1f36-142">現在、CPE のない製品は、デバイス レベルのソフトウェア インベントリでのみ、ソフトウェア インベントリ ページに表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1f36-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="f1f36-143">デバイス上のソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="f1f36-143">Software inventory on devices</span></span>

<span data-ttu-id="f1f36-144">Microsoft Defender Security Center ナビゲーション パネルから、[デバイス] リスト **[に移動します](machines-view-overview.md)**。</span><span class="sxs-lookup"><span data-stu-id="f1f36-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="f1f36-145">デバイスページ (Computer1 など) を開くデバイスの名前を選択し、[ソフトウェア インベントリ] タブを選択して、デバイスに存在する既知のすべてのソフトウェアの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="f1f36-146">詳細については、特定のソフトウェア エントリを選択してフライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="f1f36-147">ソフトウェアは、脅威と脆弱性の管理で現在サポートされていない場合でも、デバイス レベルで表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1f36-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="f1f36-148">ただし、使用できるデータは制限付きのみです。</span><span class="sxs-lookup"><span data-stu-id="f1f36-148">However, only limited data will be available.</span></span> <span data-ttu-id="f1f36-149">ソフトウェアがサポートされていないかどうかは、[弱さ] 列に "使用できません" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="f1f36-150">CPE がないソフトウェアは、このデバイス固有のソフトウェア インベントリの下に表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="f1f36-151">ソフトウェアの証拠</span><span class="sxs-lookup"><span data-stu-id="f1f36-151">Software evidence</span></span>

<span data-ttu-id="f1f36-152">レジストリ、ディスク、または両方からデバイス上の特定のソフトウェアが検出された場所の証拠を参照してください。デバイス ソフトウェア インベントリ内の任意のデバイスで検索できます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="f1f36-153">ソフトウェア名を選択して、フライアウトを開き、"Software Evidence" というセクションを探します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![デバイスの一覧から Windows 10 のソフトウェア証拠の例を示し、ソフトウェア証拠レジストリ パスを示します。](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="f1f36-155">ソフトウェア ページ</span><span class="sxs-lookup"><span data-stu-id="f1f36-155">Software pages</span></span>

<span data-ttu-id="f1f36-156">ソフトウェア ページは、次に示すいくつかの方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="f1f36-157">ソフトウェア インベントリ ページ >ソフトウェア名を選択 **>で** [ソフトウェアを開く] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="f1f36-158">[[セキュリティに関する推奨事項>](tvm-security-recommendation.md) 選択] **>で** [ソフトウェアを開く] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="f1f36-159">[[イベント タイムライン](threat-and-vuln-mgt-event-timeline.md) ] ページ > イベントを選択する > フライアウトの [関連コンポーネント] というセクションで、ハイパーリンクされたソフトウェア名 (Visual Studio 2017 など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="f1f36-160">特定のソフトウェアのすべての詳細と次の情報が表示される完全なページ。</span><span class="sxs-lookup"><span data-stu-id="f1f36-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="f1f36-161">ベンダー情報を含むサイド パネル、組織内のソフトウェアの普及率 (インストールされているデバイスの数、パッチが適用されていない公開されたデバイスを含む)、利用可能かどうかと悪用の可否、および露出スコアへの影響。</span><span class="sxs-lookup"><span data-stu-id="f1f36-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="f1f36-162">脆弱性と構成ミスの数と重大度を示すデータの視覚化。</span><span class="sxs-lookup"><span data-stu-id="f1f36-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="f1f36-163">また、公開されているデバイスの数を示すグラフも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="f1f36-164">次のような情報を示すタブ。</span><span class="sxs-lookup"><span data-stu-id="f1f36-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="f1f36-165">特定された弱点と脆弱性に対する対応するセキュリティ推奨事項。</span><span class="sxs-lookup"><span data-stu-id="f1f36-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="f1f36-166">検出された脆弱性の名前付き CVEs。</span><span class="sxs-lookup"><span data-stu-id="f1f36-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="f1f36-167">ソフトウェアがインストールされているデバイス (デバイス名、ドメイン、OS などと共に)。</span><span class="sxs-lookup"><span data-stu-id="f1f36-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="f1f36-168">ソフトウェア のバージョン 一覧 (バージョンがインストールされているデバイスの数、検出された脆弱性の数、インストールされているデバイスの名前を含む)。</span><span class="sxs-lookup"><span data-stu-id="f1f36-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![ソフトウェアの詳細、Visual Studio、公開されているデバイスなど、2017 年のソフトウェアサンプル ページ。](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="f1f36-170">レポートの不正確さ</span><span class="sxs-lookup"><span data-stu-id="f1f36-170">Report inaccuracy</span></span>

<span data-ttu-id="f1f36-171">あいまいな情報、不正確な情報、または不完全な情報が表示された場合は、誤検知を報告します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="f1f36-172">既に修復済みのセキュリティ推奨事項について報告できます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="f1f36-173">[ソフトウェア インベントリ] ページでソフトウェア フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="f1f36-174">[ **不正確なレポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1f36-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="f1f36-175">フライアウト ウィンドウで、ドロップダウン メニューから不正確なカテゴリを選択し、電子メール アドレスを入力し、不正確な情報の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="f1f36-176">[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1f36-176">Select **Submit**.</span></span> <span data-ttu-id="f1f36-177">フィードバックは、脅威と脆弱性管理の専門家に直ちに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f1f36-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f1f36-178">関連記事</span><span class="sxs-lookup"><span data-stu-id="f1f36-178">Related articles</span></span>

- [<span data-ttu-id="f1f36-179">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="f1f36-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1f36-180">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="f1f36-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="f1f36-181">イベントのタイムライン</span><span class="sxs-lookup"><span data-stu-id="f1f36-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="f1f36-182">Microsoft Defender for Endpoint Devices リストの表示と整理</span><span class="sxs-lookup"><span data-stu-id="f1f36-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
