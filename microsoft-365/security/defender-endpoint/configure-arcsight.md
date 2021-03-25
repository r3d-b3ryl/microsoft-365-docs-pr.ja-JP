---
title: エンドポイント検出用の Microsoft Defender を取得する Micro Focus ArcSight を構成する
description: Microsoft Defender セキュリティ センターから検出を受信およびプルする Micro Focus ArcSight を構成する
keywords: Micro Focus ArcSight、セキュリティ情報とイベント管理ツール、arcsight を構成する
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166187"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="b7bd7-104">エンドポイント検出用の Defender をプルする Micro Focus ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="b7bd7-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7bd7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b7bd7-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7bd7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7bd7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7bd7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7bd7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="b7bd7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="b7bd7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7bd7-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="b7bd7-110">エンドポイント検出用の Defender を取得するために、Micro Focus ArcSight を使用する一部のファイルとツールをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="b7bd7-111">[Defender for Endpoint Alert](alerts.md) は、1 つ以上の検出から構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="b7bd7-112">[エンドポイント検出の Defender は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b7bd7-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="b7bd7-113">Before you begin</span></span>

<span data-ttu-id="b7bd7-114">Micro Focus ArcSight Connector ツールを構成するには、Azure Active Directory (AAD) アプリケーションから検出をプルして解析するために、いくつかの構成ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="b7bd7-115">このセクションでは、必要な構成ファイルを正しく設定して使用するために必要な情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="b7bd7-116">[設定] メニューから SIEM 統合機能を有効に **してください** 。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="b7bd7-117">詳細については、「Defender [for Endpoint で SIEM 統合を有効にする」を参照してください](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="b7bd7-118">SIEM 統合機能を有効にしたファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="b7bd7-119">次の値を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="b7bd7-120">OAuth 2.0 トークン更新 URL</span><span class="sxs-lookup"><span data-stu-id="b7bd7-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="b7bd7-121">OAuth 2.0 クライアント ID</span><span class="sxs-lookup"><span data-stu-id="b7bd7-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="b7bd7-122">OAuth 2.0 クライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="b7bd7-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="b7bd7-123">次の構成ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="b7bd7-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="b7bd7-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="b7bd7-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="b7bd7-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="b7bd7-126">組織で使用する SIEM の種類として [Micro Focus ArcSight] を選択すると、これら 2 つのファイルを含む .zip ファイルが保存されているはずです。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="b7bd7-127">次のトークンを生成し、準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="b7bd7-128">アクセス トークン</span><span class="sxs-lookup"><span data-stu-id="b7bd7-128">Access token</span></span>
  - <span data-ttu-id="b7bd7-129">refreshtoken</span><span class="sxs-lookup"><span data-stu-id="b7bd7-129">Refresh token</span></span>

  <span data-ttu-id="b7bd7-130">これらのトークンは、ポータルの **SIEM 統合セットアップ** セクションから生成できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="b7bd7-131">Micro Focus ArcSight FlexConnector のインストールと構成</span><span class="sxs-lookup"><span data-stu-id="b7bd7-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="b7bd7-132">次の手順では、「開始する前に」で必要なすべての手順を完了 [したと仮定します](#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="b7bd7-133">最新の 32 ビット Windows FlexConnector インストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="b7bd7-134">この情報は、HPE ソフトウェア センターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="b7bd7-135">ツールは通常、次の既定の場所にインストールされます `C:\Program Files\ArcSightFlexConnectors\current\bin` 。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="b7bd7-136">ツールを保存する場所を選択できます (たとえば、C: \\ \current\bin folder_location\current\bin などfolder_location場所を表します。 </span><span class="sxs-lookup"><span data-stu-id="b7bd7-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="b7bd7-137">インストール ウィザードに従って、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="b7bd7-138">概要</span><span class="sxs-lookup"><span data-stu-id="b7bd7-138">Introduction</span></span>
   - <span data-ttu-id="b7bd7-139">[フォルダーのインストール] を選択する</span><span class="sxs-lookup"><span data-stu-id="b7bd7-139">Choose Install Folder</span></span>
   - <span data-ttu-id="b7bd7-140">[インストール セット] の選択</span><span class="sxs-lookup"><span data-stu-id="b7bd7-140">Choose Install Set</span></span>
   - <span data-ttu-id="b7bd7-141">ショートカット フォルダーの選択</span><span class="sxs-lookup"><span data-stu-id="b7bd7-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="b7bd7-142">インストール前の概要</span><span class="sxs-lookup"><span data-stu-id="b7bd7-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="b7bd7-143">Installing...</span><span class="sxs-lookup"><span data-stu-id="b7bd7-143">Installing...</span></span>

   <span data-ttu-id="b7bd7-144">これらの各タスクの既定値を保持するか、要件に合わせて選択内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="b7bd7-145">エクスプローラーを開き、SIEM 統合機能を有効にした場合に保存した 2 つの構成ファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="b7bd7-146">次に示す 2 つのファイルを FlexConnector のインストール場所に置く。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="b7bd7-147">WDATP-connector.jsonparser.properties: C: folder_location \\ \current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="b7bd7-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="b7bd7-148">WDATP-connector.properties: C: folder_location \\ \current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="b7bd7-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="b7bd7-149">構成ファイルは、この場所に置く必要があります *。folder_locationツールを* インストールした場所を表します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="b7bd7-150">コア コネクタのインストールが完了すると、[コネクタのセットアップ] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="b7bd7-151">[コネクタのセットアップ] ウィンドウで、[コネクタの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="b7bd7-152">[種類: **ArcSight FlexConnector REST] を選択し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="b7bd7-153">パラメーターの詳細フォームに次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="b7bd7-154">フォーム内の他のすべての値は省略可能で、空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="b7bd7-155">フィールド</span><span class="sxs-lookup"><span data-stu-id="b7bd7-155">Field</span></span></th>
    <th><span data-ttu-id="b7bd7-156">値</span><span class="sxs-lookup"><span data-stu-id="b7bd7-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="b7bd7-157">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b7bd7-157">Configuration File</span></span></td>
    <td><span data-ttu-id="b7bd7-158">クライアント プロパティ ファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-158">Type in the name of the client property file.</span></span> <span data-ttu-id="b7bd7-159">名前は、ダウンロードした .zip で指定されたファイルと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="b7bd7-160">たとえば、flexagent ディレクトリの構成ファイルの名前がWDATP-Connector.jsonparser.properties の場合は、クライアント プロパティ ファイルの名前として &quot; &quot; &quot; &quot; &quot; WDATP-Connector と入力 &quot; する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="b7bd7-161">イベント URL</span><span class="sxs-lookup"><span data-stu-id="b7bd7-161">Events URL</span></span></td>
    <td><span data-ttu-id="b7bd7-162">データセンターの場所に応じて、EU または米国の URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="b7bd7-163"><b>EU の</b>場合 : <i></i> https:// wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="b7bd7-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="b7bd7-164"><b>米国の場合:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="b7bd7-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="b7bd7-165"><b>英国 :</b>https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="b7bd7-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="b7bd7-166">認証の種類</span><span class="sxs-lookup"><span data-stu-id="b7bd7-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="b7bd7-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="b7bd7-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="b7bd7-168">OAuth 2 クライアント プロパティ ファイル</span><span class="sxs-lookup"><span data-stu-id="b7bd7-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="b7bd7-169"><em>wdatp-connector.properties ファイルの場所を参照</em>します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="b7bd7-170">名前は、ダウンロードした .zip で指定されたファイルと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="b7bd7-171">更新トークン</span><span class="sxs-lookup"><span data-stu-id="b7bd7-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="b7bd7-172">更新トークンは <b>、SIEM</b> 設定ページから更新トークンを生成するか、restutil ツールを使用する方法の 2 つの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="b7bd7-173">Preferences セットアップから更新トークンを生成する方法<b></b>の詳細については、「Defender for Endpoint で SIEM 統合を有効<a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">にする」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="b7bd7-174"><b>restutil ツールを使用して更新トークンを取得します。</b> </span><span class="sxs-lookup"><span data-stu-id="b7bd7-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="b7bd7-175">a.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-175">a.</span></span> <span data-ttu-id="b7bd7-176">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-176">Open a command prompt.</span></span> <span data-ttu-id="b7bd7-177">ツールをインストールした場所<em>folder_location\current\bin</em>folder_location C:\ に移動します。 <em></em></span><span class="sxs-lookup"><span data-stu-id="b7bd7-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="b7bd7-178">b.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-178">b.</span></span> <span data-ttu-id="b7bd7-179">Type: <code>arcsight restutil token -config</code> from the bin directory.たとえば <b>、arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Web ブラウザー ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="b7bd7-180">c.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-180">c.</span></span> <span data-ttu-id="b7bd7-181">資格情報を入力し、パスワード フィールドをクリックしてページをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="b7bd7-182">ログイン プロンプトで、資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="b7bd7-183">d.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-183">d.</span></span> <span data-ttu-id="b7bd7-184">更新トークンがコマンド プロンプトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="b7bd7-185">e.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-185">e.</span></span> <span data-ttu-id="b7bd7-186">[トークンの更新] フィールドに <b>コピーして貼り付</b> けます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="b7bd7-187">コネクタによってブラウザー ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="b7bd7-188">アプリケーション資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-188">Login with your application credentials.</span></span> <span data-ttu-id="b7bd7-189">ログイン後、OAuth2 クライアントにアクセス許可を与えるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="b7bd7-190">コネクタ構成を認証するには、OAuth 2 クライアントにアクセス許可を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="b7bd7-191">https <code>redirect_uri</code> URL の場合は、ローカル ホスト上の URL にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="b7bd7-192">ローカル ホストで実行されているコネクタによって提供される証明書を信頼する要求をするページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="b7bd7-193">証明書が https の場合は、この証明書redirect_uri必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="b7bd7-194">ただし、証明書の http URL を指定redirect_uri、証明書の信頼に同意する必要はございません。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="b7bd7-195">[Micro Focus ArcSight Connector Setup] ウィンドウに戻って、コネクタのセットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="b7bd7-196">移動先 **として ArcSight Manager (暗号化)** を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="b7bd7-197">[マネージャーのホスト名] に宛先 IP/ホスト名を **入力** し、パラメーター フォームに資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="b7bd7-198">フォーム内の他のすべての値は、既定値と一緒に保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="b7bd7-199">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-199">Click **Next**.</span></span>

11. <span data-ttu-id="b7bd7-200">コネクタの詳細フォームにコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="b7bd7-201">フォーム内の他のすべての値は省略可能で、空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="b7bd7-202">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-202">Click **Next**.</span></span>

12. <span data-ttu-id="b7bd7-203">ESM Manager インポート証明書ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="b7bd7-204">[証明書 **を宛先からコネクタにインポートする] を選択し、[** 次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="b7bd7-205">[ **コネクタの概要の追加]** ウィンドウが表示され、証明書がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="b7bd7-206">[コネクタの概要の追加] ウィンドウの **詳細が正** しいか確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="b7bd7-207">[サービス **としてインストール] を選択し、[** 次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="b7bd7-208">[サービスの内部名] **フィールドに名前を入力** します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="b7bd7-209">フォーム内の他のすべての値は、既定値または空白のままにして保持できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="b7bd7-210">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-210">Click **Next**.</span></span>

16. <span data-ttu-id="b7bd7-211">サービス パラメーターを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="b7bd7-212">[サービスの概要の **インストール] ウィンドウが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="b7bd7-213">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-213">Click **Next**.</span></span>

17. <span data-ttu-id="b7bd7-214">[終了] と [次へ] を **選択してインストール** を **完了します**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="b7bd7-215">Micro Focus ArcSight コンソールのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="b7bd7-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="b7bd7-216">インストール ウィザードに従って、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="b7bd7-217">概要</span><span class="sxs-lookup"><span data-stu-id="b7bd7-217">Introduction</span></span>
   - <span data-ttu-id="b7bd7-218">使用許諾契約書</span><span class="sxs-lookup"><span data-stu-id="b7bd7-218">License Agreement</span></span>
   - <span data-ttu-id="b7bd7-219">特別な通知</span><span class="sxs-lookup"><span data-stu-id="b7bd7-219">Special Notice</span></span>
   - <span data-ttu-id="b7bd7-220">[ArcSight インストール ディレクトリの選択]</span><span class="sxs-lookup"><span data-stu-id="b7bd7-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="b7bd7-221">ショートカット フォルダーの選択</span><span class="sxs-lookup"><span data-stu-id="b7bd7-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="b7bd7-222">インストール前の概要</span><span class="sxs-lookup"><span data-stu-id="b7bd7-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="b7bd7-223">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-223">Click **Install**.</span></span> <span data-ttu-id="b7bd7-224">インストールが完了すると、ArcSight コンソール構成ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="b7bd7-225">[マネージャー のホスト名] **に「localhost」と入力し、[** マネージャー ポート] に「8443」 **と入力し、[次** へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="b7bd7-226">[直接接続 **を使用する] を** 選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="b7bd7-227">[パスワード **ベース認証] を選択** し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="b7bd7-228">[これは **単一のユーザー インストールです] を選択します。(推奨) をクリック** し、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="b7bd7-229">[ **完了] を** クリックしてインストーラーを終了します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="b7bd7-230">Micro Focus ArcSight コンソールにログインします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="b7bd7-231">[アクティブ なチャネル **セット] [**  >  **新しい条件**  >  **デバイスデバイス製品]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="b7bd7-232">デバイス **製品を設定する = Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="b7bd7-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="b7bd7-233">イベントがツールに流れ込むのを確認した場合は、もう一度プロセスを停止して Windows Services に移動し、ArcSight FlexConnector REST を開始します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="b7bd7-234">これで、Micro Focus ArcSight コンソールでクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="b7bd7-235">Defender for Endpoint detections は個別のイベントとして表示され、ベンダーは "Microsoft"、デバイス名は "Windows Defender ATP" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="b7bd7-236">Micro Focus ArcSight 接続のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b7bd7-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="b7bd7-237">**問題:** トークンの更新に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="b7bd7-238">ログは、ツールをインストールした場所をfolder_location \\ \current\logs folder_location C: にあります。 </span><span class="sxs-lookup"><span data-stu-id="b7bd7-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="b7bd7-239">_agent.log を開いて_ 探します `ERROR/FATAL/WARN` 。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="b7bd7-240">**現象:** 次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="b7bd7-241">**解決方法:**</span><span class="sxs-lookup"><span data-stu-id="b7bd7-241">**Solution:**</span></span>

1. <span data-ttu-id="b7bd7-242">[コネクタ] ウィンドウの [Ctrl ] + [C] をクリックして、プロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="b7bd7-243">「 **バッチ ジョブ Y/N** を終了する」というメッセージが表示された場合は、[Y] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="b7bd7-244">WDATP-connector.properties ファイルを保存したフォルダーに移動し、編集して次の値を追加します `reauthenticate=true` 。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="b7bd7-245">次のコマンドを実行してコネクタを再起動します `arcsight.bat connectors` 。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="b7bd7-246">ブラウザー ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-246">A browser window appears.</span></span> <span data-ttu-id="b7bd7-247">実行を許可し、表示されなくなり、コネクタが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="b7bd7-248">もう一度プロセスを停止して、コネクタが実行されている状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="b7bd7-249">次に、コネクタを再度起動すると、ブラウザー ウィンドウは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b7bd7-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7bd7-250">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7bd7-250">Related topics</span></span>
- [<span data-ttu-id="b7bd7-251">Defender for Endpoint で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="b7bd7-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="b7bd7-252">SIEM ツールへの検出のプル</span><span class="sxs-lookup"><span data-stu-id="b7bd7-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="b7bd7-253">REST API を使用したエンドポイント検出用の Defender のプル</span><span class="sxs-lookup"><span data-stu-id="b7bd7-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="b7bd7-254">SIEM ツールの統合に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b7bd7-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
