---
title: プレビューとテストWindows 11 とMicrosoft マネージド デスクトップ
description: 環境でWindows 11 を取得する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8dee18909d82656bcfb3e63fdc078328c678e660
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461389"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a><span data-ttu-id="655bd-104">プレビューとテストWindows 11 とMicrosoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="655bd-104">Preview and test Windows 11 with Microsoft Managed Desktop</span></span>

 <span data-ttu-id="655bd-105">11 の互換性テスト プログラムWindows環境に登録して参加するMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="655bd-105">How to enroll and participate in the Windows 11 compatibility testing program within your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="655bd-106">11 と WindowsのMicrosoft マネージド デスクトップについては、「Windows [11」を参照Microsoft マネージド デスクトップ。](../intro/win11-overview.md)</span><span class="sxs-lookup"><span data-stu-id="655bd-106">For more about Windows 11 and Microsoft Managed Desktop generally, see [Windows 11 and Microsoft Managed Desktop](../intro/win11-overview.md).</span></span> 

## <a name="check-device-eligibility"></a><span data-ttu-id="655bd-107">デバイスの適格性を確認する</span><span class="sxs-lookup"><span data-stu-id="655bd-107">Check device eligibility</span></span>

<span data-ttu-id="655bd-108">現在までに、デバイスの 95% 以上Microsoft マネージド デスクトップ 11 の適格性Windows[満たしています](/windows/whats-new/windows-11-requirements)。</span><span class="sxs-lookup"><span data-stu-id="655bd-108">To date, more than 95% of Microsoft Managed Desktop devices meet [eligibility criteria for Windows 11](/windows/whats-new/windows-11-requirements).</span></span> <span data-ttu-id="655bd-109">デバイスの適格性の状態に関する詳細は、Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="655bd-109">You can request details about the eligibility status of your devices from Microsoft Managed Desktop.</span></span> <span data-ttu-id="655bd-110">要求をファイルするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="655bd-110">To file the request, follow these steps:</span></span>

1. <span data-ttu-id="655bd-111">サービス エンジニアリング チームと一緒に新Microsoft マネージド デスクトップを開きます。</span><span class="sxs-lookup"><span data-stu-id="655bd-111">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span> <span data-ttu-id="655bd-112">要求をファイルする方法の詳細については、「管理者サポート」 [を参照してください](admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="655bd-112">If you need more info on how to file the request, see [Admin support](admin-support.md).</span></span>
2. <span data-ttu-id="655bd-113">フィールドには、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="655bd-113">Use these values for the fields:</span></span>
    - <span data-ttu-id="655bd-114">タイトル: Windows 11 デバイスの適格性</span><span class="sxs-lookup"><span data-stu-id="655bd-114">Title: Windows 11 device eligibility</span></span>
    - <span data-ttu-id="655bd-115">要求の種類: 情報の要求</span><span class="sxs-lookup"><span data-stu-id="655bd-115">Request type: Request for information</span></span>
    - <span data-ttu-id="655bd-116">カテゴリ: デバイス</span><span class="sxs-lookup"><span data-stu-id="655bd-116">Category: Devices</span></span>
    - <span data-ttu-id="655bd-117">サブカテゴリ: その他</span><span class="sxs-lookup"><span data-stu-id="655bd-117">Subcategory: Other</span></span>


## <a name="add-devices-to-the-windows-11-test-group"></a><span data-ttu-id="655bd-118">デバイスを 11 Windowsグループに追加する</span><span class="sxs-lookup"><span data-stu-id="655bd-118">Add devices to the Windows 11 test group</span></span>

<span data-ttu-id="655bd-119">まず、デバイス グループ **\[ (Modern Workplace \] Windows 11** プレリリース テスト デバイス) にデバイスを追加し、11 のテストと評価Windowsします。</span><span class="sxs-lookup"><span data-stu-id="655bd-119">Start by adding devices to the device group (**\[Modern Workplace\] Windows 11 Pre-Release Test Devices**) created for testing and evaluating Windows 11.</span></span> <span data-ttu-id="655bd-120">このグループのデバイスは、Windows 11 のビルドとMicrosoft マネージド デスクトップベースライン構成を取得し、信頼性の問題を監視します。</span><span class="sxs-lookup"><span data-stu-id="655bd-120">Devices in this group get new Windows 11 builds and Microsoft Managed Desktop baseline configurations as they become available and are monitored for reliability issues.</span></span>

<span data-ttu-id="655bd-121">Windows 11 テスト用に既存のデバイスまたは新しいデバイスを選択できますが、プレリリース ビルドでの欠陥や互換性の問題のリスクが高く、このグループに実稼働デバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="655bd-121">You can choose any of your existing or new devices for Windows 11 testing, but you shouldn't enroll production devices in this group due to the elevated risk of defects or compatibility issues in pre-release builds.</span></span> <span data-ttu-id="655bd-122">以前のデバイス グループの割り当ては、このグループへの割り当て時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="655bd-122">Prior device group assignments are removed upon assignment to this group.</span></span>

<span data-ttu-id="655bd-123">プレリリース テスト グループにデバイスを登録するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="655bd-123">To enroll your devices in the pre-release test group:</span></span>

1. <span data-ttu-id="655bd-124">サービス エンジニアリング チームと一緒に新Microsoft マネージド デスクトップを開きます。</span><span class="sxs-lookup"><span data-stu-id="655bd-124">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span>
2. <span data-ttu-id="655bd-125">フィールドには、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="655bd-125">Use these values for the fields:</span></span>
    - <span data-ttu-id="655bd-126">タイトル: Windows 11 互換登録</span><span class="sxs-lookup"><span data-stu-id="655bd-126">Title: Windows 11 compatibility enrollment</span></span>
    - <span data-ttu-id="655bd-127">要求の種類: 変更要求</span><span class="sxs-lookup"><span data-stu-id="655bd-127">Request type: Change request</span></span>
    - <span data-ttu-id="655bd-128">カテゴリ: デバイス</span><span class="sxs-lookup"><span data-stu-id="655bd-128">Category: Devices</span></span>
    - <span data-ttu-id="655bd-129">サブカテゴリ: 展開グループの割り当て</span><span class="sxs-lookup"><span data-stu-id="655bd-129">Subcategory: Deployment group assignment</span></span>
3. <span data-ttu-id="655bd-130">[説明] フィールドに、11 テストで使用するデバイスのシリアルWindowsします。</span><span class="sxs-lookup"><span data-stu-id="655bd-130">In the description field, list the serial numbers of the devices that you want to use for Windows 11 testing.</span></span> <span data-ttu-id="655bd-131">指定したデバイスがある場合は、そのデバイスがテナントにまだMicrosoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="655bd-131">Note which, if any, of the specified devices aren't yet deployed in your Microsoft Managed Desktop tenant.</span></span>

## <a name="prioritize-applications-to-submit-to-test-base"></a><span data-ttu-id="655bd-132">テスト ベースに送信するアプリケーションの優先順位を設定する</span><span class="sxs-lookup"><span data-stu-id="655bd-132">Prioritize applications to submit to Test Base</span></span>

<span data-ttu-id="655bd-133">ビジネスクリティカルなアプリケーションは、11 環境で閉じた環境での検証をWindows候補です。</span><span class="sxs-lookup"><span data-stu-id="655bd-133">Business-critical applications are the best candidates for more validation in a closed Windows 11 environment.</span></span> <span data-ttu-id="655bd-134">使用状況と信頼性データに基づいて、Windows 11 テストのアプリの優先順位を設定できます。</span><span class="sxs-lookup"><span data-stu-id="655bd-134">We can help you prioritize apps for Windows 11 testing based on usage and reliability data.</span></span> <span data-ttu-id="655bd-135">推奨事項を要求するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="655bd-135">To request our recommendations, follow these steps:</span></span>

1. <span data-ttu-id="655bd-136">サービス エンジニアリング チームと一緒に新Microsoft マネージド デスクトップを開きます。</span><span class="sxs-lookup"><span data-stu-id="655bd-136">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span> <span data-ttu-id="655bd-137">要求をファイルする方法の詳細については、「管理者サポート」 [を参照してください](admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="655bd-137">If you need more info on how to file the request, see [Admin support](admin-support.md).</span></span>
2. <span data-ttu-id="655bd-138">フィールドには、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="655bd-138">Use these values for the fields:</span></span>
    - <span data-ttu-id="655bd-139">タイトル: Windows 11 名</span><span class="sxs-lookup"><span data-stu-id="655bd-139">Title: Windows 11 Test Base candidates</span></span>
    - <span data-ttu-id="655bd-140">要求の種類: 情報の要求</span><span class="sxs-lookup"><span data-stu-id="655bd-140">Request type: Request for information</span></span>
    - <span data-ttu-id="655bd-141">カテゴリ: アプリ</span><span class="sxs-lookup"><span data-stu-id="655bd-141">Category: Apps</span></span>
    - <span data-ttu-id="655bd-142">サブカテゴリ: その他</span><span class="sxs-lookup"><span data-stu-id="655bd-142">Subcategory: Other</span></span>

## <a name="report-issues"></a><span data-ttu-id="655bd-143">問題の報告</span><span class="sxs-lookup"><span data-stu-id="655bd-143">Report issues</span></span>

<span data-ttu-id="655bd-144">line-of-business または Windows アプリとの 11 の互換性の問題が発生した場合は、調査と修復Microsoft 365報告してください。</span><span class="sxs-lookup"><span data-stu-id="655bd-144">If you encounter Windows 11 compatibility issues with your line-of-business or Microsoft 365 apps, report them to us for investigation and remediation.</span></span> <span data-ttu-id="655bd-145">問題を報告するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="655bd-145">To report an issue, follow these steps:</span></span>

1. <span data-ttu-id="655bd-146">サービス エンジニアリング チームと一緒に新Microsoft マネージド デスクトップを開きます。</span><span class="sxs-lookup"><span data-stu-id="655bd-146">Open a new service request with the Microsoft Managed Desktop Service Engineering team.</span></span>
2. <span data-ttu-id="655bd-147">フィールドには、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="655bd-147">Use these values for the fields:</span></span>
    - <span data-ttu-id="655bd-148">タイトル: Windows 11 の互換性テスト</span><span class="sxs-lookup"><span data-stu-id="655bd-148">Title: Windows 11 compatibility testing</span></span>
    - <span data-ttu-id="655bd-149">要求の種類: インシデント</span><span class="sxs-lookup"><span data-stu-id="655bd-149">Request type: Incident</span></span>
    - <span data-ttu-id="655bd-150">カテゴリ: デバイス</span><span class="sxs-lookup"><span data-stu-id="655bd-150">Category: Devices</span></span>
    - <span data-ttu-id="655bd-151">サブカテゴリ: Windows/更新</span><span class="sxs-lookup"><span data-stu-id="655bd-151">Subcategory: Windows Upgrade/Update</span></span>
3. <span data-ttu-id="655bd-152">動作と、実稼働環境でのビジネスの妨げとなる深刻な状況を説明します。</span><span class="sxs-lookup"><span data-stu-id="655bd-152">Describe the behavior and how severely it would hinder your business in a production environment.</span></span>

<span data-ttu-id="655bd-153">Microsoft マネージド デスクトップ影響に基づいて、プレリリース ビルドの問題をトリアージして処理します。</span><span class="sxs-lookup"><span data-stu-id="655bd-153">Microsoft Managed Desktop triages and handles issues with pre-release builds based on the effect on productivity.</span></span> <span data-ttu-id="655bd-154">サービスの説明ではプレリリース ビルドに関する問題は説明されませんが、ユーザーの生産性をブロックする問題が特定のテナント内で移行を開始する前に解決されるのを確認するために、お客様の管理者と連絡を取る予定です。</span><span class="sxs-lookup"><span data-stu-id="655bd-154">While our service description doesn't cover issues with pre-release builds, we'll confer with customer admins to ensure that issues that block user productivity are resolved prior to starting migration within any given tenant.</span></span>
