---
title: ユーザーサポートを受Microsoft マネージド デスクトップ
description: ユーザーがサービスとデバイスに関するヘルプを受け取る方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362608"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="0ae7d-104">ユーザーのヘルプ</span><span class="sxs-lookup"><span data-stu-id="0ae7d-104">Getting help for users</span></span>

<span data-ttu-id="0ae7d-105">管理者特権のデバイス アクセスまたは Microsoft[](../service-description/user-support.md)へのエスカレーションを要求する必要があるワークフローのポイントに達した場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="0ae7d-106">これらのサポート オプションは、テスト グループ内のデバイスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="0ae7d-107">昇格要求</span><span class="sxs-lookup"><span data-stu-id="0ae7d-107">Elevation requests</span></span>

<span data-ttu-id="0ae7d-108">デバイスへの昇格されたアクセスを要求する前に、最適なアクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="0ae7d-109">**一般的な** アクションは、このプロセスの目的であり、デバイスの問題のトラブルシューティング中に日常的にMicrosoft マネージド デスクトップです。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="0ae7d-110">たとえば、次のような情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-110">Examples include:</span></span>
    - <span data-ttu-id="0ae7d-111">組み込みのシステムのトラブルシューティングツール、コマンド プロンプト、または管理者Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ae7d-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="0ae7d-112">業務上のアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0ae7d-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="0ae7d-113">回避策を使用して、設計によって機能する必要があるものを修正する (BitLocker のアクティブ化やシステム時刻が更新されないなど)</span><span class="sxs-lookup"><span data-stu-id="0ae7d-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="0ae7d-114">ドライバーの更新、デバイスのアンインストール、新しい変更のスキャンを行うデバイス マネージャーの昇格</span><span class="sxs-lookup"><span data-stu-id="0ae7d-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="0ae7d-115">**推奨されないアクションには、次** のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="0ae7d-116">ソフトウェアまたはブラウザーのインストール</span><span class="sxs-lookup"><span data-stu-id="0ae7d-116">Installing software or browsers</span></span>
    - <span data-ttu-id="0ae7d-117">周辺機器を含む、Windows設定の外部にドライバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="0ae7d-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="0ae7d-118">ファイルの.msiまたは.exeする</span><span class="sxs-lookup"><span data-stu-id="0ae7d-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="0ae7d-119">新しいWindowsのインストール</span><span class="sxs-lookup"><span data-stu-id="0ae7d-119">Installing Windows features</span></span>

- <span data-ttu-id="0ae7d-120">**サポートされていないアクションには、次** のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="0ae7d-121">セキュリティまたは管理機能または操作にMicrosoft マネージド デスクトップするソフトウェアまたは機能のインストール</span><span class="sxs-lookup"><span data-stu-id="0ae7d-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="0ae7d-122">BitLocker などのWindowsに必要なMicrosoft マネージド デスクトップ機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="0ae7d-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="0ae7d-123">組織が管理する設定の変更</span><span class="sxs-lookup"><span data-stu-id="0ae7d-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="0ae7d-124">昇格を要求するには</span><span class="sxs-lookup"><span data-stu-id="0ae7d-124">To request elevation</span></span>

1. <span data-ttu-id="0ae7d-125">ポータルに移動し [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) 、資格情報を使用してサインインAzure Active Directoryします。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="0ae7d-126">[新 **しい昇格要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="0ae7d-127">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-127">Provide these details:</span></span>
    - <span data-ttu-id="0ae7d-128">**独自のサポート** チケット システムからのサポート チケット ID。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="0ae7d-129">**デバイス名**: デバイスのシリアル番号を入力し、メニューからデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="0ae7d-130">**カテゴリ**: 問題に最も適したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="0ae7d-131">閉じるオプションがない場合は、[その他]**を選択** し、[タイトル] フィールドと [アクションの計画] フィールドに詳細情報 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="0ae7d-132">可能であれば、カテゴリを選択してください。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="0ae7d-133">**サブカテゴリ**: 問題に最も適したサブカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="0ae7d-134">閉じるオプションがない場合は、[その **他]** を選択し、[タイトル] で簡単な説明を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="0ae7d-135">[ **アクションの計画]** で、昇格が許可された後に実行する予定のトラブルシューティング手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="0ae7d-136">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="0ae7d-137">エスカレーション要求</span><span class="sxs-lookup"><span data-stu-id="0ae7d-137">Escalation requests</span></span>


<span data-ttu-id="0ae7d-138">Microsoft に問題を [エスカレートする](../service-description/user-support.md#escalation-portal) 必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="0ae7d-139">ポータルに移動し [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) 、資格情報を使用してサインインAzure Active Directoryします。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="0ae7d-140">[ **エスカレーション要求] を選択** し、[新しいエス **カレーション要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="0ae7d-141">次の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-141">Provide these details:</span></span>
    - <span data-ttu-id="0ae7d-142">**カテゴリ**: 問題に最も適したカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="0ae7d-143">**Title**: 簡単な説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="0ae7d-144">**説明**: チームが問題を理解するのに役立つ詳細情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="0ae7d-145">ファイルを添付する必要がある場合は、送信後に要求に戻ってそれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="0ae7d-146">**主な連絡先情報**: チームの作業を担当する主要な担当者に連絡する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="0ae7d-147">**[送信]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-147">Select **Submit**.</span></span>
5. <span data-ttu-id="0ae7d-148">チームとやり取りするために、同じポータルでチケットを再訪します。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="0ae7d-149">このパスを使用してエスカレートできるのは、重大度 C の問題のみです。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="0ae7d-150">その他の問題については、IT 管理者に問い合わせ、管理ポータルから要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="0ae7d-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>