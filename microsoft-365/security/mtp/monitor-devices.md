---
title: デバイス監視 & レポート作成-セキュリティセンター
description: 組織において、デバイスのセキュリティを確保し、最新の状態を維持し、潜在的な脅威を特定する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、デバイス
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8abb4960318bb12b0205d014c32e48a60d4b9ae5
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866815"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="19079-104">Microsoft 365 セキュリティセンターでのデバイスの監視とレポート</span><span class="sxs-lookup"><span data-stu-id="19079-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="19079-105">モバイルデバイスのセキュリティを確保し、最新の状態に保つことができます。また、潜在的な脅威については、Microsoft 365 セキュリティセンターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="19079-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="19079-106">デバイスの通知を表示する</span><span class="sxs-lookup"><span data-stu-id="19079-106">View device alerts</span></span>

<span data-ttu-id="19079-107">Microsoft Defender ATP (E5 ライセンス付き) から、デバイスに対する違反アクティビティやその他の脅威に関する最新の通知を入手できます。</span><span class="sxs-lookup"><span data-stu-id="19079-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="19079-108">Microsoft 365 セキュリティセンターは、優先ワークフローを使用して、これらのアラートを高レベルで効果的に監視します。</span><span class="sxs-lookup"><span data-stu-id="19079-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="19079-109">影響度の高いアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="19079-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="19079-110">Microsoft Defender ATP の各アラートには、対応する重要度 (高、中、低、または情報) があります。</span><span class="sxs-lookup"><span data-stu-id="19079-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="19079-111">これは、無人のままでネットワークに影響を与える可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="19079-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="19079-112">**デバイスアラートの重要度**カードを使用して、より深刻で、即時応答を必要とする可能性があるアラートに特に注目します。</span><span class="sxs-lookup"><span data-stu-id="19079-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="19079-113">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19079-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイス通知の重要度カード](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="19079-115">通知のソースを理解する</span><span class="sxs-lookup"><span data-stu-id="19079-115">Understand sources of alerts</span></span>

<span data-ttu-id="19079-116">Microsoft Defender ATP は、さまざまなセキュリティセンサーおよびインテリジェンスソースからのデータを利用して、アラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="19079-116">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="19079-117">たとえば、Microsoft Defender ウイルス対策およびサードパーティのマルウェア対策の検出情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="19079-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="19079-118">Web サービス API を介して提供される独自のカスタム脅威インテリジェンスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="19079-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="19079-119">**デバイスアラート検出**ソースカードは、通知のソース別の配布を示しています。</span><span class="sxs-lookup"><span data-stu-id="19079-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="19079-120">特定のソース (特にカスタムソース) に関連するアクティビティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="19079-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="19079-121">また、カードを使用して、悪意のあるアクティビティやコンポーネントを自動的にブロックするように構成されていないセンサーからのアラートに焦点を当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="19079-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![デバイスアラート検出ソースカード](../../media/device-alert-detection-sources.png)

<span data-ttu-id="19079-123">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19079-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="19079-124">アラートを発生させる脅威の種類を理解する</span><span class="sxs-lookup"><span data-stu-id="19079-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="19079-125">Microsoft Defender ATP は、各アラートを、アタックチェーンまたは脅威コンポーネントの特定の段階を表すカテゴリに分類します。</span><span class="sxs-lookup"><span data-stu-id="19079-125">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="19079-126">たとえば、検出された脅威アクティビティは、ネットワーク上の他のデバイスに到達しようとしたことを示すために、"横方向の移動" として分類されることがあります。</span><span class="sxs-lookup"><span data-stu-id="19079-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="19079-127">このアクティビティは、攻撃者が初期 foothold を獲得した後に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19079-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="19079-128">検出された場合、脅威コンポーネントはマルウェアとして、または特に特定の脅威の種類として分類されることがあります。</span><span class="sxs-lookup"><span data-stu-id="19079-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="19079-129">具体的には、ランサムウェア、資格情報の盗用、悪意のあるまたは望ましくないソフトウェアの種類があります。</span><span class="sxs-lookup"><span data-stu-id="19079-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="19079-130">**デバイスの脅威カテゴリ**カードには、これらのカテゴリへのアラートの配布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="19079-131">この情報を使用して、通常はソーシャルエンジニアリングの試みよりも影響が大きい、資格情報の盗用の試行などの脅威のアクティビティを特定します。</span><span class="sxs-lookup"><span data-stu-id="19079-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="19079-132">また、ランサムウェアなどの潜在的な破壊的脅威を監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="19079-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![デバイスの脅威カテゴリカード](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="19079-134">アクティブなアラートを監視する</span><span class="sxs-lookup"><span data-stu-id="19079-134">Monitor active alerts</span></span>

<span data-ttu-id="19079-135">**デバイス通知ステータス**カードは、解決されていないアラートの数を示し、注意が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="19079-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="19079-136">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19079-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![デバイスアラートステータスカード](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="19079-138">解決されたアラートの分類を監視する</span><span class="sxs-lookup"><span data-stu-id="19079-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="19079-139">Microsoft Defender ATP 通知を解決するとき、セキュリティ担当者は通知を次のように確認するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="19079-139">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="19079-140">実際の違反アクティビティまたは脅威コンポーネントを識別する真の通知</span><span class="sxs-lookup"><span data-stu-id="19079-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="19079-141">通常のアクティビティを誤って検出した false アラート</span><span class="sxs-lookup"><span data-stu-id="19079-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="19079-142">**デバイス通知分類**カードは、解決済みのアラートが true または誤通知として分類されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="19079-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="19079-143">このカードから、Microsoft Defender セキュリティセンターポータルの詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19079-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="19079-144">注: 状況によっては、特定の通知に対して分類情報を使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="19079-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![デバイスアラート分類カード](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="19079-146">解決されたアラートの決定を監視する</span><span class="sxs-lookup"><span data-stu-id="19079-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="19079-147">解決時にアラートが true であるか false であるかの分類に加えて、セキュリティ担当者は決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19079-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="19079-148">決定は、通知の検証中に検出された通常または悪意のあるアクティビティの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="19079-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="19079-149">**デバイス通知判別**カードは、各通知に対して指定された決定を示します。</span><span class="sxs-lookup"><span data-stu-id="19079-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="19079-150">**APT**: 高度な永続的な脅威。検出されたアクティビティまたは脅威のコンポーネントが、影響を受けるネットワークで foothold を取得するように設計された高度な違反の一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="19079-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="19079-151">**マルウェア**: 悪意のあるファイルまたはコード</span><span class="sxs-lookup"><span data-stu-id="19079-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="19079-152">**セキュリティ担当者**: セキュリティスタッフによって実行される通常のアクティビティ</span><span class="sxs-lookup"><span data-stu-id="19079-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="19079-153">**セキュリティテスト**: 実際の脅威をシミュレートし、セキュリティセンサーをトリガーして通知を生成するように設計されたアクティビティまたはコンポーネント</span><span class="sxs-lookup"><span data-stu-id="19079-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="19079-154">**不要なソフトウェア**: 悪意のあるアプリやその他のソフトウェア。それ以外の場合は、ポリシーや使用規約に違反します。</span><span class="sxs-lookup"><span data-stu-id="19079-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="19079-155">**その他: 指定**された型に該当しないその他の決定</span><span class="sxs-lookup"><span data-stu-id="19079-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="19079-156">このカードから、Microsoft Defender セキュリティセンターの詳細情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="19079-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![デバイスのアラート判別カード](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="19079-158">危険にさらされているデバイスを理解する</span><span class="sxs-lookup"><span data-stu-id="19079-158">Understand which devices are at risk</span></span>

<span data-ttu-id="19079-159">**デバイス保護** は、デバイスのリスクレベルを示しています。</span><span class="sxs-lookup"><span data-stu-id="19079-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="19079-160">リスクレベルは、デバイス上のアラートの種類や重要度などの要因に基づいています。</span><span class="sxs-lookup"><span data-stu-id="19079-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![デバイス保護カード](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="19079-162">Intune で管理されているデバイスの状態を監視および報告する</span><span class="sxs-lookup"><span data-stu-id="19079-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="19079-163">次のレポートには、Intune に登録されたデバイスからのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="19079-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="19079-164">未登録のデバイスからのデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="19079-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="19079-165">これらのカードを表示できるのは、全体管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="19079-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="19079-166">Intune 登録デバイスデータには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19079-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="19079-167">デバイスのポリシー準拠</span><span class="sxs-lookup"><span data-stu-id="19079-167">Device compliance</span></span>
* <span data-ttu-id="19079-168">アクティブなマルウェアがあるデバイス</span><span class="sxs-lookup"><span data-stu-id="19079-168">Devices with active malware</span></span>
* <span data-ttu-id="19079-169">デバイス上のマルウェアの種類</span><span class="sxs-lookup"><span data-stu-id="19079-169">Types of malware on devices</span></span>
* <span data-ttu-id="19079-170">デバイスのマルウェア</span><span class="sxs-lookup"><span data-stu-id="19079-170">Malware on devices</span></span>
* <span data-ttu-id="19079-171">マルウェアが検出されるデバイス</span><span class="sxs-lookup"><span data-stu-id="19079-171">Devices with malware detections</span></span>
* <span data-ttu-id="19079-172">マルウェアが検出されるユーザー</span><span class="sxs-lookup"><span data-stu-id="19079-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="19079-173">デバイスコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="19079-173">Monitor device compliance</span></span>

<span data-ttu-id="19079-174">**デバイスのコンプライアンス** Intune に登録されているデバイスの数が、構成ポリシーに準拠していることを示します。</span><span class="sxs-lookup"><span data-stu-id="19079-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![デバイスコンプライアンスカード](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="19079-176">マルウェアが検出されるデバイスを検出する</span><span class="sxs-lookup"><span data-stu-id="19079-176">Discover devices with malware detections</span></span>

<span data-ttu-id="19079-177">**デバイスマルウェアの検出** では、マルウェアが完全に解決されていない Intune 登録デバイスの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="19079-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="19079-178">解決策の欠如は、保留中のアクション、再起動、完全なスキャン、手動によるユーザー操作、または修復アクションが正常に完了しなかったことが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19079-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![デバイスマルウェア検出カード](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="19079-180">検出されたマルウェアの種類を理解する</span><span class="sxs-lookup"><span data-stu-id="19079-180">Understand the types of malware detected</span></span>

<span data-ttu-id="19079-181">**デバイス上のマルウェアの種類** は、Intune に登録されているデバイスで検出されたさまざまな種類のマルウェアを示しています。</span><span class="sxs-lookup"><span data-stu-id="19079-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="19079-182">Microsoft 365 セキュリティセンターでは、それぞれの種類を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="19079-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![デバイスカードのマルウェアの種類](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="19079-184">デバイスで検出された特定のマルウェアについて理解する</span><span class="sxs-lookup"><span data-stu-id="19079-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="19079-185">**デバイス上のマルウェア** は、デバイスで検出された特定のマルウェアの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="19079-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![デバイスカードのマルウェア](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="19079-187">最もマルウェアがあるデバイスを理解する</span><span class="sxs-lookup"><span data-stu-id="19079-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="19079-188">**マルウェアが検出** されたデバイスには、マルウェアが検出されたデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="19079-189">Microsoft 365 セキュリティセンターでは、マルウェアがアクティブであるかどうか、デバイスを使用しているかどうか、および Intune での管理状態を調査できます。</span><span class="sxs-lookup"><span data-stu-id="19079-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![マルウェア検出カードがあるデバイス](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="19079-191">最も多くのマルウェアがあるデバイスをどのユーザーが所有しているかを理解する</span><span class="sxs-lookup"><span data-stu-id="19079-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="19079-192">**マルウェアが検出** されたユーザーには、マルウェアが検出されたデバイスを持つユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="19079-193">Microsoft 365 セキュリティセンターでは、各ユーザーに割り当てられているデバイスの数と、各デバイスおよびマルウェアの種類に関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="19079-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![マルウェア検出カードを使用するユーザー](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="19079-195">攻撃対象領域の削減ルールの展開と検出を監視および管理する</span><span class="sxs-lookup"><span data-stu-id="19079-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="19079-196">[Attack Surface Reduction (ASR) ルール](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) は、マルウェアに感染した場合によく使用される操作やアプリを阻止するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="19079-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="19079-197">このようなルールによって、実行可能ファイルの実行を許可するタイミングと方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="19079-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="19079-198">たとえば、JavaScript や VBScript がダウンロードした実行可能ファイルを開始することを禁止したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行するプロセスをブロックしたりできます。</span><span class="sxs-lookup"><span data-stu-id="19079-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![アタック表面減少カード](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="19079-200">**[攻撃面の減少ルール]** カードには、デバイス全体に配置するルールの概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="19079-201">カードの上部バーには、次の配置モードになっているデバイスの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="19079-202">**ブロックモード**: 検出されたアクティビティをブロックするように、少なくとも1つのルールを持つデバイス</span><span class="sxs-lookup"><span data-stu-id="19079-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="19079-203">**監査モード**: 検出されたアクティビティをブロックするようにルールが設定されていないデバイスが、検出されたアクティビティを監査するために少なくとも1つのルールセットを持つ</span><span class="sxs-lookup"><span data-stu-id="19079-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="19079-204">**Off**: すべての ASR ルールがオフになっているデバイス</span><span class="sxs-lookup"><span data-stu-id="19079-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="19079-205">このカードの下側には、デバイス全体のルール別の設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="19079-206">各棒は、ブロック、監査検出、またはルールを完全にオフにするように設定されているデバイスの数を示します。</span><span class="sxs-lookup"><span data-stu-id="19079-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="19079-207">ASR 検出を表示する</span><span class="sxs-lookup"><span data-stu-id="19079-207">View ASR detections</span></span>

<span data-ttu-id="19079-208">ネットワーク内の ASR ルールの検出に関する詳細情報を表示するには、[ **Attack surface reduction ルール**カード] の [**検出の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19079-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="19079-209">[詳細レポート] ページの [ **検出** ] タブが開きます。</span><span class="sxs-lookup"><span data-stu-id="19079-209">The **Detections** tab in the detailed report page will open.</span></span>

![[検出] タブ](../../media/detections-tab.png)

<span data-ttu-id="19079-211">ページ上部のグラフには、ブロックまたは監査された時間帯の検出の検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="19079-212">下部の表は、最近の検出のリストです。</span><span class="sxs-lookup"><span data-stu-id="19079-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="19079-213">表に示された次の情報を使用して、検出の種類を理解します。</span><span class="sxs-lookup"><span data-stu-id="19079-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="19079-214">**検出さ**れたファイル: 通常はスクリプトまたはドキュメントで、そのコンテンツによって発生した可能性のある攻撃アクティビティがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="19079-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="19079-215">**ルール**: ルールが検出するように設計されたアタックアクティビティを記述する名前。</span><span class="sxs-lookup"><span data-stu-id="19079-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="19079-216">既存の ASR ルールについての情報を読む</span><span class="sxs-lookup"><span data-stu-id="19079-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="19079-217">**ソースアプリ**: 攻撃の疑いのある活動をトリガーするコンテンツを読み込んだ、または実行したアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="19079-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="19079-218">Web ブラウザー、Office アプリケーション、PowerShell のようなシステムツールなどの正当なアプリケーションである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19079-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="19079-219">**Publisher**: ソースアプリをリリースしたベンダー</span><span class="sxs-lookup"><span data-stu-id="19079-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="19079-220">デバイス ASR ルールの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="19079-220">Review device ASR rule settings</span></span>

<span data-ttu-id="19079-221">[ **Attack surface reduction ルール** レポート] ページで、[ **構成** ] タブに移動して個々のデバイスのルールの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="19079-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="19079-222">デバイスを選択して、各ルールがブロックモード、監査モード、または完全にオフになっているかどうかに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="19079-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![[構成] タブ](../../media/configuration-tab.png)

<span data-ttu-id="19079-224">Microsoft Intune は、ASR ルールの管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="19079-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="19079-225">設定を更新する場合は、タブの [デバイスの**構成**] の [**開始**] を選択して、Intune でデバイス管理を開きます。</span><span class="sxs-lookup"><span data-stu-id="19079-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="19079-226">ASR ルールからファイルを除外する</span><span class="sxs-lookup"><span data-stu-id="19079-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="19079-227">Microsoft 365 セキュリティセンターでは、攻撃対象から [除外する可能性のあるファイル](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) の名前を検出します。</span><span class="sxs-lookup"><span data-stu-id="19079-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="19079-228">ファイルを除外することで、誤検知を減らすことができます。ブロックモードでは、攻撃対象領域の削減ルールをより確実に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="19079-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="19079-229">除外は Microsoft Intune で管理されますが、Microsoft 365 セキュリティセンターには、ファイルを理解するのに役立つ分析ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="19079-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="19079-230">除外するファイルの収集を開始するには、[ **Attack surface reduction ルール**レポート] ページの [**除外の追加**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="19079-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="19079-231">このツールでは、すべての攻撃対象領域の削減ルールによって検出が分析されますが、 [一部のルールのみが除外をサポート](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)します。</span><span class="sxs-lookup"><span data-stu-id="19079-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![[除外の追加] タブ](../../media/add-exclusions-tab.png)

<span data-ttu-id="19079-233">攻撃対象領域の削減ルールによって検出されたすべてのファイル名の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="19079-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="19079-234">ファイルを選択して、それらを除外した場合の影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="19079-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="19079-235">検出回数を減らす</span><span class="sxs-lookup"><span data-stu-id="19079-235">How many fewer detections</span></span>
* <span data-ttu-id="19079-236">検出を報告するデバイス数の削減</span><span class="sxs-lookup"><span data-stu-id="19079-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="19079-237">選択したファイルの完全パスを除外するには、[除外する **パスを取得**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19079-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="19079-238">**Windows ローカルセキュリティ機関サブシステムからの資格情報の保護に関するログ (lsass.exe)** ソースアプリ**lsass.exe**をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="19079-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="19079-239">これは通常のシステムファイルですが、検出されたファイルとして取得されます。</span><span class="sxs-lookup"><span data-stu-id="19079-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="19079-240">そのため、生成された除外パスの一覧には、このファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="19079-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="19079-241">**lsass.exe**ではなく、このルールをトリガーしたファイルを除外するには、検出されたファイルの代わりにソースアプリへのパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="19079-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="19079-242">ソースアプリを見つけるには、この特定のルールに対して次の [高度な検索クエリ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) を実行します (ルール ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 によって識別されます)。</span><span class="sxs-lookup"><span data-stu-id="19079-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="19079-243">ファイルの除外を確認する</span><span class="sxs-lookup"><span data-stu-id="19079-243">Check files for exclusion</span></span>

<span data-ttu-id="19079-244">ASR からファイルを除外する前に、ファイルを検査して、本当に悪意がないかどうかを判断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19079-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="19079-245">ファイルを確認するには、Microsoft Defender セキュリティセンターの [ [ファイル情報] ページ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) を使用します。</span><span class="sxs-lookup"><span data-stu-id="19079-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="19079-246">このページには、流行情報と、VirusTotal のウイルス検出率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19079-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="19079-247">ページを使用して、詳細な分析のためにファイルを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="19079-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="19079-248">Microsoft Defender セキュリティセンターで検出されたファイルを特定するには、次の高度な検索クエリを使用して、すべての ASR 検出を検索します。</span><span class="sxs-lookup"><span data-stu-id="19079-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="19079-249">結果で **SHA1** または **InitiatingProcessSHA1** を使用して、Microsoft Defender セキュリティセンターのユニバーサル検索バーを使用してファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="19079-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
