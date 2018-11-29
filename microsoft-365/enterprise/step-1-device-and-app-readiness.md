---
title: 手順 1 - デバイスとアプリの準備
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 環境内のデバイスとアプリの準備を評価する方法について説明します。
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869647"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="eb899-103">手順 1: デバイスとアプリの準備</span><span class="sxs-lookup"><span data-stu-id="eb899-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="eb899-104">デバイスとアプリのインベントリを使用してデスクトップ展開プロジェクトを開始し、転送するものに優先度を設定し、優先度が設定されたアプリとデバイスをテストし、展開の準備に必要なものを修復します。</span><span class="sxs-lookup"><span data-stu-id="eb899-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="eb899-105"><strong>手順 1: デバイスとアプリの準備</strong></span><span class="sxs-lookup"><span data-stu-id="eb899-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="eb899-106">デバイスとアプリのインベントリを使用してデスクトップ展開プロジェクトを開始し、転送するものに優先度を設定し、優先度が設定されたアプリとデバイスをテストし、展開の準備に必要なものを修復します。</span><span class="sxs-lookup"><span data-stu-id="eb899-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="eb899-p101">デバイスとアプリの準備は、推奨されている展開プロセスの輪における最初の手順であり、アプリケーションとハードウェアの互換性に関する包括的な側面をカバーします。完全なデスクトップ展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb899-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="eb899-p102">これまで、ユーザーのデスクトップをアップグレードする際には、アプリケーションとハードウェアの互換性が大きなハードルになっていました。Windows 10 および Office 365 ProPlus への移行を計画しているときには、好都合なことに、過去 10 年間に作成されたアプリケーションのほとんどが Windows 10 で稼働するものであり、組織が Office 2010 以降の各バージョンで使用している COM アドインと VBA マクロは最新バージョンの Office でも変更なしで動作します。</span><span class="sxs-lookup"><span data-stu-id="eb899-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="eb899-111">そのため、組織の規模と歴史によっては、アプリケーションとハードウェアの互換性を検証することが、推奨される 8 フェーズの展開プロセスにおける重要な最初の手順になることがあります。</span><span class="sxs-lookup"><span data-stu-id="eb899-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="eb899-112">この記事では、最初のフェーズであるデバイスとアプリの準備に、新しい Windows Analytics の Upgrade Readiness ツールを使用する方法について説明します。このツールは、インテリジェントなクラウド ベースのソリューションであり、Windows ライセンスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb899-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="eb899-113">現時点で目的の環境に Windows Analytics をセットアップしていない場合や、試用のためにサインアップしようとしている場合は、[Windows Analytics ページ](http://www.aka.ms/windowsanalytics)に移動して開始してください。</span><span class="sxs-lookup"><span data-stu-id="eb899-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="eb899-114">推奨されるツール: Windows Analytics の Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="eb899-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="eb899-p103">Windows Analytics の Upgrade Readiness は、従来のデスクトップ管理システムよりも多くのメリットをもたらす推奨ツールです。これは、エージェントレス型のツールであり、実行する必要のある手順をガイドします。数百万台のコンシューマー PC のアップグレードを通じて収集したアプリケーションとドライバーの互換性情報を活用して、詳細な評価を示し、アップグレードの障害になる可能性のある互換性の問題を特定すると共に、Microsoft にとって既知の提案される修正プログラムへのリンクが示されます。</span><span class="sxs-lookup"><span data-stu-id="eb899-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="eb899-p104">Window Analytics の Upgrade Readiness をセットアップするには、まず、Azure サブスクリプションを設定して、そのサブスクリプションに Azure Log Analytics ワークスペースを含めておく必要があります。Windows Analytics Upgrade Readiness サービスを実行すると、インターネットに接続された Windows 7 SP1 以降のデバイスを「グループ ポリシー」設定から登録できるようになります。これは簡単なことです。展開するエージェントはありません。また、Windows Analytics Upgrade Readiness のビジュアル ワークフローにより、パイロット展開から運用展開へのガイドが示されます。必要に応じて、Windows Analytics Upgrade Readiness から System Center Configuration Manager などのソフトウェア展開ツールにデータをエクスポートして、展開の準備が整ったときに PC を直接対象としてコレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="eb899-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="eb899-122">デバイスとアプリの準備プロセス</span><span class="sxs-lookup"><span data-stu-id="eb899-122">Device and App Readiness Process</span></span>

<span data-ttu-id="eb899-p105">デバイスとアプリの準備は、「1. インベントリ」、「2. 優先度設定」、「3. テスト」、「4. 修復」の 4 つの手順で成立します。これらの手順について、順番に説明します。</span><span class="sxs-lookup"><span data-stu-id="eb899-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="eb899-p106">1\. インベントリ</span><span class="sxs-lookup"><span data-stu-id="eb899-p106">1\. Inventory</span></span>

<span data-ttu-id="eb899-131">Windows Analytics Upgrade Readiness サービスは、エージェントレス型のプロセスを使用して、デスクトップ資産全体にわたるコンピューター、アプリケーション、および Office アドインをインベントリに登録します。</span><span class="sxs-lookup"><span data-stu-id="eb899-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="eb899-132">さらに、頻繁にアクセスされるインターネット サイト、アプリおよびイントラネットの場所に関するレポートを示します。これは、この後の互換性テストの役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb899-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="eb899-p107">2\. 優先度設定</span><span class="sxs-lookup"><span data-stu-id="eb899-p107">2\. Prioritize</span></span>

<span data-ttu-id="eb899-135">インベントリの作成により、Windows Analytics Upgrade Readiness は、優先度を設定する際に役立つ、組織で最も一般的に使用されているアプリとハードウェアを特定します。また、できるだけ多くの PC の展開のために排除する障害に注目する際にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb899-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="eb899-136">さらに、次の手順「テスト」で問題を解決するために必要な更新プログラムを評価する際に役立つガイダンスも提供します。</span><span class="sxs-lookup"><span data-stu-id="eb899-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="eb899-p108">3\. テスト</span><span class="sxs-lookup"><span data-stu-id="eb899-p108">3\. Testing</span></span>

<span data-ttu-id="eb899-p109">インベントリに登録されたほとんどのアプリケーション、ドライバー、およびアドインは、そのままの状態で動作することがわかるでしょう。Windows Analytics Upgrade Readiness によって問題があると評価されたアイテムについては、互換性問題を解決するためのバージョン更新プログラムがある場所が含まれた既知の情報が示されます。重要でなく展開されている数が少ないアプリケーションと古いデバイスに時間とリソースを費やすのではなく、そうしたアイテムはユーザーと協力して使用中止にして置き換えるようにします。</span><span class="sxs-lookup"><span data-stu-id="eb899-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="eb899-p110">Windows Analytics の Upgrade Readiness を使用して、ユーザーがアクセスした Web サイトと Web アプリのうち Microsoft Edge ブラウザーでサポートされなくなったレガシ テクノロジ (ActiveX コントロール、ブラウザー ヘルパー オブジェクト、VBScript など) を依然として使用しているものを識別することで、ブラウザー ベースの互換性問題についても評価できます。ユーザーは、そうしたサイトに対して引き続き Internet Explorer 11 を使用する必要があるため、これに該当するサイトは Enterprise Mode Site List Manager を使用して[エンタープライズ モード サイト一覧](https://docs.microsoft.com/ja-JP/microsoft-edge/deploy/emie-to-improve-compatibility)に追加してください。</span><span class="sxs-lookup"><span data-stu-id="eb899-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/ja-JP/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="eb899-144">さらに、Office 365 ProPlus への移行を円滑に進めるために、[Readiness Toolkit for Office](https://docs.microsoft.com/ja-JP/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) を利用して、アドインと Microsoft Visual Basic for Applications (VBA) マクロの互換性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eb899-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/ja-JP/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="eb899-p111">4\. 修復</span><span class="sxs-lookup"><span data-stu-id="eb899-p111">4\. Remediation</span></span>

<span data-ttu-id="eb899-p112">デバイスとアプリの準備の最終フェーズでは「修復」を実行します。このフェーズでは、必要なソフトウェアまたはドライバーのパッケージを収集することになります。収集したパッケージは、展開プロセスの一環として古いバージョンを置き換えたり更新したりするために使用します。</span><span class="sxs-lookup"><span data-stu-id="eb899-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="eb899-p113">問題を修復するリストに対する作業を進めるにつれて、さらに多くの PC が「展開準備完了」になることがわかります。つまり、PC 上のドライバーとアプリの両方が展開の対象としている Windows 10 のバージョンと互換性があることがわかるということです。</span><span class="sxs-lookup"><span data-stu-id="eb899-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="eb899-151">テレメトリ ツールの継続使用</span><span class="sxs-lookup"><span data-stu-id="eb899-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="eb899-p114">Windows Analytics の Upgrade Readiness は、Windows 10 および Office 365 ProPlus への移行に役立つだけのツールではありません。デスクトップで Windows 10 と Office 365 を実行している場合、このツールは、半年ごとの機能更新プログラムの展開と管理を維持して最新の状態に保つために利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb899-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="eb899-154">次の手順</span><span class="sxs-lookup"><span data-stu-id="eb899-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="eb899-155">手順 2: ディレクトリとネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="eb899-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)