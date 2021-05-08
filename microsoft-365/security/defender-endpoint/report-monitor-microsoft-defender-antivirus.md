---
title: Microsoft Defender ウイルス対策保護の監視とレポート
description: Configuration Manager またはセキュリティ情報とイベント管理 (SIEM) ツールを使用してレポートを使用し、PowerShell と WMI を使用して Microsoft Defender AV を監視します。
keywords: siem, 監視, レポート, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5780daaa65a4d83376dd7977e03e88e2d828befc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269590"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="23246-104">Microsoft Defender ウイルス対策のレポート</span><span class="sxs-lookup"><span data-stu-id="23246-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="23246-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="23246-105">**Applies to:**</span></span>

- [<span data-ttu-id="23246-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="23246-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="23246-107">Microsoft Defender ウイルス対策は、Windows 10、Windows Server 2019、および Windows Server 2016 に組み込されています。</span><span class="sxs-lookup"><span data-stu-id="23246-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="23246-108">Microsoft Defender Antivirus は、Microsoft Defender for Endpoint の次世代保護の一部です。</span><span class="sxs-lookup"><span data-stu-id="23246-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="23246-109">次世代の保護は、電子メール、アプリ、クラウド、Web 全体のウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威からデバイスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23246-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="23246-110">Microsoft Defender ウイルス対策では、保護の状態とアラートを確認するためのいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="23246-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="23246-111">Microsoft Endpoint Manager を使用して [、Microsoft Defender ウイルス対策を監視](/configmgr/protect/deploy-use/monitor-endpoint-protection) したり、電子メール [通知を作成したりできます](/configmgr/protect/deploy-use/endpoint-configure-alerts)。</span><span class="sxs-lookup"><span data-stu-id="23246-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="23246-112">または、Microsoft Intune を使用して保護 [を監視できます](/intune/introduction-intune)。</span><span class="sxs-lookup"><span data-stu-id="23246-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="23246-113">Microsoft Operations Management [](/windows/deployment/update/update-compliance-get-started) Suite には、保護更新プログラムやリアルタイム保護設定など、Microsoft Defender ウイルス対策の主要な問題を報告する更新コンプライアンス アドインがあります。</span><span class="sxs-lookup"><span data-stu-id="23246-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="23246-114">サードパーティのセキュリティ情報とイベント管理 (SIEM) サーバーがある場合は、クライアント イベントをWindows Defender [することもできます](/windows/win32/events/windows-events)。</span><span class="sxs-lookup"><span data-stu-id="23246-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="23246-115">Windows イベントは、セキュリティ アカウント マネージャー (SAM) イベント[(Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)用に拡張された[](/windows/device-security/auditing/security-auditing-overview)イベント、セキュリティ監査トピックも参照)、およびセキュリティ イベントなど、いくつかのセキュリティ イベント[ソースでWindows Defenderされます](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="23246-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="23246-116">これらのイベントは、Windows イベント コレクターを使用して一般 [に集約できます](/windows/win32/wec/windows-event-collector)。</span><span class="sxs-lookup"><span data-stu-id="23246-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="23246-117">多くの場合、SIEM サーバーには Windows イベント用のコネクタが用意され、SIEM サーバー内のすべてのセキュリティ イベントを関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="23246-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="23246-118">また、Log [Analytics のマルウェア評価ソリューションを使用してマルウェア イベントを監視することもできます](/azure/log-analytics/log-analytics-malware)。</span><span class="sxs-lookup"><span data-stu-id="23246-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="23246-119">PowerShell、WMI、または Microsoft Azure を使用して状態を監視または決定するには、(展開、管理、およびレポートオプションの表 [) を参照してください](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。</span><span class="sxs-lookup"><span data-stu-id="23246-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="23246-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="23246-120">Related articles</span></span>

- [<span data-ttu-id="23246-121">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="23246-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="23246-122">Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="23246-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="23246-123">Microsoft Defender ウイルス対策の展開</span><span class="sxs-lookup"><span data-stu-id="23246-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)