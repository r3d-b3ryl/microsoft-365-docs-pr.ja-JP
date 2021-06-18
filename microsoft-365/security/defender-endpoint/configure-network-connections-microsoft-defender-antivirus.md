---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策クラウド保護サービスへの接続を構成およびテストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, クラウド, 攻撃性, 保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 6ccc2eb171e85793899a7862ed9a317815d89626
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007586"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="e75ab-104">Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="e75ab-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="e75ab-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e75ab-105">**Applies to:**</span></span>

- [<span data-ttu-id="e75ab-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e75ab-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e75ab-107">Microsoft Defender ウイルス対策クラウド配信保護が適切に機能するには、セキュリティ チームがエンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75ab-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, your security team must configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="e75ab-108">この記事では、ファイアウォール ルールの使用など、許可する必要がある接続の一覧と、接続の検証手順を示します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="e75ab-109">保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="e75ab-110">ネットワーク接続の詳細については [、「Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) エンドポイントの重要な変更点」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e75ab-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="e75ab-111">Microsoft Defender for Endpoint のデモ Web [サイトを参照](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して、demo.wd.microsoft.com 機能が動作しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-111">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="e75ab-112">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="e75ab-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="e75ab-113">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="e75ab-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="e75ab-114">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="e75ab-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="e75ab-115">Microsoft Defender ウイルス対策クラウド サービスへの接続を許可する</span><span class="sxs-lookup"><span data-stu-id="e75ab-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="e75ab-116">Microsoft Defender ウイルス対策クラウド サービスは、エンドポイントに高速で強力な保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="e75ab-117">クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e75ab-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span> <span data-ttu-id="e75ab-118">[Intune、Microsoft](enable-cloud-protection-microsoft-defender-antivirus.md) Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリの個々のクライアントでサービスを有効にする方法の詳細については、「クラウドによる保護を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e75ab-118">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="e75ab-119">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の接続を許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e75ab-119">After you've enabled the service, you might need to configure your network or firewall to allow connections between it and your endpoints.</span></span> <span data-ttu-id="e75ab-120">保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、365 機械学習サービスを利用Office Microsoft Defender にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75ab-120">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="e75ab-121">任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。</span><span class="sxs-lookup"><span data-stu-id="e75ab-121">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

> [!NOTE]
> <span data-ttu-id="e75ab-122">Microsoft Defender ウイルス対策クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="e75ab-122">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="e75ab-123">クラウド サービスと呼ばれるのはクラウド サービスですが、クラウドに保存されているファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-123">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

## <a name="services-and-urls"></a><span data-ttu-id="e75ab-124">サービスと URL</span><span class="sxs-lookup"><span data-stu-id="e75ab-124">Services and URLs</span></span>

<span data-ttu-id="e75ab-125">このセクションの表に、サービスと関連付けられた Web サイト アドレス (URL) の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-125">The table in this section lists the services and their associated website addresses (URLs).</span></span> 

<span data-ttu-id="e75ab-126">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しないか確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-126">Make sure that there are no firewall or network filtering rules denying access to these URLs.</span></span> <span data-ttu-id="e75ab-127">それ以外の場合は、許可ルール (URL を除く) を作成する必要があります `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="e75ab-127">Otherwise, you might need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="e75ab-128">次の表の URL は、通信にポート 443 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-128">The URLs in the following table use port 443 for communication.</span></span>

| <span data-ttu-id="e75ab-129">サービスと説明</span><span class="sxs-lookup"><span data-stu-id="e75ab-129">Service and description</span></span> | <span data-ttu-id="e75ab-130">URL</span><span class="sxs-lookup"><span data-stu-id="e75ab-130">URL</span></span> |
|----|---- |
| <span data-ttu-id="e75ab-131">Microsoft Defender ウイルス対策クラウド配信保護サービス (MICROSOFT Active Protection Service (MAPS) とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="e75ab-131">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span><p><span data-ttu-id="e75ab-132">このサービスは、Microsoft Defender ウイルス対策によってクラウド配信の保護を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-132">This service is used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| <span data-ttu-id="e75ab-133">Microsoft Update Service (MU) と Windows Update Service (WU)</span><span class="sxs-lookup"><span data-stu-id="e75ab-133">Microsoft Update Service (MU) and Windows Update Service (WU)</span></span> <p><span data-ttu-id="e75ab-134">これらのサービスにより、セキュリティ インテリジェンスと製品の更新が可能</span><span class="sxs-lookup"><span data-stu-id="e75ab-134">These services allow for security intelligence and product updates</span></span>   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> <span data-ttu-id="e75ab-135">詳細については [、「Windows Update の接続エンドポイント」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="e75ab-135">For more details, see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="e75ab-136">セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)</span><span class="sxs-lookup"><span data-stu-id="e75ab-136">Security intelligence updates Alternate Download Location (ADL)</span></span><p><span data-ttu-id="e75ab-137">これは、インストールされているセキュリティ インテリジェンスが最新の (7 日以上遅れている) 場合、Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムの別の場所です。</span><span class="sxs-lookup"><span data-stu-id="e75ab-137">This is an alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="e75ab-138">マルウェアの送信ストレージ</span><span class="sxs-lookup"><span data-stu-id="e75ab-138">Malware submission storage</span></span> <p><span data-ttu-id="e75ab-139">これは、申請フォームまたは自動サンプル送信を介して Microsoft に送信されたファイルのアップロード場所です。</span><span class="sxs-lookup"><span data-stu-id="e75ab-139">This is the upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span> | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="e75ab-140">証明書失効リスト (CRL)</span><span class="sxs-lookup"><span data-stu-id="e75ab-140">Certificate Revocation List (CRL)</span></span> <p><span data-ttu-id="e75ab-141">この一覧は、CRL を更新するための MAPS への SSL 接続を作成するときに Windows で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-141">This list is used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="e75ab-142">シンボル ストア</span><span class="sxs-lookup"><span data-stu-id="e75ab-142">Symbol Store</span></span> <p><span data-ttu-id="e75ab-143">シンボル ストアは、修復フロー中に特定の重要なファイルを復元するために Microsoft Defender ウイルス対策によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-143">The symbol store is used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>   | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="e75ab-144">ユニバーサル テレメトリ クライアント</span><span class="sxs-lookup"><span data-stu-id="e75ab-144">Universal Telemetry Client</span></span> <p><span data-ttu-id="e75ab-145">このクライアントは、Windows がクライアント診断データを送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-145">This client is used by Windows to send client diagnostic data</span></span><p> <span data-ttu-id="e75ab-146">Microsoft Defender ウイルス対策は、製品品質の監視の目的で利用統計情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-146">Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>    | <span data-ttu-id="e75ab-147">この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e75ab-147">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:</span></span> <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="e75ab-148">ネットワークとクラウド間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="e75ab-148">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="e75ab-149">上記の URL を許可した後、Microsoft Defender Antivirus クラウド サービスに接続しており、情報を正しく報告および受信して、完全に保護されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-149">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a><span data-ttu-id="e75ab-150">cmdline ツールを使用してクラウド配信の保護を検証する</span><span class="sxs-lookup"><span data-stu-id="e75ab-150">Use the cmdline tool to validate cloud-delivered protection</span></span>

<span data-ttu-id="e75ab-151">Microsoft Defender ウイルス対策コマンド ライン ユーティリティ ( ) で次の引数を使用して、ネットワークが Microsoft Defender ウイルス対策クラウド サービスと通信できると `mpcmdrun.exe` 確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-151">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="e75ab-152">管理者レベルのバージョンのコマンド プロンプトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75ab-152">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="e75ab-153">[スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e75ab-153">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="e75ab-154">このコマンドは、Windows 10 バージョン 1703 以上でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-154">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="e75ab-155">詳細については、「Microsoft Defender Antivirus with the mpcmdrun.exe コマンド ライン [ツール」を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e75ab-155">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a><span data-ttu-id="e75ab-156">Microsoft から偽のマルウェア ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e75ab-156">Attempt to download a fake malware file from Microsoft</span></span>

<span data-ttu-id="e75ab-157">クラウドに適切に接続されている場合、Microsoft Defender Antivirus が検出してブロックするサンプル ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-157">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="e75ab-158">にアクセスしてファイルをダウンロードします [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。</span><span class="sxs-lookup"><span data-stu-id="e75ab-158">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="e75ab-159">このファイルは、実際のマルウェアではありません。</span><span class="sxs-lookup"><span data-stu-id="e75ab-159">This file is not an actual piece of malware.</span></span> <span data-ttu-id="e75ab-160">これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。</span><span class="sxs-lookup"><span data-stu-id="e75ab-160">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="e75ab-161">適切に接続されている場合は、警告の Microsoft Defender ウイルス対策通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-161">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="e75ab-162">Microsoft Edge を使用している場合は、次の通知メッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-162">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

:::image type="content" source="../../media/wdav-bafs-edge.png" alt-text="Edge でマルウェアが見つかったという通知のスクリーンショット":::

<span data-ttu-id="e75ab-164">次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="e75ab-164">A similar message occurs if you're using Internet Explorer:</span></span>

:::image type="content" source="../../media/wdav-bafs-ie.png" alt-text="マルウェアが見つかったという Microsoft Defender AV 通知":::

<span data-ttu-id="e75ab-166">また、Windows セキュリティ アプリの[スキャン履歴]セクションの [検疫された脅威] の下に検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e75ab-166">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="e75ab-167">タスク バーのシールド アイコンをクリックするか、スタート メニューの [セキュリティ] を検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="e75ab-167">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="e75ab-168">[ **ウイルス対策&保護] を選択し**、[保護の履歴] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e75ab-168">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="e75ab-169">[検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。</span><span class="sxs-lookup"><span data-stu-id="e75ab-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e75ab-170">バージョン 1703 より前のバージョンの Windows 10 では、ユーザー インターフェイスが異なります。</span><span class="sxs-lookup"><span data-stu-id="e75ab-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="e75ab-171">Windows セキュリティ [アプリで Microsoft Defender ウイルス対策を参照してください](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e75ab-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="e75ab-172">Windows イベント ログには、クライアント [Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e75ab-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

