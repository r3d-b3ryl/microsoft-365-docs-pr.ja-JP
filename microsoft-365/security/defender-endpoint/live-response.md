---
title: Microsoft Defender ATP でライブ応答を使用してデバイス上のエンティティを調査する
description: 安全なリモート シェル接続を使用してデバイスにアクセスし、調査作業を行い、デバイスでリアルタイムで即座に応答アクションを実行します。
keywords: リモート、シェル、接続、ライブ、応答、リアルタイム、コマンド、スクリプト、修復、ハント、エクスポート、ログ、ドロップ、ダウンロード、ファイル、
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
ms.openlocfilehash: 784e73467efc114f05ebdfca9bc4034e2d75f6c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185709"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="63ed0-104">ライブ応答を使用してデバイス上のエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="63ed0-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="63ed0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="63ed0-105">**Applies to:**</span></span>
- [<span data-ttu-id="63ed0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="63ed0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="63ed0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63ed0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="63ed0-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="63ed0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="63ed0-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="63ed0-110">ライブ応答により、セキュリティ運用チームはリモート シェル接続を使用してデバイス (コンピューターとも呼ばれます) に瞬時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="63ed0-111">これにより、詳細な調査作業を行い、迅速に特定された脅威をリアルタイムに含める即時対応アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="63ed0-112">ライブ応答は、セキュリティ運用チームが法医学データを収集し、スクリプトを実行し、分析のために疑わしいエンティティを送信し、脅威を修復し、新たな脅威を積極的に捜し出して調査を強化するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="63ed0-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="63ed0-113">ライブ応答を使用すると、アナリストは次のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="63ed0-114">基本的なコマンドと高度なコマンドを実行して、デバイスで調査作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="63ed0-115">PowerShell スクリプトのマルウェア サンプルや結果などのファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="63ed0-116">バックグラウンドでファイルをダウンロードする (new!)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="63ed0-117">PowerShell スクリプトまたは実行可能ファイルをライブラリにアップロードし、テナント レベルからデバイスで実行します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="63ed0-118">修復アクションを実行または元に戻します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="63ed0-119">はじめに</span><span class="sxs-lookup"><span data-stu-id="63ed0-119">Before you begin</span></span>

<span data-ttu-id="63ed0-120">デバイスでセッションを開始する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63ed0-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="63ed0-121">**サポートされているバージョンの Windows を実行しているのを確認します**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="63ed0-122">デバイスは、次のいずれかのバージョンの Windows を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="63ed0-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="63ed0-123">**Windows 10**</span></span>
    - <span data-ttu-id="63ed0-124">[バージョン 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) 以降</span><span class="sxs-lookup"><span data-stu-id="63ed0-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="63ed0-125">[バージョン 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) [(KB4515384)](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="63ed0-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="63ed0-126">[KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)のバージョン[1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)</span><span class="sxs-lookup"><span data-stu-id="63ed0-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="63ed0-127">[バージョン 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="63ed0-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="63ed0-128">[バージョン 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="63ed0-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="63ed0-129">**Windows Server 2019 - パブリック プレビューにのみ適用**</span><span class="sxs-lookup"><span data-stu-id="63ed0-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="63ed0-130">バージョン 1903 以降 [(KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)を使用)</span><span class="sxs-lookup"><span data-stu-id="63ed0-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="63ed0-131">バージョン 1809 [(KB4537818 付](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)き)</span><span class="sxs-lookup"><span data-stu-id="63ed0-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="63ed0-132">**[詳細設定] ページからライブ応答を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="63ed0-133">[高度な機能の設定] ページでライブ応答機能 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="63ed0-134">これらの設定を編集できるのは、セキュリティまたはグローバル管理者の役割を管理するユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="63ed0-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="63ed0-135">**[詳細設定] ページ (推奨) からサーバーのライブ応答を有効** にします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="63ed0-136">これらの設定を編集できるのは、セキュリティまたはグローバル管理者の役割を管理するユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="63ed0-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="63ed0-137">**デバイスにオートメーション修復レベルが割り当てられているか確認します**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="63ed0-138">少なくとも、特定のデバイス グループの最小修復レベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="63ed0-139">それ以外の場合は、そのグループのメンバーに対してライブ応答セッションを確立できません。</span><span class="sxs-lookup"><span data-stu-id="63ed0-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="63ed0-140">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-140">You'll receive the following error:</span></span>

    ![エラー メッセージのイメージ](images/live-response-error.png)

- <span data-ttu-id="63ed0-142">**ライブ応答の署名されていないスクリプトの実行を有効** にする (オプション)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="63ed0-143">署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="63ed0-144">署名されていないスクリプトを実行すると、脅威にさらされる可能性が高くなされるため、お勧めできません。</span><span class="sxs-lookup"><span data-stu-id="63ed0-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="63ed0-145">ただし、それらを使用する必要がある場合は、[高度な機能の設定] ページで設定 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="63ed0-146">**適切なアクセス許可を持っている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="63ed0-147">適切なアクセス許可を持つプロビジョニングされたユーザーだけがセッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="63ed0-148">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="63ed0-149">ライブラリにファイルをアップロードするオプションは、適切な RBAC アクセス許可を持つユーザーにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="63ed0-150">委任されたアクセス許可のみを持つユーザーの場合、ボタンはグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="63ed0-151">付与されている役割に応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="63ed0-152">ユーザーのアクセス許可は、RBAC カスタム ロールによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="63ed0-153">ライブ応答ダッシュボードの概要</span><span class="sxs-lookup"><span data-stu-id="63ed0-153">Live response dashboard overview</span></span>
<span data-ttu-id="63ed0-154">デバイスでライブ応答セッションを開始すると、ダッシュボードが開きます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="63ed0-155">ダッシュボードには、次のようなセッションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="63ed0-156">セッションを作成したユーザー</span><span class="sxs-lookup"><span data-stu-id="63ed0-156">Who created the session</span></span>
- <span data-ttu-id="63ed0-157">セッションが開始された場合</span><span class="sxs-lookup"><span data-stu-id="63ed0-157">When the session started</span></span>
- <span data-ttu-id="63ed0-158">セッションの期間</span><span class="sxs-lookup"><span data-stu-id="63ed0-158">The duration of the session</span></span>

<span data-ttu-id="63ed0-159">ダッシュボードでは、次の情報にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="63ed0-160">セッションを切断する</span><span class="sxs-lookup"><span data-stu-id="63ed0-160">Disconnect session</span></span>
- <span data-ttu-id="63ed0-161">ライブラリへのファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="63ed0-161">Upload files to the library</span></span> 
- <span data-ttu-id="63ed0-162">コマンド コンソール</span><span class="sxs-lookup"><span data-stu-id="63ed0-162">Command console</span></span>
- <span data-ttu-id="63ed0-163">コマンド ログ</span><span class="sxs-lookup"><span data-stu-id="63ed0-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="63ed0-164">デバイスでライブ応答セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="63ed0-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="63ed0-165">Microsoft Defender セキュリティ センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="63ed0-166">[デバイス] リスト ページに移動し、調査するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="63ed0-167">[デバイス] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-167">The devices page opens.</span></span>

3. <span data-ttu-id="63ed0-168">[ライブ応答セッションの開始] を選択して、ライブ **応答セッションを起動します**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="63ed0-169">コマンド コンソールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-169">A command console is displayed.</span></span> <span data-ttu-id="63ed0-170">セッションがデバイスに接続するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="63ed0-171">組み込みのコマンドを使用して調査作業を行います。</span><span class="sxs-lookup"><span data-stu-id="63ed0-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="63ed0-172">詳細については、「ライブ応答コマンド [」を参照してください](#live-response-commands)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="63ed0-173">調査が完了したら、[セッションの切断] **を選択し**、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="63ed0-174">ライブ応答コマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-174">Live response commands</span></span>

<span data-ttu-id="63ed0-175">付与されている役割に応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="63ed0-176">ユーザーのアクセス許可は、RBAC カスタム ロールによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="63ed0-177">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="63ed0-178">ライブ応答はクラウドベースの対話型シェルであり、エンド ユーザーとターゲット デバイスの間のネットワーク品質とシステム負荷に応じて、特定のコマンド エクスペリエンスが応答時間によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="63ed0-179">基本コマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-179">Basic commands</span></span>

<span data-ttu-id="63ed0-180">次のコマンドは、基本的なライブ応答コマンドを実行する機能が付与されたユーザー **ロールで** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="63ed0-181">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="63ed0-182">コマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-182">Command</span></span> | <span data-ttu-id="63ed0-183">説明</span><span class="sxs-lookup"><span data-stu-id="63ed0-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="63ed0-184">現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="63ed0-185">コンソール画面をクリアします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="63ed0-186">デバイスへのライブ応答セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="63ed0-187">すべてのアクティブな接続を表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="63ed0-188">ディレクトリ内のファイルとサブディレクトリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="63ed0-189">バックグラウンドでファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="63ed0-190">ドライバー</span><span class="sxs-lookup"><span data-stu-id="63ed0-190">drivers</span></span> |  <span data-ttu-id="63ed0-191">デバイスにインストールされているすべてのドライバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="63ed0-192">ファイルのダウンロードをフォアグラウンドに返します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="63ed0-193">ファイルに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="63ed0-194">デバイス上の特定の名前でファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="63ed0-195">ライブ応答コマンドのヘルプ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="63ed0-196">デバイス上のすべての既知の永続化メソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="63ed0-197">デバイスで実行しているすべてのプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="63ed0-198">レジストリ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="63ed0-199">デバイス上のすべてのスケジュールされたタスクを表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="63ed0-200">デバイス上のすべてのサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="63ed0-201">ターミナルのログ モードをデバッグに設定します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="63ed0-202">高度なコマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-202">Advanced commands</span></span>
<span data-ttu-id="63ed0-203">次のコマンドは、高度なライブ応答コマンドを実行する機能が付与されたユーザー **ロールで** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="63ed0-204">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="63ed0-205">コマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-205">Command</span></span> | <span data-ttu-id="63ed0-206">説明</span><span class="sxs-lookup"><span data-stu-id="63ed0-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="63ed0-207">さまざまな犯罪エンジンを使用してエンティティを分析し、評決に達します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="63ed0-208">デバイスからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="63ed0-209">注: このコマンドには、前提条件のコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="63ed0-210">このコマンドを組み `-auto` 合わせて使用すると `getfile` 、前提条件コマンドを自動的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="63ed0-211">デバイス上のライブラリから PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="63ed0-212">ライブ応答ライブラリにアップロードされたファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="63ed0-213">ライブラリからデバイスにファイルを置く。</span><span class="sxs-lookup"><span data-stu-id="63ed0-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="63ed0-214">ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="63ed0-215">デバイス上のエンティティを修復します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-215">Remediates an entity on the device.</span></span> <span data-ttu-id="63ed0-216">修復アクションは、エンティティの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="63ed0-217">- ファイル: 削除</span><span class="sxs-lookup"><span data-stu-id="63ed0-217">- File: delete</span></span><br><span data-ttu-id="63ed0-218">- プロセス: イメージ ファイルを停止、削除する</span><span class="sxs-lookup"><span data-stu-id="63ed0-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="63ed0-219">- サービス: イメージ ファイルの停止、削除</span><span class="sxs-lookup"><span data-stu-id="63ed0-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="63ed0-220">- レジストリ エントリ: 削除</span><span class="sxs-lookup"><span data-stu-id="63ed0-220">- Registry entry: delete</span></span><br><span data-ttu-id="63ed0-221">- スケジュールされたタスク: 削除</span><span class="sxs-lookup"><span data-stu-id="63ed0-221">- Scheduled task: remove</span></span><br><span data-ttu-id="63ed0-222">- スタートアップ フォルダーアイテム: ファイルの削除</span><span class="sxs-lookup"><span data-stu-id="63ed0-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="63ed0-223">注: このコマンドには、前提条件のコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="63ed0-224">このコマンドを組み `-auto` 合わせて使用すると `remediate` 、前提条件コマンドを自動的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="63ed0-225">修復されたエンティティを復元します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="63ed0-226">ライブ応答コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="63ed0-226">Use live response commands</span></span>

<span data-ttu-id="63ed0-227">コンソールで使用できるコマンドは、Windows コマンドと同様の原則 [に従います](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)。</span><span class="sxs-lookup"><span data-stu-id="63ed0-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="63ed0-228">高度なコマンドは、ファイルのダウンロードとアップロード、デバイスでのスクリプトの実行、エンティティに対する修復アクションの実行など、より強力なアクションを実行できる、より堅牢なアクションセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="63ed0-229">デバイスからファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="63ed0-229">Get a file from the device</span></span>

<span data-ttu-id="63ed0-230">調査中のデバイスからファイルを取得するシナリオでは、このコマンドを使用 `getfile` できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="63ed0-231">これにより、詳細な調査のためにデバイスからファイルを保存できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="63ed0-232">次のファイル サイズの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="63ed0-233">`getfile` limit: 3 GB</span><span class="sxs-lookup"><span data-stu-id="63ed0-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="63ed0-234">`fileinfo` limit: 10 GB</span><span class="sxs-lookup"><span data-stu-id="63ed0-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="63ed0-235">`library` limit: 250 MB</span><span class="sxs-lookup"><span data-stu-id="63ed0-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="63ed0-236">バックグラウンドでファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="63ed0-236">Download a file in the background</span></span>

<span data-ttu-id="63ed0-237">セキュリティ運用チームが影響を受けるデバイスの調査を続行するために、ファイルをバックグラウンドでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="63ed0-238">バックグラウンドでファイルをダウンロードするには、ライブ応答コマンド コンソールに「. `download <file_path> &`</span><span class="sxs-lookup"><span data-stu-id="63ed0-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="63ed0-239">ファイルのダウンロードを待っている場合は、Ctrl + Z を使用してバックグラウンドに移動できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="63ed0-240">ファイルのダウンロードをフォアグラウンドに移動するには、ライブ応答コマンド コンソールに `fg <command_id>` 「.</span><span class="sxs-lookup"><span data-stu-id="63ed0-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="63ed0-241">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-241">Here are some examples:</span></span>


|<span data-ttu-id="63ed0-242">コマンド</span><span class="sxs-lookup"><span data-stu-id="63ed0-242">Command</span></span>  |<span data-ttu-id="63ed0-243">目的</span><span class="sxs-lookup"><span data-stu-id="63ed0-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="63ed0-244">バックグラウンドで *some_file.exeダウンロードを* 開始します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="63ed0-245">コマンド ID *1234* のダウンロードをフォアグラウンドに返します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="63ed0-246">ライブラリにファイルを置く</span><span class="sxs-lookup"><span data-stu-id="63ed0-246">Put a file in the library</span></span>

<span data-ttu-id="63ed0-247">ライブ応答には、ファイルを挿入できるライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="63ed0-248">ライブラリには、テナント レベルでライブ応答セッションで実行できるファイル (スクリプトなど) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="63ed0-249">ライブ応答を使用すると、PowerShell スクリプトを実行することができますが、ファイルを実行する前に、まずファイルをライブラリに挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="63ed0-250">ライブ応答セッションを開始するデバイスで実行できる PowerShell スクリプトのコレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="63ed0-251">ライブラリ内のファイルをアップロードするには</span><span class="sxs-lookup"><span data-stu-id="63ed0-251">To upload a file in the library</span></span>

1. <span data-ttu-id="63ed0-252">[ファイル **をライブラリにアップロード] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="63ed0-253">[参照 **] をクリック** し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="63ed0-254">簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-254">Provide a brief description.</span></span>

4. <span data-ttu-id="63ed0-255">同じ名前のファイルを上書きするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="63ed0-256">スクリプトに必要なパラメーターを知りたい場合は、[スクリプト パラメーター] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="63ed0-257">テキスト フィールドに例と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="63ed0-258">[確認 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="63ed0-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="63ed0-259">(省略可能)ファイルがライブラリにアップロードされたと確認するには、コマンドを実行 `library` します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="63ed0-260">コマンドの取り消し</span><span class="sxs-lookup"><span data-stu-id="63ed0-260">Cancel a command</span></span>
<span data-ttu-id="63ed0-261">セッション中は、Ctrl + C キーを押してコマンドをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="63ed0-262">このショートカットを使用すると、エージェント側でコマンドが停止しない。</span><span class="sxs-lookup"><span data-stu-id="63ed0-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="63ed0-263">このコマンドは、ポータル内のコマンドのみを取り消します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="63ed0-264">したがって、"修復" などの操作を変更すると、コマンドが取り消される間、続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="63ed0-265">前提条件コマンドを自動的に実行する</span><span class="sxs-lookup"><span data-stu-id="63ed0-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="63ed0-266">一部のコマンドには、実行する前提条件のコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="63ed0-267">前提条件コマンドを実行しない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="63ed0-268">たとえば、コマンドを実行せずに `download` 実行 `fileinfo` すると、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="63ed0-269">自動フラグを使用すると、次に示す前提条件コマンドを自動的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="63ed0-270">PowerShell スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="63ed0-270">Run a PowerShell script</span></span> 

<span data-ttu-id="63ed0-271">PowerShell スクリプトを実行する前に、まずライブラリにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="63ed0-272">スクリプトをライブラリにアップロードした後、コマンド `run` を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="63ed0-273">セッションで署名されていないスクリプトを使用する場合は、[高度な機能の設定] ページで設定 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="63ed0-274">署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="63ed0-275">コマンド パラメーターの適用</span><span class="sxs-lookup"><span data-stu-id="63ed0-275">Apply command parameters</span></span>

- <span data-ttu-id="63ed0-276">コマンド パラメーターの詳細については、コンソール のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63ed0-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="63ed0-277">個々のコマンドの詳細については、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="63ed0-278">コマンドにパラメーターを適用する場合、パラメーターは固定順序に基づいて処理されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="63ed0-279">固定順序以外のパラメーターを指定する場合は、値を指定する前に、パラメーターの名前をハイフンで指定します。</span><span class="sxs-lookup"><span data-stu-id="63ed0-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="63ed0-280">必須コマンドがあるコマンドを使用する場合は、フラグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="63ed0-281">`<command name> -type file -id <file path> - auto` または `remediate file <file path> - auto`。</span><span class="sxs-lookup"><span data-stu-id="63ed0-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="63ed0-282">サポートされている出力の種類</span><span class="sxs-lookup"><span data-stu-id="63ed0-282">Supported output types</span></span>

<span data-ttu-id="63ed0-283">ライブ応答は、テーブルと JSON 形式の出力の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="63ed0-284">コマンドごとに、既定の出力動作があります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="63ed0-285">次のコマンドを使用して、出力を好みの出力形式で変更できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="63ed0-286">スペースが限られているので、テーブル形式で表示されるフィールドは少なめになります。</span><span class="sxs-lookup"><span data-stu-id="63ed0-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="63ed0-287">出力の詳細を表示するには、JSON 出力コマンドを使用して詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="63ed0-288">サポートされている出力パイプ</span><span class="sxs-lookup"><span data-stu-id="63ed0-288">Supported output pipes</span></span>

<span data-ttu-id="63ed0-289">ライブ応答は、CLI とファイルへの出力パイプをサポートします。</span><span class="sxs-lookup"><span data-stu-id="63ed0-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="63ed0-290">CLI は既定の出力動作です。</span><span class="sxs-lookup"><span data-stu-id="63ed0-290">CLI is the default output behavior.</span></span> <span data-ttu-id="63ed0-291">[command] コマンドと [filename].txt を使用して、出力をファイル>パイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="63ed0-292">例:</span><span class="sxs-lookup"><span data-stu-id="63ed0-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="63ed0-293">コマンド ログの表示</span><span class="sxs-lookup"><span data-stu-id="63ed0-293">View the command log</span></span>

<span data-ttu-id="63ed0-294">[コマンド **ログ] タブを** 選択すると、セッション中にデバイスで使用されるコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="63ed0-295">各コマンドは、次のような完全な詳細で追跡されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="63ed0-296">ID</span><span class="sxs-lookup"><span data-stu-id="63ed0-296">ID</span></span>
- <span data-ttu-id="63ed0-297">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="63ed0-297">Command line</span></span>
- <span data-ttu-id="63ed0-298">Duration</span><span class="sxs-lookup"><span data-stu-id="63ed0-298">Duration</span></span>
- <span data-ttu-id="63ed0-299">状態と入力または出力のサイド バー</span><span class="sxs-lookup"><span data-stu-id="63ed0-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="63ed0-300">制限事項</span><span class="sxs-lookup"><span data-stu-id="63ed0-300">Limitations</span></span>

- <span data-ttu-id="63ed0-301">ライブ応答セッションは、一度に 10 回のライブ応答セッションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="63ed0-302">大規模なコマンド実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63ed0-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="63ed0-303">ライブ応答セッションの非アクティブタイムアウト値は 5 分です。</span><span class="sxs-lookup"><span data-stu-id="63ed0-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="63ed0-304">ユーザーは一度に 1 つのセッションのみを開始できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="63ed0-305">デバイスは、一度に 1 つのセッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="63ed0-306">次のファイル サイズの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="63ed0-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="63ed0-307">`getfile` limit: 3 GB</span><span class="sxs-lookup"><span data-stu-id="63ed0-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="63ed0-308">`fileinfo` limit: 10 GB</span><span class="sxs-lookup"><span data-stu-id="63ed0-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="63ed0-309">`library` limit: 250 MB</span><span class="sxs-lookup"><span data-stu-id="63ed0-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="63ed0-310">関連記事</span><span class="sxs-lookup"><span data-stu-id="63ed0-310">Related article</span></span>
- [<span data-ttu-id="63ed0-311">ライブ応答コマンドの例</span><span class="sxs-lookup"><span data-stu-id="63ed0-311">Live response command examples</span></span>](live-response-command-examples.md)
