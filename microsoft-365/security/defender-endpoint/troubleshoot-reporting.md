---
title: Microsoft Defender AV のレポート ツールに関する問題のトラブルシューティング
description: Microsoft Defender AV 保護の状態を更新コンプライアンスで報告しようとするときに一般的な問題を特定して解決する
keywords: トラブルシューティング、エラー、修正、更新コンプライアンス、oms、モニター、レポート、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274894"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="4dd6f-104">更新プログラムのコンプライアンスでの Microsoft Defender ウイルス対策レポートのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dd6f-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4dd6f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4dd6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="4dd6f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4dd6f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="4dd6f-107">2020 年 3 月 31 日に、更新Microsoft Defender ウイルス対策レポート機能が削除されます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="4dd6f-108">セキュリティの機能と更新プログラムを細かく制御できる Microsoft エンドポイント マネージャー を使用して、引[き続き](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)セキュリティ コンプライアンス ポリシーを定義および確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="4dd6f-109">更新プログラムのコンプライアンスMicrosoft Defender ウイルス対策を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="4dd6f-110">E3、B、F1、VL、およびライセンスの状態Pro表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="4dd6f-111">ただし、E5 ライセンスの場合は [、Microsoft Defender for Endpoint ポータルを使用する必要があります](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="4dd6f-112">ライセンス オプションの詳細については、「製品[ライセンス オプションWindows 10を参照してください](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="4dd6f-113">[Windows Analytics Update Compliance](/windows/deployment/update/update-compliance-using#wdav-assessment)を使用して、Microsoft Defender ウイルス対策 を使用しているネットワーク内のデバイスまたはエンドポイントの保護状態に関するレポートを取得すると、問題や問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="4dd6f-114">通常、問題の最も一般的なインジケーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="4dd6f-115">表示を期待していたすべてのデバイスの数またはサブセットのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="4dd6f-116">デバイスが一切表示されない</span><span class="sxs-lookup"><span data-stu-id="4dd6f-116">You do not see any devices at all</span></span>
- <span data-ttu-id="4dd6f-117">表示されるレポートと情報が古くなっている (数日以上前)</span><span class="sxs-lookup"><span data-stu-id="4dd6f-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="4dd6f-118">更新コンプライアンスに関連しない Microsoft Defender ウイルス対策 サービスに関連する一般的なエラー コードとイベントの MICROSOFT DEFENDER ウイルス対策[を参照してください](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="4dd6f-119">これらの問題のトラブルシューティングには、次の 3 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="4dd6f-120">すべての前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="4dd6f-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="4dd6f-121">クラウド ベースのサービスへの接続Windows Defender確認する</span><span class="sxs-lookup"><span data-stu-id="4dd6f-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="4dd6f-122">サポート ログの送信</span><span class="sxs-lookup"><span data-stu-id="4dd6f-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="4dd6f-123">通常、デバイスが更新コンプライアンスに表示され始めるには 3 日かかる。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="4dd6f-124">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="4dd6f-124">Confirm prerequisites</span></span>

<span data-ttu-id="4dd6f-125">デバイスが更新コンプライアンスに適切に表示するには、更新コンプライアンス サービスと更新プログラムの両方の前提条件を満たす必要Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="4dd6f-126">エンドポイントは、Microsoft Defender ウイルス対策ウイルス対策保護アプリとして使用しています。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="4dd6f-127">[他のウイルス対策アプリを使用すると、Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) はそれ自体を無効にし、エンドポイントは Update Compliance で報告されません。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="4dd6f-128">[クラウド配信の保護が有効になっています](enable-cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="4dd6f-129">エンドポイントは Microsoft Defender AV クラウド [に接続できます](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="4dd6f-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="4dd6f-130">エンドポイントがバージョン 1607 Windows 10前に実行されている場合、Windows 10データを拡張[レベルに設定する必要があります](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="4dd6f-131">すべての要件が満たされたのは 3 日間です。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="4dd6f-132">"更新プログラムのコンプライアンスMicrosoft Defender ウイルス対策を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="4dd6f-133">E3、B、F1、VL、およびライセンスの状態Pro表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="4dd6f-134">ただし、E5 ライセンスの場合は、Microsoft Defender for Endpoint ポータル ( を使用する必要があります https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="4dd6f-135">ライセンス オプションの詳細については、「製品Windows 10」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="4dd6f-136">上記の前提条件が満たされている場合は、次の手順に進み、診断情報を収集して送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd6f-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4dd6f-137">更新コンプライアンスのトラブルシューティングの診断データを収集する</span><span class="sxs-lookup"><span data-stu-id="4dd6f-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="4dd6f-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="4dd6f-138">Related topics</span></span>

- [<span data-ttu-id="4dd6f-139">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="4dd6f-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="4dd6f-140">展開Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="4dd6f-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)