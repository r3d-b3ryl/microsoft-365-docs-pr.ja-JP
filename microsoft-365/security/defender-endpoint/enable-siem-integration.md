---
title: エンドポイント向け Microsoft Defender で SIEM 統合を有効にする
description: SIEM 統合を有効にして、セキュリティ情報とイベント管理 (SIEM) ソリューションで検出を受け取る。
keywords: SIEM コネクタ、SIEM、コネクタ、セキュリティ情報、イベントを有効にする
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
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068204"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6f97d-104">エンドポイント向け Microsoft Defender で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="6f97d-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f97d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6f97d-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f97d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f97d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="6f97d-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6f97d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6f97d-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6f97d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="6f97d-109">セキュリティ情報とイベント管理 (SIEM) 統合を有効にして、Microsoft Defender セキュリティ センターから検出を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="6f97d-110">SIEM ソリューションを使用するか、検出 REST API に直接接続して検出をプルします。</span><span class="sxs-lookup"><span data-stu-id="6f97d-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="6f97d-111">[Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="6f97d-112">[Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="6f97d-113">Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。</span><span class="sxs-lookup"><span data-stu-id="6f97d-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="6f97d-114">詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="6f97d-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f97d-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="6f97d-115">Prerequisites</span></span>

- <span data-ttu-id="6f97d-116">この設定をアクティブ化するユーザーには、Azure Active Directory (AAD) でアプリを作成するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6f97d-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="6f97d-117">これは、次の役割を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6f97d-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="6f97d-118">セキュリティ管理者とグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="6f97d-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="6f97d-119">クラウド アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="6f97d-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="6f97d-120">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="6f97d-120">Application Administrator</span></span>
  - <span data-ttu-id="6f97d-121">サービス プリンシパルの所有者</span><span class="sxs-lookup"><span data-stu-id="6f97d-121">Owner of the service principal</span></span>

- <span data-ttu-id="6f97d-122">最初のライセンス認証中に、資格情報を入力するためのポップアップ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="6f97d-123">このサイトのポップアップを許可してください。</span><span class="sxs-lookup"><span data-stu-id="6f97d-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="6f97d-124">SIEM 統合の有効化</span><span class="sxs-lookup"><span data-stu-id="6f97d-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="6f97d-125">ナビゲーション ウィンドウで、[設定 SIEM]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6f97d-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![[設定] メニュー 1 からの SIEM 統合のイメージ](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="6f97d-127">SIEM コネクタ アプリケーションを有効にしようとするときにエラーが発生した場合は、ブラウザーのポップアップ ブロッカー設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f97d-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="6f97d-128">機能を有効にするときに開いている新しいウィンドウがブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f97d-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="6f97d-129">[SIEM **統合を有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6f97d-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="6f97d-130">これにより、値が事前に入力された **SIEM** コネクタ アクセスの詳細セクションがアクティブ化され、アプリケーションが Azure Active Directory (Azure Active Directory) テナントのADされます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="6f97d-131">クライアント シークレットは 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-131">The client secret is only displayed once.</span></span> <span data-ttu-id="6f97d-132">コピーを安全な場所に保管してください。</span><span class="sxs-lookup"><span data-stu-id="6f97d-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![[設定] メニュー 2 からの SIEM 統合のイメージ](images/siem_details.png)

3. <span data-ttu-id="6f97d-134">組織で使用する SIEM の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f97d-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6f97d-135">[HP ArcSight] を選択した場合は、次の 2 つの構成ファイルを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f97d-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="6f97d-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="6f97d-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="6f97d-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="6f97d-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="6f97d-138">プログラムによるアクセスを使用して検出 REST API に直接接続する場合は、[汎用 **API] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6f97d-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="6f97d-139">個々の値をコピーするか、[詳細をファイル **に保存** ] を選択して、すべての値を含むファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6f97d-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="6f97d-140">[トークン **の生成] を** 選択して、アクセス トークンと更新トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="6f97d-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="6f97d-141">90 日ごとに新しい更新トークンを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f97d-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="6f97d-142">[Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp)の Azure ADアプリ登録を作成する手順に従い、適切なアクセス許可を割り当て、アラートを読み取ってください。</span><span class="sxs-lookup"><span data-stu-id="6f97d-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="6f97d-143">これで、SIEM ソリューションの構成またはプログラムによるアクセスを通じて検出 REST API への接続を続行できます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="6f97d-144">SIEM ソリューションを構成するときにトークンを使用して、Microsoft Defender セキュリティ センターから検出を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f97d-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="6f97d-145">Microsoft Defender for Endpoint と IBM QRadar の統合</span><span class="sxs-lookup"><span data-stu-id="6f97d-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="6f97d-146">Microsoft Defender for Endpoint から検出を収集するために IBM QRadar を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f97d-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6f97d-147">詳細については [、「IBM Knowledge Center」を参照してください](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="6f97d-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f97d-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f97d-148">See also</span></span>
- [<span data-ttu-id="6f97d-149">エンドポイント検出用の Microsoft Defender をプルする HP ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="6f97d-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="6f97d-150">Microsoft Defender for Endpoint Detection フィールド</span><span class="sxs-lookup"><span data-stu-id="6f97d-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="6f97d-151">REST API を使用したエンドポイント検出用の Microsoft Defender のプル</span><span class="sxs-lookup"><span data-stu-id="6f97d-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="6f97d-152">SIEM ツールの統合に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6f97d-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
