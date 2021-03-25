---
title: ネットワーク保護を使用して、悪いサイトへの接続を防止する
description: ユーザーが既知の悪意のあるネットワーク アドレスや疑わしいネットワーク アドレスにアクセスするのを防ぐことで、ネットワークを保護する
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: be98bf810d00b6e39ba9d2674604a9fd2128a8cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198657"
---
# <a name="protect-your-network"></a><span data-ttu-id="d49e8-104">ネットワークを保護する</span><span class="sxs-lookup"><span data-stu-id="d49e8-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d49e8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d49e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="d49e8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d49e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d49e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d49e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d49e8-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d49e8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d49e8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d49e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d49e8-110">ネットワーク保護は、インターネット ベースのイベントからデバイスの攻撃表面を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="d49e8-111">これは、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="d49e8-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="d49e8-112">ネットワーク保護は [、Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) の範囲を拡張して、低評価ソース (ドメインまたはホスト名に基づく) への接続を試みるすべての送信 HTTP トラフィックをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d49e8-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="d49e8-113">ネットワーク保護は、Windows 10 バージョン 1709 から Windows でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d49e8-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="d49e8-114">ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d49e8-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="d49e8-115">グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。</span><span class="sxs-lookup"><span data-stu-id="d49e8-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="d49e8-116">ネットワーク保護の仕組みについては、「Microsoft Defender ATP testground サイト」demo.wd.microsoft.com [を参照](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) してください。</span><span class="sxs-lookup"><span data-stu-id="d49e8-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="d49e8-117">ネットワーク保護は [、Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)で最適に機能します。これにより、アラート調査シナリオの一環として、エクスプロイト保護イベントとブロックに関する詳細なレポート [が提供されます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="d49e8-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="d49e8-118">ネットワーク保護が接続をブロックすると、アクション センターから通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="d49e8-119">セキュリティ運用チームは、 [組織の詳細と](customize-attack-surface-reduction.md#customize-the-notification) 連絡先情報を使用して通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="d49e8-120">さらに、個々の攻撃表面の縮小ルールを有効にし、監視する特定の手法に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="d49e8-121">監査モードを使用 [して、](audit-windows-defender.md) ネットワーク保護が有効になっている場合に組織に与える影響を評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="d49e8-122">要件</span><span class="sxs-lookup"><span data-stu-id="d49e8-122">Requirements</span></span>

<span data-ttu-id="d49e8-123">ネットワーク保護には、Windows 10 Pro または Enterprise、および Microsoft Defender ウイルス対策のリアルタイム保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="d49e8-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="d49e8-124">Windows バージョン</span><span class="sxs-lookup"><span data-stu-id="d49e8-124">Windows version</span></span> | <span data-ttu-id="d49e8-125">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="d49e8-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="d49e8-126">Windows 10 バージョン 1709 以降</span><span class="sxs-lookup"><span data-stu-id="d49e8-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="d49e8-127">Windows Server 1803 以降</span><span class="sxs-lookup"><span data-stu-id="d49e8-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="d49e8-128">[Microsoft Defender ウイルス対策のリアルタイム保護と](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md)[クラウド配信の保護を有効](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md)にする必要があります</span><span class="sxs-lookup"><span data-stu-id="d49e8-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="d49e8-129">サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するために、ネットワークまたはファイアウォールを構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d49e8-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="d49e8-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d49e8-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="d49e8-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d49e8-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="d49e8-132">Microsoft Defender for Endpoint Security Center のネットワーク保護イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="d49e8-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="d49e8-133">Microsoft Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="d49e8-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="d49e8-134">高度な検索を使用して、Microsoft Defender for Endpoint データ [を照会できます](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="d49e8-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="d49e8-135">監査モードを使用 [している場合](audit-windows-defender.md)は、高度な検索を使用して、ネットワーク保護設定が有効になっている場合に環境に与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="d49e8-136">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d49e8-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="d49e8-137">Windows イベント ビューアーでネットワーク保護イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="d49e8-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="d49e8-138">Windows イベント ログを確認して、ネットワーク保護が悪意のある IP またはドメインへのアクセスをブロック (または監査) するときに作成されるイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d49e8-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="d49e8-139">[XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="d49e8-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="d49e8-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d49e8-140">Select **OK**.</span></span>

<span data-ttu-id="d49e8-141">この手順では、ネットワーク保護に関連する次のイベントのみを表示するためにフィルター処理するカスタム ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="d49e8-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="d49e8-142">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d49e8-142">Event ID</span></span> | <span data-ttu-id="d49e8-143">説明</span><span class="sxs-lookup"><span data-stu-id="d49e8-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="d49e8-144">5007</span><span class="sxs-lookup"><span data-stu-id="d49e8-144">5007</span></span> | <span data-ttu-id="d49e8-145">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="d49e8-145">Event when settings are changed</span></span> |
| <span data-ttu-id="d49e8-146">1125</span><span class="sxs-lookup"><span data-stu-id="d49e8-146">1125</span></span> | <span data-ttu-id="d49e8-147">監査モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="d49e8-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="d49e8-148">1126</span><span class="sxs-lookup"><span data-stu-id="d49e8-148">1126</span></span> | <span data-ttu-id="d49e8-149">ブロック モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="d49e8-149">Event when network protection fires in block mode</span></span> |

## <a name="related-articles"></a><span data-ttu-id="d49e8-150">関連記事</span><span class="sxs-lookup"><span data-stu-id="d49e8-150">Related articles</span></span>

- <span data-ttu-id="d49e8-151">[ネットワーク保護の評価|](evaluate-network-protection.md) 機能の動作と、通常作成されるイベントを示す簡単なシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="d49e8-151">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="d49e8-152">[ネットワーク保護の有効化|](enable-network-protection.md) グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。</span><span class="sxs-lookup"><span data-stu-id="d49e8-152">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
