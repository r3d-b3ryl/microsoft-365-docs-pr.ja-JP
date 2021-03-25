---
title: ライブ応答を使用して Microsoft Defender for Endpoints のサポート ログを収集する
description: ライブ応答を使用してログを収集し、Microsoft Defender for Endpoints の問題のトラブルシューティングを行う方法について説明します。
keywords: サポート、ログ、収集、トラブルシューティング、ライブ応答、liveanalyzer、アナライザー、ライブ、応答
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8b7fe8f0973cabfb5f5268be28ac606dfc4c6387
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183719"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="25ca2-104">ライブ応答を使用して Microsoft Defender for Endpoint のサポート ログを収集する</span><span class="sxs-lookup"><span data-stu-id="25ca2-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="25ca2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25ca2-105">**Applies to:**</span></span>
- [<span data-ttu-id="25ca2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25ca2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25ca2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25ca2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="25ca2-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="25ca2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25ca2-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="25ca2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="25ca2-110">サポートに連絡する場合は、Microsoft Defender for Endpoint Client Analyzer ツールの出力パッケージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ca2-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="25ca2-111">このトピックでは、Live Response を使用してツールを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="25ca2-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="25ca2-112">適切なスクリプトをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="25ca2-112">Download the appropriate script</span></span>
    * <span data-ttu-id="25ca2-113">Microsoft Defender for Endpoint クライアント センサー ログのみ:LiveAnalyzer.ps1 [ スクリプト](https://aka.ms/MDELiveAnalyzer)です。</span><span class="sxs-lookup"><span data-stu-id="25ca2-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="25ca2-114">結果パッケージの概算サイズ: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="25ca2-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="25ca2-115">Microsoft Defender for Endpoint クライアント センサーとウイルス対策ログ: [LiveAnalyzer+MDAV.ps1 スクリプト](https://aka.ms/MDELiveAnalyzerAV)です。</span><span class="sxs-lookup"><span data-stu-id="25ca2-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="25ca2-116">結果パッケージの概算サイズ: ~10 Mb</span><span class="sxs-lookup"><span data-stu-id="25ca2-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="25ca2-117">調査する [必要があるコンピューターで](live-response.md#initiate-a-live-response-session-on-a-device) ライブ応答セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="25ca2-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="25ca2-118">[ライブラリ **にファイルをアップロードする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25ca2-118">Select **Upload file to library**.</span></span>

    ![アップロード ファイルのイメージ](images/upload-file.png)

4. <span data-ttu-id="25ca2-120">[ファイル **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25ca2-120">Select **Choose file**.</span></span>

    ![ファイルの選択ボタン 1 のイメージ](images/choose-file.png)

5. <span data-ttu-id="25ca2-122">[ファイル] という名前のダウンロードしたMDELiveAnalyzer.ps1を選択し、[確認] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="25ca2-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![ファイルの選択ボタン 2 のイメージ](images/analyzer-file.png)


6. <span data-ttu-id="25ca2-124">LiveResponse セッション中は、次のコマンドを使用してアナライザーを実行し、結果ファイルを収集します。</span><span class="sxs-lookup"><span data-stu-id="25ca2-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![コマンドのイメージ](images/analyzer-commands.png)


>[!NOTE]
> - <span data-ttu-id="25ca2-126">MDEClientAnalyzer の最新のプレビュー バージョンは、次の場所からダウンロードできます [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) 。</span><span class="sxs-lookup"><span data-stu-id="25ca2-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="25ca2-127">LiveAnalyzer スクリプトは、次のファイルからトラブルシューティング パッケージをダウンロードします https://mdatpclientanalyzer.blob.core.windows.net 。</span><span class="sxs-lookup"><span data-stu-id="25ca2-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="25ca2-128">コンピューターが上記の URL に到達できない場合は、LiveAnalyzer スクリプトを実行する前にMDEClientAnalyzerPreview.zipファイルをライブラリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="25ca2-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="25ca2-129">コンピューターが Microsoft Defender for Endpoint クラウド サービスと通信していない場合、または Microsoft Defender for Endpoint ポータルに予期した通り表示されない場合に、コンピューターでローカルにデータを収集する方法の詳細については、「Verify client [connectivity to Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)service URL」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25ca2-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls).</span></span>
