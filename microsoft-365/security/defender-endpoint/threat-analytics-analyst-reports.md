---
title: 脅威分析のアナリスト レポート セクションについて
ms.reviewer: ''
description: 各脅威分析レポートのアナリスト レポート セクションについて説明します。 脅威、軽減策、検出、高度な検索クエリなどの情報を提供する方法を理解します。
keywords: アナリスト レポート、脅威分析、検出、高度な検索クエリ、軽減策、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 38d6d4f3ce1fd6a6ba51b2ac0802892c036f3e50
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068467"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="9f4cf-105">脅威分析のアナリスト レポートを理解する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f4cf-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9f4cf-106">**Applies to:**</span></span>
- [<span data-ttu-id="9f4cf-107">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) </span><span class="sxs-lookup"><span data-stu-id="9f4cf-107">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)
- [<span data-ttu-id="9f4cf-108">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9f4cf-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9f4cf-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f4cf-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9f4cf-110">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9f4cf-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f4cf-111">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="9f4cf-112">各 [脅威分析レポートには、](threat-analytics.md) 動的セクションと、アナリスト レポートと呼ばれる包括的な記述セクション _が含まれます_。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-112">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="9f4cf-113">このセクションにアクセスするには、追跡された脅威に関するレポートを開き、[アナリスト レポート] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-113">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![脅威分析レポートのアナリスト レポート セクションのイメージ](images/ta-analyst-report-small.png)

<span data-ttu-id="9f4cf-115">_脅威分析レポートのアナリスト レポート セクション_</span><span class="sxs-lookup"><span data-stu-id="9f4cf-115">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="9f4cf-116">アナリスト レポートをスキャンする</span><span class="sxs-lookup"><span data-stu-id="9f4cf-116">Scan the analyst report</span></span> 
<span data-ttu-id="9f4cf-117">アナリスト レポートの各セクションは、アクション可能な情報を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-117">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="9f4cf-118">レポートはさまざまですが、ほとんどのレポートには、次の表に示すセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-118">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="9f4cf-119">[レポート] セクション</span><span class="sxs-lookup"><span data-stu-id="9f4cf-119">Report section</span></span> | <span data-ttu-id="9f4cf-120">説明</span><span class="sxs-lookup"><span data-stu-id="9f4cf-120">Description</span></span> |
|--|--|
| <span data-ttu-id="9f4cf-121">エグゼクティブの概要</span><span class="sxs-lookup"><span data-stu-id="9f4cf-121">Executive summary</span></span> | <span data-ttu-id="9f4cf-122">脅威の概要 (最初に見られた場合を含む)、その動機、重要なイベント、主要なターゲット、および個別のツールとテクニック。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-122">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="9f4cf-123">この情報を使用して、業界、地理的位置、ネットワークのコンテキストで脅威に優先順位を付ける方法をさらに評価できます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-123">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="9f4cf-124">分析</span><span class="sxs-lookup"><span data-stu-id="9f4cf-124">Analysis</span></span> | <span data-ttu-id="9f4cf-125">攻撃の詳細、攻撃者が新しい手法または攻撃表面を利用する方法など、脅威に関する技術情報</span><span class="sxs-lookup"><span data-stu-id="9f4cf-125">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="9f4cf-126">MITRE ATT&CK 技術の観察</span><span class="sxs-lookup"><span data-stu-id="9f4cf-126">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="9f4cf-127">CK 攻撃フレームワークの[MITRE ATT](https://attack.mitre.org/)に&方法</span><span class="sxs-lookup"><span data-stu-id="9f4cf-127">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="9f4cf-128">軽減策</span><span class="sxs-lookup"><span data-stu-id="9f4cf-128">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="9f4cf-129">脅威の影響を停止または軽減する可能性がある推奨事項。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-129">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="9f4cf-130">このセクションには、脅威分析レポートの一部として動的に追跡されない軽減策も含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-130">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="9f4cf-131">検出の詳細</span><span class="sxs-lookup"><span data-stu-id="9f4cf-131">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="9f4cf-132">脅威に関連付けられたアクティビティやコンポーネントを表面化できる Microsoft セキュリティ ソリューションによって提供される特定の一般的な検出。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-132">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="9f4cf-133">高度な検出</span><span class="sxs-lookup"><span data-stu-id="9f4cf-133">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="9f4cf-134">[脅威の可能性のあるアクティビティ](advanced-hunting-overview.md) を事前に特定するための高度な検索クエリ。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-134">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="9f4cf-135">ほとんどのクエリは、特に悪意のある可能性のあるコンポーネントや、悪意のあると動的に評価できなかった動作を見つけ出す場合に、検出を補完するために提供されます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-135">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="9f4cf-136">関連情報</span><span class="sxs-lookup"><span data-stu-id="9f4cf-136">References</span></span> | <span data-ttu-id="9f4cf-137">レポートの作成中にアナリストが参照する Microsoft およびサードパーティの文書。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-137">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="9f4cf-138">脅威分析コンテンツは、Microsoft の研究者によって検証されたデータに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-138">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="9f4cf-139">一般に公開されているサードパーティのソースからの情報は、その情報として明確に識別されます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-139">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="9f4cf-140">変更ログ</span><span class="sxs-lookup"><span data-stu-id="9f4cf-140">Change log</span></span> | <span data-ttu-id="9f4cf-141">レポートが発行された時刻と、レポートに大幅な変更が加えた時刻。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-141">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="9f4cf-142">追加の軽減策を適用する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-142">Apply additional mitigations</span></span>
<span data-ttu-id="9f4cf-143">脅威分析は、セキュリティ更新プログラムと [セキュリティで保護された構成の状態を動的に追跡します](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-143">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="9f4cf-144">この情報は、[軽減策] タブのグラフと表 **として使用** できます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-144">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="9f4cf-145">これらの追跡された軽減策に加えて、アナリスト レポートでは、動的に監視されない軽減 _策も説明_ します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-145">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="9f4cf-146">動的に追跡されない重要な軽減策の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-146">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="9f4cf-147">.lnk 添付ファイルまたは _他の疑わしい_ ファイルの種類を含むメールをブロックする</span><span class="sxs-lookup"><span data-stu-id="9f4cf-147">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="9f4cf-148">ローカル管理者パスワードをランダム化する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-148">Randomize local administrator passwords</span></span>
- <span data-ttu-id="9f4cf-149">フィッシングメールや他の脅威ベクトルについてエンド ユーザーに教育する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-149">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="9f4cf-150">特定の攻撃表面 [の縮小ルールを有効にする](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="9f4cf-150">Turn on specific [attack surface reduction rules](attack-surface-reduction.md)</span></span>

<span data-ttu-id="9f4cf-151">[軽減策] タブ **を使用** して脅威に対するセキュリティの態勢を評価することもできますが、これらの推奨事項を使用すると、セキュリティ態勢の改善に向けて追加の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-151">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="9f4cf-152">アナリスト レポートのすべての軽減ガイダンスを注意深く読み、可能な限り適用します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-152">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="9f4cf-153">各脅威の検出方法を理解する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-153">Understand how each threat can be detected</span></span>
<span data-ttu-id="9f4cf-154">アナリスト レポートでは、Microsoft Defender for Endpoint ウイルス対策およびエンドポイント検出および応答 (EDR) 機能からの検出も提供します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-154">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="9f4cf-155">ウイルス対策の検出</span><span class="sxs-lookup"><span data-stu-id="9f4cf-155">Antivirus detections</span></span>
<span data-ttu-id="9f4cf-156">これらの検出は、Microsoft Defender ウイルス対策が有効 [になっているデバイスで](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-156">These detections are available on devices with [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="9f4cf-157">これらの検出が Microsoft Defender for Endpoint にオンボードされているデバイスで発生すると、レポート内のグラフを点灯するアラートもトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-157">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="9f4cf-158">アナリスト レポートには、 **追跡される** 脅威に固有のコンポーネントや動作に加えて、広範囲の脅威を識別できる一般的な検出も一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-158">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="9f4cf-159">これらの一般的な検出は、グラフには反映されません。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-159">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="9f4cf-160">エンドポイント検出と応答 (EDR) アラート</span><span class="sxs-lookup"><span data-stu-id="9f4cf-160">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="9f4cf-161">EDR アラートは、Microsoft Defender for Endpoint にオンボードされている [デバイスに対して発生します](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-161">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](onboard-configure.md).</span></span> <span data-ttu-id="9f4cf-162">これらのアラートは、通常、Microsoft Defender for Endpoint センサーによって収集されるセキュリティ信号と、強力な信号源として機能するウイルス対策、ネットワーク保護、改ざん防止などの他のエンドポイント機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-162">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="9f4cf-163">ウイルス対策の検出の一覧と同様に、一部の EDR アラートは、追跡された脅威に関連付けされない疑わしい動作に一般的にフラグを設定するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-163">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="9f4cf-164">このような場合、レポートはアラートを "汎用" として明確に識別し、レポート内のグラフには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-164">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="9f4cf-165">高度な検索を使用して、微妙な脅威のアーティファクトを検索する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-165">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="9f4cf-166">検出では追跡された脅威を自動的に特定して停止することができますが、多くの攻撃アクティビティでは、追加の検査が必要な微妙な痕跡が残っています。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-166">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="9f4cf-167">攻撃アクティビティの中には、通常の動作を示すものがあります。そのため、動的に検出すると、運用上のノイズや誤検知が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-167">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="9f4cf-168">[高度な検索](advanced-hunting-overview.md) は、Kusto クエリ言語に基づくクエリ インターフェイスを提供し、脅威アクティビティの微妙なインジケーターの検索を簡略化します。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-168">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="9f4cf-169">また、コンテキスト情報を表示し、インジケーターが脅威に接続されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-169">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="9f4cf-170">アナリスト レポートの高度な検索クエリは、Microsoft アナリストによって確認され、高度な検索クエリ エディターで実行 [する準備が整いました](https://securitycenter.windows.com/advanced-hunting)。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-170">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://securitycenter.windows.com/advanced-hunting).</span></span> <span data-ttu-id="9f4cf-171">クエリを使用して、将来の一致に関するアラート [をトリガー](custom-detection-rules.md) するカスタム検出ルールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f4cf-171">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9f4cf-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f4cf-172">Related topics</span></span>
- [<span data-ttu-id="9f4cf-173">脅威の分析の概要</span><span class="sxs-lookup"><span data-stu-id="9f4cf-173">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="9f4cf-174">高度な検索で脅威を事前に検出する</span><span class="sxs-lookup"><span data-stu-id="9f4cf-174">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="9f4cf-175">カスタム検出ルール</span><span class="sxs-lookup"><span data-stu-id="9f4cf-175">Custom detection rules</span></span>](custom-detection-rules.md)