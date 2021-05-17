---
title: Microsoft Defender for Endpoint のライブ応答を使用してデバイス上のエンティティを調査する
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
ms.openlocfilehash: fc1c1e0d3f68016651c04521e04ce348e5ab9a65
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246467"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="f1fbe-104">ライブ応答を使用してデバイス上のエンティティを調査する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1fbe-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f1fbe-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1fbe-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f1fbe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1fbe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1fbe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f1fbe-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f1fbe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f1fbe-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f1fbe-110">ライブ応答により、セキュリティ運用チームはリモート シェル接続を使用してデバイス (コンピューターとも呼ばれます) に瞬時にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="f1fbe-111">これにより、詳細な調査作業を行い、迅速に特定された脅威をリアルタイムに含める即時対応アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="f1fbe-112">ライブ応答は、セキュリティ運用チームが法医学データを収集し、スクリプトを実行し、分析のために疑わしいエンティティを送信し、脅威を修復し、新たな脅威を積極的に捜し出して調査を強化するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="f1fbe-113">ライブ応答を使用すると、アナリストは次のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="f1fbe-114">基本的なコマンドと高度なコマンドを実行して、デバイスで調査作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="f1fbe-115">PowerShell スクリプトのマルウェア サンプルや結果などのファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="f1fbe-116">バックグラウンドでファイルをダウンロードする (new!)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="f1fbe-117">アップロード PowerShell スクリプトまたは実行可能ファイルをライブラリに追加し、テナント レベルからデバイスで実行します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="f1fbe-118">修復アクションを実行または元に戻します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f1fbe-119">はじめに</span><span class="sxs-lookup"><span data-stu-id="f1fbe-119">Before you begin</span></span>

<span data-ttu-id="f1fbe-120">デバイスでセッションを開始する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="f1fbe-121">**サポートされているバージョンのファイルを** 実行Windows。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="f1fbe-122">デバイスは、次のいずれかのバージョンのデバイスを実行している必要Windows</span><span class="sxs-lookup"><span data-stu-id="f1fbe-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="f1fbe-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="f1fbe-123">**Windows 10**</span></span>
    - <span data-ttu-id="f1fbe-124">[バージョン 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) 以降</span><span class="sxs-lookup"><span data-stu-id="f1fbe-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="f1fbe-125">[バージョン 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) [(KB4515384)](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="f1fbe-126">[KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)のバージョン[1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="f1fbe-127">[バージョン 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="f1fbe-128">[バージョン 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="f1fbe-129">**WindowsServer 2019 - パブリック プレビューにのみ適用**</span><span class="sxs-lookup"><span data-stu-id="f1fbe-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="f1fbe-130">バージョン 1903 以降 [(KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)を使用)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="f1fbe-131">バージョン 1809 [(KB4537818 付](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)き)</span><span class="sxs-lookup"><span data-stu-id="f1fbe-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="f1fbe-132">**[詳細設定] ページからライブ応答を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="f1fbe-133">[高度な機能の設定] ページでライブ応答機能 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f1fbe-134">これらの設定を編集できるのは、セキュリティまたはグローバル管理者の役割を管理するユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="f1fbe-135">**[詳細設定] ページ (推奨) からサーバーのライブ応答を有効** にします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="f1fbe-136">これらの設定を編集できるのは、セキュリティまたはグローバル管理者の役割を管理するユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="f1fbe-137">**デバイスにオートメーション修復レベルが割り当てられているか確認します**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="f1fbe-138">少なくとも、特定のデバイス グループの最小修復レベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="f1fbe-139">それ以外の場合は、そのグループのメンバーに対してライブ応答セッションを確立できません。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="f1fbe-140">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-140">You'll receive the following error:</span></span>

    ![エラー メッセージのイメージ](images/live-response-error.png)

- <span data-ttu-id="f1fbe-142">**ライブ応答の署名されていないスクリプトの実行を有効** にする (オプション)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="f1fbe-143">署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="f1fbe-144">署名されていないスクリプトを実行すると、脅威にさらされる可能性が高くなされるため、お勧めできません。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="f1fbe-145">ただし、それらを使用する必要がある場合は、[高度な機能の設定] ページで設定 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="f1fbe-146">**適切なアクセス許可を持っている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="f1fbe-147">適切なアクセス許可を持つプロビジョニングされたユーザーだけがセッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="f1fbe-148">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="f1fbe-149">ライブラリにファイルをアップロードするオプションは、適切な RBAC アクセス許可を持つユーザーにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="f1fbe-150">委任されたアクセス許可のみを持つユーザーの場合、ボタンはグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="f1fbe-151">付与されている役割に応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="f1fbe-152">ユーザーのアクセス許可は、RBAC カスタム ロールによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="f1fbe-153">ライブ応答ダッシュボードの概要</span><span class="sxs-lookup"><span data-stu-id="f1fbe-153">Live response dashboard overview</span></span>
<span data-ttu-id="f1fbe-154">デバイスでライブ応答セッションを開始すると、ダッシュボードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="f1fbe-155">ダッシュボードには、次のようなセッションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="f1fbe-156">Who作成されたセッション</span><span class="sxs-lookup"><span data-stu-id="f1fbe-156">Who created the session</span></span>
- <span data-ttu-id="f1fbe-157">セッションが開始された場合</span><span class="sxs-lookup"><span data-stu-id="f1fbe-157">When the session started</span></span>
- <span data-ttu-id="f1fbe-158">セッションの期間</span><span class="sxs-lookup"><span data-stu-id="f1fbe-158">The duration of the session</span></span>

<span data-ttu-id="f1fbe-159">ダッシュボードでは、次の情報にアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="f1fbe-160">セッションを切断する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-160">Disconnect session</span></span>
- <span data-ttu-id="f1fbe-161">アップロードライブラリにファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-161">Upload files to the library</span></span> 
- <span data-ttu-id="f1fbe-162">コマンド コンソール</span><span class="sxs-lookup"><span data-stu-id="f1fbe-162">Command console</span></span>
- <span data-ttu-id="f1fbe-163">コマンド ログ</span><span class="sxs-lookup"><span data-stu-id="f1fbe-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="f1fbe-164">デバイスでライブ応答セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="f1fbe-165">サインインしてMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="f1fbe-166">[デバイス] リスト ページに移動し、調査するデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="f1fbe-167">[デバイス] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-167">The devices page opens.</span></span>

3. <span data-ttu-id="f1fbe-168">[ライブ応答セッションの開始] を選択して、ライブ **応答セッションを起動します**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="f1fbe-169">コマンド コンソールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-169">A command console is displayed.</span></span> <span data-ttu-id="f1fbe-170">セッションがデバイスに接続するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="f1fbe-171">組み込みのコマンドを使用して調査作業を行います。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="f1fbe-172">詳細については、「ライブ応答コマンド [」を参照してください](#live-response-commands)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="f1fbe-173">調査が完了したら、[セッションの切断] **を選択し**、[確認] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="f1fbe-174">ライブ応答コマンド</span><span class="sxs-lookup"><span data-stu-id="f1fbe-174">Live response commands</span></span>

<span data-ttu-id="f1fbe-175">付与されている役割に応じて、基本的なライブ応答コマンドまたは高度なライブ応答コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="f1fbe-176">ユーザーのアクセス許可は、RBAC カスタム ロールによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="f1fbe-177">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="f1fbe-178">ライブ応答はクラウドベースの対話型シェルであり、エンド ユーザーとターゲット デバイスの間のネットワーク品質とシステム負荷に応じて、特定のコマンド エクスペリエンスが応答時間によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="f1fbe-179">基本コマンド</span><span class="sxs-lookup"><span data-stu-id="f1fbe-179">Basic commands</span></span>

<span data-ttu-id="f1fbe-180">次のコマンドは、基本的なライブ応答コマンドを実行する機能が付与されたユーザー **ロールで** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="f1fbe-181">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="f1fbe-182">コマンド</span><span class="sxs-lookup"><span data-stu-id="f1fbe-182">Command</span></span> | <span data-ttu-id="f1fbe-183">説明</span><span class="sxs-lookup"><span data-stu-id="f1fbe-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="f1fbe-184">現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="f1fbe-185">コンソール画面をクリアします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="f1fbe-186">デバイスへのライブ応答セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="f1fbe-187">すべてのアクティブな接続を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="f1fbe-188">ディレクトリ内のファイルとサブディレクトリの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="f1fbe-189">デバイスにインストールされているすべてのドライバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="f1fbe-190">指定したジョブをフォアグラウンドのフォアグラウンドに配置し、現在のジョブに設定します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="f1fbe-191">メモ: fg は、PID ではなくジョブから使用できる "コマンド ID" を受け取る</span><span class="sxs-lookup"><span data-stu-id="f1fbe-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="f1fbe-192">ファイルに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="f1fbe-193">デバイス上の特定の名前でファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="f1fbe-194">ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="f1fbe-195">ライブ応答コマンドのヘルプ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="f1fbe-196">現在実行中のジョブ、その ID、状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="f1fbe-197">デバイス上のすべての既知の永続化メソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="f1fbe-198">デバイスで実行しているすべてのプロセスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="f1fbe-199">レジストリ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="f1fbe-200">デバイス上のすべてのスケジュールされたタスクを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="f1fbe-201">デバイス上のすべてのサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="f1fbe-202">ターミナルのログ モードをデバッグに設定します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="f1fbe-203">高度なコマンド</span><span class="sxs-lookup"><span data-stu-id="f1fbe-203">Advanced commands</span></span>
<span data-ttu-id="f1fbe-204">次のコマンドは、高度なライブ応答コマンドを実行する機能が付与されたユーザー **ロールで** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="f1fbe-205">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="f1fbe-206">コマンド</span><span class="sxs-lookup"><span data-stu-id="f1fbe-206">Command</span></span> | <span data-ttu-id="f1fbe-207">説明</span><span class="sxs-lookup"><span data-stu-id="f1fbe-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="f1fbe-208">さまざまな犯罪エンジンを使用してエンティティを分析し、評決に達します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="f1fbe-209">デバイス上のライブラリから PowerShell スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="f1fbe-210">ライブ応答ライブラリにアップロードされたファイルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="f1fbe-211">ライブラリからデバイスにファイルを置く。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="f1fbe-212">ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="f1fbe-213">デバイス上のエンティティを修復します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-213">Remediates an entity on the device.</span></span> <span data-ttu-id="f1fbe-214">修復アクションは、エンティティの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="f1fbe-215">- ファイル: 削除</span><span class="sxs-lookup"><span data-stu-id="f1fbe-215">- File: delete</span></span><br><span data-ttu-id="f1fbe-216">- プロセス: イメージ ファイルを停止、削除する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="f1fbe-217">- サービス: イメージ ファイルの停止、削除</span><span class="sxs-lookup"><span data-stu-id="f1fbe-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="f1fbe-218">- レジストリ エントリ: 削除</span><span class="sxs-lookup"><span data-stu-id="f1fbe-218">- Registry entry: delete</span></span><br><span data-ttu-id="f1fbe-219">- スケジュールされたタスク: 削除</span><span class="sxs-lookup"><span data-stu-id="f1fbe-219">- Scheduled task: remove</span></span><br><span data-ttu-id="f1fbe-220">- スタートアップ フォルダーアイテム: ファイルの削除</span><span class="sxs-lookup"><span data-stu-id="f1fbe-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="f1fbe-221">注: このコマンドには、前提条件のコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="f1fbe-222">このコマンドを組み `-auto` 合わせて使用すると `remediate` 、前提条件コマンドを自動的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="f1fbe-223">修復されたエンティティを復元します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="f1fbe-224">ライブ応答コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="f1fbe-224">Use live response commands</span></span>

<span data-ttu-id="f1fbe-225">コンソールで使用できるコマンドは、「コマンド」と同様の原則[Windows従います](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-225">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="f1fbe-226">高度なコマンドは、ファイルのダウンロードとアップロード、デバイスでのスクリプトの実行、エンティティに対する修復アクションの実行など、より強力なアクションを実行できる、より堅牢なアクションセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="f1fbe-227">デバイスからファイルを取得する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-227">Get a file from the device</span></span>

<span data-ttu-id="f1fbe-228">調査中のデバイスからファイルを取得するシナリオでは、このコマンドを使用 `getfile` できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="f1fbe-229">これにより、詳細な調査のためにデバイスからファイルを保存できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="f1fbe-230">次のファイル サイズの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="f1fbe-231">`getfile` limit: 3 GB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="f1fbe-232">`fileinfo` limit: 10 GB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="f1fbe-233">`library` limit: 250 MB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="f1fbe-234">バックグラウンドでファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f1fbe-234">Download a file in the background</span></span>

<span data-ttu-id="f1fbe-235">セキュリティ運用チームが影響を受けるデバイスの調査を続行するために、ファイルをバックグラウンドでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="f1fbe-236">バックグラウンドでファイルをダウンロードするには、ライブ応答コマンド コンソールに「. `download <file_path> &`</span><span class="sxs-lookup"><span data-stu-id="f1fbe-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="f1fbe-237">ファイルのダウンロードを待っている場合は、Ctrl + Z を使用してバックグラウンドに移動できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="f1fbe-238">ファイルのダウンロードをフォアグラウンドに移動するには、ライブ応答コマンド コンソールに `fg <command_id>` 「.</span><span class="sxs-lookup"><span data-stu-id="f1fbe-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="f1fbe-239">次に、いくつかの例を示します:</span><span class="sxs-lookup"><span data-stu-id="f1fbe-239">Here are some examples:</span></span>


|<span data-ttu-id="f1fbe-240">command</span><span class="sxs-lookup"><span data-stu-id="f1fbe-240">Command</span></span>  |<span data-ttu-id="f1fbe-241">目的</span><span class="sxs-lookup"><span data-stu-id="f1fbe-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="f1fbe-242">バックグラウンドで *some_file.exeダウンロードを* 開始します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="f1fbe-243">コマンド ID *1234* のダウンロードをフォアグラウンドに返します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="f1fbe-244">ライブラリにファイルを置く</span><span class="sxs-lookup"><span data-stu-id="f1fbe-244">Put a file in the library</span></span>

<span data-ttu-id="f1fbe-245">ライブ応答には、ファイルを挿入できるライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="f1fbe-246">ライブラリには、テナント レベルでライブ応答セッションで実行できるファイル (スクリプトなど) が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="f1fbe-247">ライブ応答を使用すると、PowerShell スクリプトを実行することができますが、ファイルを実行する前に、まずファイルをライブラリに挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="f1fbe-248">ライブ応答セッションを開始するデバイスで実行できる PowerShell スクリプトのコレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="f1fbe-249">ライブラリ内のファイルをアップロードするには</span><span class="sxs-lookup"><span data-stu-id="f1fbe-249">To upload a file in the library</span></span>

1. <span data-ttu-id="f1fbe-250">[ファイル **アップロードライブラリ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="f1fbe-251">[参照 **] をクリック** し、ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="f1fbe-252">簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-252">Provide a brief description.</span></span>

4. <span data-ttu-id="f1fbe-253">同じ名前のファイルを上書きするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="f1fbe-254">スクリプトに必要なパラメーターを知りたい場合は、[スクリプト パラメーター] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="f1fbe-255">テキスト フィールドに例と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="f1fbe-256">[確認 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="f1fbe-257">(省略可能)ファイルがライブラリにアップロードされたと確認するには、コマンドを実行 `library` します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="f1fbe-258">コマンドの取り消し</span><span class="sxs-lookup"><span data-stu-id="f1fbe-258">Cancel a command</span></span>
<span data-ttu-id="f1fbe-259">セッション中は、Ctrl + C キーを押してコマンドをキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="f1fbe-260">このショートカットを使用すると、エージェント側でコマンドが停止しない。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="f1fbe-261">このコマンドは、ポータル内のコマンドのみを取り消します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="f1fbe-262">したがって、"修復" などの操作を変更すると、コマンドが取り消される間、続行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="f1fbe-263">PowerShell スクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="f1fbe-263">Run a PowerShell script</span></span> 

<span data-ttu-id="f1fbe-264">PowerShell スクリプトを実行する前に、まずライブラリにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="f1fbe-265">スクリプトをライブラリにアップロードした後、コマンド `run` を使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="f1fbe-266">セッションで署名されていないスクリプトを使用する場合は、[高度な機能の設定] ページで設定 [を有効にする必要](advanced-features.md) があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="f1fbe-267">署名されていないスクリプトの使用を許可すると、脅威にさらされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="f1fbe-268">コマンド パラメーターの適用</span><span class="sxs-lookup"><span data-stu-id="f1fbe-268">Apply command parameters</span></span>

- <span data-ttu-id="f1fbe-269">コマンド パラメーターの詳細については、コンソール のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="f1fbe-270">個々のコマンドの詳細については、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="f1fbe-271">コマンドにパラメーターを適用する場合、パラメーターは固定順序に基づいて処理されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="f1fbe-272">固定順序以外のパラメーターを指定する場合は、値を指定する前に、パラメーターの名前をハイフンで指定します。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="f1fbe-273">必須コマンドがあるコマンドを使用する場合は、フラグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="f1fbe-274">`<command name> -type file -id <file path> - auto` または `remediate file <file path> - auto`。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="f1fbe-275">サポートされている出力の種類</span><span class="sxs-lookup"><span data-stu-id="f1fbe-275">Supported output types</span></span>

<span data-ttu-id="f1fbe-276">ライブ応答は、テーブルと JSON 形式の出力の種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="f1fbe-277">コマンドごとに、既定の出力動作があります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="f1fbe-278">次のコマンドを使用して、出力を好みの出力形式で変更できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="f1fbe-279">スペースが限られているので、テーブル形式で表示されるフィールドは少なめになります。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="f1fbe-280">出力の詳細を表示するには、JSON 出力コマンドを使用して詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="f1fbe-281">サポートされている出力パイプ</span><span class="sxs-lookup"><span data-stu-id="f1fbe-281">Supported output pipes</span></span>

<span data-ttu-id="f1fbe-282">ライブ応答は、CLI とファイルへの出力パイプをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="f1fbe-283">CLI は既定の出力動作です。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-283">CLI is the default output behavior.</span></span> <span data-ttu-id="f1fbe-284">[command] コマンドと [filename]コマンドを使用して、出力をファイル>パイプ.txt。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="f1fbe-285">例:</span><span class="sxs-lookup"><span data-stu-id="f1fbe-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="f1fbe-286">コマンド ログの表示</span><span class="sxs-lookup"><span data-stu-id="f1fbe-286">View the command log</span></span>

<span data-ttu-id="f1fbe-287">[コマンド **ログ] タブを** 選択すると、セッション中にデバイスで使用されるコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="f1fbe-288">各コマンドは、次のような完全な詳細で追跡されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="f1fbe-289">ID</span><span class="sxs-lookup"><span data-stu-id="f1fbe-289">ID</span></span>
- <span data-ttu-id="f1fbe-290">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="f1fbe-290">Command line</span></span>
- <span data-ttu-id="f1fbe-291">Duration</span><span class="sxs-lookup"><span data-stu-id="f1fbe-291">Duration</span></span>
- <span data-ttu-id="f1fbe-292">状態と入力または出力のサイド バー</span><span class="sxs-lookup"><span data-stu-id="f1fbe-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="f1fbe-293">制限事項</span><span class="sxs-lookup"><span data-stu-id="f1fbe-293">Limitations</span></span>

- <span data-ttu-id="f1fbe-294">ライブ応答セッションは、一度に 25 のライブ応答セッションに制限されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="f1fbe-295">ライブ応答セッションの非アクティブタイムアウト値は 30 分です。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="f1fbe-296">ユーザーは最大 10 の同時セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="f1fbe-297">デバイスは、一度に 1 つのセッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="f1fbe-298">次のファイル サイズの制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1fbe-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="f1fbe-299">`getfile` limit: 3 GB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="f1fbe-300">`fileinfo` limit: 10 GB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="f1fbe-301">`library` limit: 250 MB</span><span class="sxs-lookup"><span data-stu-id="f1fbe-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="f1fbe-302">関連記事</span><span class="sxs-lookup"><span data-stu-id="f1fbe-302">Related article</span></span>
- [<span data-ttu-id="f1fbe-303">ライブ応答コマンドの例</span><span class="sxs-lookup"><span data-stu-id="f1fbe-303">Live response command examples</span></span>](live-response-command-examples.md)
