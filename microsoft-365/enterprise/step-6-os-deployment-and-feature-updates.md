---
title: 手順 6 - OS の展開と機能更新プログラム
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/30/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: OS の展開と機能更新プログラムのオプションについて説明します。
ms.openlocfilehash: 16af9a57623ffbdd73d97d44993c36ce57889eaf
ms.sourcegitcommit: 03828f954b9dddb265f867fa508178ec0d4a6aeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2019
ms.locfileid: "35584543"
---
# <a name="step-6-os-deployment-and-feature-updates"></a><span data-ttu-id="3b635-103">手順 6: OS の展開と機能更新プログラム</span><span class="sxs-lookup"><span data-stu-id="3b635-103">Step 6: OS Deployment and Feature Updates</span></span>

![](media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></td>
<td><p><span data-ttu-id="3b635-104"><strong>手順 6: OS の展開と機能更新プログラム</strong></span><span class="sxs-lookup"><span data-stu-id="3b635-104"><strong>Step 6: OS Deployment and Feature Updates</strong></span></span></p>
<p><span data-ttu-id="3b635-p101">タスク シーケンスベースの展開は、ベア メタル インストール、PC の更新および PC の交換の際に、大規模な段階化された展開を自動化するために使用します。アップグレードのタスク シーケンスも、半年ごとの主要な更新プログラムで最新状態を維持するために役立ちます。また、Windows Autopilot は新しい PC の取得プロセスを最新化する最近追加された機能です。</span><span class="sxs-lookup"><span data-stu-id="3b635-p101">Task sequence-based deployment is used to automate large scale, phased deployment for bare metal installs, PC refresh and PC replacement. Upgrade task sequences will also help you stay current with major semi-annual updates. And Windows Autopilot is a recent addition that modernizes the new PC acquisition process.</span></span></p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="3b635-108">OSの展開と機能の更新は、Windows 10 OSの展開、アップグレード、機能の更新を統括する、推奨展開プロセスの6番目のステップです。</span><span class="sxs-lookup"><span data-stu-id="3b635-108">OS Deployment and Feature Updates is the sixth step in our recommended deployment process wheel covering Windows 10 OS deployment, upgrades and Feature Updates.</span></span> <span data-ttu-id="3b635-109">完全なデスクトップ展開プロセスを確認するには、[デスクトップ展開センター](https://aka.ms/HowToShift)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="3b635-109">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="3b635-110">ここまでの展開プロセスの輪に従っていれば、デバイスとアプリの準備、インフラストラクチャの準備、アプリ パッケージの構成と収集が少なくとも部分的には完了していて、ユーザー ファイルの移行と既定の設定の構成のため実施計画があり、既存のセキュリティ制御の保持と新しいセキュリティ制御の展開 (必要な場合) の計画もあるはずです。</span><span class="sxs-lookup"><span data-stu-id="3b635-110">If you’ve been following the deployment process wheel till now, you’ve at least partially completed the steps for device and app readiness, prepared your infrastructure, configured and collected app packages, have a plan in place for migrating user files and configuring default settings as well as have plans for retaining your existing security controls and perhaps deploying new ones.</span></span>

<span data-ttu-id="3b635-111">これらすべての断片を 1 つにまとめて、Windows 10 と Office 365 ProPlus、およびドライバーやアプリなどの必要なもののインストールを可能な限り自動化するという段階に達しました。</span><span class="sxs-lookup"><span data-stu-id="3b635-111">Now we’ve arrived at the stage where you’re putting all these pieces together to automate as much as you can to install Windows 10 and Office 365 ProPlus, along with the necessary drivers, apps and whatever else is needed.</span></span>

<span data-ttu-id="3b635-p103">結局のところ、OS 展開の成功についての最適な評価基準は、ユーザーの期待を満たしていることと、ユーザーの作業を中断しないことです。この手順では、段階的な展開の一部として、パイロット ユーザーを対象としたテストと展開を開始します。ここでのヒントは、展開の範囲を広げる前に、展開プロセスの輪の手順 8「[ユーザーのコミュニケーションとトレーニング](https://aka.ms/mdd8)」までスキップして、ユーザーが通知を受けていること、変更に対するユーザー自身の準備が整っていること、および「段階的な展開」を使用した継続的な検証によってロールアウトのペースを測定できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b635-p103">Ultimately, the best measure of success with an OS deployment is meeting user expectations and avoiding disruptions in their work. And in this step, you’ll start testing and deploying to pilot users as part of a phased deployment. And one tip here, before you broaden deployment, you’ll need to skip ahead to step 8 on our deployment process wheel – [User Communications and Training](https://aka.ms/mdd8) to make sure users are informed and prepared for changes coming their way and that you can measure your roll-out pace with continuous validation using Phased Deployment.</span></span>

## <a name="windows-imaging-process"></a><span data-ttu-id="3b635-115">Windows イメージング プロセス</span><span class="sxs-lookup"><span data-stu-id="3b635-115">Windows Imaging Process</span></span>

<span data-ttu-id="3b635-p104">ほとんどの組織は、PC イメージングのプロセスを使用して、Windows のクローンを構成してキャプチャします。これには、いくつかの標準インストール済みアプリの基本セットを含めることもありますが、アプリケーションのランタイムと更新プログラムのみを含むシン イメージにすることもあります。これを実行するための最適な方法は、予期しないドライバ関連の互換性問題を避けるために、このプロセスと自動化を目的とした仮想マシンを使用することです。</span><span class="sxs-lookup"><span data-stu-id="3b635-p104">Most organizations use the process of PC imaging to configure and capture a clone of Windows, including a base set of a few standard apps installed, or an even a thinner image with only application runtimes and updates. The best way to do this is using a virtual machine for this process to avoid any unexpected driver-related compatibility issues and for automation purposes.</span></span>

<span data-ttu-id="3b635-p105">イメージ キャプチャのルートを進める場合は、最高品質のイメージと繰り返し可能なプロセスを確実なものにするために、作業を可能な限り自動化することをお勧めします。ほとんどの展開について、キャプチャ前の Windows イメージに含まれるカスタマイズと事前インストール済アプリは、できるだけ少なくすることをお勧めします。これは、「シン イメージ」と呼ばれるアプローチで、イメージ内のアプリの数を削減することでネットワーク全体の帯域幅を節約できます。シン ベース イメージから始めることで、ユーザーの要求に応じて必要になるアプリ、言語および構成を動的に積み重ねることができます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p105">If going the image capture route, it’s best to automate as much as possible to ensure the best quality image and a repeatable process. For most deployments, it is also recommended to put as little customization and pre-installed apps as possible in the Windows image prior to capturing. This is what is called a ‘thin image’ approach, which can save overall bandwidth on the network by eliminating the number of apps within the image. By starting with a thin base image, you can layer on required apps, languages and configurations dynamically tailored to users.</span></span>

<span data-ttu-id="3b635-122">ビルドおよびキャプチャ プロセスでは、Windows 10 インストールをイメージとしてキャプチャする前に、System Center Configuration Manager (Current Branch) や Microsoft Deployment Toolkit などのツールでは「一般化」コマンドとシステム準備ツール (Sysprep) を使用して、イメージを再シールします。</span><span class="sxs-lookup"><span data-stu-id="3b635-122">During the build and capture process, tools like System Center Configuration Manager and the Microsoft Deployment Toolkit use the System Preparation Tool – or Sysprep – along with the “Generalize” command to reseal your image before they capture the Windows 10 installation as an image.</span></span>

<span data-ttu-id="3b635-p106">キャプチャされたイメージは、標準の Windows インストール メディアのような Windows イメージ (WIM) 形式になります。カスタムの WIM ファイルがあれば、OS 展開の一環として別のタスク シーケンスを使用して、System Center Configuration Manager または Microsoft Deployment Toolkit で展開関連のタスクを実行することや、イメージを適用することや、Windows イメージの適用前後にタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p106">The captured image will have the Windows image – or WIM – format like standard Windows installation media. Once you have your custom WIM file, you can use another task sequence as part of your OS deployment in System Center Configuration Manager or Microsoft Deployment Toolkit to perform deployment-related tasks, to apply the image and run tasks before and after your Windows image is applied.</span></span>

<span data-ttu-id="3b635-125">
  [Windows 10 参照イメージの作成](https://docs.microsoft.com/ja-JP/windows/deployment/deploy-windows-mdt/create-a-windows-10-reference-image)</span><span class="sxs-lookup"><span data-stu-id="3b635-125">[Create a Windows 10 Reference Image](https://docs.microsoft.com/en-us/windows/deployment/deploy-windows-mdt/create-a-windows-10-reference-image)</span></span>

<span data-ttu-id="3b635-126">
  [オペレーティング システムをインストールするタスク シーケンスの作成](https://docs.microsoft.com/ja-JP/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)</span><span class="sxs-lookup"><span data-stu-id="3b635-126">[Create a Task Sequence to Install an Operating System](https://docs.microsoft.com/en-us/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)</span></span>

### <a name="deployment-types"></a><span data-ttu-id="3b635-127">展開の種類</span><span class="sxs-lookup"><span data-stu-id="3b635-127">Deployment Types</span></span>

<span data-ttu-id="3b635-128">カスタム イメージの準備が整っている場合、インストールまたは移行の種類は次の 3 つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="3b635-128">With your custom image ready, the installation or migration type will fall into the following categories:</span></span>

  - <span data-ttu-id="3b635-p107">1 つ目は、**ベア メタル展開**です。これは、クリーンなディスクにイメージを展開する場合や、ディスク上のデータを保持しておくつもりのないコンピューターを再イメージ化する場合に使用するシナリオです。</span><span class="sxs-lookup"><span data-stu-id="3b635-p107">First, **bare metal deployment**. This is the scenario used to deploy an image to a clean disk, or to reimage a computer where you don’t intend to keep any of the data on the disk</span></span>

  - <span data-ttu-id="3b635-131">2 つ目は、**コンピューター更新**です。これは、ベア メタルに似ていますが、ユーザー状態がディスクに維持される\*、またはインストール完了後に復元されるいう主な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="3b635-131">And second, similar to bare metal, is **Computer Refresh,** with the key difference that user state remains on the disk\* or will be restored after the install is complete</span></span>

  - <span data-ttu-id="3b635-p108">最後は、**コンピューターの交換**です。その名前が示すように、PC を別の PC に交換します。通常、この場合は、最初の PC のユーザー ファイルを集中管理される場所にバックアップしておいて、そのファイルを 2 番目の PC に復元します。</span><span class="sxs-lookup"><span data-stu-id="3b635-p108">And last is **Computer Replacement**. Here as the name implies, you are replacing a PC with another PC. In this case, there is often a backup of user files from the first PC to a central location, then a restore of those files to the second PC.</span></span>

<span data-ttu-id="3b635-135">上記の 3 つのシナリオすべてに共通点があります。これらは、タスク シーケンスを使用して実行し、カスタム イメージを毎回適用できます。</span><span class="sxs-lookup"><span data-stu-id="3b635-135">All three of these scenarios have something in common, they use a task sequence to run, and a custom image can be applied each time.</span></span>

<span data-ttu-id="3b635-136">
  [Windows 10 展開シナリオ](https://docs.microsoft.com/ja-JP/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="3b635-136">[More About Windows 10 Deployment Scenarios](https://docs.microsoft.com/en-us/windows/deployment/windows-10-deployment-scenarios)</span></span>

### <a name="in-place-upgrade-using-task-sequence-automation"></a><span data-ttu-id="3b635-137">タスク シーケンスの自動化を使用した一括アップグレード</span><span class="sxs-lookup"><span data-stu-id="3b635-137">In-place Upgrade using Task Sequence Automation</span></span>

<span data-ttu-id="3b635-138">前述の展開の種類に加えて、Windows 10 では System Center Configuration Manager (Current Branch) のタスク シーケンスとして使用できるようになった新しいオプションとアップグレード タスク シーケンスを使用した一括アップグレードがあります。</span><span class="sxs-lookup"><span data-stu-id="3b635-138">In addition to these deployment types, there is a new option available now as a System Center Configuration Manager Task Sequence with Windows 10 – and in-place upgrade using the Upgrade Task Sequence.</span></span>

<span data-ttu-id="3b635-p109">タスクシーケンスは、以前のバージョンの Windows からの一括アップグレードには必要ありませんが、エンタープライズ規模で展開する場合には推奨されるアプローチです。一括アップグレードでは、アプリケーションにカスタムイメージを適用することはできませんが、オフライン サービスを使用することで既定の install.wim を更新できます。たとえば、アップグレードの実行前に、最新の Windows 更新プログラムが適用されているようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p109">In-place upgrades from a previous version of Windows do not require a task sequence, but it is a recommended approach when deploying at enterprise scale. An in-place upgrade does not allow you to apply a custom image with applications, but you can update the default install.wim using offline servicing. For example, you can to make sure it has the latest Windows updates applied prior to performing upgrades.</span></span>

<span data-ttu-id="3b635-p110">一括アップグレードには、Windows セットアップが使用されます。このセットアップ エンジンは、複数の小さなインストール前チェックを実行して、既知の互換性問題を調べます。また、ユーザー状態とアプリケーションを維持して、インストールする Windows 10 のバージョンと互換性がないものだけを削除します。このオプションでは、以前にインストールしていたアプリケーションとユーザー状態が維持されます。さらに、一括アップグレードを使用すると、トラブルシューティングのために必要になる場合は、前にインストールされていた OS にロールバックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p110">In-place upgrade uses windows setup. The setup engine runs several small pre-installation checks looking for known compatibility issues. It also preserves the user state and applications and only removes what isn’t compatible with the version of Windows 10 being installed. With this option, previously installed applications and user state are preserved. In-place upgrade also allows you to roll-back to the previous OS installed if needed for troubleshooting purposes.</span></span>

[<span data-ttu-id="3b635-147">setup.exe を使用した Windows 10 のアップグレード前検証</span><span class="sxs-lookup"><span data-stu-id="3b635-147">Windows 10 Pre-Upgrade Validation Using setup.exe</span></span>](https://blogs.technet.microsoft.com/mniehaus/2015/08/23/windows-10-pre-upgrade-validation-using-setup-exe/)

![](media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-3.png)

<span data-ttu-id="3b635-p111">一括アップグレード シナリオは、前バージョンの Windows 10 からのアップグレードだけでなく、レガシ バージョンの Windows から Windows 10 への移行にも使用できます。Windows セットアップによるアップグレードの完了後、タスク シーケンスは実行を継続して、Office などのアプリケーションをアップグレードし、ドライバーを置き換えて、個人用設定を適用できます。同様に、アップグレード タスク シーケンスを使用して、インストール前タスクや、アップグレードの実施前チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p111">The in-place upgrade scenario can be used to migrate to Windows 10 from legacy versions of Windows, as well as upgrade from previous versions of Windows 10. After Windows Setup completes the upgrade, your task sequence can continue to run and upgrade applications like Office, replace drivers, and apply personalization settings. Likewise, you can use the Upgrade Task Sequence to perform pre-installation tasks or checks prior to carrying out the upgrade.</span></span>

<span data-ttu-id="3b635-151">
  [Configuration Manager を使用して Windows 10 への一括アップグレードを実行する](https://docs.microsoft.com/ja-JP/windows/deployment/upgrade/upgrade-to-windows-10-with-system-center-configuraton-manager)</span><span class="sxs-lookup"><span data-stu-id="3b635-151">[Perform an in-place upgrade to Windows 10 using Configuration Manager](https://docs.microsoft.com/en-us/windows/deployment/upgrade/upgrade-to-windows-10-with-system-center-configuraton-manager)</span></span>

<span data-ttu-id="3b635-152">
  [Configuration Manager で OS をアップグレードするタスク シーケンスを作成する](https://docs.microsoft.com/ja-JP/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)</span><span class="sxs-lookup"><span data-stu-id="3b635-152">[Create a task sequence to upgrade an OS in Configuration Manager](https://docs.microsoft.com/en-us/sccm/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)</span></span>

### <a name="phased-deployment"></a><span data-ttu-id="3b635-153">段階的な展開</span><span class="sxs-lookup"><span data-stu-id="3b635-153">Phased Deployment</span></span>

<span data-ttu-id="3b635-p112">展開を計画しているときには、ベア メタル、更新、交換およびアップグレードのパスをターゲットにしていることでしょう。この場合に推奨されるアプローチは、同様のマシンのコレクションに段階的な展開を使用することです。この方法により、展開の規模を拡大する前に、互換性、配信と自動化、ユーザー受け入れ、ネットワーク帯域幅の使用量などの要因を検証できます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p112">As you're planning your deployment, you'll be targeting computers for bare metal, refresh, replace and upgrade paths. The recommended approach in this case is to use phased deployment to collections of similar machines. This way, you can validate compatibility, delivery and automation, user acceptance, network bandwidth consumption, and other factors before increasing the scale of your deployment.</span></span>

![](media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-4.png)

### <a name="recommended-tools-system-center-configuration-manager-current-branch-and-the-microsoft-deployment-toolkit"></a><span data-ttu-id="3b635-157">推奨されるツール: System Center Configuration Manager (Current Branch) および Microsoft Deployment Toolkit</span><span class="sxs-lookup"><span data-stu-id="3b635-157">Recommended Tools: System Center Configuration Manager and the Microsoft Deployment Toolkit</span></span>

<span data-ttu-id="3b635-p113">どの展開の種類を選択したかに関係なく、予測可能性と再現性をできるだけ自動化する必要があります。Microsoft は、自動化されたタスク シーケンスを使用して OS の展開を自動化するためのソリューションを 2 つ用意しています。</span><span class="sxs-lookup"><span data-stu-id="3b635-p113">Regardless of the deployment type you choose, you’ll want to make sure it’s as automated as possible for predictability and repeatability. Microsoft offers two solutions to automate OS deployment using automated task sequences:</span></span>

  - <span data-ttu-id="3b635-p114">
  **
  [System Center Configuration Manager](https://docs.microsoft.com/ja-JP/sccm/core/understand/introduction)\*\* (ConfigMgr) には、ソフトウェア配布とソフトウェア更新の管理機能を補完する組み込みのオペレーティング システム展開機能が用意されています。ConfigMgr は、あらゆる規模の組織で広く使用されていて、4 つの Windows の展開の種類をすべてサポートしています。ConfigMgr は、必要に応じて Microsoft Intune と統合できます。これにより、展開とデバイス管理に関する追加の機能が加わります。</span><span class="sxs-lookup"><span data-stu-id="3b635-p114">**[System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/core/understand/introduction)** (ConfigMgr) provides built-in operating system deployment capabilities to complement its capabilities for software distribution and software update management. ConfigMgr is widely used by organizations of all sizes and supports all four Windows deployment types. Optionally, you can integrate ConfigMgr with Microsoft Intune to add additional capabilities for deployment and device management.</span></span>

  - <span data-ttu-id="3b635-p115">もう 1 つの一般的な展開オプションは、無料の **[Microsoft Deployment Toolkit](https://docs.microsoft.com/ja-JP/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit)** (MDT) です。通常、このツールキットは、中小規模の組織が OS の展開に使用します。インフラストラクチャは、ほとんど必要とされません。MDT は、ネットワーク ブートのために Windows 展開サービスと統合されます。4 つの展開の種類をすべてサポートし、アプリケーション、ドライバー、および設定のインストールもサポートしています。当然のことながら、MDT は Configuration Manager とも統合できます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p115">And one other popular deployment option is the free **[Microsoft Deployment Toolkit](https://docs.microsoft.com/en-us/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit)** (MDT) which is typically used by small and medium sized organizations for OS deployment. This requires very little infrastructure. MDT integrates with Windows Deployment Services (WDS) for network boot. It supports all four deployment types as well as installation of applications, drivers, and settings. And of course, MDT can even be integrated with Configuration Manager.</span></span>

![](media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-5.png)

### <a name="windows-autopilot"></a><span data-ttu-id="3b635-168">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="3b635-168">Windows Autopilot</span></span>

<span data-ttu-id="3b635-169">Windows 10の新しいオプションとして、Windows Autopilotを使用してハードウェアの更新サイクルの一部として新しいPCを構成することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="3b635-169">A new option with Windows 10 is to configure new PCs as part of your hardware refresh cycle using Windows Autopilot.</span></span> <span data-ttu-id="3b635-170">ここでは、サポート契約を結んでいるハードウェア会社と同期して、規定のWindowsセットアップ環境をカスタマイズすることができます。たとえば、ライセンス契約や診断データ設定など、ユーザーに提示されるオプションを排除することができます。</span><span class="sxs-lookup"><span data-stu-id="3b635-170">Here you can work with supporting hardware vendors to customize the default Windows setup experience – for example by eliminating options presented to users, like Licensing Agreements or diagnostic data settings.</span></span>

<span data-ttu-id="3b635-p117">その後で、ユーザーがセットアップ時に Azure AD 資格情報を使用して PC にサインインすると、デバイスは Microsoft Intune に登録されます。展開プロセスは、これが引き継いで、アプリケーション、ソフトウェアの更新プログラム、構成およびコンプライアンス ポリシーを適用します。Windows Autopilot は、必要に応じて、プロビジョニングが完了するまで、ユーザーが最初のセッションにアクセスできないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3b635-p117">Then, when a user signs in to the PC during setup using their Azure AD credentials, the device enrolls into Microsoft Intune, which can then take over the deployment process and apply applications, software updates configurations and compliance policies. Windows Autopilot can also optionally prevent the user from accessing the first session until provisioning is complete.</span></span>

<span data-ttu-id="3b635-173">
  [Windows Autopilot の概要](https://docs.microsoft.com/ja-JP/windows/deployment/windows-autopilot/windows-10-autopilot)</span><span class="sxs-lookup"><span data-stu-id="3b635-173">[Overview of Windows Autopilot](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/windows-10-autopilot)</span></span>

<span data-ttu-id="3b635-174">
  [Windows Autopilot Prerequisites](https://docs.microsoft.com/ja-JP/windows/deployment/windows-autopilot/windows-10-autopilot#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="3b635-174">[Windows Autopilot Prerequisites](https://docs.microsoft.com/en-us/windows/deployment/windows-autopilot/windows-10-autopilot#prerequisites)</span></span>

## <a name="windows-update-for-business-for-feature-updates"></a><span data-ttu-id="3b635-175">機能更新のためのWindows Update for Business</span><span class="sxs-lookup"><span data-stu-id="3b635-175">Windows Update for Business for Feature Updates</span></span>

<span data-ttu-id="3b635-176">Windows Update for Businessは、ITの専門化がデバイスをWindows Updateサービスに直接接続することによって、Windows 10デバイスを常に最新の状態に保つことを可能にする無料サービスです。</span><span class="sxs-lookup"><span data-stu-id="3b635-176">Windows Update for Business is a free service that enables IT Pros to keep Windows 10 devices always up to date by directly connecting the devices to the Windows Update service.</span></span> <span data-ttu-id="3b635-177">Windows Update for Businessは、グループポリシーまたはMicrosoft IntuneなどのMDMソリューションを介して構成でき、ITの専門化は新しいビルドを検証するために[展開リング](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-deployment-rings-windows-10-updates)を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3b635-177">Windows Update for Business can be configured via Group Policy or through MDM solutions such as Microsoft Intune and allows IT Pros to create [deployment rings](https://docs.microsoft.com/en-us/windows/deployment/update/waas-deployment-rings-windows-10-updates) to validate new builds.</span></span> <span data-ttu-id="3b635-178">これはWindows Server Update Services（WSUS）、System Center Configuration Manager (Current Branch)、および Microsoft Intune などの既存の管理ツールに統合されています。</span><span class="sxs-lookup"><span data-stu-id="3b635-178">It is integrated into existing management tools such as Windows Server Update Services (WSUS), System Center Configuration Manager (current branch), and Microsoft Intune.</span></span> <span data-ttu-id="3b635-179">さらに、Windows Update for Businessはピアツーピア配信をサポートし、帯域幅効率を最適化し、ネットワークの輻輳を軽減します。</span><span class="sxs-lookup"><span data-stu-id="3b635-179">Additionally, Windows Update for Business supports peer-to-peer delivery to help optimize bandwidth efficiency and reduce network congestion.</span></span>

<span data-ttu-id="3b635-180">Windows Update for Businessの詳細については、以下の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b635-180">For more detailed information on Windows Update for Business please review the following documentation:</span></span>

- <span data-ttu-id="3b635-181">
  [Windows Update for Businessで更新を展開する](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="3b635-181">[Deploy Updates Using Windows Update for Business](https://docs.microsoft.com/en-us/windows/deployment/update/waas-manage-updates-wufb)</span></span>
- <span data-ttu-id="3b635-182">
  [Windows Update for Businessを構成する](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-configure-wufb)</span><span class="sxs-lookup"><span data-stu-id="3b635-182">[Configure Windows Update for Business](https://docs.microsoft.com/en-us/windows/deployment/update/waas-configure-wufb)</span></span>
- <span data-ttu-id="3b635-183">
  [Windows Update for Businessを既存の管理ツールと統合する](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-integrate-wufb)</span><span class="sxs-lookup"><span data-stu-id="3b635-183">[Integrate Windows Update for Business with Existing Management Tools](https://docs.microsoft.com/en-us/windows/deployment/update/waas-integrate-wufb)</span></span>
- <span data-ttu-id="3b635-184">
  [グループポリシーを使用してWindows Update for Businessを構成する](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-wufb-group-policy)</span><span class="sxs-lookup"><span data-stu-id="3b635-184">[Use Group Policy to configure Windows Update for Business](https://docs.microsoft.com/en-us/windows/deployment/update/waas-wufb-group-policy)</span></span>
- <span data-ttu-id="3b635-185">
  [Microsoft Intuneを使用してWindows Update for Businessを構成する](https://docs.microsoft.com/ja-JP/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="3b635-185">[Use Microsoft Intune to configure Windows Update for Business](https://docs.microsoft.com/en-us/intune/windows-update-for-business-configure)</span></span>

## <a name="next-step"></a><span data-ttu-id="3b635-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b635-186">Next Step</span></span> 

## <a name="step-7-windows-and-office-servicinghttpsakamsmdd7"></a>[<span data-ttu-id="3b635-187">ステップ7：WindowsとOfficeのサービス</span><span class="sxs-lookup"><span data-stu-id="3b635-187">Step 7: Windows and Office Servicing</span></span>](https://aka.ms/mdd7)

## <a name="previous-step"></a><span data-ttu-id="3b635-188">前の手順</span><span class="sxs-lookup"><span data-stu-id="3b635-188">Previous Step</span></span>

## <a name="step-5-security-and-compliance-considerationshttpsakamsmdd5"></a>[<span data-ttu-id="3b635-189">手順 5: セキュリティとコンプライアンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3b635-189">Step 5: Security and Compliance Considerations</span></span>](https://aka.ms/mdd5)