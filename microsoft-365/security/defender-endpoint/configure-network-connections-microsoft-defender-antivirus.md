---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策クラウド保護サービスへの接続を構成およびテストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, Defender, クラウド, 攻撃性, 保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5a6b2ce77d6018cb07a1af389b5226b57e2f7427
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691431"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="1163c-104">Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="1163c-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1163c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1163c-105">**Applies to:**</span></span>

- [<span data-ttu-id="1163c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1163c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1163c-107">Microsoft Defender ウイルス対策クラウド配信保護が適切に機能するには、エンドポイントと特定の Microsoft サーバー間の接続を許可するネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1163c-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span>

<span data-ttu-id="1163c-108">この記事では、ファイアウォール ルールの使用など、許可する必要がある接続の一覧と、接続の検証手順を示します。</span><span class="sxs-lookup"><span data-stu-id="1163c-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="1163c-109">保護を適切に構成すると、クラウド配信の保護サービスから最高の価値を確実に受け取るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1163c-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="1163c-110">ネットワーク接続の詳細については [、「Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) エンドポイントの重要な変更点」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1163c-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

>[!TIP]
><span data-ttu-id="1163c-111">Microsoft Defender for Endpoint のデモ Web サイトにアクセス [して、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能が動作しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1163c-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
>- <span data-ttu-id="1163c-112">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="1163c-112">Cloud-delivered protection</span></span>
>- <span data-ttu-id="1163c-113">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="1163c-113">Fast learning (including block at first sight)</span></span>
>- <span data-ttu-id="1163c-114">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="1163c-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="1163c-115">Microsoft Defender ウイルス対策クラウド サービスへの接続を許可する</span><span class="sxs-lookup"><span data-stu-id="1163c-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="1163c-116">Microsoft Defender ウイルス対策クラウド サービスは、エンドポイントに高速で強力な保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="1163c-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="1163c-117">クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1163c-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

>[!NOTE]
><span data-ttu-id="1163c-118">Microsoft Defender ウイルス対策クラウド サービスは、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="1163c-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="1163c-119">クラウド サービスと呼ばれるのはクラウド サービスですが、クラウドに保存されているファイルの保護ではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="1163c-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="1163c-120">[Intune、Microsoft](enable-cloud-protection-microsoft-defender-antivirus.md) Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、または Windows セキュリティ アプリの個々のクライアントでサービスを有効にする方法の詳細については、「クラウドによる保護を有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1163c-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="1163c-121">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の接続を許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1163c-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="1163c-122">保護はクラウド サービスなので、コンピューターはインターネットにアクセスし、365 機械学習サービスを利用Office Microsoft Defender にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1163c-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="1163c-123">任意の種類のネットワーク 検査から URL `*.blob.core.windows.net` を除外しない。</span><span class="sxs-lookup"><span data-stu-id="1163c-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="1163c-124">次の表に、サービスと関連付けられている URL の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1163c-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="1163c-125">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、または(URL を除く) 許可ルールを作成する必要がある場合があります `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="1163c-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="1163c-126">以下に示す URL は、通信にポート 443 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1163c-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="1163c-127">**サービス**</span><span class="sxs-lookup"><span data-stu-id="1163c-127">**Service**</span></span>| <span data-ttu-id="1163c-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="1163c-128">**Description**</span></span> |<span data-ttu-id="1163c-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="1163c-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="1163c-130">Microsoft Defender ウイルス対策クラウド配信保護サービス (MICROSOFT Active Protection Service (MAPS) とも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="1163c-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="1163c-131">Microsoft Defender ウイルス対策によってクラウド配信の保護を提供するために使用される</span><span class="sxs-lookup"><span data-stu-id="1163c-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="1163c-132">Microsoft Update Service (MU)</span><span class="sxs-lookup"><span data-stu-id="1163c-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="1163c-133">Windows Update Service (WU)</span><span class="sxs-lookup"><span data-stu-id="1163c-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="1163c-134">セキュリティ インテリジェンスと製品の更新</span><span class="sxs-lookup"><span data-stu-id="1163c-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="1163c-135">詳細については [、「Windows Update の接続エンドポイント」を参照してください。](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span><span class="sxs-lookup"><span data-stu-id="1163c-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="1163c-136">セキュリティ インテリジェンスの更新代替ダウンロード場所 (ADL)</span><span class="sxs-lookup"><span data-stu-id="1163c-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="1163c-137">Microsoft Defender ウイルス対策セキュリティ インテリジェンスの更新プログラムの別の場所 (インストールされているセキュリティ インテリジェンスが最新でなされていない場合 )(7 日以上遅れる)</span><span class="sxs-lookup"><span data-stu-id="1163c-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="1163c-138">マルウェアの送信ストレージ</span><span class="sxs-lookup"><span data-stu-id="1163c-138">Malware submission storage</span></span>|<span data-ttu-id="1163c-139">申請フォームまたは自動サンプル送信を介して Microsoft に送信されたファイルのアップロード場所</span><span class="sxs-lookup"><span data-stu-id="1163c-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="1163c-140">証明書失効リスト (CRL)</span><span class="sxs-lookup"><span data-stu-id="1163c-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="1163c-141">CRL を更新するために MAPS への SSL 接続を作成するときに Windows で使用される</span><span class="sxs-lookup"><span data-stu-id="1163c-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="1163c-142">シンボル ストア</span><span class="sxs-lookup"><span data-stu-id="1163c-142">Symbol Store</span></span>|<span data-ttu-id="1163c-143">修復フロー中に特定の重要なファイルを復元するために Microsoft Defender ウイルス対策によって使用される</span><span class="sxs-lookup"><span data-stu-id="1163c-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="1163c-144">ユニバーサル テレメトリ クライアント</span><span class="sxs-lookup"><span data-stu-id="1163c-144">Universal Telemetry Client</span></span>| <span data-ttu-id="1163c-145">Windows がクライアント診断データを送信するために使用します。Microsoft Defender ウイルス対策は、製品品質の監視の目的で利用統計情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="1163c-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="1163c-146">この更新プログラムは SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="1163c-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="1163c-147">ネットワークとクラウド間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="1163c-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="1163c-148">上記の URL を許可した後、Microsoft Defender Antivirus クラウド サービスに接続しており、情報を正しく報告および受信して、完全に保護されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1163c-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="1163c-149">**cmdline ツールを使用して、クラウド配信の保護を検証します。**</span><span class="sxs-lookup"><span data-stu-id="1163c-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="1163c-150">Microsoft Defender ウイルス対策コマンド ライン ユーティリティ ( ) で次の引数を使用して、ネットワークが Microsoft Defender ウイルス対策クラウド サービスと通信できると `mpcmdrun.exe` 確認します。</span><span class="sxs-lookup"><span data-stu-id="1163c-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="1163c-151">管理者レベルのバージョンのコマンド プロンプトを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="1163c-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="1163c-152">[スタート] メニューのアイテムを右クリックし、[管理者として実行] をクリック **し、アクセス** 許可のプロンプト **で [は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1163c-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="1163c-153">このコマンドは、Windows 10 バージョン 1703 以上でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="1163c-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="1163c-154">詳細については、「Microsoft Defender Antivirus with the mpcmdrun.exe コマンド ライン [ツール」を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="1163c-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1163c-155">**Microsoft から偽のマルウェア ファイルをダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="1163c-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="1163c-156">クラウドに適切に接続されている場合、Microsoft Defender Antivirus が検出してブロックするサンプル ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="1163c-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="1163c-157">にアクセスしてファイルをダウンロードします [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 。</span><span class="sxs-lookup"><span data-stu-id="1163c-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

>[!NOTE]
><span data-ttu-id="1163c-158">このファイルは、実際のマルウェアではありません。</span><span class="sxs-lookup"><span data-stu-id="1163c-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="1163c-159">これは、クラウドに適切に接続されている場合にテストするように設計された偽のファイルです。</span><span class="sxs-lookup"><span data-stu-id="1163c-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="1163c-160">適切に接続されている場合は、警告の Microsoft Defender ウイルス対策通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1163c-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="1163c-161">Microsoft Edge を使用している場合は、次の通知メッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1163c-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![マルウェアが見つかったとユーザーに通知する Microsoft Edge](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="1163c-163">次のようなメッセージが表示されます。次のコマンドを使用Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="1163c-163">A similar message occurs if you're using Internet Explorer:</span></span>

![マルウェアが見つかったとユーザーに通知する Microsoft Defender ウイルス対策通知](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="1163c-165">また、Windows セキュリティ アプリの[スキャン履歴]セクションの [検疫された脅威] の下に検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1163c-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="1163c-166">タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="1163c-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="1163c-167">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[スキャン履歴] **ラベルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="1163c-167">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Scan history** label:</span></span>

    ![Windows セキュリティ アプリのスキャン履歴ラベルのスクリーンショット](images/defender/wdav-history-wdsc.png)

3. <span data-ttu-id="1163c-169">[検疫された **脅威] セクションで** 、[完全な履歴を **表示** ] を選択して、検出された偽のマルウェアを確認します。</span><span class="sxs-lookup"><span data-stu-id="1163c-169">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1163c-170">バージョン 1703 より前のバージョンの Windows 10 では、ユーザー インターフェイスが異なります。</span><span class="sxs-lookup"><span data-stu-id="1163c-170">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="1163c-171">Windows セキュリティ [アプリで Microsoft Defender ウイルス対策を参照してください](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="1163c-171">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="1163c-172">Windows イベント ログには、クライアント [Windows Defender ID 1116 も表示されます](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="1163c-172">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="1163c-173">関連記事</span><span class="sxs-lookup"><span data-stu-id="1163c-173">Related articles</span></span>

- [<span data-ttu-id="1163c-174">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="1163c-174">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="1163c-175">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="1163c-175">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="1163c-176">コマンド ラインの引数</span><span class="sxs-lookup"><span data-stu-id="1163c-176">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="1163c-177">Microsoft Active Protection Services エンドポイントの重要な変更点</span><span class="sxs-lookup"><span data-stu-id="1163c-177">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)