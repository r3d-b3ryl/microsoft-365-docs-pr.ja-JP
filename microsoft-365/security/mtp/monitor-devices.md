---
title: デバイス監視&レポート - セキュリティ センター
description: デバイスをセキュリティで保護し、最新の状態に保ち、組織内の潜在的な脅威を特定する方法について説明します。
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, 監視, レポート, デバイス
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930500"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="de8ac-104">Microsoft 365 セキュリティ センターでのデバイスの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="de8ac-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="de8ac-105">デバイスをセキュリティで保護し、最新の状態に保ち、Microsoft 365 セキュリティ センターで潜在的な脅威を特定します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="de8ac-106">デバイスのアラートを表示する</span><span class="sxs-lookup"><span data-stu-id="de8ac-106">View device alerts</span></span>

<span data-ttu-id="de8ac-107">Microsoft Defender for Endpoint (E5 ライセンスで利用可能) から、デバイス上の侵害アクティビティや他の脅威に関する最新のアラートを取得します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="de8ac-108">Microsoft 365 セキュリティ センターでは、お好みのワークフローを使用して、これらのアラートを高いレベルで効果的に監視します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="de8ac-109">影響の大きなアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="de8ac-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="de8ac-110">各 Microsoft Defender for Endpoint アラートには、対応する重大度 (高、中、低、または情報) があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="de8ac-111">これは、無人のままにしておくとネットワークに影響を与える可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="de8ac-112">デバイスアラート **の重大度カードを使って** 、特に重要度が高く、直ちに応答が必要になる可能性があるアラートに重点を置く。</span><span class="sxs-lookup"><span data-stu-id="de8ac-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="de8ac-113">このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイスアラートの重大度カード](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="de8ac-115">アラートのソースを理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-115">Understand sources of alerts</span></span>

<span data-ttu-id="de8ac-116">Microsoft Defender for Endpoint は、広範なセキュリティ センサーとインテリジェンス ソースからのデータを利用して、アラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="de8ac-117">たとえば、Microsoft Defender ウイルス対策とサード パーティのマルウェア対策からの検出情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="de8ac-118">また、Web サービス API を通じて提供される独自のカスタム脅威インテリジェンスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="de8ac-119">デバイス **アラート検出ソース カード** には、ソース別のアラートの配布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="de8ac-120">特定のソース、特にカスタム ソースに関連するアクティビティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="de8ac-121">また、このカードを使用して、悪意のあるアクティビティやコンポーネントを自動的にブロックするように構成されていないセンサーからのアラートに焦点を当てすることもできます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![デバイスアラート検出ソース カード](../../media/device-alert-detection-sources.png)

<span data-ttu-id="de8ac-123">このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="de8ac-124">アラートをトリガーする脅威の種類を理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="de8ac-125">Microsoft Defender for Endpoint は、各アラートを、攻撃チェーンまたは脅威コンポーネントの種類の特定のステージを表すカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="de8ac-126">たとえば、検出された脅威アクティビティは、ネットワーク上の他のデバイスに到達しようとしたかどうかを示すために、"横方向の動き" として分類できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="de8ac-127">このアクティビティは、攻撃者が最初の足がかりを獲得した後に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="de8ac-128">検出された脅威コンポーネントは、広範にマルウェアとして分類される場合や、具体的には特定の脅威の種類として分類される場合があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="de8ac-129">具体的には、ランサムウェア、資格情報の盗用、その他の種類の悪意のあるソフトウェアや不要なソフトウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="de8ac-130">デバイス **の脅威カテゴリ カード** には、これらのカテゴリへのアラートの分布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="de8ac-131">この情報を使用して、資格情報の盗難の試みなど、通常はソーシャル エンジニアリングの試みよりも大きな影響を与える脅威アクティビティを特定します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="de8ac-132">ランサムウェアなどの潜在的な破壊的な脅威を監視できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![デバイスの脅威カテゴリ カード](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="de8ac-134">アクティブなアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="de8ac-134">Monitor active alerts</span></span>

<span data-ttu-id="de8ac-135">デバイス **アラートステータス カード** は、解決されていないアラートの数を示し、注意が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="de8ac-136">このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイスアラートの状態カード](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="de8ac-138">解決済みアラートの分類を監視する</span><span class="sxs-lookup"><span data-stu-id="de8ac-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="de8ac-139">Microsoft Defender for Endpoint の警告を解決する際、セキュリティ スタッフはアラートが次のように検証されているかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="de8ac-140">実際の侵害アクティビティまたは脅威コンポーネントを識別する真のアラート</span><span class="sxs-lookup"><span data-stu-id="de8ac-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="de8ac-141">通常のアクティビティを誤って検出した誤ったアラート</span><span class="sxs-lookup"><span data-stu-id="de8ac-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="de8ac-142">デバイス **アラート分類カードには** 、解決済みアラートが true アラートと False アラートの分類の 2 つが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="de8ac-143">このカードから、Microsoft Defender セキュリティ センター ポータルで詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="de8ac-144">注: 場合によっては、特定のアラートで分類情報を使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![デバイスアラート分類カード](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="de8ac-146">解決済みアラートの判断を監視する</span><span class="sxs-lookup"><span data-stu-id="de8ac-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="de8ac-147">解決時にアラートが正しいか偽かを分類すると共に、セキュリティ スタッフが判断を下す場合があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="de8ac-148">判定は、アラートの検証中に検出された通常または悪意のあるアクティビティの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="de8ac-149">デバイス **アラート判定カードには** 、各アラートに対して提供された判定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="de8ac-150">**APT**: 検出されたアクティビティまたは脅威コンポーネントが、影響を受けるネットワークの足がかりを得るために設計された高度な侵害の一部であることを示す、持続的な脅威</span><span class="sxs-lookup"><span data-stu-id="de8ac-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="de8ac-151">**マルウェア**: 悪意のあるファイルまたはコード</span><span class="sxs-lookup"><span data-stu-id="de8ac-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="de8ac-152">**セキュリティ担当者**: セキュリティ スタッフが実行する通常のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="de8ac-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="de8ac-153">**セキュリティ テスト**: 実際の脅威をシミュレートし、セキュリティ センサーをトリガーしてアラートを生成すると予想されるアクティビティまたはコンポーネント</span><span class="sxs-lookup"><span data-stu-id="de8ac-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="de8ac-154">**望ましくないソフトウェア**: 悪意のあると見なされないアプリや他のソフトウェア。ポリシーや許容される使用基準に違反する</span><span class="sxs-lookup"><span data-stu-id="de8ac-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="de8ac-155">**その** 他 : 指定された種類に該当しないその他の判断</span><span class="sxs-lookup"><span data-stu-id="de8ac-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="de8ac-156">このカードから、Microsoft Defender セキュリティ センターで詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![デバイスアラート判定カード](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="de8ac-158">どのデバイスが危険にさらされているのかについて理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-158">Understand which devices are at risk</span></span>

<span data-ttu-id="de8ac-159">**デバイス保護は** 、デバイスのリスク レベルを示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="de8ac-160">リスク レベルは、デバイス上のアラートの種類や重要度などの要因に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![デバイス保護カード](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="de8ac-162">Intune で管理されているデバイスの状態を監視およびレポートする</span><span class="sxs-lookup"><span data-stu-id="de8ac-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="de8ac-163">次のレポートには、Intune に登録されているデバイスからのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="de8ac-164">登録解除されたデバイスからのデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="de8ac-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="de8ac-165">これらのカードを表示できるのはグローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="de8ac-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="de8ac-166">Intune に登録されているデバイス データには、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="de8ac-167">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="de8ac-167">Device compliance</span></span>
* <span data-ttu-id="de8ac-168">アクティブなマルウェアを持つデバイス</span><span class="sxs-lookup"><span data-stu-id="de8ac-168">Devices with active malware</span></span>
* <span data-ttu-id="de8ac-169">デバイス上のマルウェアの種類</span><span class="sxs-lookup"><span data-stu-id="de8ac-169">Types of malware on devices</span></span>
* <span data-ttu-id="de8ac-170">デバイス上のマルウェア</span><span class="sxs-lookup"><span data-stu-id="de8ac-170">Malware on devices</span></span>
* <span data-ttu-id="de8ac-171">マルウェアが検出されたデバイス</span><span class="sxs-lookup"><span data-stu-id="de8ac-171">Devices with malware detections</span></span>
* <span data-ttu-id="de8ac-172">マルウェアが検出されたユーザー</span><span class="sxs-lookup"><span data-stu-id="de8ac-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="de8ac-173">デバイスのコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="de8ac-173">Monitor device compliance</span></span>

<span data-ttu-id="de8ac-174">**デバイス コンプライアンスは** 、Intune に登録されているデバイスが構成ポリシーに準拠しているデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![デバイス コンプライアンス カード](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="de8ac-176">マルウェアが検出されたデバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="de8ac-176">Discover devices with malware detections</span></span>

<span data-ttu-id="de8ac-177">**デバイスのマルウェア検出** では、完全に解決されていないマルウェアが Intune に登録されたデバイスの数を提供します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="de8ac-178">解決策がないのは、保留中のアクション、再起動、フル スキャン、手動ユーザー操作、または修復アクションが正常に完了しなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="de8ac-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![デバイス マルウェア検出カード](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="de8ac-180">検出されたマルウェアの種類を理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-180">Understand the types of malware detected</span></span>

<span data-ttu-id="de8ac-181">**デバイス上のマルウェアの種類には** 、Intune に登録されているデバイスで検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="de8ac-182">Microsoft 365 セキュリティ センターでは、それぞれの種類を調査できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![デバイス カードのマルウェアの種類](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="de8ac-184">デバイスで検出された特定のマルウェアについて理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="de8ac-185">**デバイス上のマルウェア** は、デバイスで検出された特定のマルウェアの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![デバイス カード上のマルウェア](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="de8ac-187">マルウェアが最も多いデバイスを理解する</span><span class="sxs-lookup"><span data-stu-id="de8ac-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="de8ac-188">**マルウェアが検出されたデバイスは、** 最もマルウェアが検出されたデバイスを示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="de8ac-189">Microsoft 365 セキュリティ センターでは、マルウェアがアクティブかどうか、デバイスを使用するユーザー、Intune での管理状態を調査できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![マルウェア検出カードを含むデバイス](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="de8ac-191">マルウェアが最も多いデバイスを持つユーザーを把握する</span><span class="sxs-lookup"><span data-stu-id="de8ac-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="de8ac-192">**マルウェアが検出されたユーザーは** 、最もマルウェアが検出されたデバイスを持つユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="de8ac-193">Microsoft 365 セキュリティ センターでは、各ユーザーに割り当てられているデバイスの数と、各デバイスとマルウェアの種類に関する詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![マルウェア検出カードを持つユーザー](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="de8ac-195">攻撃表面の縮小ルールの展開と検出を監視および管理する</span><span class="sxs-lookup"><span data-stu-id="de8ac-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="de8ac-196">[攻撃表面の縮小 (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ルールは、悪用を求めるマルウェアがデバイスに感染するために通常使用するアクションやアプリを防止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="de8ac-197">このようなルールによって、実行可能ファイルの実行を許可するタイミングと方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="de8ac-198">たとえば、JavaScript や VBScript がダウンロードした実行可能ファイルを開始することを禁止したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行するプロセスをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻撃表面の縮小カード](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="de8ac-200">**[攻撃面の減少ルール]** カードには、デバイス全体に配置するルールの概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="de8ac-201">カードの上部バーには、次の配置モードになっているデバイスの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="de8ac-202">**ブロック モード**: 検出されたアクティビティをブロックするように少なくとも 1 つのルールが構成されているデバイス</span><span class="sxs-lookup"><span data-stu-id="de8ac-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="de8ac-203">**監査モード**: 検出されたアクティビティをブロックするルールが設定されているのに、検出されたアクティビティを監査するルールが少なくとも 1 つ設定されているデバイス</span><span class="sxs-lookup"><span data-stu-id="de8ac-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="de8ac-204">**オフ**: すべての ASR ルールがオフになっているデバイス</span><span class="sxs-lookup"><span data-stu-id="de8ac-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="de8ac-205">このカードの下側には、デバイス全体のルール別の設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="de8ac-206">各バーは、ブロック、監査検出、またはルールが完全にオフに設定されているデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="de8ac-207">ASR 検出の表示</span><span class="sxs-lookup"><span data-stu-id="de8ac-207">View ASR detections</span></span>

<span data-ttu-id="de8ac-208">ネットワーク内の ASR ルールの検出に関する詳細情報を表示するには、攻撃表面の縮小ルール カードで [検出の表示 **] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="de8ac-209">詳細 **レポート ページ** の [検出] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-209">The **Detections** tab in the detailed report page will open.</span></span>

![[検出] タブ](../../media/detections-tab.png)

<span data-ttu-id="de8ac-211">ページの上部にあるグラフには、ブロックまたは監査された検出を、時間のときどき積み重ねたった検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="de8ac-212">下部の表は、最近の検出のリストです。</span><span class="sxs-lookup"><span data-stu-id="de8ac-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="de8ac-213">表に示された次の情報を使用して、検出の種類を理解します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="de8ac-214">**検出されたファイル**: 攻撃の疑いのあるアクティビティをトリガーした内容のファイル (通常はスクリプトまたはドキュメント)</span><span class="sxs-lookup"><span data-stu-id="de8ac-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="de8ac-215">**Rule**: ルールがキャッチするように設計されている攻撃アクティビティを説明する名前。</span><span class="sxs-lookup"><span data-stu-id="de8ac-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="de8ac-216">既存の ASR ルールの読み取り</span><span class="sxs-lookup"><span data-stu-id="de8ac-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="de8ac-217">**ソース アプリ**: 攻撃の疑いのあるアクティビティをトリガーするコンテンツを読み込んだ、または実行したアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="de8ac-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="de8ac-218">Web ブラウザー、Office アプリケーション、PowerShell などのシステム ツールなど、正当なアプリケーションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de8ac-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="de8ac-219">**発行** 元: ソース アプリをリリースしたベンダー</span><span class="sxs-lookup"><span data-stu-id="de8ac-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="de8ac-220">デバイス ASR ルールの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="de8ac-220">Review device ASR rule settings</span></span>

<span data-ttu-id="de8ac-221">[攻撃表面 **の縮小ルール]** レポート ページで、[構成] タブに移動して、個々のデバイスのルール設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="de8ac-222">デバイスを選択すると、各ルールがブロック モード、監査モード、または完全にオフになっているかどうかに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![[構成] タブ](../../media/configuration-tab.png)

<span data-ttu-id="de8ac-224">Microsoft Intune は、ASR ルールの管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="de8ac-225">設定を更新する場合は、タブの[デバイスの構成] の [開始] を選択して、Intune でデバイス管理を開きます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="de8ac-226">ASR ルールからファイルを除外する</span><span class="sxs-lookup"><span data-stu-id="de8ac-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="de8ac-227">Microsoft 365 セキュリティ センターは、攻撃[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)表面の縮小ルールによって、検出から除外する可能性があるファイルの名前を収集します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="de8ac-228">ファイルを除外することで、誤検知の検出を減らし、攻撃表面の縮小ルールをブロック モードでより自信を持って展開できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="de8ac-229">除外は Microsoft Intune で管理されますが、Microsoft 365 セキュリティ センターには、ファイルを理解するのに役立つ分析ツールが提供されています。</span><span class="sxs-lookup"><span data-stu-id="de8ac-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="de8ac-230">除外するファイルの収集を開始するには、[攻撃表面の縮小ルール] レポート ページの [除外の追加 **] タブに** 移動します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="de8ac-231">このツールは、すべての攻撃表面の縮小ルールによる検出を分析しますが、除外 [をサポートするルールは一部のみです](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)。</span><span class="sxs-lookup"><span data-stu-id="de8ac-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![[除外の追加] タブ](../../media/add-exclusions-tab.png)

<span data-ttu-id="de8ac-233">次の表に、攻撃表面の縮小ルールによって検出されたファイル名の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="de8ac-234">ファイルを選択すると、除外の影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="de8ac-235">検出数の少ない数</span><span class="sxs-lookup"><span data-stu-id="de8ac-235">How many fewer detections</span></span>
* <span data-ttu-id="de8ac-236">検出を報告するデバイスの数</span><span class="sxs-lookup"><span data-stu-id="de8ac-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="de8ac-237">除外する完全なパスを持つ、選択したファイルの一覧を取得するには、[除外パスの取得 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="de8ac-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="de8ac-238">ASR ルールのログ。Windows ローカル セキュリティ機関サブシステム **(lsass.exe)** からの資格情報の盗用をブロックし、ソース アプリを取得 **lsass.exe。**</span><span class="sxs-lookup"><span data-stu-id="de8ac-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="de8ac-239">通常のシステム ファイルですが、検出されたファイルとしてキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="de8ac-240">その結果、生成された除外パスの一覧にこのファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="de8ac-241">lsass.exeではなく、このルールをトリガーしたファイルを除外するには、検出されたファイルの代わりにソース アプリのパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="de8ac-242">ソース アプリを見つけるには、この[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)特定のルールに対して次の高度な検索クエリを実行します (ルール ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 によって識別されます)。</span><span class="sxs-lookup"><span data-stu-id="de8ac-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="de8ac-243">除外するファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="de8ac-243">Check files for exclusion</span></span>

<span data-ttu-id="de8ac-244">ASR からファイルを除外する前に、ファイルを検査して、実際に悪意のあるファイルではないかどうかを判断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de8ac-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="de8ac-245">ファイルを確認するには、Microsoft Defender セキュリティ センター [の](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) ファイル情報ページを使います。</span><span class="sxs-lookup"><span data-stu-id="de8ac-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="de8ac-246">このページには、確認率情報と VirusTotal ウイルス検出率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="de8ac-247">ページを使用して、詳細分析のためにファイルを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="de8ac-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="de8ac-248">Microsoft Defender セキュリティ センターで検出されたファイルを見つけるには、次の高度な捜索クエリを使用してすべての ASR 検出を検索します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="de8ac-249">結果で **SHA1** または **InitiatingProcessSHA1** を使用して、Microsoft Defender セキュリティ センターのユニバーサル検索バーを使用してファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="de8ac-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
