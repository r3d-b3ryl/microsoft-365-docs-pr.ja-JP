---
title: 手順 1 - デバイスとアプリの準備
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 環境内のデバイスとアプリの準備を評価する方法について説明します。
ms.openlocfilehash: 2059904bf7c0f89876c2142d83212ce75542c505
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073157"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="02c67-103">手順 1: デバイスとアプリの準備</span><span class="sxs-lookup"><span data-stu-id="02c67-103">Step 1: Device and App Readiness</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="02c67-104"><strong>手順 1: デバイスとアプリの準備</strong></span><span class="sxs-lookup"><span data-stu-id="02c67-104"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="02c67-105">デバイスとアプリのインベントリを使用してデスクトップ展開プロジェクトを開始し、転送する必要があるものに優先度を設定し、優先度が設定されたアプリとデバイスをテストし、展開の準備に必要なものを修復します。</span><span class="sxs-lookup"><span data-stu-id="02c67-105">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you need to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="02c67-106">デバイスとアプリの準備は、推奨されている展開プロセスの輪における最初の手順であり、アプリケーションとハードウェアの互換性に関する包括的な側面をカバーします。</span><span class="sxs-lookup"><span data-stu-id="02c67-106">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility.</span></span> <span data-ttu-id="02c67-107">デスクトップ展開プロセス全体を確認するには、[デスクトップ展開センター](https://aka.ms/HowToShift)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02c67-107">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="02c67-p102">これまで、ユーザーのデスクトップをアップグレードする際には、アプリケーションとハードウェアの互換性が大きなハードルになっていました。Windows 10 および Office 365 ProPlus への移行を計画しているときには、好都合なことに、過去 10 年間に作成されたアプリケーションのほとんどが Windows 10 で稼働するものであり、組織が Office 2010 以降の各バージョンで使用している COM アドインと VBA マクロは最新バージョンの Office でも変更なしで動作します。</span><span class="sxs-lookup"><span data-stu-id="02c67-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="02c67-110">そのため、組織の規模と歴史によっては、アプリケーションとハードウェアの互換性を検証することが、推奨される 8 フェーズの展開プロセスにおける重要な最初の手順になることがあります。</span><span class="sxs-lookup"><span data-stu-id="02c67-110">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="02c67-111">この記事では、最初のフェーズであるデバイスとアプリの準備に、新しい Windows Analytics の Upgrade Readiness ツールなどの Microsoft の準備状況評価ツールを使用する方法について説明します。このツールは、インテリジェントなクラウド ベースのソリューションであり、Windows ライセンスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="02c67-111">In this article we take you through that first phase – Device and App Readiness – using Microsoft readiness assessment tools including the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

## <a name="windows-10-compatibility-scan"></a><span data-ttu-id="02c67-112">Windows 10 互換性スキャン</span><span class="sxs-lookup"><span data-stu-id="02c67-112">Windows 10 Compatibility Scan</span></span>

<span data-ttu-id="02c67-113">Windows 10 を展開する前に、Windows 7、8、8.1 のいずれかを実行している既存のデバイスの準備状況を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02c67-113">Before deploying Windows 10 Microsoft recommends checking the readiness of your existing devices running Windows 7 or 8/8.1.</span></span> <span data-ttu-id="02c67-114">Windows 10 インストール メディアでは、setup.exe でアップグレードを実行するためのコマンド ライン スイッチがサポートされていますが、互換性のチェックのみを行い、実際にアップグレードを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="02c67-114">Windows 10 installation media supports a command line switch for the setup.exe to run the upgrade but only check for compatibility, not actually perform the upgrade.</span></span> <span data-ttu-id="02c67-115">ScanOnly は、スクリプト化されたバッチファイルとして実行するか、または System Center Configuration Manager のタスク シーケンスに統合できます。これには、ScanOnly をネットワークから直接実行して、Windows 10 インストールメディアをローカル デバイスにストリーミングしないようにする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02c67-115">ScanOnly can be run as a scripted batch file or integrated into a System Center Configuration Manager task sequence, including the ability to run the ScanOnly directly from the network so the Windows 10 installation media isn't streamed down to the local device.</span></span> <span data-ttu-id="02c67-116">ScanOnly が完了すると、Setup.EXE によって生成されたログファイルのリターン コードを介して結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="02c67-116">When ScanOnly completes the results are returned via return codes in log files generated by Setup.EXE.</span></span>   

<span data-ttu-id="02c67-117">互換性スキャンをサイレントで完了する ScanOnly コマンド ラインの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="02c67-117">A sample ScanOnly command line that completes the compatibility scan silently would look like the below:</span></span>

    Setup.EXE /Auto Upgrade /Quiet /NoReboot /Compat ScanOnly

<span data-ttu-id="02c67-118">ScanOnly やその他の Windows セットアップ コマンド スイッチの詳細については、「[Windows セットアップ コマンドライン オプション](https://aka.ms/setupswitches)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02c67-118">For more information on ScanOnly and other Windows setup command switches please review the [Windows Setup Commmand-line Options](https://aka.ms/setupswitches).</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="02c67-119">推奨されるツール: Windows Analytics の Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="02c67-119">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="02c67-120">Windows Analytics の Upgrade Readiness は、従来のデスクトップ管理システムよりも利点が多く、お勧めのツールです。</span><span class="sxs-lookup"><span data-stu-id="02c67-120">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool.</span></span> <span data-ttu-id="02c67-121">エージェントレスであり、何億ものコンシューマー PC のアップグレードにより収集されたアプリケーションとドライバーの互換性情報を利用して、実行する必要がある手順をガイドします。</span><span class="sxs-lookup"><span data-stu-id="02c67-121">It is agentless and guides you through what needs to be done making use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs.</span></span> <span data-ttu-id="02c67-122">その情報を使用して詳細な評価を行い、アップグレードをブロックする可能性のある互換性の問題を特定し、Microsoft が把握している修正プログラムへのリンクを提供してサポートします。</span><span class="sxs-lookup"><span data-stu-id="02c67-122">This information gives you a detailed assessment, identifying compatibility issues that might block your upgrade, supported with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="02c67-123">Window Analytics の Upgrade Readiness を設定するには、まず Azure サブスクリプションを設定し、それに Azure Log Analytics ワークスペースを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="02c67-123">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that.</span></span> <span data-ttu-id="02c67-124">Windows Analytics の Upgrade Readiness サービスが起動したことを確認したら、グループ ポリシー設定を使用してインターネットに接続された Windows 7 SP1 以降のデバイスを登録できます。とても簡単です。</span><span class="sxs-lookup"><span data-stu-id="02c67-124">Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings - it’s that simple.</span></span> <span data-ttu-id="02c67-125">エージェントを展開する必要はありません。Windows Analytics の Upgrade Readiness の視覚的なワークフローにより、パイロットから運用環境への展開をガイドします。</span><span class="sxs-lookup"><span data-stu-id="02c67-125">There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment.</span></span> <span data-ttu-id="02c67-126">必要に応じて、Windows Analytics の Upgrade Readiness から System Center Configuration Manager などのソフトウェア展開ツールにデータをエクスポートしたり、ターゲット PC に直接データをエクスポートしたりして、展開の準備が整い次第コレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="02c67-126">If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

<span data-ttu-id="02c67-127">現時点で目的の環境に Windows Analytics をセットアップしていない場合や、試用のためにサインアップしようとしている場合は、[Windows Analytics ページ](http://www.aka.ms/windowsanalytics)に移動して開始してください。</span><span class="sxs-lookup"><span data-stu-id="02c67-127">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="02c67-128">デバイスとアプリの準備プロセス</span><span class="sxs-lookup"><span data-stu-id="02c67-128">Device and App Readiness Process</span></span>

<span data-ttu-id="02c67-129">デバイスとアプリの準備は 4 つの手順で構成されています。1.</span><span class="sxs-lookup"><span data-stu-id="02c67-129">Device and App Readiness is comprised of four steps: 1.</span></span> <span data-ttu-id="02c67-130">インベントリ、2.</span><span class="sxs-lookup"><span data-stu-id="02c67-130">Inventory, 2.</span></span> <span data-ttu-id="02c67-131">優先度設定、3.</span><span class="sxs-lookup"><span data-stu-id="02c67-131">Prioritize, 3.</span></span> <span data-ttu-id="02c67-132">テスト、4.</span><span class="sxs-lookup"><span data-stu-id="02c67-132">Test, 4.</span></span> <span data-ttu-id="02c67-133">修復。</span><span class="sxs-lookup"><span data-stu-id="02c67-133">Remediate.</span></span> <span data-ttu-id="02c67-134">それぞれについて順番に確認しましょう。</span><span class="sxs-lookup"><span data-stu-id="02c67-134">Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="02c67-135">1\.</span><span class="sxs-lookup"><span data-stu-id="02c67-135">1\.</span></span> <span data-ttu-id="02c67-136">インベントリ</span><span class="sxs-lookup"><span data-stu-id="02c67-136">Inventory</span></span>

<span data-ttu-id="02c67-137">Windows Analytics Upgrade Readiness サービスは、エージェントレス型のプロセスを使用して、デスクトップ資産全体にわたるコンピューター、アプリケーション、Office アドインをインベントリに登録します。</span><span class="sxs-lookup"><span data-stu-id="02c67-137">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications, and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="02c67-138">さらに、頻繁にアクセスされるインターネット サイト、アプリおよびイントラネットの場所に関するレポートを示します。これは、この後の互換性テストの役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="02c67-138">It also provides reports on highly visited Internet sites, apps, and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="02c67-139">2\.</span><span class="sxs-lookup"><span data-stu-id="02c67-139">2\.</span></span> <span data-ttu-id="02c67-140">優先度設定</span><span class="sxs-lookup"><span data-stu-id="02c67-140">Prioritize</span></span>

<span data-ttu-id="02c67-141">インベントリの作成により、Windows Analytics の Upgrade Readiness は、優先度を設定するときに役立つ、組織で最も一般的に使用されているアプリとハードウェアを特定します。また、できるだけ多くの PC の展開のために排除する障害に注目するときにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="02c67-141">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, as well as what to focus on to unblock as many PCs as possible for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="02c67-142">さらに、次の手順「テスト」で問題を解決するために必要な更新プログラムを評価するときに役立つガイダンスも提供します。</span><span class="sxs-lookup"><span data-stu-id="02c67-142">It also provides guidance to help you assess the updates necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="02c67-143">3\.</span><span class="sxs-lookup"><span data-stu-id="02c67-143">3\.</span></span> <span data-ttu-id="02c67-144">テスト</span><span class="sxs-lookup"><span data-stu-id="02c67-144">Testing</span></span>

<span data-ttu-id="02c67-145">インベントリに登録されたアプリケーション、ドライバー、アドインのほとんどは、そのままで動作することがわかります。</span><span class="sxs-lookup"><span data-stu-id="02c67-145">You will find that most of the applications, drivers, and add-ins inventoried will work as-is.</span></span> <span data-ttu-id="02c67-146">Windows Analytics の Upgrade Readiness で問題ありと評価された項目については、互換性の問題を解決するためのバージョン更新の入手先など、既知の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="02c67-146">For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information including where to find version updates to resolve compatibility problems.</span></span> <span data-ttu-id="02c67-147">わずかしか展開されていない重要性の低いアプリケーションや古いデバイスに関する複雑な問題を解決するために時間とリソースを割くのではなく、ユーザーと協力してこれらの項目をインベントリから削除し置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="02c67-147">Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="02c67-p111">Windows Analytics の Upgrade Readiness を使用して、ユーザーがアクセスした Web サイトと Web アプリのうち Microsoft Edge ブラウザーでサポートされなくなったレガシ テクノロジ (ActiveX コントロール、ブラウザー ヘルパー オブジェクト、VBScript など) を依然として使用しているものを識別することで、ブラウザー ベースの互換性問題についても評価できます。ユーザーは、そうしたサイトに対して引き続き Internet Explorer 11 を使用する必要があるため、これに該当するサイトは Enterprise Mode Site List Manager を使用して[エンタープライズ モード サイト一覧](https://docs.microsoft.com/ja-JP/microsoft-edge/deploy/emie-to-improve-compatibility)に追加してください。</span><span class="sxs-lookup"><span data-stu-id="02c67-p111">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/en-us/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="02c67-150">さらに、Office 365 ProPlus への移行を円滑に進めるために、[Readiness Toolkit for Office](https://docs.microsoft.com/ja-JP/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) を利用して、アドインと Microsoft Visual Basic for Applications (VBA) マクロの互換性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="02c67-150">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/en-us/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="02c67-p112">4\. 修復</span><span class="sxs-lookup"><span data-stu-id="02c67-p112">4\. Remediation</span></span>

<span data-ttu-id="02c67-153">デバイスとアプリの準備の最終フェーズでは「修復」を実行します。</span><span class="sxs-lookup"><span data-stu-id="02c67-153">The final phase of device and app readiness is to ‘remediate’.</span></span> <span data-ttu-id="02c67-154">このフェーズでは、必要なソフトウェアまたはドライバーのパッケージを収集することになります。収集したパッケージは、展開プロセスの一環として前のバージョンを置き換えたり更新したりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="02c67-154">Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="02c67-p114">問題を修復するリストに対する作業を進めるにつれて、さらに多くの PC が「展開準備完了」になることがわかります。つまり、PC 上のドライバーとアプリの両方が展開の対象としている Windows 10 のバージョンと互換性があることがわかるということです。</span><span class="sxs-lookup"><span data-stu-id="02c67-p114">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

### <a name="configuration-manager-software-inventory-for-application-prioritization"></a><span data-ttu-id="02c67-157">アプリケーションの優先順位付けの Configuration Manager ソフトウェア インベントリ</span><span class="sxs-lookup"><span data-stu-id="02c67-157">Configuration Manager Software Inventory for Application Prioritization</span></span>

<span data-ttu-id="02c67-158">Configuration Manager ソフトウェア インベントリは、クラウドベースの分析ソリューションを使ってデバイスとアプリの準備を整える方法に代わる手段です。</span><span class="sxs-lookup"><span data-stu-id="02c67-158">Configuration Manager software inventory is an alternative to using cloud-based analytics solutions for device and app readiness.</span></span> <span data-ttu-id="02c67-159">インストール数を使用したり、特定のコンピューターを詳細に調査したりして、互換性のテストと検証の優先順位を定め、パッケージ設定を使用してアプリケーション パッケージを Windows 10 互換として設定できます。</span><span class="sxs-lookup"><span data-stu-id="02c67-159">You can use installation counts and drill into specific computers to help prioritize compatibility testing and validation and set application packages as compatible with Windows 10 via package settings.</span></span> <span data-ttu-id="02c67-160">このオプションでは既知の互換性情報と Microsoft の分析サービスとを比較することはできませんが、優先度の高いアプリのより小さなセットを対象に手動テストを行うための効果的なソリューションになり得ます。</span><span class="sxs-lookup"><span data-stu-id="02c67-160">While this option does not offer the ability to compare known compatibility information with Microsoft’s analytics services, it can be an effective solution to target a smaller set of prioritized apps for manual testing.</span></span> 

<span data-ttu-id="02c67-161">詳細については、「[System Center Configuration Manager のソフトウェア インベントリの概要](https://docs.microsoft.com/ja-JP/sccm/core/clients/manage/inventory/introduction-to-software-inventory)」を参照してください。アプリケーション パッケージのプラットフォーム設定の要件については、「[System Center Configuration Manager のパッケージとプログラム](https://docs.microsoft.com/ja-JP/sccm/apps/deploy-use/packages-and-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02c67-161">For more information, see [Introduction to software inventory in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/core/clients/manage/inventory/introduction-to-software-inventory) and setting platform requirements in application packages in [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>


## <a name="desktop-app-assure"></a><span data-ttu-id="02c67-162">Desktop App Assure</span><span class="sxs-lookup"><span data-stu-id="02c67-162">Desktop App Assure</span></span>

<span data-ttu-id="02c67-163">Windows 10 と Office 365 ProPlus アプリの互換性を支援する別のツールは、FastTrack Center から入手できる、[Desktop App Assure](https://aka.ms/desktopappassure) プログラムです。</span><span class="sxs-lookup"><span data-stu-id="02c67-163">Another tool to help with Windows 10 and Office 365 ProPlus app compatibility is the [Desktop App Assure](https://aka.ms/desktopappassure) program available through the FastTrack Center.</span></span> <span data-ttu-id="02c67-164">有効なアプリケーションの問題が発生した場合でも、Desktop App Assure を使用すれば、Microsoft のエンジニアと協力して、追加料金なしでアプリケーションの非互換性を修復できます。</span><span class="sxs-lookup"><span data-stu-id="02c67-164">Through Desktop App Assure in the event of valid application issues a Microsoft engineer with work with you at no additional cost to help remediate the application incompatibility.</span></span>

## <a name="continued-use-of-diagnostic-data-tools"></a><span data-ttu-id="02c67-165">診断データ ツールの継続的な使用</span><span class="sxs-lookup"><span data-stu-id="02c67-165">Continued Use of Diagnostic Data Tools</span></span>

<span data-ttu-id="02c67-p117">Windows Analytics の Upgrade Readiness は、Windows 10 および Office 365 ProPlus への移行に役立つだけのツールではありません。デスクトップで Windows 10 と Office 365 を実行している場合、このツールは、半年ごとの機能更新プログラムの展開と管理を維持して最新の状態に保つために利用できます。</span><span class="sxs-lookup"><span data-stu-id="02c67-p117">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="02c67-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="02c67-168">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="02c67-169">手順 2: ディレクトリとネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="02c67-169">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)