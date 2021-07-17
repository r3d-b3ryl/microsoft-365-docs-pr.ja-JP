---
title: Microsoft Defender for Identity の評価環境の有効化、MDI インスタンスのセットアップ、MDI センサーのインストールと構成、MDI センサーによるローカル管理者の検出
description: Microsoft Defender for Identity を Microsoft 365 Defender試用版ラボまたはパイロット環境でセットアップするには、&センサーをインストールし、他のコンピューターにローカル管理者を検出します。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458075"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="874c4-103">Microsoft Defender for Identity の評価環境を有効にする</span><span class="sxs-lookup"><span data-stu-id="874c4-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="874c4-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="874c4-104">**Applies to:**</span></span>
- <span data-ttu-id="874c4-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="874c4-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="874c4-106">この記事は、Microsoft Defender for Identity の評価環境をセットアップする手順 [2/2](eval-defender-identity-overview.md) です。</span><span class="sxs-lookup"><span data-stu-id="874c4-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="874c4-107">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="874c4-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="874c4-108">次の手順を使用して、Microsoft Defender for Identity 環境をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="874c4-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Microsoft Defender 評価環境で Microsoft Defender for Identity を有効にする手順](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="874c4-110">手順 1.Id インスタンスの Defender をセットアップする</span><span class="sxs-lookup"><span data-stu-id="874c4-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="874c4-111">手順 2.センサーのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="874c4-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="874c4-112">手順 3.センサーを使用してコンピューターのイベント ログとプロキシ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="874c4-113">手順 4.Defender for Identity で他のコンピューター上のローカル管理者を識別する許可</span><span class="sxs-lookup"><span data-stu-id="874c4-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="874c4-114">手順 1.</span><span class="sxs-lookup"><span data-stu-id="874c4-114">Step 1.</span></span> <span data-ttu-id="874c4-115">Id インスタンスの Defender をセットアップする</span><span class="sxs-lookup"><span data-stu-id="874c4-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="874c4-116">Defender for Identity ポータルにサインインしてインスタンスを作成し、このインスタンスを Active Directory 環境に接続します。</span><span class="sxs-lookup"><span data-stu-id="874c4-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="874c4-117">手順</span><span class="sxs-lookup"><span data-stu-id="874c4-117">Step</span></span>     |<span data-ttu-id="874c4-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="874c4-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="874c4-119">1</span><span class="sxs-lookup"><span data-stu-id="874c4-119">1</span></span>     | <span data-ttu-id="874c4-120">Defender for Identity インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="874c4-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="874c4-121">クイック スタート: Microsoft Defender for Identity インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="874c4-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="874c4-122">2</span><span class="sxs-lookup"><span data-stu-id="874c4-122">2</span></span>     | <span data-ttu-id="874c4-123">Connect Defender for Identity インスタンスを Active Directory フォレストに移動する</span><span class="sxs-lookup"><span data-stu-id="874c4-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="874c4-124">クイック スタート: Connect Active Directory フォレストにアクセスする</span><span class="sxs-lookup"><span data-stu-id="874c4-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="874c4-125">手順 2.</span><span class="sxs-lookup"><span data-stu-id="874c4-125">Step 2.</span></span> <span data-ttu-id="874c4-126">センサーのインストールと構成</span><span class="sxs-lookup"><span data-stu-id="874c4-126">Install and configure the sensor</span></span>

<span data-ttu-id="874c4-127">次に、ドメイン コントローラーおよびオンプレミス環境の FS AD Defender for Identity センサーをダウンロード、インストール、および構成します。</span><span class="sxs-lookup"><span data-stu-id="874c4-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="874c4-128">手順</span><span class="sxs-lookup"><span data-stu-id="874c4-128">Step</span></span>     |<span data-ttu-id="874c4-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="874c4-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="874c4-130">1</span><span class="sxs-lookup"><span data-stu-id="874c4-130">1</span></span>     | <span data-ttu-id="874c4-131">必要な Microsoft Defender for Identity センサーの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="874c4-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="874c4-132">Microsoft Defender for Identity の容量を計画する</span><span class="sxs-lookup"><span data-stu-id="874c4-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="874c4-133">2</span><span class="sxs-lookup"><span data-stu-id="874c4-133">2</span></span>     | <span data-ttu-id="874c4-134">センサー セットアップ パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="874c4-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="874c4-135">クイック スタート: Microsoft Defender for Identity センサーセットアップ パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="874c4-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="874c4-136">3</span><span class="sxs-lookup"><span data-stu-id="874c4-136">3</span></span>     | <span data-ttu-id="874c4-137">Defender for Identity センサーのインストール</span><span class="sxs-lookup"><span data-stu-id="874c4-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="874c4-138">クイック スタート: Microsoft Defender for Identity センサーのインストール</span><span class="sxs-lookup"><span data-stu-id="874c4-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="874c4-139">4 </span><span class="sxs-lookup"><span data-stu-id="874c4-139">4</span></span>     | <span data-ttu-id="874c4-140">センサーを構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-140">Configure the sensor</span></span>       |  [<span data-ttu-id="874c4-141">Microsoft Defender for Identity センサーの設定を構成する </span><span class="sxs-lookup"><span data-stu-id="874c4-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="874c4-142">手順 3.</span><span class="sxs-lookup"><span data-stu-id="874c4-142">Step 3.</span></span> <span data-ttu-id="874c4-143">センサーを使用してコンピューターのイベント ログとプロキシ設定を構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="874c4-144">センサーをインストールしたコンピューターで、検出機能を有効Windows強化するために、イベント ログ コレクションとインターネット プロキシ設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="874c4-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="874c4-145">手順</span><span class="sxs-lookup"><span data-stu-id="874c4-145">Step</span></span>     |<span data-ttu-id="874c4-146">詳細情報</span><span class="sxs-lookup"><span data-stu-id="874c4-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="874c4-147">1</span><span class="sxs-lookup"><span data-stu-id="874c4-147">1</span></span>     | <span data-ttu-id="874c4-148">イベント Windowsコレクションを構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="874c4-149">イベント コレクションWindows構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="874c4-150">2</span><span class="sxs-lookup"><span data-stu-id="874c4-150">2</span></span>     | <span data-ttu-id="874c4-151">インターネット プロキシ設定の構成</span><span class="sxs-lookup"><span data-stu-id="874c4-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="874c4-152">Microsoft Defender for Identity Sensor のエンドポイント プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="874c4-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="874c4-153">手順 4.</span><span class="sxs-lookup"><span data-stu-id="874c4-153">Step 4.</span></span> <span data-ttu-id="874c4-154">Defender for Identity で他のコンピューター上のローカル管理者を識別する許可</span><span class="sxs-lookup"><span data-stu-id="874c4-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="874c4-155">Microsoft Defender for Identity 横移動パスの検出は、特定のコンピューター上のローカル管理者を識別するクエリに依存します。</span><span class="sxs-lookup"><span data-stu-id="874c4-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="874c4-156">これらのクエリは、Defender for Identity Service アカウントを使用して SAM-R プロトコルを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="874c4-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="874c4-157">Windows クライアントとサーバーで Defender for Identity アカウントが SAM-R を実行するようにするには、ネットワーク アクセス ポリシーに記載されている構成済みのアカウントに加えて、Defender for Identity サービス アカウントを追加するためにグループ ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="874c4-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="874c4-158">ドメイン コントローラーを除くすべてのコンピューターにグループ ポリシー **を適用してください**。</span><span class="sxs-lookup"><span data-stu-id="874c4-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="874c4-159">これを行う方法については [、「Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="874c4-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="874c4-160">次の手順</span><span class="sxs-lookup"><span data-stu-id="874c4-160">Next steps</span></span>

<span data-ttu-id="874c4-161">手順 3 / 3: [Id の Microsoft Defender のパイロット](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="874c4-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="874c4-162">Id の Microsoft Defender の [評価の概要に戻る](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="874c4-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="874c4-163">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="874c4-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>