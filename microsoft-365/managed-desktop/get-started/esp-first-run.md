---
title: 自動操縦と登録の状態ページでの初回実行時の動作
description: ESP の使用方法、使用されている設定、例外を展開する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d4083e48033787ca46ad2374ea461b4a77d21e0d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296006"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="83eb6-104">自動操縦と登録の状態ページでの初回実行時の動作</span><span class="sxs-lookup"><span data-stu-id="83eb6-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="83eb6-105">Microsoft マネージドデスクトップでは、 [Windows 自動操縦](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) と microsoft Intune の [登録状態ページ (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) の両方を使用して、ユーザーに最適な最初の実行環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-105">Microsoft Managed Desktop uses both [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="83eb6-106">[登録の状態] ページは、現在パブリックプレビューにあります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="83eb6-107">初期展開</span><span class="sxs-lookup"><span data-stu-id="83eb6-107">Initial deployment</span></span>

<span data-ttu-id="83eb6-108">ESP の動作を提供するには、Microsoft Managed Desktop service でデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="83eb6-109">登録の詳細については、「 [新しいデバイスを自分で登録](../get-started/register-devices-self.md) する」または「 [パートナーがデバイスを登録するための手順](../get-started/register-devices-partner.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83eb6-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="83eb6-110">デバイスがサービスに登録されたら、 [管理者ポータル](https://portal.azure.com/)を使用してサポートチケットを提出することによって、Microsoft マネージドデスクトップデバイスの ESP を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="83eb6-111">最初に、チケットをファイル化するときに、ESP 構成をテストグループに展開します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="83eb6-112">このグループは、24時間ごとに展開された他のグループ (最初、高速、広範) に展開されます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="83eb6-113">展開を一時停止するには、別のチケットをファイルに保存する操作を要求します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="83eb6-114">自動操縦プロファイルの設定</span><span class="sxs-lookup"><span data-stu-id="83eb6-114">Autopilot profile settings</span></span>

<span data-ttu-id="83eb6-115">Microsoft マネージドデスクトップでは、ユーザーのデバイスに使用する自動操縦プロファイルでこれらの設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="83eb6-116">設定</span><span class="sxs-lookup"><span data-stu-id="83eb6-116">Setting</span></span>  |<span data-ttu-id="83eb6-117">値</span><span class="sxs-lookup"><span data-stu-id="83eb6-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="83eb6-118">展開モード</span><span class="sxs-lookup"><span data-stu-id="83eb6-118">Deployment mode</span></span> |  <span data-ttu-id="83eb6-119">ユーザー主導</span><span class="sxs-lookup"><span data-stu-id="83eb6-119">User Driven</span></span>       |
|<span data-ttu-id="83eb6-120">Azure AD に参加する</span><span class="sxs-lookup"><span data-stu-id="83eb6-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="83eb6-121">Azure AD 参加済み</span><span class="sxs-lookup"><span data-stu-id="83eb6-121">Azure AD joined</span></span>       |
|<span data-ttu-id="83eb6-122">言語 (地域)</span><span class="sxs-lookup"><span data-stu-id="83eb6-122">Language (Region)</span></span>     | <span data-ttu-id="83eb6-123">オペレーティングシステムの既定値</span><span class="sxs-lookup"><span data-stu-id="83eb6-123">Operating system default</span></span>        |
|<span data-ttu-id="83eb6-124">キーボードの自動構成</span><span class="sxs-lookup"><span data-stu-id="83eb6-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="83eb6-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="83eb6-125">No</span></span>        |
|<span data-ttu-id="83eb6-126">マイクロソフトソフトウェアライセンス条項</span><span class="sxs-lookup"><span data-stu-id="83eb6-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="83eb6-127">非表示</span><span class="sxs-lookup"><span data-stu-id="83eb6-127">Hide</span></span>       |
|<span data-ttu-id="83eb6-128">プライバシーの設定</span><span class="sxs-lookup"><span data-stu-id="83eb6-128">Privacy settings</span></span>     | <span data-ttu-id="83eb6-129">非表示</span><span class="sxs-lookup"><span data-stu-id="83eb6-129">Hide</span></span>        |
|<span data-ttu-id="83eb6-130">アカウントの変更オプションを非表示にする</span><span class="sxs-lookup"><span data-stu-id="83eb6-130">Hide change account options</span></span>     | <span data-ttu-id="83eb6-131">Show</span><span class="sxs-lookup"><span data-stu-id="83eb6-131">Show</span></span>        |
|<span data-ttu-id="83eb6-132">ユーザーアカウントの種類</span><span class="sxs-lookup"><span data-stu-id="83eb6-132">User account type</span></span>     |  <span data-ttu-id="83eb6-133">Standard</span><span class="sxs-lookup"><span data-stu-id="83eb6-133">Standard</span></span>       |
|<span data-ttu-id="83eb6-134">白色のグローブ OOBE を許可する</span><span class="sxs-lookup"><span data-stu-id="83eb6-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="83eb6-135">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-135">Yes</span></span>       |
|<span data-ttu-id="83eb6-136">デバイス名テンプレートの適用</span><span class="sxs-lookup"><span data-stu-id="83eb6-136">Apply device name template</span></span>     | <span data-ttu-id="83eb6-137">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-137">Yes</span></span>        |
|<span data-ttu-id="83eb6-138">名前を入力してください</span><span class="sxs-lookup"><span data-stu-id="83eb6-138">Enter a name</span></span>     | <span data-ttu-id="83eb6-139">MMD-% RAND: 7%</span><span class="sxs-lookup"><span data-stu-id="83eb6-139">MMD-%RAND:7%</span></span>        |



## <a name="enrollment-status-page-settings"></a><span data-ttu-id="83eb6-140">登録の状態ページの設定</span><span class="sxs-lookup"><span data-stu-id="83eb6-140">Enrollment Status Page settings</span></span>

<span data-ttu-id="83eb6-141">Microsoft マネージドデスクトップは、次の設定を使用して登録の状態のページの機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-141">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="83eb6-142">設定</span><span class="sxs-lookup"><span data-stu-id="83eb6-142">Setting</span></span>  |<span data-ttu-id="83eb6-143">値</span><span class="sxs-lookup"><span data-stu-id="83eb6-143">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="83eb6-144">アプリとプロファイルの構成の進行状況を表示する</span><span class="sxs-lookup"><span data-stu-id="83eb6-144">Show app and profile configuration progress</span></span>     | <span data-ttu-id="83eb6-145">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-145">Yes</span></span>        |
|<span data-ttu-id="83eb6-146">インストール時に指定した分数を超える時間が発生した場合にエラーを表示する</span><span class="sxs-lookup"><span data-stu-id="83eb6-146">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="83eb6-147">60</span><span class="sxs-lookup"><span data-stu-id="83eb6-147">60</span></span>       |
|<span data-ttu-id="83eb6-148">時間制限エラーが発生した場合にカスタムメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="83eb6-148">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="83eb6-149">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-149">Yes</span></span>       |
|<span data-ttu-id="83eb6-150">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="83eb6-150">Error message</span></span>     | <span data-ttu-id="83eb6-151">はい。デバイスのセットアップには、予想よりも少し時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-151">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="83eb6-152">開始するには以下をクリックしてください。バックグラウンドで設定を完了します</span><span class="sxs-lookup"><span data-stu-id="83eb6-152">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="83eb6-153">ユーザーがインストールエラーに関するログを収集できるようにする</span><span class="sxs-lookup"><span data-stu-id="83eb6-153">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="83eb6-154">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-154">Yes</span></span>       |
|<span data-ttu-id="83eb6-155">[すぐにプロビジョニングされたデバイスにのみページを表示する (OOBE)]</span><span class="sxs-lookup"><span data-stu-id="83eb6-155">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="83eb6-156">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-156">Yes</span></span>        |
|<span data-ttu-id="83eb6-157">すべてのアプリとプロファイルがインストールされるまで、デバイスの使用をブロックする</span><span class="sxs-lookup"><span data-stu-id="83eb6-157">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="83eb6-158">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-158">Yes</span></span>       |
|<span data-ttu-id="83eb6-159">インストールエラーが発生した場合にユーザーがデバイスをリセットすることを許可する</span><span class="sxs-lookup"><span data-stu-id="83eb6-159">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="83eb6-160">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-160">Yes</span></span>       |
|<span data-ttu-id="83eb6-161">インストールエラーが発生した場合にユーザーにデバイスの使用を許可する</span><span class="sxs-lookup"><span data-stu-id="83eb6-161">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="83eb6-162">はい</span><span class="sxs-lookup"><span data-stu-id="83eb6-162">Yes</span></span>       |
|<span data-ttu-id="83eb6-163">ユーザー/デバイスに割り当てられている場合は、これらの必要なアプリがインストールされるまで、デバイスを使用することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-163">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="83eb6-164">モダンタイムプレース修正</span><span class="sxs-lookup"><span data-stu-id="83eb6-164">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="83eb6-165">登録の状態のページの動作は、3つのフェーズで行われます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-165">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="83eb6-166">詳細については、「 [登録ステータスページの追跡情報](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83eb6-166">For more, see [Enrollment Status Page tracking information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="83eb6-167">この作業は次のように進めます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-167">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="83eb6-168">自動操縦作業が開始され、ユーザーが資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-168">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="83eb6-169">デバイスが [登録の状態] ページを開き、デバイスの準備とデバイスのセットアップフェーズを続行します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-169">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="83eb6-170">3番目の手順 (アカウントのセットアップ) は、ユーザーの ESP が無効になっているため、Microsoft マネージドデスクトップの構成で *現在スキップ* されています。</span><span class="sxs-lookup"><span data-stu-id="83eb6-170">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="83eb6-171">デバイスが再起動します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-171">The device restarts.</span></span>
3. <span data-ttu-id="83eb6-172">再起動した後、デバイスによって Windows サインインページが **他のユーザー**と共に開かれます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-172">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="83eb6-173">ユーザーが資格情報をもう一度入力すると、デスクトップが開きます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-173">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="83eb6-174">Win32 アプリは、Windows 10 のバージョンが1903以降の場合にのみ ESP の間に展開されます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-174">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

![「デバイスの準備」と「デバイスのセットアップ」のフェーズが表示されている自動操縦のセットアップの開始ページです。](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a><span data-ttu-id="83eb6-176">白いグローブプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="83eb6-176">White glove provisioning</span></span>

<span data-ttu-id="83eb6-177">Microsoft Managed Desktop は現在、Windows 自動操縦の "白のグローブ" 機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="83eb6-177">Microsoft Managed Desktop doesn't currently support the "white glove" feature of Windows Autopilot.</span></span>

## <a name="exceptions"></a><span data-ttu-id="83eb6-178">例外</span><span class="sxs-lookup"><span data-stu-id="83eb6-178">Exceptions</span></span>

<span data-ttu-id="83eb6-179">Microsoft マネージドデスクトップで使用されているセットアップがニーズに正確に一致しない場合は、例外の要求をファイルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-179">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can file a request for an exception.</span></span> <span data-ttu-id="83eb6-180">これを行うには、「 [Request for exception](../service-description/customizing.md#request-an-exception)」の「詳細」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83eb6-180">To do this, see details in [Request an exception](../service-description/customizing.md#request-an-exception).</span></span> <span data-ttu-id="83eb6-181">必要な例外の種類の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-181">Here are some examples of the types of exceptions you might need:</span></span>

### <a name="autopilot-exception"></a><span data-ttu-id="83eb6-182">自動操縦例外</span><span class="sxs-lookup"><span data-stu-id="83eb6-182">Autopilot exception</span></span>

<span data-ttu-id="83eb6-183">別のデバイス名テンプレートを要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-183">You might want to request a different device name template.</span></span> <span data-ttu-id="83eb6-184">ただし、[展開モードの変更]、[Azure に参加]、[プライバシー設定]、または [ユーザーアカウントの種類] には変更できません。</span><span class="sxs-lookup"><span data-stu-id="83eb6-184">You cannot, however, change Deployment Mode, Join to Azure As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-exception"></a><span data-ttu-id="83eb6-185">登録の状態ページの例外</span><span class="sxs-lookup"><span data-stu-id="83eb6-185">Enrollment Status Page exception</span></span>

- <span data-ttu-id="83eb6-186">"インストール時に指定した時間より長く時間が経過した場合にエラーを表示する" 設定の時間を長くします。</span><span class="sxs-lookup"><span data-stu-id="83eb6-186">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="83eb6-187">表示されるエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="83eb6-187">The error message displayed</span></span>
- <span data-ttu-id="83eb6-188">"ブロックデバイスでのアプリケーションの追加または削除は、これらの必要なアプリがユーザー/デバイスに割り当てられている場合にインストールされるようにする" 設定にします。</span><span class="sxs-lookup"><span data-stu-id="83eb6-188">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="83eb6-189">必要なアプリケーション</span><span class="sxs-lookup"><span data-stu-id="83eb6-189">Required applications</span></span>

- <span data-ttu-id="83eb6-190">モダン Workplace *device groups* テスト、ファースト、Fast、および広範なアプリケーションで、アプリケーションを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-190">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="83eb6-191">アプリケーションは、"System" コンテキストにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-191">Applications must install in the "System" context.</span></span> <span data-ttu-id="83eb6-192">テストグループ内の ESP でテストを完了してから、すべてのグループに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="83eb6-192">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="83eb6-193">アプリケーションでデバイスを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="83eb6-193">No applications should require the device to restart.</span></span> <span data-ttu-id="83eb6-194">アプリケーションパッケージを再起動する必要がある場合は、アプリケーションパッケージの作成時にアプリケーションを "実行しない" に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83eb6-194">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="83eb6-195">必要なアプリケーションを、ユーザーがデバイスにサインインするときにすぐに必要とするコアアプリケーションのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="83eb6-195">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="83eb6-196">アプリケーションのインストール段階でタイムアウトが発生しないように、すべてのアプリケーションの合計サイズを 1 GB 以下にまとめておきます。</span><span class="sxs-lookup"><span data-stu-id="83eb6-196">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="83eb6-197">アプリが依存関係を持たないことが理想的です。</span><span class="sxs-lookup"><span data-stu-id="83eb6-197">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="83eb6-198">依存関係が *必要* なアプリがある場合は、ESP 評価の一部として構成、テスト、検証を行うようにしてください。</span><span class="sxs-lookup"><span data-stu-id="83eb6-198">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="83eb6-199">"User" コンテキスト (Teams など) を必要とするアプリケーションは、ESP のパブリックプレビューに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="83eb6-199">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>