---
title: ネットワーク保護に関する問題のトラブルシューティング
description: Microsoft Defender for Endpoint のネットワーク保護に関する問題のトラブルシューティングを行うリソースとサンプル コード。
keywords: トラブルシューティング、エラー、修正、Windows Defender 例、asr、ルール、ヒップ、トラブルシューティング、監査、除外、誤検知、破損、ブロック、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f77ce94fda63a9e7e8a9484a67a22eeec136d619
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935883"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="58c57-104">ネットワーク保護のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="58c57-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="58c57-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="58c57-105">**Applies to:**</span></span>
- [<span data-ttu-id="58c57-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="58c57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="58c57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58c57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="58c57-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="58c57-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58c57-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="58c57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="58c57-110">ネットワーク保護を [使用すると、](network-protection.md) 次のような問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="58c57-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="58c57-111">ネットワーク保護は、安全な Web サイトをブロックします (誤検知)</span><span class="sxs-lookup"><span data-stu-id="58c57-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="58c57-112">ネットワーク保護で疑わしい Web サイトまたは既知の悪意のある Web サイトをブロックできない (false negative)</span><span class="sxs-lookup"><span data-stu-id="58c57-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="58c57-113">これらの問題のトラブルシューティングには、次の 4 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="58c57-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="58c57-114">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="58c57-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="58c57-115">監査モードを使用してルールをテストする</span><span class="sxs-lookup"><span data-stu-id="58c57-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="58c57-116">指定したルールの除外を追加する (誤検知の場合)</span><span class="sxs-lookup"><span data-stu-id="58c57-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="58c57-117">サポート ログの送信</span><span class="sxs-lookup"><span data-stu-id="58c57-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="58c57-118">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="58c57-118">Confirm prerequisites</span></span>

<span data-ttu-id="58c57-119">ネットワーク保護は、次の条件を持つデバイスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="58c57-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="58c57-120">エンドポイントは、バージョン 1709 Windows 10 ProまたはEnterpriseバージョン 1709 以上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="58c57-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="58c57-121">エンドポイントは、Microsoft Defender ウイルス対策ウイルス対策保護アプリとして使用しています。</span><span class="sxs-lookup"><span data-stu-id="58c57-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="58c57-122">[Microsoft 以外のウイルス対策ソリューションを使用している場合の問題を確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="58c57-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="58c57-123">[リアルタイム保護が](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 有効になっています。</span><span class="sxs-lookup"><span data-stu-id="58c57-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="58c57-124">[クラウド配信の保護が](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 有効になっています。</span><span class="sxs-lookup"><span data-stu-id="58c57-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="58c57-125">監査モードが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="58c57-125">Audit mode is not enabled.</span></span> <span data-ttu-id="58c57-126">グループ [ポリシーを使用して](enable-network-protection.md#group-policy) ルールを無効 **(値** : **0) に設定します**。</span><span class="sxs-lookup"><span data-stu-id="58c57-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="58c57-127">監査モードを使用する</span><span class="sxs-lookup"><span data-stu-id="58c57-127">Use audit mode</span></span>

<span data-ttu-id="58c57-128">監査モードでネットワーク保護を有効にしてから、作成した Web サイトにアクセスして機能をデモできます。</span><span class="sxs-lookup"><span data-stu-id="58c57-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="58c57-129">すべての Web サイト接続はネットワーク保護によって許可されますが、ネットワーク保護が有効になっている場合にブロックされた接続を示すイベントがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="58c57-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="58c57-130">ネットワーク保護を監査モード **に設定します**。</span><span class="sxs-lookup"><span data-stu-id="58c57-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="58c57-131">問題の原因となっている接続アクティビティを実行します (たとえば、サイトにアクセスしようとしたり、ブロックしたりしない IP アドレスに接続したりします)。</span><span class="sxs-lookup"><span data-stu-id="58c57-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="58c57-132">[ネットワーク保護イベント ログを確認](network-protection.md#review-network-protection-events-in-windows-event-viewer) して、機能が [有効] に設定されている場合に接続がブロックされた可能性を確認 **します**。</span><span class="sxs-lookup"><span data-stu-id="58c57-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="58c57-133">ネットワーク保護がブロックする必要がある接続をブロックしていない場合は、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="58c57-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="58c57-134">誤検知または偽陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="58c57-134">Report a false positive or false negative</span></span>

<span data-ttu-id="58c57-135">デモ サイトと監査モードで機能をテストし、ネットワーク保護が事前構成されたシナリオで動作しているが、特定の接続で期待通りには動作しない場合は[、Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) Web ベースの申請フォームを使用して、ネットワーク保護に対して誤検知または誤検知を報告します。</span><span class="sxs-lookup"><span data-stu-id="58c57-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="58c57-136">E5 サブスクリプションを使用すると、関連 [付けられたアラートへのリンクを提供できます](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="58c57-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="58c57-137">「Address [false positives/negatives in Microsoft Defender for Endpoint」を参照してください](defender-endpoint-false-positives-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="58c57-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="58c57-138">ネットワーク保護スコープから Web サイトを除外する</span><span class="sxs-lookup"><span data-stu-id="58c57-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="58c57-139">ブロックされている Web サイト (誤検知) を許可するには、信頼できるサイトの一覧に URL [を追加します](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)。</span><span class="sxs-lookup"><span data-stu-id="58c57-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="58c57-140">このリストの Web リソースは、ネットワーク保護チェックをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="58c57-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="58c57-141">ファイル提出の診断データを収集する</span><span class="sxs-lookup"><span data-stu-id="58c57-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="58c57-142">ネットワーク保護に関する問題を報告する場合は、Microsoft のサポートチームとエンジニアリング チームが問題のトラブルシューティングに役立つ診断データを収集して提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58c57-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="58c57-143">管理者特権のコマンド プロンプトを開き、次のディレクトリWindows Defenderします。</span><span class="sxs-lookup"><span data-stu-id="58c57-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="58c57-144">次のコマンドを実行して、診断ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="58c57-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="58c57-145">提出フォームにファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="58c57-145">Attach the file to the submission form.</span></span> <span data-ttu-id="58c57-146">既定では、診断ログはで保存されます `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="58c57-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="58c57-147">ネットワーク保護に関する接続の問題を解決する (E5 のお客様向け)</span><span class="sxs-lookup"><span data-stu-id="58c57-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="58c57-148">ネットワーク保護が実行される環境のため、Microsoft はオペレーティング システムのプロキシ設定を確認できません。</span><span class="sxs-lookup"><span data-stu-id="58c57-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="58c57-149">場合によっては、ネットワーク保護クライアントがクラウド サービスにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="58c57-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="58c57-150">ネットワーク保護に関する接続の問題を解決するには、次のいずれかのレジストリ キーを構成して、ネットワーク保護がプロキシ構成を認識します。</span><span class="sxs-lookup"><span data-stu-id="58c57-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="58c57-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="58c57-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="58c57-152">レジストリ キーは、PowerShell、Microsoft エンドポイント マネージャーグループ ポリシーを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="58c57-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="58c57-153">以下に役立つリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="58c57-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="58c57-154">レジストリ キーの操作</span><span class="sxs-lookup"><span data-stu-id="58c57-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="58c57-155">ユーザー設定のカスタム クライアント設定を構成Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="58c57-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="58c57-156">グループ ポリシー設定を使用してグループ ポリシーをEndpoint Protection</span><span class="sxs-lookup"><span data-stu-id="58c57-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="58c57-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="58c57-157">See also</span></span>

- [<span data-ttu-id="58c57-158">ネットワーク保護</span><span class="sxs-lookup"><span data-stu-id="58c57-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="58c57-159">ネットワーク保護を評価する</span><span class="sxs-lookup"><span data-stu-id="58c57-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="58c57-160">ネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="58c57-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="58c57-161">Defender for Endpoint で誤検知/負のアドレスを指定する</span><span class="sxs-lookup"><span data-stu-id="58c57-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
