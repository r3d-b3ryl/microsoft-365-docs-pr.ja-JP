---
title: 手順 3 - Office および LOB アプリの配信
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/27/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office および LOB アプリの配信方法について説明します。
ms.openlocfilehash: a4bc1a765edf6938ad37d91d8bf94950b6672bfe
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112593"
---
# <a name="step-3-office-and-lob-app-delivery"></a><span data-ttu-id="ecddd-103">手順 3: Office および LOB アプリの配信</span><span class="sxs-lookup"><span data-stu-id="ecddd-103">Step 3: Office and LOB App Delivery</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><span data-ttu-id="ecddd-104"><strong>手順 3: Office および LOB アプリの配信</strong></span><span class="sxs-lookup"><span data-stu-id="ecddd-104"><strong>Step 3: Office and LOB App Delivery</strong></span></span></p>
<p><span data-ttu-id="ecddd-p101">目的のアプリがパッケージ化されていて、自動インストールの準備が整っていることを確認してください。Office 365 ProPlus のクイック実行パッケージが、Office アプリケーションの構成、配信および最新状態の維持のための新しいオプションをどのように提供するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p101">Ensure your apps are packaged and ready for automated installation. Learn how Click-to-Run packaging with Office 365 ProPlus gives you new options to configure, deliver and keep your Office apps up-to-date.</span></span></p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="ecddd-107">Office および LOB アプリの配信は、推奨される展開プロセスの輪における 3 番目の手順であり、Office と LOB をインストールおよび管理するためのオプションもこの手順に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-107">Office and LOB App Delivery is the third step in our recommended deployment process wheel covering the options to install and manage Office and LOB.</span></span> <span data-ttu-id="ecddd-108">展開を正常に行うために、最初の 2 つの手順は必ず実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-108">For successful deployment do not skip the first two steps.</span></span>  <span data-ttu-id="ecddd-109">デスクトップ展開プロセス全体を確認するには、「[デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecddd-109">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="ecddd-110">この時点で、Office および基幹業務アプリを配信する準備は整っています。そのための方法はいくつかありますが、その中には優れた新しいオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecddd-110">You are now ready to deliver Office and your Line of Business Apps and there are a number of ways to do this, including some exciting new options.</span></span> <span data-ttu-id="ecddd-111">一部のアプリケーションは 32 ビットまたは 64 ビットのどちらかでコンパイルされたバージョンとしてのみの使用となりますが、それ以外の Office 365 ProPlus などのアプリケーションは 32 ビットおよび 64 ビットでネイティブにコンパイル済みのコードとして使用できるため、展開するバージョンを決めることがとても重要になります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-111">While some applications are only available as either a 32-bit or 64-bit compiled version, others such as Office 365 ProPlus, offer both as 32-bit and 64-bit native compiled code, and one of biggest decisions you will make is which version to deploy.</span></span> <span data-ttu-id="ecddd-112">新しいデバイスで追加の計算能力と RAM を活用するには、32 ビットの依存関係がない場合は 64 ビット バージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ecddd-112">To take advantage of additional compute power and RAM on new devices Microsoft recommends using the 64-bit version when there are no 32-bit dependencies.</span></span> <span data-ttu-id="ecddd-113">アドインやファイルに関連する互換性の問題を特定するには、先に進む前に「手順 1: デバイスとアプリの準備」を再度確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ecddd-113">To determine any add-in or file-related compatibility challenges you may have it is recommended to revisit Step 1 Device and App Readiness before you continue.</span></span>

<span data-ttu-id="ecddd-p104">障害になるものがない場合は、Microsoft Office を含めてすべてのアプリの 64 ビット バージョンを展開することをお勧めします。64 ビット ネイティブでコンパイルされたアプリは、最高のパフォーマンスを発揮する、最も将来性のある選択になります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p104">If nothing is blocking you, we recommend you deploy 64-bit versions of all apps, including Microsoft Office. 64-bit native compiled apps offer the best performance and is the most future-proof choice.</span></span>

<span data-ttu-id="ecddd-116">Windows にアプリをインストールするための方法とモデルは多数あります。次に、選択可能な配信のオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ecddd-116">There are many methods and models for installing apps on Windows, so let’s look at your delivery options.</span></span>

[<span data-ttu-id="ecddd-117">Windows 10 アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="ecddd-117">Windows 10 application management</span></span>](https://docs.microsoft.com/windows/application-management/)

## <a name="msi-based-deployments"></a><span data-ttu-id="ecddd-118">MSI ベースの展開</span><span class="sxs-lookup"><span data-stu-id="ecddd-118">MSI-based Deployments</span></span>

<span data-ttu-id="ecddd-119">基幹業務アプリについては、MSI ベースのパッケージまたは実行可能ファイルを使用して、OS 展開のタスク シーケンスの一部としてアプリをインストールすることになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="ecddd-119">For your line of business apps, you’ll probably use MSI-based packages or executable  and install apps as part of an OS deployment task sequence.</span></span> <span data-ttu-id="ecddd-120">そうしたパッケージは、Windows 10 でも引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="ecddd-120">Windows 10 continues to work with these packages.</span></span>

<span data-ttu-id="ecddd-p106">Microsoft Endpoint Configuration Manager や Microsoft Intune などのソフトウェア展開ツールも、MSI パッケージ型のアプリを配信するように最適化されています。Windows 10 でアプリを検証していれば、アプリの配信に Microsoft Endpoint Configuration Manager (Current Branch) を使用できます。Microsoft Intune の「ポータル サイト」を使用している場合は、IT 部門によって承認された組織が利用できるアプリの選択を拡張して、最新のアプリケーションを含めるようにすると、ユーザーは必要なものを自分で選択できます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p106">Software deployment tools like System Center Configuration Manager and Microsoft Intune are also optimized to deliver MSI-packaged apps. Once you have validated your apps on Windows 10, you can use System Center Configuration Manager (current branch) for app delivery. If you use the Company Portal in Microsoft Intune you can extend the choice of IT sanctioned apps available to your organization to include the latest applications, and users to self-select what they need.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a><span data-ttu-id="ecddd-124">PC のイメージング</span><span class="sxs-lookup"><span data-stu-id="ecddd-124">PC Imaging</span></span>

<span data-ttu-id="ecddd-125">もう 1 つの一般的なアプリの配信方法は、PC のイメージングです。</span><span class="sxs-lookup"><span data-stu-id="ecddd-125">Another popular method of app delivery is PC imaging.</span></span> <span data-ttu-id="ecddd-126">この場合、タスク シーケンスまたは手動のどちらかでサンプル PC にアプリケーションをインストールし、必要なアプリケーションがプレインストールされた状態のシステム イメージをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="ecddd-126">In this case, applications are either installed via task sequence or manually on a sample PC, then a system image is captured with the required applications pre-installed.</span></span> <span data-ttu-id="ecddd-127">ビルドとキャプチャのためのイメージングは、新しい PC のプロビジョニング時に時間を節約することができますが、そのイメージ内のオペレーティング システムとアプリはすぐに古いものになってしまいます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-127">The imaging approach to build and capture can save time when provisioning new PCs but remember operating systems and apps within the image can become stale quickly.</span></span> <span data-ttu-id="ecddd-128">Windows 10 および Office 365 ProPlus の累積的な更新プログラム モデルでこの問題に対処することはできますが、完全に解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="ecddd-128">The Cumulative Update model in Windows 10 and Office 365 ProPlus help with this problem, but doesn’t eliminate it completely.</span></span> <span data-ttu-id="ecddd-129">そのため、展開時にアプリケーションをイメージの外側からインストールする thin イメージのアプローチをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ecddd-129">This is why we recommend a thin image approach, where your applications are installed from outside the image at deploy time.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

<span data-ttu-id="ecddd-130">イメージに Office 365 ProPlus を含める必要がある場合は、ユーザー ベースのライセンス認証を使用することになります。システム管理者が事前にライセンス認証することはできません。Office 展開ツールを使用して、イメージングするデバイスに Office をプレインストールして、ユーザー サインインをスキップします。</span><span class="sxs-lookup"><span data-stu-id="ecddd-130">If you do want to include Office 365 ProPlus in your image, remember that this uses a user-based activation; it cannot be pre-activated by the system admin. Use the Office Deployment Tool to pre-install Office on the device you are imaging and skip the user sign-in.</span></span> <span data-ttu-id="ecddd-131">イメージが展開されれば、エンドユーザーは自分の Office 365 の資格情報でサインインし、Office 365 ProPlus をアクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-131">Once the image is deployed end users can sign-in using their Office 365 credentials and activate Office 365 ProPlus.</span></span>

[<span data-ttu-id="ecddd-132">オペレーティング システムをインストールするタスク シーケンスの作成</span><span class="sxs-lookup"><span data-stu-id="ecddd-132">Create a Task Sequence to Install an Operating System</span></span>](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

[<span data-ttu-id="ecddd-133">オペレーティング システム イメージの一部としての Office 365 ProPlus の展開</span><span class="sxs-lookup"><span data-stu-id="ecddd-133">Deploy Office 365 ProPlus as part of an operating system image</span></span>](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-as-part-of-an-operating-system-image)

## <a name="office-click-to-run"></a><span data-ttu-id="ecddd-134">Office クイック実行</span><span class="sxs-lookup"><span data-stu-id="ecddd-134">Office Click-to-Run</span></span> 

<span data-ttu-id="ecddd-135">Office 365 ProPlus はクイック実行を使用してインストールします。今後リリースされる Windows の Office 2019 リリースのすべてのバージョンでは、MSI ベースのパッケージではなくクイック実行になります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-135">Office 365 ProPlus is installed using Click-to-Run, and Click-to-Run replaces MSI-based packaging in every version of the upcoming Office 2019 release for Windows.</span></span> <span data-ttu-id="ecddd-136">クイック実行には、より速いインストール、より速くて効率的な更新、アンインストールの円滑な実行などの多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-136">It brings with it a number of advantages, including faster installations, faster and more efficient updating, and cleaner uninstallation.</span></span> 

<span data-ttu-id="ecddd-137">クイック実行によって配信されたプログラムは、コンピューター上の仮想アプリケーション環境で実行されるため、競合することなく他のアプリケーションと共存することができます。使用するディスク領域は、MSI ベースのパッケージの約半分のみとなります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-137">Programs delivered via Click-to-Run execute in a virtual application environment on your computer and so co-exist with other applications without conflict; they also take about half the disk space they would as an MSI-based package.</span></span> <span data-ttu-id="ecddd-138">Office アプリケーションの配信および管理は、Office アプリのダウンロード、構成、カスタマイズに必要な Office セットアップ エンジンである[Office 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)で行います。</span><span class="sxs-lookup"><span data-stu-id="ecddd-138">Office applications are delivered and managed via the [Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) which is the Office setup engine needed to download, configure, and customize your Office apps.</span></span> <span data-ttu-id="ecddd-139">Office 展開ツールは、Office インストールの構成およびカスタマイズの方法に関するメタデータの処理手順を提供する構成 XML ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-139">The Office Deployment Tool reads a configuration XML file which provides the metadata instructions on how to configure and customization your Office installation.</span></span>

<span data-ttu-id="ecddd-140">Microsoft では、展開の設定をカスタマイズして構成 XML ファイルを作成するには、[Office カスタマイズ ツール](https://config.office.com/)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ecddd-140">Microsoft recommends using the [Office Customization Tool](https://config.office.com/) to customize your deployment settings and create your configuration XML file.</span></span> <span data-ttu-id="ecddd-141">Office カスタマイズ ツールを使用して、インストールするアプリケーションと言語、アプリケーションの更新方法、アプリケーションの設定、インストール操作を決めることができます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-141">Through the Office Customization Tool you can set which applications and languages will be installed, how the applications will be updated, application preferences, and installation expereince settings.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-7.png)

<span data-ttu-id="ecddd-p112">Configuration Manager は、引き続き Office 365 ProPlus の広範囲の展開に使用できます。Configuration Manager (Current Branch) には、最新版 Office カスタマイズ ツールのネイティブ サポート、インストール時のクイック実行に対応するパッケージのカスタマイズ、およびインストール後のソフトウェア更新管理のネイティブ サポートがあります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p112">If you use System Center Configuration Manager, you can still use it for broad deployment of Office 365 ProPlus. System Center Configuration Manager (current branch) has native support for the updated Office Customization Tool, package customization for Click-to-Run at install time, and native support for software update management post installation.</span></span>

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-6.png)

[<span data-ttu-id="ecddd-144">Office 365 ProPlus の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="ecddd-144">Deployment Guide for Office 365 ProPlus</span></span>](https://docs.microsoft.com/deployoffice/deployment-guide-for-office-365-proplus)

[<span data-ttu-id="ecddd-145">Office 365 ProPlus にアップグレードする際に Office の既存の MSI バージョンを削除する</span><span class="sxs-lookup"><span data-stu-id="ecddd-145">Remove existing MSI versions of Office when upgrading to Office 365 ProPlus</span></span>](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version)

[<span data-ttu-id="ecddd-146">Configuration Manager を使用した Office 365 ProPlus の管理</span><span class="sxs-lookup"><span data-stu-id="ecddd-146">Manage Office 365 ProPlus with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

[<span data-ttu-id="ecddd-147">Microsoft Intune で Windows 10 デバイスに Office 365 アプリを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ecddd-147">Assign Office 365 apps to Windows 10 devices with Microsoft Intune</span></span>](https://docs.microsoft.com/intune/apps-add-office365)

## <a name="browser-based-apps"></a><span data-ttu-id="ecddd-148">ブラウザー ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="ecddd-148">Browser-based Apps</span></span>

<span data-ttu-id="ecddd-p113">ブラウザー ベースのアプリケーションが引き続き期待どおりに動作するようにするには、いくつかの考慮すべき事項があります。Microsoft Edge との互換性に問題がある特定の Web サイトとアプリがある場合は、エンタープライズ モード サイト一覧を使用することで、その Web サイトが自動的に Internet Explorer 11 で開かれるようになります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p113">There are a few things to consider in order to make sure that your browser-based applications continue to work as expected. If you have specific web sites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the web sites will automatically open using Internet Explorer 11.</span></span>

<span data-ttu-id="ecddd-p114">さらに、イントラネット サイトが Microsoft Edge では正常に動作しなくなることがわかっている場合は、すべてのイントラネット サイトが自動的に Internet Explorer 11 で開かれるように設定することもできます。このプロセスでは、それぞれのサイトに IE11 を使用するかどうかを制御するために XML ファイルを使用します (設定の適用にはグループ ポリシーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p114">Additionally, if you know that your intranet sites aren't going to work properly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. This process uses an XML file to govern whether IE11 is used for each site, using Group Policy to enforce settings.</span></span>

[<span data-ttu-id="ecddd-153">エンタープライズ モードとは</span><span class="sxs-lookup"><span data-stu-id="ecddd-153">What is Enterprise Mode</span></span>](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

<span data-ttu-id="ecddd-154">ここまでは、よく知られている展開方法を見てきました。</span><span class="sxs-lookup"><span data-stu-id="ecddd-154">So far, we have covered well known deployment methods.</span></span> <span data-ttu-id="ecddd-155">これら以外にも、アプリの新しい展開方法が 2 つありますので、ぜひ検討してみてください。</span><span class="sxs-lookup"><span data-stu-id="ecddd-155">But there are two new approaches to app deployment you may wish to consider.</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="ecddd-156">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ecddd-156">Microsoft Store for Business</span></span> 

<span data-ttu-id="ecddd-157">ビジネス向け Microsoft Store には、無料および有料アプリの検索、取得、管理、および Windows 10 デバイスへの配布に関する方法が幅広く用意されています。</span><span class="sxs-lookup"><span data-stu-id="ecddd-157">Microsoft Store for Business provides a flexible way discover, acquire, manage, and distribute free and paid apps to Windows 10 devices at scale.</span></span> <span data-ttu-id="ecddd-158">IT 管理者は、必要に応じてライセンスを割り当てて再利用しながら、選択した Microsoft Store アプリを独自のカスタム アプリと共に自分のプライベート ストアに公開できます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-158">As an IT admin, you can publish selected Microsoft Store apps, along with your custom own apps, to your own private store while assigning and re-using licenses as needed.</span></span> <span data-ttu-id="ecddd-159">ユーザーはこのストアにのみアクセスすることができ、検索してインストールできるのは承認されたアプリのみとなります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-159">Your users are directed to this store only, and so can only find and install approved apps.</span></span>

<span data-ttu-id="ecddd-p117">Store アプリは、UWP アプリとしてネイティブにビルドすることも、デスクトップ ブリッジを使用して Store の既存のアプリを再パッケージ化して、Windows 10 の最新のエクスペリエンスを追加することもできます。Windows 10 のエクスペリエンスを際立たせるために使用するコードを除いて、アプリは未変更のまま引き続き完全信頼のユーザー モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p117">Store apps can be natively built as UWP apps or you can use the Desktop Bridge to repackage your existing apps for the Store and add modern experiences for Windows 10. Aside from the code that you use to light up Windows 10 experiences, your app remains unchanged and continues to run in full-trust user mode.</span></span>

## <a name="msix-containerization"></a><span data-ttu-id="ecddd-162">MSIX コンテナー化</span><span class="sxs-lookup"><span data-stu-id="ecddd-162">MSIX Containerization</span></span>

<span data-ttu-id="ecddd-163">アプリケーション パッケージの新しいオプションが MSIX です。</span><span class="sxs-lookup"><span data-stu-id="ecddd-163">A new option for application packaging is MSIX.</span></span> <span data-ttu-id="ecddd-164">MSIX では、Windows で利用可能なコンテナー化のテクノロジが駆使されます。MSIX は、クイック実行、UWP、MSI パッケージの強みを持ち合わせています。</span><span class="sxs-lookup"><span data-stu-id="ecddd-164">MSIX uses the containerization technology available in Windows, bringing together the best aspects of Click-to-Run, UWP and MSI packaging.</span></span> <span data-ttu-id="ecddd-165">EXE、MSI、APPV、APPX などの既存のインストーラーを MSIX に直接移行するツールを使用すれば、MSIX コンテナー化が、今日使用されている多くのインストール手法が統合されたものであることが分かるはずです。</span><span class="sxs-lookup"><span data-stu-id="ecddd-165">With tools to migrate existing installers like EXE, MSI, APPV and APPX directly to MSIX we see MSIX Containerization provides a unifed path for the many installation technologies in use today.</span></span> <span data-ttu-id="ecddd-166">MSIX は、現在のバージョンの Windows でサポートされています。Windows 10 RS5 以降を実行しているデバイスには、MSIX パッケージ アプリのインストールと実行に必要なすべてのものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecddd-166">MSIX support is included in current versions of Windows: any device running Windows 10 RS5 or newer includes everything you need to install and run MSIX packaged apps.</span></span> <span data-ttu-id="ecddd-167">Windows 10 は、受け入れた MSIX コンテナーを動的に統合しますが、アプリケーションはオペレーティング システムから分離されたままの状態となります。</span><span class="sxs-lookup"><span data-stu-id="ecddd-167">Windows 10 dynamically integrates MSIX containers it receives, while keeping the applications separate from the operating system.</span></span>

<span data-ttu-id="ecddd-p119">コンテナー化によって、パッケージのアンインストールと削除がクリーンなものになります。これは、システムにアイテムを残してしまうことがある、現在の多くの MSI および EXE ベースのパッケージとは異なります。また、アプリケーションのインストールには標準ユーザーの資格情報のみが必要になります。MSIX コンテナーのインストールには管理者の資格情報は必要ありません。MSIX コンテナーによって、更新も効率的になります。更新プログラムが公開されたときに、ブロック レベルの差分を使用することで、正味の新しいバイナリのみが適用されます。これにより、更新プログラムのペイロードが小さくなり、ネットワーク帯域幅の使用量が減って展開が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="ecddd-p119">Containerization means clean uninstall and removal of packages, unlike a lot of MSI and EXE-based packages today that may leave items on the system. It also means only needing Standard User credentials to install applications – you do not have to have Administrator credentials to install MSIX containers. MSIX containers are more efficient to update too. When an update is published, use of block level differentials means only net new binaries are applied, reducing the update payload, for faster deployments consuming less network bandwidth.</span></span>

<span data-ttu-id="ecddd-172">MSIX の詳細については、「[MSIX 技術コミュニティ サイト](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecddd-172">You can find more information on MSIX via the [MSIX Tech Community site](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)</span></span>

## <a name="next-step"></a><span data-ttu-id="ecddd-173">次の手順</span><span class="sxs-lookup"><span data-stu-id="ecddd-173">Next Step</span></span>

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="ecddd-174">手順 4: ユーザーのファイルと設定</span><span class="sxs-lookup"><span data-stu-id="ecddd-174">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)

## <a name="previous-step"></a><span data-ttu-id="ecddd-175">前の手順</span><span class="sxs-lookup"><span data-stu-id="ecddd-175">Previous Step</span></span>

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="ecddd-176">手順 2: ディレクトリとネットワークの準備</span><span class="sxs-lookup"><span data-stu-id="ecddd-176">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2) 