---
title: クラウド ブロックのMicrosoft Defender ウイルス対策期間を構成する
description: クラウドの決定を待機Microsoft Defender ウイルス対策ファイルの実行をブロックする期間を構成できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、ディフェンダー、クラウド、タイムアウト、ブロック、期間、秒
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789089"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="25163-104">クラウド ブロックのタイムアウト期間の構成</span><span class="sxs-lookup"><span data-stu-id="25163-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="25163-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25163-105">**Applies to:**</span></span>

- [<span data-ttu-id="25163-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25163-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="25163-107">不審Microsoft Defender ウイルス対策検出すると、クラウド サービスのクエリ中にファイルが実行Microsoft Defender ウイルス対策[可能性があります](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="25163-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="25163-108">ファイルがブロックされる [既定の期間](configure-block-at-first-sight-microsoft-defender-antivirus.md) は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="25163-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="25163-109">セキュリティ管理者の場合は、ファイルの実行が許可される前に待機する時間を長く指定できます。</span><span class="sxs-lookup"><span data-stu-id="25163-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="25163-110">クラウド ブロックのタイムアウト期間を延長すると、クラウド サービスから適切な判断を受け取るのに十分な時間Microsoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="25163-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="25163-111">拡張クラウド ブロック タイムアウトを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="25163-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="25163-112">[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) し、その前提条件を有効にしてから、延長タイムアウト期間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25163-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="25163-113">データを使用して延長タイムアウト期間をMicrosoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="25163-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="25163-114">クラウド ブロックのタイムアウト期間は、エンドポイント セキュリティ ポリシーを使用して指定[Microsoft エンドポイント マネージャー。](/mem/intune/protect/endpoint-security-policy)</span><span class="sxs-lookup"><span data-stu-id="25163-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="25163-115">管理センター ( ) エンドポイント マネージャーに移動し [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="25163-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="25163-116">[エンドポイント **セキュリティ] を** 選択し、[管理] で **[ウイルス** 対策] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25163-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="25163-117">ウイルス対策ポリシーを選択 (または作成) します。</span><span class="sxs-lookup"><span data-stu-id="25163-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="25163-118">[構成設定 **] セクションで** 、[クラウド保護] **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="25163-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="25163-119">次に **、[Defender Cloud Extended Timeout in Seconds]** ボックスで、1 秒から 50 秒の時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="25163-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="25163-120">指定した値は、既定の 10 秒に追加されます。</span><span class="sxs-lookup"><span data-stu-id="25163-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="25163-121">(この手順は省略可能です)ウイルス対策ポリシーに他の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="25163-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="25163-122">(ヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="25163-122">(Need help?</span></span> <span data-ttu-id="25163-123">[「設定ポリシー Microsoft Defender ウイルス対策」を参照Microsoft Intune.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)</span><span class="sxs-lookup"><span data-stu-id="25163-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="25163-124">[ **次へ]** を選択し、ポリシーの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="25163-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="25163-125">グループ ポリシーを使用して延長タイムアウト期間を指定する</span><span class="sxs-lookup"><span data-stu-id="25163-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="25163-126">グループ ポリシーを使用して、クラウド チェックの延長タイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="25163-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="25163-127">グループ ポリシー管理コンピューターで、グループ ポリシー管理 [コンソールを開きます。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="25163-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="25163-128">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="25163-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="25163-129">グループ ポリシー **管理エディターで、[** コンピューターの構成] **に** 移動し、[管理用テンプレート] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="25163-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="25163-130">MpEngine のコンポーネント **Windowsツリー**  >  **Microsoft Defender ウイルス対策**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="25163-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="25163-131">[拡張クラウド チェック **の構成] をダブルクリックし** 、オプションが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="25163-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="25163-132">クラウドの決定を待っている間にファイルが実行されるのを防ぐための余分な時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="25163-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="25163-133">1 秒から 50 秒の余分な時間を秒で指定します。</span><span class="sxs-lookup"><span data-stu-id="25163-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="25163-134">指定した値は、既定の 10 秒に追加されます。</span><span class="sxs-lookup"><span data-stu-id="25163-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="25163-135">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="25163-135">Select **OK**.</span></span>

 