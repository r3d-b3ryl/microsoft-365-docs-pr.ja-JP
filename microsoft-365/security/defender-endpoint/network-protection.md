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
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844264"
---
# <a name="protect-your-network"></a><span data-ttu-id="1c648-104">ネットワークを保護する</span><span class="sxs-lookup"><span data-stu-id="1c648-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c648-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1c648-105">**Applies to:**</span></span>
- [<span data-ttu-id="1c648-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1c648-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1c648-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c648-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1c648-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="1c648-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1c648-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1c648-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1c648-110">ネットワーク保護は、インターネット ベースのイベントからデバイスの攻撃表面を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1c648-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="1c648-111">これは、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="1c648-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="1c648-112">ネットワーク保護は[、Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)の範囲を拡張して、低評価ソース (ドメインまたはホスト名に基づく) への接続を試みるすべての送信 HTTP トラフィックをブロックします。</span><span class="sxs-lookup"><span data-stu-id="1c648-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="1c648-113">ネットワーク保護は、Windowsバージョン 1709 Windows 10からサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1c648-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="1c648-114">ネットワーク保護は他のオペレーティング システムではまだサポートされていませんが、Web 保護は、新しいオペレーティング システムを使用Microsoft EdgeサポートChromium。</span><span class="sxs-lookup"><span data-stu-id="1c648-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="1c648-115">詳細については、「Web 保護」 [を参照してください](web-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="1c648-116">ネットワーク保護は、Web 保護の保護 [をオペレーティング](web-protection-overview.md) システム レベルまで拡張します。</span><span class="sxs-lookup"><span data-stu-id="1c648-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="1c648-117">Edge の Web 保護機能は、サポートされている他のブラウザーやブラウザー以外のアプリケーションに提供されます。</span><span class="sxs-lookup"><span data-stu-id="1c648-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="1c648-118">さらに、ネットワーク保護は、エンドポイントの検出と応答で使用する場合に、侵害の指標 (IOC) の可視性とブロック [を提供します](overview-endpoint-detection-response.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="1c648-119">たとえば、ネットワーク保護はカスタム インジケーターと [動作します](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="1c648-120">ネットワーク保護を有効にする方法の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="1c648-121">グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。</span><span class="sxs-lookup"><span data-stu-id="1c648-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="1c648-122">ネットワーク保護のしくみについては、「Microsoft Defender for [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Endpoint testground」の demo.wd.microsoft.com を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c648-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="1c648-123">ネットワーク保護は [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)で最適に機能します。これにより、アラート調査シナリオの一環として、エクスプロイト保護イベントとブロックに関する詳細なレポート [が提供されます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="1c648-124">ネットワーク保護が接続をブロックすると、アクション センターから通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c648-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="1c648-125">セキュリティ運用チームは、 [組織の詳細と](customize-attack-surface-reduction.md#customize-the-notification) 連絡先情報を使用して通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="1c648-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="1c648-126">さらに、個々の攻撃表面の縮小ルールを有効にし、監視する特定の手法に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="1c648-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="1c648-127">監査モードを使用 [して、](audit-windows-defender.md) ネットワーク保護が有効になっている場合に組織に与える影響を評価することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c648-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c648-128">要件</span><span class="sxs-lookup"><span data-stu-id="1c648-128">Requirements</span></span>

<span data-ttu-id="1c648-129">ネットワーク保護には、Windows 10 ProまたはEnterprise、リアルタイムMicrosoft Defender ウイルス対策保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c648-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="1c648-130">Windows バージョン</span><span class="sxs-lookup"><span data-stu-id="1c648-130">Windows version</span></span> | <span data-ttu-id="1c648-131">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="1c648-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="1c648-132">Windows 10バージョン 1709 以降</span><span class="sxs-lookup"><span data-stu-id="1c648-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="1c648-133">Windowsサーバー 1803 以降</span><span class="sxs-lookup"><span data-stu-id="1c648-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="1c648-134">[Microsoft Defender ウイルス対策保護とクラウド](configure-real-time-protection-microsoft-defender-antivirus.md)[配信保護を有効](enable-cloud-protection-microsoft-defender-antivirus.md)にする必要があります</span><span class="sxs-lookup"><span data-stu-id="1c648-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="1c648-135">サービスを有効にした後、サービスとデバイス (エンドポイントとも呼ばれます) 間の接続を許可するために、ネットワークまたはファイアウォールを構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c648-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="1c648-136">Microsoft Defender for Endpoint Security Center のネットワーク保護イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="1c648-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="1c648-137">Microsoft Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="1c648-138">高度な検索を使用して、Microsoft Defender for Endpoint データ [を照会できます](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="1c648-139">監査モードを使用 [している場合](audit-windows-defender.md)は、高度な検索を使用して、ネットワーク保護設定が有効になっている場合に環境に与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1c648-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="1c648-140">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1c648-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="1c648-141">イベント ビューアーでネットワーク保護イベントWindows確認する</span><span class="sxs-lookup"><span data-stu-id="1c648-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="1c648-142">ネットワーク保護が悪意のある IP またはドメインWindowsアクセスをブロック (または監査) するときに作成されるイベントを確認するには、次のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c648-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="1c648-143">[XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="1c648-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="1c648-144">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c648-144">Select **OK**.</span></span>

<span data-ttu-id="1c648-145">この手順では、ネットワーク保護に関連する次のイベントのみを表示するためにフィルター処理するカスタム ビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c648-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="1c648-146">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1c648-146">Event ID</span></span> | <span data-ttu-id="1c648-147">説明</span><span class="sxs-lookup"><span data-stu-id="1c648-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="1c648-148">5007</span><span class="sxs-lookup"><span data-stu-id="1c648-148">5007</span></span> | <span data-ttu-id="1c648-149">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="1c648-149">Event when settings are changed</span></span> |
| <span data-ttu-id="1c648-150">1125</span><span class="sxs-lookup"><span data-stu-id="1c648-150">1125</span></span> | <span data-ttu-id="1c648-151">監査モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="1c648-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="1c648-152">1126</span><span class="sxs-lookup"><span data-stu-id="1c648-152">1126</span></span> | <span data-ttu-id="1c648-153">ブロック モードでネットワーク保護が発生した場合のイベント</span><span class="sxs-lookup"><span data-stu-id="1c648-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="1c648-154">マルチ セッションをWindowsしている仮想デスクトップWindows 10 Enterpriseに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1c648-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="1c648-155">マルチ ユーザーの性質上、Windows 10 Enterpriseに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c648-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="1c648-156">ネットワーク保護はデバイス全体の機能であり、特定のユーザー セッションを対象とすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c648-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="1c648-157">Web コンテンツ フィルター ポリシーもデバイス全体です。</span><span class="sxs-lookup"><span data-stu-id="1c648-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="1c648-158">ユーザー グループを区別する必要がある場合は、仮想デスクトップ ホスト プールと割り当てのWindows作成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1c648-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="1c648-159">監査モードでネットワーク保護をテストし、展開する前に動作を評価します。</span><span class="sxs-lookup"><span data-stu-id="1c648-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="1c648-160">多数のユーザーまたは多数のマルチユーザー セッションがある場合は、展開のサイズを変更してください。</span><span class="sxs-lookup"><span data-stu-id="1c648-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="1c648-161">ネットワーク保護の代替オプション</span><span class="sxs-lookup"><span data-stu-id="1c648-161">Alternative option for network protection</span></span>

<span data-ttu-id="1c648-162">Azure Windows 10 Enterprise Windows Virtual Desktop で使用されるマルチセッション 1909 以上の場合、Microsoft Edge のネットワーク保護は次の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1c648-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="1c648-163">[ [ネットワーク保護を有効にする] を](enable-network-protection.md) 使用し、指示に従ってポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1c648-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="1c648-164">次の PowerShell コマンドを実行します。 `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="1c648-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="1c648-165">ネットワーク保護のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1c648-165">Network protection troubleshooting</span></span>

<span data-ttu-id="1c648-166">ネットワーク保護が実行される環境のため、Microsoft はオペレーティング システムのプロキシ設定を検出できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c648-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="1c648-167">場合によっては、ネットワーク保護クライアントがクラウド サービスにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c648-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="1c648-168">接続の問題を解決するには、E5 ライセンスをお持ちのお客様は、次のいずれかの Defender レジストリ キーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c648-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="1c648-169">関連資料</span><span class="sxs-lookup"><span data-stu-id="1c648-169">Related articles</span></span>

- <span data-ttu-id="1c648-170">[ネットワーク保護の評価|](evaluate-network-protection.md) 機能の動作と、通常作成されるイベントを示す簡単なシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c648-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="1c648-171">[ネットワーク保護の有効化|](enable-network-protection.md) グループ ポリシー、PowerShell、MDM CSP を使用して、ネットワーク内のネットワーク保護を有効にして管理します。</span><span class="sxs-lookup"><span data-stu-id="1c648-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
