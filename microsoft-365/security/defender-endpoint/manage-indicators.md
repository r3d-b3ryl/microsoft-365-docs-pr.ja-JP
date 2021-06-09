---
title: インジケーターの作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを作成します。
keywords: 管理、許可、ブロックされた、ブロック、クリーン、悪意のある、ファイル ハッシュ、ip アドレス、URL、ドメイン
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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842244"
---
# <a name="create-indicators"></a><span data-ttu-id="8ae2a-104">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="8ae2a-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ae2a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8ae2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ae2a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ae2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ae2a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ae2a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="8ae2a-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="8ae2a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ae2a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="8ae2a-110">侵害インジケーター (IoCs) マッチングは、すべてのエンドポイント保護ソリューションで不可欠な機能です。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="8ae2a-111">この機能により、SecOps は検出およびブロック (防止と応答) のインジケーターの一覧を設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="8ae2a-112">エンティティの検出、防止、除外を定義するインジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="8ae2a-113">実行するアクションと、アクションを適用する期間とその時期、アクションを適用するデバイス グループの範囲を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="8ae2a-114">現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、エンドポイント防止エンジン (Microsoft Defender ウィルス対策) です。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="8ae2a-115">**クラウド検出エンジン**</span><span class="sxs-lookup"><span data-stu-id="8ae2a-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="8ae2a-116">Defender for Endpoint のクラウド検出エンジンは、収集されたデータを定期的にスキャンし、設定したインジケーターと一致するものを探します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="8ae2a-117">一致がある場合、IoC に指定した設定に従ってアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="8ae2a-118">**エンドポイント防止エンジン**</span><span class="sxs-lookup"><span data-stu-id="8ae2a-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="8ae2a-119">インジケーターの同じリストは、防止エージェントによって適用されます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="8ae2a-120">つまり、Microsoft Defender AV が主な AV 構成である場合、一致したインジケーターは設定に従って処理されます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="8ae2a-121">たとえば、アクションが "Alert and Block (警告とブロック)" の場合、Microsoft Defender AV によってファイルの実行 (ブロックおよび修復) が防止され、対応する警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="8ae2a-122">一方、アクションが "許可" に設定されている場合、Microsoft Defender AV ではファイルの検出やファイルの実行がブロックされません。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="8ae2a-123">**自動調査と修復エンジン**</span><span class="sxs-lookup"><span data-stu-id="8ae2a-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="8ae2a-124">自動調査と修復は同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="8ae2a-125">インジケーターが "許可" に設定されている場合、自動調査と修復では"悪い" 判定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="8ae2a-126">"ブロック" に設定すると、自動調査と修復は、"悪い" として処理します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="8ae2a-127">EnableFileHashComputation 設定は、ファイル スキャン時に cert とファイル IoC のファイル ハッシュを計算します。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="8ae2a-128">このポリシーは、信頼できるアプリケーションに属するハッシュと cert の IoC 適用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="8ae2a-129">ファイル設定の許可またはブロックで、同時に有効化、無効化できます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="8ae2a-130">EnableFileHashComputation はグループ ポリシーから手動で有効にでき、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="8ae2a-131">現在サポートされているアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-131">The current supported actions are:</span></span>
- <span data-ttu-id="8ae2a-132">許可</span><span class="sxs-lookup"><span data-stu-id="8ae2a-132">Allow</span></span>
- <span data-ttu-id="8ae2a-133">通知のみ</span><span class="sxs-lookup"><span data-stu-id="8ae2a-133">Alert only</span></span>
- <span data-ttu-id="8ae2a-134">通知とブロック</span><span class="sxs-lookup"><span data-stu-id="8ae2a-134">Alert and block</span></span>


<span data-ttu-id="8ae2a-135">次のインジケーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="8ae2a-136">ファイル</span><span class="sxs-lookup"><span data-stu-id="8ae2a-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="8ae2a-137">IP アドレス、URL/ドメイン</span><span class="sxs-lookup"><span data-stu-id="8ae2a-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="8ae2a-138">証明書</span><span class="sxs-lookup"><span data-stu-id="8ae2a-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="8ae2a-139">1 テナントあたり 15,000 件のインジケーターの制限があります。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="8ae2a-140">ファイルおよび証明書インジケーターは、[Microsoft Defender ウイルス対策ソフトウェア用に定義された例外](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="8ae2a-141">Microsoft Defender ウイルス対策はパッシブ モードの場合にインジケーターをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="8ae2a-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="8ae2a-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8ae2a-142">Related topics</span></span>

- [<span data-ttu-id="8ae2a-143">コンテキスト IoC の作成</span><span class="sxs-lookup"><span data-stu-id="8ae2a-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="8ae2a-144">エンドポイント インジケーター API に Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="8ae2a-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="8ae2a-145">パートナー統合ソリューションの使用</span><span class="sxs-lookup"><span data-stu-id="8ae2a-145">Use partner integrated solutions</span></span>](partner-applications.md)
