---
title: 手順 3 - Office および LOB アプリの配信
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
description: Office および LOB アプリの配信方法について説明します。
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869653"
---
# <a name="step-3-office-and-lob-app-delivery"></a><span data-ttu-id="40c94-103">手順 3: Office および LOB アプリの配信</span><span class="sxs-lookup"><span data-stu-id="40c94-103">Step 3: Office and LOB App Delivery</span></span>

<span data-ttu-id="40c94-p101">この時点で、Office および基幹業務アプリを配信する準備は整っています。そのための方法はいくつかありますが、その中には優れた新しいオプションが含まれています。現在のニーズに対応する最適な方法を調べて選択するために、ある程度の時間を割いてください。</span><span class="sxs-lookup"><span data-stu-id="40c94-p101">You are now ready to deliver Office and your Line of Business Apps. There are a number of ways to do this, including some exciting new options. Take some time to review and chose the best methods for your current needs.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><span data-ttu-id="40c94-107"><strong>手順 3: Office および LOB アプリの配信</strong></span><span class="sxs-lookup"><span data-stu-id="40c94-107"><strong>Step 3: Office and LOB App Delivery</strong></span></span></p>
<p><span data-ttu-id="40c94-p102">目的のアプリがパッケージ化されていて、自動インストールの準備が整っていることを確認してください。Office 365 ProPlus のクイック実行パッケージが、Office アプリケーションの構成、配信および最新状態の維持のための新しいオプションをどのように提供するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40c94-p102">Ensure your apps are packaged and ready for automated installation. Learn how Click-to-Run packaging with Office 365 ProPlus gives you new options to configure, deliver and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="40c94-p103">Office および LOB アプリの配信は、推奨される展開プロセスの輪における 3 番目の手順であり、Office と LOB をインストールおよび管理するためのオプションをカバーしています。展開が正常に成功するように、最初の 2 つの手順は省略しないでください。完全なデスクトップ展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c94-p103">Office and LOB App Delivery is the third step in our recommended deployment process wheel covering the options to install and manage Office and LOB. For successful deployment do not skip the first two steps.  To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="40c94-p104">一部のアプリケーションは 32 ビットまたは 64 ビットのどちらかでコンパイルされたバージョンとしてのみ使用できますが、それ以外の Office 365 ProPlus などのアプリケーションは 32 ビットおよび 64 ビットの両方でネイティブにコンパイルされたコードとして使用できるため、どちらのバージョンを展開するかが重大な決断の 1 つになります。新しいデバイスに備わった追加の計算能力と RAM を活用するには、64 ビット バージョンの使用が望まれますが、その前に、アドインやファイルに関連する互換性の問題を把握しておく必要があります。そのために、まず、「手順 1: デバイスとアプリの準備」を再確認しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p104">While some applications are only available as either a 32-bit or 64-bit compiled version, others, including Office 365 ProPlus, both as 32-bit and 64-bit native compiled code, and one of biggest decisions you will make is which version to deploy. To take advantage of additional compute power and RAM on new devices, you will want to use the 64-bit version, but before you do you will need to figure out any add-in or file-related compatibility challenges you may have. This may require you to revisit Step 1 Device and App Readiness before you continue.</span></span>

<span data-ttu-id="40c94-p105">障害になるものがない場合は、Microsoft Office を含めてすべてのアプリの 64 ビット バージョンを展開することをお勧めします。64 ビット ネイティブでコンパイルされたアプリは、最高のパフォーマンスを発揮する、最も将来性のある選択になります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p105">If nothing is blocking you, we recommend you deploy 64-bit versions of all apps, including Microsoft Office. 64-bit native compiled apps offer the best performance and is the most future-proof choice.</span></span>

<span data-ttu-id="40c94-118">Windows にアプリをインストールするための方法とモデルは多数あります。次に、選択可能な配信のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40c94-118">There are many methods and models for installing apps on Windows, so let’s look at your delivery options.</span></span>

[<span data-ttu-id="40c94-119">Windows 10 アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="40c94-119">Windows 10 application management</span></span>](https://docs.microsoft.com/ja-JP/windows/application-management/)

## <a name="msi-based-deployments"></a><span data-ttu-id="40c94-120">MSI ベースの展開</span><span class="sxs-lookup"><span data-stu-id="40c94-120">MSI-based Deployments</span></span>

<span data-ttu-id="40c94-p106">基幹業務アプリについては、MSI ベースのパッケージまたは実行可能ファイルを使用して、OS 展開のタスク シーケンスの一部としてアプリをインストールすることになるでしょう。そうしたパッケージは、Windows 10 でも引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="40c94-p106">For your line of business apps, you’ll probably use MSI-based packages or executables, and install apps as part of an OS deployment task sequence. Windows 10 continues to work with these packages</span></span>

<span data-ttu-id="40c94-p107">System Center Configuration Manager や Microsoft Intune などのソフトウェア展開ツールも、MSI パッケージ型のアプリを配信するように最適化されています。Windows 10 でアプリを検証していれば、アプリの配信に System Center Configuration Manager (現在のブランチ) を使用できます。Microsoft Intune の「ポータル サイト」を使用している場合は、IT 部門によって承認された組織が利用できるアプリの選択を拡張して、最新のアプリケーションを含めるようにすると、ユーザーは必要なものを自分で選択できます。</span><span class="sxs-lookup"><span data-stu-id="40c94-p107">Software deployment tools like System Center Configuration Manager and Microsoft Intune are also optimized to deliver MSI-packaged apps. Once you have validated your apps on Windows 10, you can use System Center Configuration Manager (current branch) for app delivery. If you use the Company Portal in Microsoft Intune you can extend the choice of IT sanctioned apps available to your organization to include the latest applications, and users to self-select what they need.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a><span data-ttu-id="40c94-126">PC のイメージング</span><span class="sxs-lookup"><span data-stu-id="40c94-126">PC Imaging</span></span>

<span data-ttu-id="40c94-p108">もう 1 つの一般的なアプリ配信の方法は、PC のイメージングです。この場合は、タスク シーケンスまたは手動のどちらかでサンプル PC にアプリケーションをインストールしてから、必要なアプリケーションがプレインストールされた状態のシステム イメージをキャプチャします。イメージングによるビルドとキャプチャのアプローチは、新しい PC のプロビジョニングにかかる時間を短縮できますが、そのイメージに含まれるオペレーティング システムとアプリは、すぐに古いものになってしまう点に注意してください。Windows 10 および Office 365 ProPlus の「累積的な更新プログラム」モデルは、この問題への対応に役立ちますが、問題を完全に排除することにはなりません。そのため、展開時にイメージの外部からアプリケーションをインストールする、シン イメージのアプローチをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="40c94-p108">Another popular method of app delivery is PC imaging. In this case, applications are either installed via task sequence or manually on a sample PC, then a system image is captured with the required applications pre-installed. The imaging approach to build and capture can save time when provisioning new PCs but remember Operating systems and apps within the image can become stale quickly. The Cumulative Update model in Windows 10 and Office 365 ProPlus help with this problem, but doesn’t eliminate it completely. This is why we recommend a thin image approach, where your applications are installed from outside the image at deploy time.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

<span data-ttu-id="40c94-p109">イメージに Office 365 ProPlus を含める必要がある場合は、ユーザー ベースのライセンス認証を使用することになる点に注意してください。システム管理者が事前にライセンス認証することはできません。「Office 展開ツール」を使用して、イメージングするデバイスに Office をプレインストールして、ユーザー サインインをスキップします。ユーザーはサインインして、ライセンス認証の割り当てなどの初回使用時のサインインを利用する機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="40c94-p109">If you do want to include Office 365 ProPlus in your image, remember that this uses a user-based activation; it cannot be pre-activated by the system admin. Use the Office Deployment Tool to pre-install Office on the device you are imaging and skip the user sign-in. Users can sign-in, be assigned the activation and take advantage of other capabilities that leverage sign-in on first use.</span></span>

[<span data-ttu-id="40c94-134">オペレーティング システムをインストールするタスク シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="40c94-134">Create a Task Sequence to Install an Operating System</span></span>](https://docs.microsoft.com/ja-JP/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a><span data-ttu-id="40c94-135">クイック実行</span><span class="sxs-lookup"><span data-stu-id="40c94-135">Click-to-Run</span></span> 

<span data-ttu-id="40c94-p110">Office 365 ProPlus は、クイック実行を使用してインストールされます。クイック実行は、近日リリースされる Windows 用 Office 2019 リリースのすべてのバージョンで MSI ベースのパッケージ化に置き換わるものです。これには、インストールの高速化、更新の高速化と能率化、アンインストールのクリーン化などの多数の利点があります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p110">Office 365 ProPlus is installed using Click-to-Run, and Click-to-Run replaces MSI-based packaging in every version of the upcoming Office 2019 release for Windows. It brings with it a number of advantages, including faster installations, faster and more efficient updating, and cleaner uninstallation</span></span>

<span data-ttu-id="40c94-p111">クイック実行によって配信されたプログラムは、コンピューター上の仮想アプリケーション環境内で実行されるため、別のアプリケーションと競合することなく共存できます。また、占有されるディスク領域は MSI ベースのパッケージの半分程度で済みます。さらに、クイック実行はプログラムのストリーミングをサポートしているため、最も一般的に使用される機能を最初にストリーミングすることで、ユーザーは、最初に Office が完全にインストールされるまで待機するのではなく、数分間で Office アプリケーションの使用を開始できます。これは、初期展開の場合以外にも重要なことです。更新プログラムは、ユーザーに影響を与えることなくバックグラウンドでシームレスにストリーミングされるからです。</span><span class="sxs-lookup"><span data-stu-id="40c94-p111">Programs delivered via Click-to-Run execute in a virtual application environment on your computer and so co-exist with other applications without conflict; they also take about half the disk space they would as an MSI-based package. And because Click-to-Run supports program streaming, by streaming the most commonly used features first, users can start using Office applications in just a few minutes, rather than waiting for Office to install fully first. This is important not just for the initial deployment, it means updates can be streamed seamlessly in the background with minimal impact on users.</span></span>

<span data-ttu-id="40c94-p112">System Center Configuration Manager は、引き続き Office 365 ProPlus の広範囲の展開に使用できます。System Center Configuration Manager (現在のブランチ) には、最新版 Office カスタマイズ ツールのネイティブ サポート、インストール時のクイック実行に対応するパッケージのカスタマイズ、およびインストール後のソフトウェア更新管理のネイティブ サポートがあります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p112">If you use System Center Configuration Manager, you can still use it for broad deployment of Office 365 ProPlus. System Center Configuration Manager (current branch) has native support for the updated Office Customization Tool, package customization for Click-to-Run at install time, and native support for software update management post installation.</span></span>

[<span data-ttu-id="40c94-143">Office 365 ProPlus の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="40c94-143">Deployment Guide for Office 365 ProPlus</span></span>](https://docs.microsoft.com/ja-JP/deployoffice/deployment-guide-for-office-365-proplus)

[<span data-ttu-id="40c94-144">Office 365 ProPlus にアップグレードする際に Office の既存の MSI バージョンを削除する</span><span class="sxs-lookup"><span data-stu-id="40c94-144">Remove existing MSI versions of Office when upgrading to Office 365 ProPlus</span></span>](https://docs.microsoft.com/ja-JP/deployoffice/upgrade-from-msi-version)

[<span data-ttu-id="40c94-145">Configuration Manager を使用した Office 365 ProPlus の管理</span><span class="sxs-lookup"><span data-stu-id="40c94-145">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/ja-JP/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[<span data-ttu-id="40c94-146">Microsoft Intune で Windows 10 デバイスに Office 365 アプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="40c94-146">Assign Office 365 apps to Windows 10 devices with Microsoft Intune</span></span>](https://docs.microsoft.com/ja-JP/intune/apps-add-office365)

## <a name="browser-based-apps"></a><span data-ttu-id="40c94-147">ブラウザー ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="40c94-147">Browser-based Apps</span></span>

<span data-ttu-id="40c94-p113">ブラウザー ベースのアプリケーションが引き続き期待どおりに動作するようにするには、いくつかの考慮すべき事項があります。Microsoft Edge との互換性に問題がある特定の Web サイトとアプリがある場合は、エンタープライズ モード サイト一覧を使用することで、その Web サイトが自動的に Internet Explorer 11 で開かれるようになります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p113">There are a few things to consider in order to make sure that your browser-based applications continue to work as expected. If you have specific web sites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the web sites will automatically open using Internet Explorer 11.</span></span>

<span data-ttu-id="40c94-p114">さらに、イントラネット サイトが Microsoft Edge では正常に動作しなくなることがわかっている場合は、すべてのイントラネット サイトが自動的に Internet Explorer 11 で開かれるように設定することもできます。このプロセスでは、それぞれのサイトに IE11 を使用するかどうかを制御するために XML ファイルを使用します (設定の適用にはグループ ポリシーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="40c94-p114">Additionally, if you know that your intranet sites aren't going to work properly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. This process uses an XML file to govern whether IE11 is used for each site, using Group Policy to enforce settings.</span></span>

<span data-ttu-id="40c94-p115">ここまでは、よく知られている展開方法について説明しました。それ以外にも、検討対象になる 2 つの新しいアプリ展開のアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="40c94-p115">So far, we have covered well known deployment methods. But there are two new approaches to app deployment you may wish to consider.</span></span>

[<span data-ttu-id="40c94-154">エンタープライズ モードとは</span><span class="sxs-lookup"><span data-stu-id="40c94-154">What is Enterprise Mode</span></span>](https://docs.microsoft.com/ja-JP/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a><span data-ttu-id="40c94-155">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="40c94-155">Microsoft Store for Business</span></span> 

<span data-ttu-id="40c94-p116">ビジネス向け Microsoft Store は、Windows 10 デバイスの無料/有料アプリを大規模に検索、取得、管理および配布する柔軟な方法を提供します。IT 管理者は、自分のプライベート ストアに選択した Microsoft Store アプリと独自のカスタム アプリを公開できます。また、必要に応じてライセンスの割り当てと再使用ができます。ユーザーは、このストアにのみ転送されるため、承認されたアプリケーションのみを見つけてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="40c94-p116">Microsoft Store for Business provides a flexible way discover, acquire, manage, and distribute free and paid apps to Windows 10 devices at scale. As an IT admin, you can publish selected Microsoft Store apps, along with your custom own apps, to your own private store, and assign and re-use licenses as needed. Your users are directed to this store only, and so can only find and install approved apps.</span></span>

<span data-ttu-id="40c94-p117">Store アプリは、UWP アプリとしてネイティブにビルドすることも、デスクトップ ブリッジを使用して Store の既存のアプリを再パッケージ化して、Windows 10 の最新のエクスペリエンスを追加することもできます。Windows 10 のエクスペリエンスを際立たせるために使用するコードを除いて、アプリは未変更のまま引き続き完全信頼のユーザー モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="40c94-p117">Store apps can be natively built as UWP apps or you can use the Desktop Bridge to repackage your existing apps for the Store and add modern experiences for Windows 10. Aside from the code that you use to light up Windows 10 experiences, your app remains unchanged and continues to run in full-trust user mode.</span></span>

## <a name="msix-containerization"></a><span data-ttu-id="40c94-161">MSIX コンテナー化</span><span class="sxs-lookup"><span data-stu-id="40c94-161">MSIX Containerization</span></span>

<span data-ttu-id="40c94-p118">アプリケーション パッケージの新しいオプションが MSIX です。MSIX は Windows で使用可能なコンテナー化テクノロジを使用して、クイック実行、UWP および MSI パッケージの最良の側面をまとめて提供します。既存のインストーラー (EXE、MSI、APPV、APPX など) を直接 MSIX に移行するツールを使用することで、MSIX コンテナー化が、現在使用されている多数のインストール テクノロジに統合されたパスを提供することがわかります。MSIX のサポートは、Windows の現行バージョンに含まれています。Windows 10 RS5 を実行するデバイスには、MSIX パッケージ型のアプリをインストールして実行するために必要なものがすべて含まれています。Windows 10 は、受け入れた MSIX コンテナーを動的に統合しますが、アプリケーションはオペレーティング システムから分離された状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="40c94-p118">A new option for application packaging is MSIX. MSIX uses the containerization technology available in Windows, bringing together the best aspects of Click-to-Run, UWP and MSI packaging. With tools to migrate existing installers like EXE, MSI, APPV and APPX directly to MSIX we see MSIX Containerization provides a unifed path for the many installation technologies in use today. MSIX support is included in current versions of Windows: any device running Windows 10 RS5 or newer, includes everything you need to install and run MSIX packaged apps. Windows 10 dynamically integrates MSIX containers it receives, while keeping the applications separate from the operating system.</span></span>

<span data-ttu-id="40c94-p119">コンテナー化によって、パッケージのアンインストールと削除がクリーンなものになります。これは、システムにアイテムを残してしまうことがある、現在の多くの MSI および EXE ベースのパッケージとは異なります。また、アプリケーションのインストールには標準ユーザーの資格情報のみが必要になります。MSIX コンテナーのインストールには管理者の資格情報は必要ありません。MSIX コンテナーによって、更新も効率的になります。更新プログラムが公開されたときに、ブロック レベルの差分を使用することで、正味の新しいバイナリのみが適用されます。これにより、更新プログラムのペイロードが小さくなり、ネットワーク帯域幅の使用量が減って展開が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="40c94-p119">Containerization means clean uninstall and removal of packages, unlike a lot of MSI and EXE-based packages today that may leave items on the system. It also means only needing Standard User credentials to install applications – you do not have to have Administrator credentials to install MSIX containers. MSIX containers are more efficient to update too. When an update is published, use of block level differentials means only net new binaries are applied, reducing the update payload, for faster deployments consuming less network bandwidth.</span></span>

<span data-ttu-id="40c94-171">MSIX の詳細については、「[MSIX 技術コミュニティ サイト](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c94-171">You can find more information on MSIX via the [MSIX Tech Community site](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span></span>

## <a name="next-step"></a><span data-ttu-id="40c94-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="40c94-172">Next Step</span></span>

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="40c94-173">手順 4: ユーザーのファイルと設定</span><span class="sxs-lookup"><span data-stu-id="40c94-173">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)

## <a name="previous-step"></a><span data-ttu-id="40c94-174">前の手順</span><span class="sxs-lookup"><span data-stu-id="40c94-174">Previous Step</span></span>

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="40c94-175">手順 2: ディレクトリとネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="40c94-175">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2) 