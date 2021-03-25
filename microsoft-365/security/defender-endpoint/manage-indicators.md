---
title: インジケーターの作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを作成します。
keywords: 管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a04f3be1f13fb57cd76cda7115d014f2ba3aa8d6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198827"
---
# <a name="create-indicators"></a><span data-ttu-id="5a33e-104">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="5a33e-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5a33e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5a33e-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a33e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5a33e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a33e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a33e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="5a33e-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5a33e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5a33e-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="5a33e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="5a33e-110">侵害の指標 (IoC) 照合は、すべてのエンドポイント保護ソリューションに不可欠な機能です。</span><span class="sxs-lookup"><span data-stu-id="5a33e-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="5a33e-111">この機能により、SecOps は検出およびブロック (予防と応答) のインジケーターの一覧を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="5a33e-112">エンティティの検出、防止、除外を定義するインジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a33e-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="5a33e-113">実行するアクションと、アクションを適用する期間、およびアクションを適用するデバイス グループの範囲を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="5a33e-114">現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、およびエンドポイント防止エンジン (Microsoft Defender Antivirus) です。</span><span class="sxs-lookup"><span data-stu-id="5a33e-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="5a33e-115">**クラウド検出エンジン**</span><span class="sxs-lookup"><span data-stu-id="5a33e-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="5a33e-116">Defender for Endpoint のクラウド検出エンジンは、収集されたデータを定期的にスキャンし、設定したインジケーターの一致を試みます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="5a33e-117">一致がある場合は、IoC に指定した設定に従ってアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="5a33e-118">**エンドポイント防止エンジン**</span><span class="sxs-lookup"><span data-stu-id="5a33e-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="5a33e-119">インジケーターの同じリストは、予防エージェントによって受け入れされます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="5a33e-120">つまり、Microsoft Defender AV がプライマリ AV 構成の場合、一致するインジケーターは設定に従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="5a33e-121">たとえば、アクションが "Alert and Block" の場合、Microsoft Defender AV はファイルの実行 (ブロックと修復) を防止し、対応するアラートが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a33e-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="5a33e-122">一方、アクションが "許可" に設定されている場合、Microsoft Defender AV はファイルの実行を検出またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="5a33e-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="5a33e-123">**自動調査と修復エンジン**</span><span class="sxs-lookup"><span data-stu-id="5a33e-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="5a33e-124">自動調査と修復は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="5a33e-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="5a33e-125">インジケーターが "許可" に設定されている場合、自動調査と修復は、そのインジケーターの "悪い" 評決を無視します。</span><span class="sxs-lookup"><span data-stu-id="5a33e-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="5a33e-126">"Block" に設定すると、自動調査と修復によって"悪い" と処理されます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="5a33e-127">現在サポートされているアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5a33e-127">The current supported actions are:</span></span>
- <span data-ttu-id="5a33e-128">許可</span><span class="sxs-lookup"><span data-stu-id="5a33e-128">Allow</span></span>
- <span data-ttu-id="5a33e-129">アラートのみ</span><span class="sxs-lookup"><span data-stu-id="5a33e-129">Alert only</span></span>
- <span data-ttu-id="5a33e-130">アラートとブロック</span><span class="sxs-lookup"><span data-stu-id="5a33e-130">Alert and block</span></span>


<span data-ttu-id="5a33e-131">次のインジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a33e-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="5a33e-132">Files</span><span class="sxs-lookup"><span data-stu-id="5a33e-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="5a33e-133">IP アドレス、URL/ドメイン</span><span class="sxs-lookup"><span data-stu-id="5a33e-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="5a33e-134">証明書</span><span class="sxs-lookup"><span data-stu-id="5a33e-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="5a33e-135">テナントごとに 15,000 のインジケーターの制限があります。</span><span class="sxs-lookup"><span data-stu-id="5a33e-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="5a33e-136">ファイルと証明書のインジケーターは、Microsoft Defender ウイルス対策用に [定義された除外をブロックしない](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5a33e-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="5a33e-137">インジケーターは、Microsoft Defender ウイルス対策がパッシブ モードでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5a33e-137">Indicators are not supported in Microsoft Defender Antivirus is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="5a33e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a33e-138">Related topics</span></span>

- [<span data-ttu-id="5a33e-139">コンテキスト IoC の作成</span><span class="sxs-lookup"><span data-stu-id="5a33e-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="5a33e-140">Microsoft Defender for Endpoint インジケーター API を使用する</span><span class="sxs-lookup"><span data-stu-id="5a33e-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="5a33e-141">パートナー統合ソリューションの使用</span><span class="sxs-lookup"><span data-stu-id="5a33e-141">Use partner integrated solutions</span></span>](partner-applications.md)
