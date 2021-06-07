---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: クラウド保護サービスへの接続を構成Microsoft Defender ウイルス対策テストします。
keywords: ウイルス対策、 Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、防御、クラウド、攻撃性、保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca5737a0224825a0c88159c4a3931cc0c310b69b
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788453"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="bcc80-104">Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="bcc80-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="bcc80-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bcc80-105">**Applies to:**</span></span>

- [<span data-ttu-id="bcc80-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bcc80-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bcc80-107">クラウドでMicrosoft Defender ウイルス対策保護が適切に動作するには、セキュリティ チームが、エンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc80-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, your security team must configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="bcc80-108">この記事では、ファイアウォール ルールの使用など、許可する必要がある接続の一覧と、接続の検証手順を示します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="bcc80-109">保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="bcc80-110">ネットワーク接続の詳細については [、「Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) エンドポイントの重要な変更点」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc80-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="bcc80-111">Microsoft Defender for Endpoint のデモ Web [サイトを参照](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) して、demo.wd.microsoft.com 機能が動作しているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-111">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="bcc80-112">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="bcc80-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="bcc80-113">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="bcc80-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="bcc80-114">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="bcc80-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="bcc80-115">クラウド サービスへの接続Microsoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="bcc80-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="bcc80-116">クラウド Microsoft Defender ウイルス対策は、エンドポイントに高速で強力な保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="bcc80-117">クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bcc80-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span> <span data-ttu-id="bcc80-118">[Intune、Microsoft Endpoint Configuration Manager、](enable-cloud-protection-microsoft-defender-antivirus.md)グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリ内の個々のクライアントでサービスを有効にする方法の詳細については、「クラウドによる保護を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc80-118">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="bcc80-119">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の接続を許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcc80-119">After you've enabled the service, you might need to configure your network or firewall to allow connections between it and your endpoints.</span></span> <span data-ttu-id="bcc80-120">保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、Microsoft Defender にアクセスして機械学習サービスOffice 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc80-120">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="bcc80-121">任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。</span><span class="sxs-lookup"><span data-stu-id="bcc80-121">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

> [!NOTE]
> <span data-ttu-id="bcc80-122">クラウド Microsoft Defender ウイルス対策は、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="bcc80-122">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="bcc80-123">クラウド サービスと呼ばれるのはクラウド サービスですが、クラウドに保存されているファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-123">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

## <a name="services-and-urls"></a><span data-ttu-id="bcc80-124">サービスと URL</span><span class="sxs-lookup"><span data-stu-id="bcc80-124">Services and URLs</span></span>

<span data-ttu-id="bcc80-125">このセクションの表に、サービスと関連付けられた Web サイト アドレス (URL) の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-125">The table in this section lists the services and their associated website addresses (URLs).</span></span> 

<span data-ttu-id="bcc80-126">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタールールが存在しないか確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-126">Make sure that there are no firewall or network filtering rules denying access to these URLs.</span></span> <span data-ttu-id="bcc80-127">それ以外の場合は、許可ルール (URL を除く) を作成する必要があります `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="bcc80-127">Otherwise, you might need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="bcc80-128">次の表の URL は、通信にポート 443 を使用します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-128">The URLs in the following table use port 443 for communication.</span></span>

| <span data-ttu-id="bcc80-129">サービスと説明</span><span class="sxs-lookup"><span data-stu-id="bcc80-129">Service and description</span></span> | <span data-ttu-id="bcc80-130">URL</span><span class="sxs-lookup"><span data-stu-id="bcc80-130">URL</span></span> |
|----|---- |
| <span data-ttu-id="bcc80-131">Microsoft Defender ウイルス対策 (MAPS) とも呼ばれるクラウド配信Microsoft Active Protection Service保護サービス</span><span class="sxs-lookup"><span data-stu-id="bcc80-131">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span><p><span data-ttu-id="bcc80-132">このサービスは、クラウドMicrosoft Defender ウイルス対策を提供するために、ユーザーが使用します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-132">This service is used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| <span data-ttu-id="bcc80-133">Microsoft Update Service (MU) および Windows 更新サービス (WU)</span><span class="sxs-lookup"><span data-stu-id="bcc80-133">Microsoft Update Service (MU) and Windows Update Service (WU)</span></span> <p><span data-ttu-id="bcc80-134">これらのサービスにより、セキュリティ インテリジェンスと製品の更新が可能</span><span class="sxs-lookup"><span data-stu-id="bcc80-134">These services allow for security intelligence and product updates</span></span>   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> <span data-ttu-id="bcc80-135">詳細については、「接続エンドポイント for [Windows Update」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="bcc80-135">For more details, see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="bcc80-136">セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)</span><span class="sxs-lookup"><span data-stu-id="bcc80-136">Security intelligence updates Alternate Download Location (ADL)</span></span><p><span data-ttu-id="bcc80-137">これは、インストールされているセキュリティ インテリジェンスがMicrosoft Defender ウイルス対策 (7 日以上遅れている) 場合のセキュリティ インテリジェンス更新プログラムの別の場所です。</span><span class="sxs-lookup"><span data-stu-id="bcc80-137">This is an alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="bcc80-138">マルウェアの送信ストレージ</span><span class="sxs-lookup"><span data-stu-id="bcc80-138">Malware submission storage</span></span> <p><span data-ttu-id="bcc80-139">これは、申請フォームまたは自動サンプル送信を介して Microsoft に送信されたファイルのアップロード場所です。</span><span class="sxs-lookup"><span data-stu-id="bcc80-139">This is the upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span> | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="bcc80-140">証明書失効リスト (CRL)</span><span class="sxs-lookup"><span data-stu-id="bcc80-140">Certificate Revocation List (CRL)</span></span> <p><span data-ttu-id="bcc80-141">この一覧は、CRL をWindowsするために MAPS への SSL 接続を作成するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-141">This list is used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="bcc80-142">シンボル ストア</span><span class="sxs-lookup"><span data-stu-id="bcc80-142">Symbol Store</span></span> <p><span data-ttu-id="bcc80-143">シンボル ストアは、修復フロー中にMicrosoft Defender ウイルス対策ファイルを復元するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-143">The symbol store is used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>   | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="bcc80-144">ユニバーサル テレメトリ クライアント</span><span class="sxs-lookup"><span data-stu-id="bcc80-144">Universal Telemetry Client</span></span> <p><span data-ttu-id="bcc80-145">このクライアントは、クライアント診断Windows送信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-145">This client is used by Windows to send client diagnostic data</span></span><p> <span data-ttu-id="bcc80-146">Microsoft Defender ウイルス対策品質監視の目的で利用統計情報を使用する場合</span><span class="sxs-lookup"><span data-stu-id="bcc80-146">Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>    | <span data-ttu-id="bcc80-147">この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="bcc80-147">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:</span></span> <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="bcc80-148">ネットワークとクラウド間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="bcc80-148">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="bcc80-149">上記の URL を許可した後、Microsoft Defender ウイルス対策 クラウド サービスに接続しており、情報を正しく報告および受信して、完全に保護されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-149">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a><span data-ttu-id="bcc80-150">cmdline ツールを使用してクラウド配信の保護を検証する</span><span class="sxs-lookup"><span data-stu-id="bcc80-150">Use the cmdline tool to validate cloud-delivered protection</span></span>

<span data-ttu-id="bcc80-151">次の引数を Microsoft Defender ウイルス対策 コマンド ライン ユーティリティ ( ) と一緒に使用して、ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策 `mpcmdrun.exe` します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-151">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="bcc80-152">管理者レベルのバージョンのコマンド プロンプトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc80-152">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="bcc80-153">[スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcc80-153">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="bcc80-154">このコマンドは、バージョン 1703 Windows 10上でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-154">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="bcc80-155">詳細については、「コマンド ライン ツール[を使用Microsoft Defender ウイルス対策管理mpcmdrun.exeを参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc80-155">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a><span data-ttu-id="bcc80-156">Microsoft から偽のマルウェア ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="bcc80-156">Attempt to download a fake malware file from Microsoft</span></span>

<span data-ttu-id="bcc80-157">クラウドに正しく接続されているMicrosoft Defender ウイルス対策検出およびブロックするサンプル ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-157">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="bcc80-158">にアクセスしてファイルをダウンロードします [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。</span><span class="sxs-lookup"><span data-stu-id="bcc80-158">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="bcc80-159">このファイルは、実際のマルウェアではありません。</span><span class="sxs-lookup"><span data-stu-id="bcc80-159">This file is not an actual piece of malware.</span></span> <span data-ttu-id="bcc80-160">これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。</span><span class="sxs-lookup"><span data-stu-id="bcc80-160">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="bcc80-161">適切に接続されている場合は、警告メッセージが表示Microsoft Defender ウイルス対策表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-161">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="bcc80-162">アプリを使用しているMicrosoft Edge、通知メッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-162">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![Microsoft Edgeが見つかったとユーザーに通知する](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="bcc80-164">次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="bcc80-164">A similar message occurs if you're using Internet Explorer:</span></span>

![Microsoft Defender ウイルス対策が見つかったという通知をユーザーに通知する](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="bcc80-166">また、次のアプリの [スキャン履歴] セクションの [検疫された脅威] の下に検出Windows セキュリティ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcc80-166">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="bcc80-167">タスク バーのWindows セキュリティをクリックするか、スタート メニューの [セキュリティ] を検索して、アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="bcc80-167">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="bcc80-168">[ **ウイルス対策&保護] を選択し**、[保護の履歴] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bcc80-168">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="bcc80-169">[検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcc80-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcc80-170">バージョン 1703 Windows 10以前のバージョンのユーザー インターフェイスは異なります。</span><span class="sxs-lookup"><span data-stu-id="bcc80-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="bcc80-171">[「Microsoft Defender ウイルス対策」を参照Windows セキュリティします](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc80-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="bcc80-172">またWindowsイベント ログには、クライアント[Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc80-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

