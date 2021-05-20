---
title: Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する
description: Microsoft Defender ウイルス対策クラウド保護サービスへの接続を構成し、テストします。
keywords: ウイルス対策, Microsoft Defender ウイルス対策, マルウェア対策, セキュリティ, 防御者, クラウド, 攻撃性, 保護レベル
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572527"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a><span data-ttu-id="baf0d-104">Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="baf0d-104">Configure and validate Microsoft Defender Antivirus network connections</span></span>

<span data-ttu-id="baf0d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="baf0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="baf0d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="baf0d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="baf0d-107">クラウドで提供される保護Microsoft Defender ウイルス対策正常に機能させるには、エンドポイントと特定の Microsoft サーバー間の接続を許可するようにネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-107">To ensure Microsoft Defender Antivirus cloud-delivered protection works properly, you need to configure your network to allow connections between your endpoints and certain Microsoft servers.</span></span> <span data-ttu-id="baf0d-108">この資料では、ファイアウォール規則を使用するなどして許可する必要がある接続の一覧と、接続を検証する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-108">This article lists the connections that must be allowed, such as by using firewall rules, and provides instructions for validating your connection.</span></span> <span data-ttu-id="baf0d-109">保護を適切に構成することで、クラウドで提供される保護サービスから最高の価値を得られるようになります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-109">Configuring your protection properly helps ensure that you receive the best value from your cloud-delivered protection services.</span></span>

<span data-ttu-id="baf0d-110">ネットワーク接続の詳細については、ブログの投稿 [Microsoft アクティブ プロテクション サービス エンドポイントへの重要な変更](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf0d-110">See the blog post [Important changes to Microsoft Active Protection Services endpoint](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) for some details about network connectivity.</span></span>

> [!TIP]
> <span data-ttu-id="baf0d-111">また [、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) の Microsoft Defender for Endpoint デモ Web サイトにアクセスして、次の機能が機能していることを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-111">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
>
> - <span data-ttu-id="baf0d-112">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="baf0d-112">Cloud-delivered protection</span></span>
> - <span data-ttu-id="baf0d-113">高速学習(一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="baf0d-113">Fast learning (including block at first sight)</span></span>
> - <span data-ttu-id="baf0d-114">望ましくない可能性のあるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="baf0d-114">Potentially unwanted application blocking</span></span>

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a><span data-ttu-id="baf0d-115">Microsoft Defender ウイルス対策 クラウド サービスへの接続を許可する</span><span class="sxs-lookup"><span data-stu-id="baf0d-115">Allow connections to the Microsoft Defender Antivirus cloud service</span></span>

<span data-ttu-id="baf0d-116">Microsoft Defender ウイルス対策 クラウド サービスは、エンドポイントに対して高速で強力な保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-116">The Microsoft Defender Antivirus cloud service provides fast, strong protection for your endpoints.</span></span> <span data-ttu-id="baf0d-117">クラウド配信の保護サービスを有効にすることはオプションですが、エンドポイントやネットワーク全体でマルウェアに対する重要な保護を提供するため、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="baf0d-117">Enabling the cloud-delivered protection service is optional, however it's highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

> [!NOTE]
> <span data-ttu-id="baf0d-118">Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに最新の保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="baf0d-118">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="baf0d-119">クラウド サービスと呼ばれますが、クラウドに格納されているファイルを保護するだけではなく、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンスの更新よりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-119">Although it's called a cloud service, it's not simply protection for files stored in the cloud, rather it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="baf0d-120">Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、またはWindows セキュリティ アプリの個々のクライアントでサービスを有効にする方法の詳細については、「[クラウド配信保護を有効](enable-cloud-protection-microsoft-defender-antivirus.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf0d-120">See [Enable cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) for details on enabling the service with Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, or on individual clients in the Windows Security app.</span></span> 

<span data-ttu-id="baf0d-121">サービスを有効にした後、ネットワークまたはファイアウォールを構成して、サービスとエンドポイントとの間の接続を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-121">After you've enabled the service, you may need to configure your network or firewall to allow connections between it and your endpoints.</span></span>

<span data-ttu-id="baf0d-122">保護はクラウド サービスであるため、コンピューターはインターネットにアクセスでき、機械学習サービスをOffice 365するために Microsoft Defender にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-122">Because your protection is a cloud service, computers must have access to the internet and reach the Microsoft Defender for Office 365 machine learning services.</span></span> <span data-ttu-id="baf0d-123">ネットワーク検査の種類から URL を除外しないでください `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="baf0d-123">Don't exclude the URL `*.blob.core.windows.net` from any kind of network inspection.</span></span> 

<span data-ttu-id="baf0d-124">次の表に、サービスと関連付けられた URL を示します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-124">The table below lists the services and their associated URLs.</span></span> <span data-ttu-id="baf0d-125">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルタリング ルールがないことを確認するか、または URL を除く許可ルールを作成する必要がある場合があります `*.blob.core.windows.net` 。</span><span class="sxs-lookup"><span data-stu-id="baf0d-125">Make sure that there are no firewall or network filtering rules denying access to these URLs, or you may need to create an allow rule specifically for them (excluding the URL `*.blob.core.windows.net`).</span></span> <span data-ttu-id="baf0d-126">以下の URL は通信にポート 443 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="baf0d-126">Below mention URLs are using port 443 for communication.</span></span>


| <span data-ttu-id="baf0d-127">**サービス**</span><span class="sxs-lookup"><span data-stu-id="baf0d-127">**Service**</span></span>| <span data-ttu-id="baf0d-128">**説明**</span><span class="sxs-lookup"><span data-stu-id="baf0d-128">**Description**</span></span> |<span data-ttu-id="baf0d-129">**URL**</span><span class="sxs-lookup"><span data-stu-id="baf0d-129">**URL**</span></span> |
| :--: | :-- | :-- |
| <span data-ttu-id="baf0d-130">Microsoft Defender ウイルス対策クラウド提供の保護サービス(Microsoft Active Protection Serviceとも呼ばれる)(MAPS)</span><span class="sxs-lookup"><span data-stu-id="baf0d-130">Microsoft Defender Antivirus cloud-delivered protection service, also referred to as Microsoft Active Protection Service (MAPS)</span></span>|<span data-ttu-id="baf0d-131">クラウドで提供される保護を提供するためにMicrosoft Defender ウイルス対策で使用</span><span class="sxs-lookup"><span data-stu-id="baf0d-131">Used by Microsoft Defender Antivirus to provide cloud-delivered protection</span></span>|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| <span data-ttu-id="baf0d-132">マイクロソフトアップデートサービス (MU)</span><span class="sxs-lookup"><span data-stu-id="baf0d-132">Microsoft Update Service (MU)</span></span> <br/> <span data-ttu-id="baf0d-133">Windows更新サービス (WU)</span><span class="sxs-lookup"><span data-stu-id="baf0d-133">Windows Update Service (WU)</span></span>|  <span data-ttu-id="baf0d-134">セキュリティ インテリジェンスと製品の更新</span><span class="sxs-lookup"><span data-stu-id="baf0d-134">Security intelligence and product updates</span></span>   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> <span data-ttu-id="baf0d-135">詳細については[、「Windows更新の接続エンドポイント」を](/windows/privacy/manage-windows-1709-endpoints#windows-update)参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf0d-135">For details see [Connection endpoints for Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)</span></span>|
|<span data-ttu-id="baf0d-136">セキュリティ インテリジェンス更新プログラム代替ダウンロード場所 (ADL)</span><span class="sxs-lookup"><span data-stu-id="baf0d-136">Security intelligence updates Alternate Download Location (ADL)</span></span>|   <span data-ttu-id="baf0d-137">Microsoft Defender ウイルス対策 セキュリティ インテリジェンスの更新プログラムがインストールされていない場合 (7 日以上遅れている) セキュリティ インテリジェンスの更新プログラムの別の場所</span><span class="sxs-lookup"><span data-stu-id="baf0d-137">Alternate location for Microsoft Defender Antivirus Security intelligence updates if the installed Security intelligence is out of date (7 or more days behind)</span></span>|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| <span data-ttu-id="baf0d-138">マルウェアの提出ストレージ</span><span class="sxs-lookup"><span data-stu-id="baf0d-138">Malware submission storage</span></span>|<span data-ttu-id="baf0d-139">提出書類または自動サンプル提出を介して Microsoft に送信されるファイルの場所をアップロード</span><span class="sxs-lookup"><span data-stu-id="baf0d-139">Upload location for files submitted to Microsoft via the Submission form or automatic sample submission</span></span>    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| <span data-ttu-id="baf0d-140">証明書失効リスト (CRL)</span><span class="sxs-lookup"><span data-stu-id="baf0d-140">Certificate Revocation List (CRL)</span></span>|<span data-ttu-id="baf0d-141">CRL を更新するために MAPS への SSL 接続を作成する際にWindowsによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-141">Used by Windows when creating the SSL connection to MAPS for updating the CRL</span></span>   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| <span data-ttu-id="baf0d-142">シンボルストア</span><span class="sxs-lookup"><span data-stu-id="baf0d-142">Symbol Store</span></span>|<span data-ttu-id="baf0d-143">修復フロー中に特定の重要なファイルを復元するためにMicrosoft Defender ウイルス対策によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-143">Used by Microsoft Defender Antivirus to restore certain critical files during remediation flows</span></span>  | `https://msdl.microsoft.com/download/symbols` |
| <span data-ttu-id="baf0d-144">ユニバーサル テレメトリ クライアント</span><span class="sxs-lookup"><span data-stu-id="baf0d-144">Universal Telemetry Client</span></span>| <span data-ttu-id="baf0d-145">クライアント診断データを送信するためにWindowsによって使用されます。Microsoft Defender ウイルス対策製品品質監視の目的でテレメトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-145">Used by Windows to send client diagnostic data; Microsoft Defender Antivirus uses telemetry for product quality monitoring purposes</span></span>   | <span data-ttu-id="baf0d-146">この更新プログラムでは、SSL (TCP ポート 443) を使用してマニフェストをダウンロードし、次の DNS エンドポイントを使用する診断データを Microsoft にアップロードします。   `vortex-win.data.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="baf0d-146">The update uses SSL (TCP Port 443) to download manifests and upload diagnostic data to Microsoft that uses the following DNS endpoints:   `vortex-win.data.microsoft.com`</span></span> <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a><span data-ttu-id="baf0d-147">ネットワークとクラウド間の接続を検証する</span><span class="sxs-lookup"><span data-stu-id="baf0d-147">Validate connections between your network and the cloud</span></span>

<span data-ttu-id="baf0d-148">上記の URL を許可した後、Microsoft Defender ウイルス対策クラウド サービスに接続しており、情報を正しく報告および受信しているかどうかをテストして、完全に保護されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-148">After allowing the URLs listed above, you can test if you're connected to the Microsoft Defender Antivirus cloud service and are correctly reporting and receiving information to ensure you're fully protected.</span></span>

<span data-ttu-id="baf0d-149">**cmdline ツールを使用して、クラウドで提供される保護を検証します。**</span><span class="sxs-lookup"><span data-stu-id="baf0d-149">**Use the cmdline tool to validate cloud-delivered protection:**</span></span>

<span data-ttu-id="baf0d-150">Microsoft Defender ウイルス対策 コマンドライン ユーティリティ ( ) と共に次の引数 `mpcmdrun.exe` を使用して、ネットワークがMicrosoft Defender ウイルス対策 クラウド サービスと通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-150">Use the following argument with the Microsoft Defender Antivirus command-line utility (`mpcmdrun.exe`) to verify that your network can communicate with the Microsoft Defender Antivirus cloud service:</span></span>

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> <span data-ttu-id="baf0d-151">コマンド プロンプトの管理者レベルのバージョンを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-151">You need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="baf0d-152">[スタート] メニューの項目を右クリックし、[ **管理者として実行** ] をクリックして、アクセス許可のプロンプトで **[はい** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf0d-152">Right-click the item in the Start menu, click **Run as administrator** and click **Yes** at the permissions prompt.</span></span> <span data-ttu-id="baf0d-153">このコマンドは、バージョン 1703 以上のWindows 10でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-153">This command will only work on Windows 10, version 1703 or higher.</span></span>

<span data-ttu-id="baf0d-154">詳細については、「 [mpcmdrun.exe コマンド ライン ツールを使用したMicrosoft Defender ウイルス対策の管理](command-line-arguments-microsoft-defender-antivirus.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf0d-154">For more information, see [Manage Microsoft Defender Antivirus with the mpcmdrun.exe commandline tool](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="baf0d-155">**マイクロソフトから偽のマルウェア ファイルをダウンロードしよう:**</span><span class="sxs-lookup"><span data-stu-id="baf0d-155">**Attempt to download a fake malware file from Microsoft:**</span></span>

<span data-ttu-id="baf0d-156">クラウドに正しく接続している場合Microsoft Defender ウイルス対策検出してブロックするサンプル ファイルをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-156">You can download a sample file that Microsoft Defender Antivirus will detect and block if you're properly connected to the cloud.</span></span>

<span data-ttu-id="baf0d-157">にアクセスしてファイルをダウンロード [https://aka.ms/ioavtest](https://aka.ms/ioavtest) します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-157">Download the file by visiting [https://aka.ms/ioavtest](https://aka.ms/ioavtest).</span></span>

> [!NOTE]
> <span data-ttu-id="baf0d-158">このファイルは実際のマルウェアではありません。</span><span class="sxs-lookup"><span data-stu-id="baf0d-158">This file is not an actual piece of malware.</span></span> <span data-ttu-id="baf0d-159">これは、クラウドに適切に接続しているかどうかをテストするために設計された偽のファイルです。</span><span class="sxs-lookup"><span data-stu-id="baf0d-159">It's a fake file that is designed to test if you're properly connected to the cloud.</span></span>

<span data-ttu-id="baf0d-160">正しく接続している場合は、警告Microsoft Defender ウイルス対策通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-160">If you're properly connected, you'll see a warning Microsoft Defender Antivirus notification.</span></span>

<span data-ttu-id="baf0d-161">Microsoft Edgeを使用している場合は、通知メッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-161">If you're using Microsoft Edge, you'll also see a notification message:</span></span>

![マルウェアが検出されたことをユーザーに知らせるMicrosoft Edge](images/defender/wdav-bafs-edge.png)

<span data-ttu-id="baf0d-163">Internet Explorer を使用している場合も同様のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-163">A similar message occurs if you're using Internet Explorer:</span></span>

![マルウェアが検出されたことをユーザーに通知するMicrosoft Defender ウイルス対策通知](images/defender/wdav-bafs-ie.png)

<span data-ttu-id="baf0d-165">また、Windows セキュリティ アプリの [**スキャン履歴**] セクションの [**検疫された脅威**] にも検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-165">You'll also see a detection under **Quarantined threats** in the **Scan history** section in the Windows Security app:</span></span>

1. <span data-ttu-id="baf0d-166">タスク バーの盾アイコンをクリックするか、または [**セキュリティ**] の [スタート] メニューを検索して、Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-166">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="baf0d-167">[ **ウイルス&脅威対策**] を選択し、[ **保護履歴**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-167">Select **Virus & threat protection**, and then select **Protection history**.</span></span>

3. <span data-ttu-id="baf0d-168">[ **検疫された脅威** ] セクションで、[ **完全な履歴を表示]** を選択して、検出された偽のマルウェアを確認します。</span><span class="sxs-lookup"><span data-stu-id="baf0d-168">Under the **Quarantined threats** section, select **See full history** to see the detected fake malware.</span></span>

   > [!NOTE]
   > <span data-ttu-id="baf0d-169">バージョン 1703 より前のWindows 10のバージョンには、異なるユーザー・インターフェースがあります。</span><span class="sxs-lookup"><span data-stu-id="baf0d-169">Versions of Windows 10 before version 1703 have a different user interface.</span></span> <span data-ttu-id="baf0d-170">[Windows セキュリティアプリのMicrosoft Defender ウイルス対策を](microsoft-defender-security-center-antivirus.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf0d-170">See [Microsoft Defender Antivirus in the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

   <span data-ttu-id="baf0d-171">Windows イベント ログには、[クライアント イベント ID 1116 Windows Defender](troubleshoot-microsoft-defender-antivirus.md)も記録されます。</span><span class="sxs-lookup"><span data-stu-id="baf0d-171">The Windows event log will also show [Windows Defender client event ID 1116](troubleshoot-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="baf0d-172">関連記事</span><span class="sxs-lookup"><span data-stu-id="baf0d-172">Related articles</span></span>

- [<span data-ttu-id="baf0d-173">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="baf0d-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="baf0d-174">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="baf0d-174">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="baf0d-175">コマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="baf0d-175">Command line arguments</span></span>](command-line-arguments-microsoft-defender-antivirus.md)

- [<span data-ttu-id="baf0d-176">マイクロソフトアクティブプロテクションサービスエンドポイントに対する重要な変更</span><span class="sxs-lookup"><span data-stu-id="baf0d-176">Important changes to Microsoft Active Protection Services endpoint</span></span>](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
