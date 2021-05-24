---
title: Microsoft Defender for Endpoint の展開をセットアップする
description: Microsoft Defender for Endpoint の展開をセットアップする方法について説明します。
keywords: 展開、セットアップ、ライセンス検証、テナント構成、ネットワーク構成
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636196"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="1d3a3-104">Microsoft Defender for Endpoint の展開をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1d3a3-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1d3a3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d3a3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d3a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d3a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d3a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d3a3-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="1d3a3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d3a3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1d3a3-110">Defender for Endpoint の展開は、次の 3 フェーズプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="1d3a3-111">[![展開フェーズ - 準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="1d3a3-112">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="1d3a3-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![展開フェーズ - セットアップ](images/phase-diagrams/setup.png)<br><span data-ttu-id="1d3a3-114">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="1d3a3-114">Phase 2: Setup</span></span> | <span data-ttu-id="1d3a3-115">[![展開フェーズ - オンボード](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="1d3a3-116">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="1d3a3-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="1d3a3-117">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="1d3a3-117">*You are here!*</span></span>||

<span data-ttu-id="1d3a3-118">現在、セットアップ フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="1d3a3-119">この展開シナリオでは、次の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="1d3a3-120">ライセンスの検証</span><span class="sxs-lookup"><span data-stu-id="1d3a3-120">Licensing validation</span></span>
- <span data-ttu-id="1d3a3-121">テナント構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-121">Tenant configuration</span></span>
- <span data-ttu-id="1d3a3-122">ネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="1d3a3-123">一般的な展開を案内する目的で、このシナリオでは、このシナリオでは、ユーザーの使用のみをMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="1d3a3-124">Defender for Endpoint は、他のオンボーディング ツールの使用をサポートしていますが、展開ガイドではこれらのシナリオについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="1d3a3-125">詳細については、「デバイスを [Microsoft Defender for Endpoint にオンボードする」を参照してください](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="1d3a3-126">ライセンスの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="1d3a3-126">Check license state</span></span>

<span data-ttu-id="1d3a3-127">ライセンスの状態を確認し、適切にプロビジョニングされたかどうかを確認するには、管理センターまたはポータルMicrosoft Azure **できます**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="1d3a3-128">ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure][セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![[Azure ライセンス] ページのイメージ](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="1d3a3-130">または、管理センターで [課金サブスクリプション]   >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="1d3a3-131">画面に、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![課金ライセンスのイメージ](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="1d3a3-133">クラウド サービス プロバイダーの検証</span><span class="sxs-lookup"><span data-stu-id="1d3a3-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="1d3a3-134">会社にプロビジョニングされるライセンスにアクセスし、ライセンスの状態を確認するには、管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="1d3a3-135">パートナー ポータルで **、[サービス** の管理]**を選択> Office 365。**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="1d3a3-136">[パートナー ポータル]**リンクをクリック** すると、[代理として管理者] オプションが開き、顧客管理センターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![O365 管理ポータルのイメージ](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="1d3a3-138">テナント構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-138">Tenant Configuration</span></span>
<span data-ttu-id="1d3a3-139">エンドポイント用 Microsoft Defender へのオンボーディングは簡単です。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="1d3a3-140">ナビゲーション メニューから、[エンドポイント] セクションの下の任意のアイテムを選択するか、インシデント、ハンティング、アクション センター、脅威分析などの Microsoft 365 Defender 機能を選択してオンボーディング プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="1d3a3-141">Web ブラウザーから、[セキュリティ センター] Microsoft 365[に移動します](https://security.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="1d3a3-142">ネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-142">Network configuration</span></span>
<span data-ttu-id="1d3a3-143">組織がプロキシを使用してインターネットにアクセスするためにエンドポイントを必要としない場合は、このセクションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="1d3a3-144">Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="1d3a3-145">埋め込まれた Microsoft Defender for Endpoint センサーは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="1d3a3-146">センサーは Microsoft Windows HTTP サービス (WinHTTP) を使用して、Microsoft Defender for Endpoint クラウド サービスとの通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="1d3a3-147">WinHTTP 構成設定は、Windows インターネット (WinINet) インターネット閲覧プロキシ設定とは独立し、次の検出方法を使用してのみプロキシ サーバーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="1d3a3-148">**自動検出メソッド:**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="1d3a3-149">透過プロキシ</span><span class="sxs-lookup"><span data-stu-id="1d3a3-149">Transparent proxy</span></span>

-   <span data-ttu-id="1d3a3-150">Web プロキシ自動検出プロトコル (WPAD)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="1d3a3-151">透過プロキシまたは WPAD がネットワーク トポロジに実装されている場合、特別な構成設定は不要です。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="1d3a3-152">プロキシ内の Microsoft Defender for Endpoint URL の除外の[](production-deployment.md#proxy-service-urls)詳細については、このドキュメントの「プロキシ サービス URL の一覧を許可する」または「デバイス プロキシとインターネット接続の設定を構成する」を[参照](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)してください。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="1d3a3-153">**手動の静的プロキシの構成:**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="1d3a3-154">レジストリ ベースの構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-154">Registry-based configuration</span></span>

-   <span data-ttu-id="1d3a3-155">netsh コマンドを使用して構成された WinHTTP</span><span class="sxs-lookup"><span data-stu-id="1d3a3-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="1d3a3-156">安定したトポロジのデスクトップにのみ適しています (たとえば、同じプロキシの背後にある企業ネットワーク内のデスクトップ)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="1d3a3-157">レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="1d3a3-158">コンピューターがインターネットへの接続を許可されていない場合、Microsoft Defender for Endpoint センサーだけが診断データを報告し、Microsoft Defender for Endpoint サービスと通信できるレジストリ ベースの静的プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="1d3a3-159">静的プロキシは、グループ ポリシー (GP) を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="1d3a3-160">グループ ポリシーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="1d3a3-161">管理用Windows コンポーネント データ収集とプレビュー ビルド接続ユーザー エクスペリエンスおよびテレメトリ サービスの認証プロキシの使用 \> \> \> を構成する</span><span class="sxs-lookup"><span data-stu-id="1d3a3-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="1d3a3-162">[有効] に **設定し、[** 認証された **プロキシの使用を無効にする] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="1d3a3-163">グループ ポリシー管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="1d3a3-164">組織のプラクティスに基づいてポリシーを作成するか、既存のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="1d3a3-165">グループ ポリシーを編集し、[管理用テンプレート] Windows コンポーネント データ収集とプレビュー ビルド接続ユーザー エクスペリエンスとテレメトリ サービスの認証プロキシの使用を **\> \> \> 構成します**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="1d3a3-166">![グループ ポリシー構成のイメージ](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="1d3a3-167">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="1d3a3-168">[認証 **されたプロキシの使用を無効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="1d3a3-169">[管理用テンプレート] Windows コンポーネント データ収集とプレビュー ビルド 接続されたユーザー エクスペリエンスとテレメトリを **\> \> \> 構成します**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="1d3a3-170">![グループ ポリシー構成設定のイメージ](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="1d3a3-171">**[有効]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="1d3a3-172">プロキシ サーバー **名を入力します**。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="1d3a3-173">このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="1d3a3-174">レジストリ値は、 `TelemetryProxyServer` 次の文字列形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="1d3a3-175">例: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="1d3a3-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="1d3a3-176">レジストリ値 `DisableEnterpriseAuthProxy` を 1に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="1d3a3-177">netsh コマンドを使用してプロキシ サーバーを手動で構成する</span><span class="sxs-lookup"><span data-stu-id="1d3a3-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="1d3a3-178">netsh を使用して、システム全体の静的プロキシを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="1d3a3-179">これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="1d3a3-180">トポロジを変更しているラップトップ (たとえば、オフィスから自宅) は netsh に誤動作します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="1d3a3-181">レジストリ ベースの静的プロキシの構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="1d3a3-182">管理者特権でコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="1d3a3-183">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="1d3a3-184">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="1d3a3-185">次のコマンドを入力して、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="1d3a3-186">例: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="1d3a3-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="1d3a3-187">ダウンレベル デバイスのプロキシ構成</span><span class="sxs-lookup"><span data-stu-id="1d3a3-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="1d3a3-188">Down-Level には、Windows 7 SP1 および Windows 8.1 ワークステーション、Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2、Windows Server 2016 Windows サーバー CB 1803 より前の Windows Server 2016 のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="1d3a3-189">これらのオペレーティング システムでは、エンドポイントから Azure への通信を処理するために、Microsoft 管理エージェントの一部としてプロキシが構成されます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="1d3a3-190">これらのデバイスでのプロキシの構成方法については、「Microsoft Management Agent Fast Deployment Guide」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="1d3a3-191">プロキシ サービスの URL</span><span class="sxs-lookup"><span data-stu-id="1d3a3-191">Proxy Service URLs</span></span>
<span data-ttu-id="1d3a3-192">v20 を含む URL は、バージョン 1803 以降のデバイスWindows 10場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="1d3a3-193">たとえば、 ```us-v20.events.data.microsoft.com``` デバイスがバージョン 1803 以降Windows 10場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="1d3a3-194">プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合、Microsoft Defender for Endpoint センサーがシステム コンテキストから接続している場合は、一覧の URL で匿名トラフィックが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="1d3a3-195">次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="1d3a3-196">これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールの作成が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="1d3a3-197">**ドメインリストのスプレッドシート**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="1d3a3-198">**説明**</span><span class="sxs-lookup"><span data-stu-id="1d3a3-198">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)<br/>  | <span data-ttu-id="1d3a3-200">サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="1d3a3-201">ここにスプレッドシートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="1d3a3-202">Microsoft Defender for Endpoint Service バックエンド IP 範囲</span><span class="sxs-lookup"><span data-stu-id="1d3a3-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="1d3a3-203">ネットワーク デバイスが DNS ベースのルールをサポートしない場合は、代わりに IP 範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="1d3a3-204">Defender for Endpoint は Azure クラウドに構築され、次の地域に展開されます。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="1d3a3-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="1d3a3-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="1d3a3-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="1d3a3-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="1d3a3-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="1d3a3-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="1d3a3-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="1d3a3-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="1d3a3-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="1d3a3-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="1d3a3-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="1d3a3-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="1d3a3-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="1d3a3-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="1d3a3-212">Azure IP 範囲とサービス タグ – パブリック クラウドで Azure IP 範囲 [を確認できます](https://www.microsoft.com/download/details.aspx?id=56519)。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="1d3a3-213">クラウドベースのソリューションとして、IP アドレス範囲が変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="1d3a3-214">DNS ベースのルールに移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="1d3a3-215">米国政府機関のお客様は、「Defender for Endpoint for US Government」ページの対応 [するセクションを参照](gov.md#service-backend-ip-ranges) してください。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="1d3a3-216">次の手順</span><span class="sxs-lookup"><span data-stu-id="1d3a3-216">Next step</span></span>

<span data-ttu-id="1d3a3-217">![**フェーズ 3: オンボード**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="1d3a3-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="1d3a3-218">[フェーズ 3: オンボード](onboarding.md): Microsoft Defender for Endpoint サービスがセンサー データを取得できるよう、デバイスをサービスにオンボードします。</span><span class="sxs-lookup"><span data-stu-id="1d3a3-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
