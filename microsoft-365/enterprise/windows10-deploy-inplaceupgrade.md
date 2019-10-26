---
title: インプレース アップグレードによる Windows 10 Enterprise の既存デバイスへの展開
description: System Center Configuration Manager を使用して、一括アップグレードとして Windows 10 Enterprise イメージを構成および展開するためのガイダンスを提供します。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、deployment、一括アップグレード、構成マネージャー、System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 69edcd65ada007ead9e0c0d628b96f6390e34696
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733459"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a><span data-ttu-id="f61f6-104">手順 2: 既存のデバイス用に Windows 10 Enterprise を一括アップグレードとして展開する</span><span class="sxs-lookup"><span data-stu-id="f61f6-104">Step 2: Deploy Windows 10 Enterprise for existing devices as an in-place upgrade</span></span>

<span data-ttu-id="f61f6-105">*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*</span><span class="sxs-lookup"><span data-stu-id="f61f6-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="f61f6-107">現在 Windows 7 または Windows 8.1 を実行している Pc をアップグレードするための最も単純なパスは、一括アップグレードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="f61f6-107">The simplest path to upgrade PCs currently running Windows 7 or Windows 8.1 to Windows 10 is through an in-place upgrade.</span></span> <span data-ttu-id="f61f6-108">System Center Configuration Manager (構成マネージャー) のタスクシーケンスを使用して、プロセスを完全に自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-108">You can use a System Center Configuration Manager (Configuration Manager) task sequence to completely automate the process.</span></span> 

<span data-ttu-id="f61f6-109">Windows 7 または Windows 8.1 を実行している既存のコンピューターがある場合は、組織で Windows 10 を展開している場合はこのパスを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-109">If you have existing computers running Windows 7 or Windows 8.1, we recommend this path if your organization is deploying Windows 10.</span></span> <span data-ttu-id="f61f6-110">Windows インストールプログラム (Setup.exe) を活用して一括アップグレードを実行すると、既存のオペレーティングシステムのバージョンからすべてのデータ、設定、アプリケーション、およびドライバーが自動的に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-110">This leverages the Windows installation program (Setup.exe) to perform an in-place upgrade, which automatically preserves all data, settings, applications, and drivers from the existing operating system version.</span></span> <span data-ttu-id="f61f6-111">複雑な展開インフラストラクチャは必要ないため、これには最小限の IT 作業が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-111">This requires the least IT effort, because there is no need for any complex deployment infrastructure.</span></span>

<span data-ttu-id="f61f6-112">構成マネージャーを一括アップグレードとして使用して Windows 10 Enterprise のイメージを構成および展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-112">Follow these steps to configure and deploy a Windows 10 Enterprise image using Configuration Manager as an in-place upgrade.</span></span>

## <a name="the-windows-10-deployment-with-system-center-configuration-manager-poster"></a><span data-ttu-id="f61f6-113">System Center Configuration Manager を使用した Windows 10 展開のポスター</span><span class="sxs-lookup"><span data-stu-id="f61f6-113">The Windows 10 deployment with System Center Configuration Manager poster</span></span>

<span data-ttu-id="f61f6-114">構成マネージャーのポスターは、横モード (17x11) の1つのページです。</span><span class="sxs-lookup"><span data-stu-id="f61f6-114">The Configuration Manager poster is one page in landscape mode (17x11).</span></span> <span data-ttu-id="f61f6-115">ブラウザーに PDF を表示するには、以下の画像をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-115">Click the image below to view a PDF in your browser.</span></span> 

<span data-ttu-id="f61f6-116">[![構成マネージャーポスターを使用して Windows 10 を展開する](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=tKD38RgLAoOCAWJ5ppEbLevBAHk7KHtWrXldy2Jl6mY%3D&st=2019-10-24T22%3A16%3A08Z&se=2019-10-25T22%3A26%3A08Z&sp=r)</span><span class="sxs-lookup"><span data-stu-id="f61f6-116">[![Deploy Windows 10 with Configuration Manager poster](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=tKD38RgLAoOCAWJ5ppEbLevBAHk7KHtWrXldy2Jl6mY%3D&st=2019-10-24T22%3A16%3A08Z&se=2019-10-25T22%3A26%3A08Z&sp=r)</span></span>

<!--

You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) format.
-->

## <a name="part-1-verify-readiness-to-upgrade-windows"></a><span data-ttu-id="f61f6-117">パート 1: Windows のアップグレードの準備を確認する</span><span class="sxs-lookup"><span data-stu-id="f61f6-117">Part 1: Verify readiness to upgrade Windows</span></span>

<span data-ttu-id="f61f6-118">最初に、Windows Analytics のアップグレード準備機能を使用して、組織内のコンピューター、アプリケーション、およびドライバーに関する強力な洞察と推奨事項を、追加の費用をかけることなく、追加のインフラストラクチャ要件を伴わずに提供します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-118">First, use the Upgrade Readiness capability of Windows Analytics to provide powerful insights and recommendations about the computers, applications, and drivers in your organization, at no extra cost and without additional infrastructure requirements.</span></span> <span data-ttu-id="f61f6-119">この新しいサービスは、Microsoft が推奨する方法に基づいてワークフローを使用して、アップグレードと機能の更新プロジェクトを案内します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-119">This new service guides you through upgrade and feature update projects using a workflow based on Microsoft recommended practices.</span></span> <span data-ttu-id="f61f6-120">最新の在庫データを使用すると、アップグレードプロジェクトのコストとリスクのバランスを取ることができます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-120">Up-to-date inventory data allows you to balance cost and risk in your upgrade projects.</span></span>

<span data-ttu-id="f61f6-121">詳細については、「[アップグレードの準備をして Windows アップグレードを管理](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)する」を参照してください。詳細については、「アップグレードの準備状況」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-121">See [Manage Windows upgrades with Upgrade Readiness](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) to learn more, get started, use, and troubleshoot Upgrade Readiness.</span></span>

<span data-ttu-id="f61f6-122">次に、ガイドに従って System Center Configuration Manager (Current Branch) を使用し、windows 7 以降のオペレーティングシステムを Windows 10 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-122">Next, follow the guide to use System Center Configuration Manager (Current Branch) to upgrade Windows 7 or later operating system to Windows 10.</span></span> <span data-ttu-id="f61f6-123">高リスク展開の場合と同様に、先に進む前にユーザーデータをバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-123">As with any high-risk deployment, we recommend backing up user data before proceeding.</span></span> <span data-ttu-id="f61f6-124">OneDrive クラウドストレージは、Microsoft 365 ユーザーのライセンスを使用する準備が整っており、そのファイルを安全に保存するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-124">OneDrive cloud storage is ready to use for licensed Microsoft 365 users and can be used to securely store their files.</span></span> <span data-ttu-id="f61f6-125">詳細については、「 [OneDrive クイックスタートガイド](https://aka.ms/ODfBquickstartguide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-125">For more info, see [OneDrive quick start guide](https://aka.ms/ODfBquickstartguide).</span></span> <span data-ttu-id="f61f6-126">このページにアクセスするには、Office 365 または Microsoft 365 テナントのテナント管理者またはグローバル管理者としてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-126">To access this page, you must sign in as a tenant admin or global admin in an Office 365 or Microsoft 365 tenant.</span></span>

<span data-ttu-id="f61f6-127">Configuration Manager のバージョンと、対応する Windows 10 クライアントのバージョンの一覧については、「 [System Center Configuration manager での windows 10 のサポート](https://aka.ms/supportforwin10sccm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-127">For a list of Configuration Manager versions and the corresponding Windows 10 client versions that are supported, see [Support for Windows 10 for System Center Configuration Manager](https://aka.ms/supportforwin10sccm).</span></span>

<span data-ttu-id="f61f6-128">**Windows のアップグレードの準備状況を確認するには**</span><span class="sxs-lookup"><span data-stu-id="f61f6-128">**To verify readiness to upgrade Windows**</span></span>

<span data-ttu-id="f61f6-129">Windows 10 の展開を開始する前に、これらの要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-129">Review these requirements before starting your Windows 10 deployment:</span></span>

- <span data-ttu-id="f61f6-130">**アップグレード対象となる windows エディション**-デバイスでは、windows 7 または windows 8.1 のエディションを実行している必要があります。これは、Windows 10 Enterprise へのアップグレードに適しています。</span><span class="sxs-lookup"><span data-stu-id="f61f6-130">**Windows editions eligible for upgrade** - Your devices must be running editions of Windows 7 or Windows 8.1 that are eligible for upgrade to Windows 10 Enterprise.</span></span> <span data-ttu-id="f61f6-131">サポートされているエディションの一覧については、「 [Windows 10 のアップグレードパス](https://aka.ms/win10upgradepaths)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-131">For a list of supported editions, see [Windows 10 upgrade paths](https://aka.ms/win10upgradepaths).</span></span> 
- <span data-ttu-id="f61f6-132">**サポート**されるデバイス-windows 8.1 と互換性のあるほとんどのコンピューターは、windows 10 と互換性があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-132">**Supported devices** - Most computers that are compatible with Windows 8.1 will be compatible with Windows 10.</span></span> <span data-ttu-id="f61f6-133">デバイスが適切に機能するには、更新されたドライバーを Windows 10 にインストールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-133">You may need to install updated drivers in Windows 10 for your devices to properly function.</span></span> <span data-ttu-id="f61f6-134">詳細については、「 [Windows 10 の仕様](https://aka.ms/windows10specifications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-134">See [Windows 10 specifications](https://aka.ms/windows10specifications) for more info.</span></span>
- <span data-ttu-id="f61f6-135">**展開の準備**-展開の構成を開始する前に、次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-135">**Deployment preparation** - Make sure you have the following before you start configuring the deployment:</span></span>
    - <span data-ttu-id="f61f6-136">Windows 10 インストールメディア-インストールメディアは、ISO が既にマウントされている別のドライブに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-136">Windows 10 installation media - The installation media must be located on a separate drive, with the ISO already mounted.</span></span> <span data-ttu-id="f61f6-137">ISO は、 [MSDN サブスクライバーダウンロード](https://aka.ms/msdn-subscriber-downloads)から入手することも、[ボリュームライセンスサービスセンター](https://aka.ms/mvlsc)から入手することもできます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-137">You can obtain the ISO from [MSDN Subscriber Downloads](https://aka.ms/msdn-subscriber-downloads) or from the [Volume Licensing Service Center](https://aka.ms/mvlsc).</span></span>
    - <span data-ttu-id="f61f6-138">ユーザーデータのバックアップ-ユーザーデータはアップグレードに移行されますが、バックアップシナリオを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-138">Backups of user data - Although user data will be migrated in the upgrade, best practice is to configure a backup scenario.</span></span> <span data-ttu-id="f61f6-139">たとえば、すべてのユーザーデータを OneDrive アカウントにエクスポートし、BitLocker から Go に暗号化された USB フラッシュドライブ、またはネットワークファイルサーバーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-139">For example, export all user data to a OneDrive account, BitLocker To Go-encrypted USB flash drive, or network file server.</span></span> <span data-ttu-id="f61f6-140">詳細については、「 [Windows でデータをバックアップまたは転送](https://aka.ms/backuptransferdatawindows)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-140">For more information, see [Back up or transfer data in Windows](https://aka.ms/backuptransferdatawindows).</span></span>
- <span data-ttu-id="f61f6-141">**環境の準備**-既存の Configuration Manager サーバー構造を使用して、オペレーティングシステムの展開を準備します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-141">**Environment preparation** - You will use an existing Configuration Manager server structure to prepare for operating system deployment.</span></span> <span data-ttu-id="f61f6-142">構成マネージャー環境では、基本設定に加えて、次の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-142">In addition to the base setup, the following configurations should be made in the Configuration Manager environment:</span></span>
    1. <span data-ttu-id="f61f6-143">[Active Directory スキーマを拡張](https://aka.ms/extendadschema)し、 [System Management コンテナーを作成](https://aka.ms/createsysmancontainer)します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-143">[Extend the Active Directory Schema](https://aka.ms/extendadschema) and [create a System Management container](https://aka.ms/createsysmancontainer).</span></span>
    2. <span data-ttu-id="f61f6-144">Active Directory フォレストの探索と Active Directory システムの検出を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-144">Enable Active Directory Forest Discovery and Active Directory System Discovery.</span></span> <span data-ttu-id="f61f6-145">詳細については、「 [Configure discovery メソッド For System Center Configuration Manager](https://aka.ms/configurediscoverymethods)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-145">For more info, see [Configure discovery methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).</span></span>
    3. <span data-ttu-id="f61f6-146">コンテンツおよびサイト割り当ての IP 範囲の境界と境界グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-146">Create IP range boundaries and boundary group for content and site assignment.</span></span> <span data-ttu-id="f61f6-147">詳細については、「 [System Center Configuration Manager のサイト境界と境界グループを定義する](https://aka.ms/definesiteboundaries)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-147">For more info, see [Define site boundaries and boundary groups for System Center Configuration Manager](https://aka.ms/definesiteboundaries).</span></span>
    4. <span data-ttu-id="f61f6-148">Configuration Manager reporting services ポイントの役割を追加して構成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-148">Add and configure the Configuration Manager reporting services point role.</span></span> <span data-ttu-id="f61f6-149">詳細については、「 [Configuration Manager でレポートを構成する](https://aka.ms/configurereporting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-149">For more info, see [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).</span></span>
    5. <span data-ttu-id="f61f6-150">パッケージ用のファイルシステムフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-150">Create a file system folder structure for packages.</span></span>
    6. <span data-ttu-id="f61f6-151">パッケージ用の Configuration Manager コンソールフォルダー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-151">Create a Configuration Manager console folder structure for packages.</span></span>
    7. <span data-ttu-id="f61f6-152">System Center Configuration Manager (現在のブランチ) 更新プログラムおよび追加の Windows 10 前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-152">Install System Center Configuration Manager (Current Branch) updates and any additional Windows 10 prerequisites.</span></span>

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a><span data-ttu-id="f61f6-153">パート 2: 構成マネージャーを使用して Windows 10 OS イメージを追加する</span><span class="sxs-lookup"><span data-stu-id="f61f6-153">Part 2: Add a Windows 10 OS image using Configuration Manager</span></span>
<span data-ttu-id="f61f6-154">ここで、完全な Windows 10 インストールメディアを含むオペレーティングシステムアップグレードパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-154">Now you'll need to create an operating system upgrade package that contains the full Windows 10 installation media.</span></span> <span data-ttu-id="f61f6-155">次の手順では、Configuration Manager を使用して Windows 10 Enterprise x64 のアップグレードパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-155">In the following steps, you’ll use Configuration Manager to create an upgrade package for Windows 10 Enterprise x64.</span></span>

<span data-ttu-id="f61f6-156">**構成マネージャーを使用して Windows 10 OS イメージを追加するには**</span><span class="sxs-lookup"><span data-stu-id="f61f6-156">**To add a Windows 10 OS image using Configuration Manager**</span></span>

1. <span data-ttu-id="f61f6-157">Configuration Manager コンソールを使用して、[**ソフトウェアライブラリ**] ワークスペースの [**オペレーティングシステムのアップグレード**パッケージ] ノードを右クリックし、[**オペレーティングシステムアップグレードパッケージの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-157">Using the Configuration Manager console, in the **Software Library** workspace, right-click the **Operating System Upgrade Packages** node, and then select **Add Operating System Upgrade Package**.</span></span>
2. <span data-ttu-id="f61f6-158">[**データソース**] ページで、Windows 10 Enterprise x64 メディアへの UNC パスを指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-158">On the **Data Source** page, specify the UNC path to the Windows 10 Enterprise x64 media, and then select **Next**.</span></span>
3. <span data-ttu-id="f61f6-159">[**全般**] ページで、 **Windows 10 Enterprise x64 Upgrade**を指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-159">On the **General** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span> 
4. <span data-ttu-id="f61f6-160">[**概要**] ページで、[**次へ**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-160">On the **Summary** page, select **Next**, and then select **Close**.</span></span> 
5. <span data-ttu-id="f61f6-161">作成した**Windows 10 Enterprise X64 更新プログラム**パッケージを右クリックして、[**コンテンツの配布**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-161">Right-click the created **Windows 10 Enterprise x64 Update** package, and then select **Distribute Content**.</span></span> 
6. <span data-ttu-id="f61f6-162">配布ポイントを選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-162">Choose your distribution point.</span></span>

## <a name="part-3-configure-deployment-settings"></a><span data-ttu-id="f61f6-163">パート 3: 展開設定を構成する</span><span class="sxs-lookup"><span data-stu-id="f61f6-163">Part 3: Configure deployment settings</span></span>
<span data-ttu-id="f61f6-164">この手順では、Windows 10 アップグレードの設定を含むアップグレードタスクシーケンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-164">In this step, you'll configure an upgrade task sequence that contains the settings for the Windows 10 upgrade.</span></span> <span data-ttu-id="f61f6-165">次に、アップグレードするデバイスを特定し、それらのデバイスにタスクシーケンスを展開します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-165">You'll then identify the devices to upgrade, and then deploy the task sequence to those devices.</span></span>

### <a name="create-a-task-sequence"></a><span data-ttu-id="f61f6-166">タスクシーケンスを作成する</span><span class="sxs-lookup"><span data-stu-id="f61f6-166">Create a task sequence</span></span>
<span data-ttu-id="f61f6-167">アップグレードタスクシーケンスを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-167">To create an upgrade task sequence, perform the following steps:</span></span>
  
1. <span data-ttu-id="f61f6-168">構成マネージャーコンソールの [**ソフトウェアライブラリ**] ワークスペースで、[**オペレーティングシステム**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-168">In the Configuration Manager console, in the **Software Library** workspace, expand **Operating Systems**.</span></span> 
2. <span data-ttu-id="f61f6-169">[**タスク**シーケンス] ノードを右クリックし、[**タスクシーケンスの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-169">Right-click the **Task Sequences** node, and then select **Create Task Sequence**.</span></span>
3. <span data-ttu-id="f61f6-170">[**タスクシーケンスの新規作成**] ページで、[**アップグレードパッケージからのオペレーティングシステムのアップグレード**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-170">On the **Create a new task sequence** page, select **Upgrade an operating system from upgrade package**, and then select **Next**.</span></span>
4. <span data-ttu-id="f61f6-171">[**タスクシーケンス情報**] ページで、 **Windows 10 Enterprise x64 Upgrade**を指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-171">On the **Task Sequence Information** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span>
5. <span data-ttu-id="f61f6-172">[ **Windows オペレーティングシステムのアップグレード**] ページで、 **[参照**] を選択して、 **windows 10 Enterprise x64 アップグレードオペレーティングシステムアップグレードパッケージ**を選択し、[ **OK**] を選択して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-172">On the **Upgrade the Windows operating system** page, select **Browse** and choose the **Windows 10 Enterprise x64 Upgrade operating system upgrade package**, select **OK**, and then select **Next**.</span></span>
6. <span data-ttu-id="f61f6-173">残りのウィザードページを続けて、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-173">Continue through the remaining wizard pages, and then select **Close**.</span></span>

### <a name="create-a-device-collection"></a><span data-ttu-id="f61f6-174">デバイスコレクションを作成する</span><span class="sxs-lookup"><span data-stu-id="f61f6-174">Create a device collection</span></span>
<span data-ttu-id="f61f6-175">アップグレードタスクシーケンスを作成した後、アップグレードするデバイスを含むコレクションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-175">After you create the upgrade task sequence, you'll need to create a collection that contains the devices you will upgrade.</span></span>

> [!NOTE]
> <span data-ttu-id="f61f6-176">次の設定を使用して、単一のデバイスで展開をテストします。</span><span class="sxs-lookup"><span data-stu-id="f61f6-176">Use the following settings to test the deployment on a single device.</span></span> <span data-ttu-id="f61f6-177">準備が整ったら、さまざまなメンバーシップルールを使用してデバイスのグループを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-177">You can use different membership rules to include groups of devices when you are ready.</span></span> <span data-ttu-id="f61f6-178">詳細については、「 [System Center Configuration Manager でコレクションを作成する方法](https://aka.ms/sccm-create-collections)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-178">For more info, see [How to create collections in System Center Configuration Manager](https://aka.ms/sccm-create-collections).</span></span>

1. <span data-ttu-id="f61f6-179">構成マネージャーコンソールの [**アセットとコンプライアンス**] ワークスペースで、[**デバイスコレクション**] を右クリックし、[**デバイスコレクションの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-179">In the Configuration Manager console, in the **Assets and Compliance** workspace, right-click **Device Collections**, and then select **Create Device Collection**.</span></span> 
2. <span data-ttu-id="f61f6-180">[デバイスコレクションの作成] ウィザードの **[全般**] ページで、次の設定を入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-180">In the Create Device Collection wizard, on the **General** page, enter the following settings and then select **Next**:</span></span>
    - <span data-ttu-id="f61f6-181">Name: Windows 10 Enterprise x64 アップグレード</span><span class="sxs-lookup"><span data-stu-id="f61f6-181">Name: Windows 10 Enterprise x64 Upgrade</span></span>
    - <span data-ttu-id="f61f6-182">コレクションを制限する: すべてのシステム</span><span class="sxs-lookup"><span data-stu-id="f61f6-182">Limiting Collection: All Systems</span></span>
3. <span data-ttu-id="f61f6-183">[**メンバーシップの規則**] ページで、[**ルール** > の**直接ルール**の追加] を選択して、[ダイレクトメンバーシップの規則の作成] ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-183">On the **Membership Rules** page, select **Add Rule** > **Direct rule** to launch the Create Direct Membership Rule Wizard.</span></span>
4. <span data-ttu-id="f61f6-184">[ダイレクトメンバーシップルールの作成] ウィザードの [**ようこそ**] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-184">On the **Welcome** page of the Create Direct Membership Rule Wizard, select **Next**.</span></span>
5. <span data-ttu-id="f61f6-185">[**リソースの検索**] ページで、次の設定を入力します。プレースホルダーの**値**のテキストは、アップグレードするデバイスの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-185">On the **Search for Resources** page, enter the following settings, replacing the placeholder **Value** text with the name of the device you are upgrading:</span></span> 
    - <span data-ttu-id="f61f6-186">リソースクラス: システムリソース</span><span class="sxs-lookup"><span data-stu-id="f61f6-186">Resource Class: System Resource</span></span>
    - <span data-ttu-id="f61f6-187">属性名: Name</span><span class="sxs-lookup"><span data-stu-id="f61f6-187">Attribute Name: Name</span></span>
    - <span data-ttu-id="f61f6-188">値: *PC0003*</span><span class="sxs-lookup"><span data-stu-id="f61f6-188">Value: *PC0003*</span></span>
6. <span data-ttu-id="f61f6-189">[**リソースの選択**] ページで、デバイスを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-189">On the **Select Resources** page, select your device, and select **Next**.</span></span>
7. <span data-ttu-id="f61f6-190">[ダイレクトメンバーシップの規則の作成] ウィザードと [デバイスコレクションの作成] ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-190">Complete the Create Direct Membership Rule wizard and the Create Device Collection Wizard.</span></span>  
8. <span data-ttu-id="f61f6-191">Windows 10 Enterprise x64 アップグレードコレクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-191">Review the Windows 10 Enterprise x64 Upgrade collection.</span></span> <span data-ttu-id="f61f6-192">コレクションに追加したコンピューターが表示されるまで、処理を続行しないでください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-192">Do not continue until you see the machines you added in the collection.</span></span>

### <a name="create-an-operating-system-deployment"></a><span data-ttu-id="f61f6-193">オペレーティングシステムの展開を作成する</span><span class="sxs-lookup"><span data-stu-id="f61f6-193">Create an operating system deployment</span></span>
<span data-ttu-id="f61f6-194">タスクシーケンスの展開を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-194">Follow these steps to create a deployment for the task sequence.</span></span>

1. <span data-ttu-id="f61f6-195">構成マネージャーコンソールの [**ソフトウェアライブラリ**] ワークスペースで、前の手順で作成したタスクシーケンスを右クリックし、[**展開**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-195">In the Configuration Manager console, in the **Software Library** workspace, right-click the task sequence you created in a previous step, and then select **Deploy**.</span></span>
2. <span data-ttu-id="f61f6-196">[**全般**] ページで、 **Windows 10 Enterprise x64 アップグレード**コレクションを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-196">On the **General** page, select the **Windows 10 Enterprise x64 Upgrade** collection, and then select **Next**.</span></span>
3. <span data-ttu-id="f61f6-197">[**コンテンツ**] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-197">On the **Content** page, select **Next**.</span></span>
4. <span data-ttu-id="f61f6-198">[**展開の設定**] ページで、次の設定を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-198">On the **Deployment Settings** page, select the following settings, and then select **Next**:</span></span>

    > [!NOTE]
    > <span data-ttu-id="f61f6-199">このテスト展開では、目的を**利用可能**に設定します。これにより、展開を開始するためにユーザーの介入が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f61f6-199">For this test deployment, you'll set the purpose to **Available**, which requires user intervention to start the deployment.</span></span> <span data-ttu-id="f61f6-200">運用環境では、必要な目的を使用して展開を自動化することができます。これには、展開の実行時のスケジュール設定など、追加のオプションの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-200">In a production environment, you may wish to automate the deployment using the Required purpose, which involves configuring additional options such as scheduling when the deployment is run.</span></span> 

    - <span data-ttu-id="f61f6-201">アクション: Install</span><span class="sxs-lookup"><span data-stu-id="f61f6-201">Action: Install</span></span>
    - <span data-ttu-id="f61f6-202">目的: 利用可能</span><span class="sxs-lookup"><span data-stu-id="f61f6-202">Purpose: Available</span></span>

5. <span data-ttu-id="f61f6-203">[**スケジュール**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-203">On the **Scheduling** page, accept the default settings, and then select **Next**.</span></span>
6. <span data-ttu-id="f61f6-204">[**ユーザーの作業**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-204">On the **User Experience** page, accept the default settings, and then select **Next**.</span></span>
7. <span data-ttu-id="f61f6-205">[**通知**] ページで、既定の設定をそのまま使用し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-205">On the **Alerts** page, accept the default settings, and then select **Next**.</span></span>
8. <span data-ttu-id="f61f6-206">[**概要**] ページで、[**次へ**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-206">On the **Summary** page, select **Next**, and then select **Close**.</span></span>

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a><span data-ttu-id="f61f6-207">パート 4: Windows 10 のアップグレードタスクシーケンスを開始する</span><span class="sxs-lookup"><span data-stu-id="f61f6-207">Part 4: Start the Windows 10 upgrade task sequence</span></span>
<span data-ttu-id="f61f6-208">アップグレードするデバイスで Windows 10 のアップグレードタスクシーケンスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-208">Follow these steps to start the Windows 10 Upgrade task sequence on the device that you are upgrading.</span></span>
 
1. <span data-ttu-id="f61f6-209">Windows コンピューターにログオンし、**ソフトウェアセンター**を起動します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-209">Log on to the Windows computer and start **Software Center**.</span></span>
2. <span data-ttu-id="f61f6-210">前の手順で作成したタスクシーケンスを選択し、[**インストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-210">Select the task sequence that you created in a previous step, and then select **Install**.</span></span>
3. <span data-ttu-id="f61f6-211">タスクシーケンスが開始されると、必要なコマンドラインパラメーターを指定して Windows セットアッププログラム (Setup.exe) を起動することによって、一括アップグレードプロセスが自動的に開始されます。これにより、すべてのデータ、設定、アプリ、およびドライバ.</span><span class="sxs-lookup"><span data-stu-id="f61f6-211">When the task sequence begins, it automatically initiates the in-place upgrade process by invoking the Windows setup program (Setup.exe) with the necessary command-line parameters to perform an automated upgrade, which preserves all data, settings, apps, and drivers.</span></span>
4. <span data-ttu-id="f61f6-212">タスクシーケンスが正常に完了すると、コンピューターは Windows 10 に完全にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-212">After the task sequence completes successfully, the computer will be fully upgraded to Windows 10.</span></span>

<span data-ttu-id="f61f6-p119">エンタープライズ環境で Windows 10 を使用するときに問題が発生した場合、「[最も一般的な問題に対する上位の Microsoft サポート ソリューション](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)」 を参照してください。これらのリソースには、サポート技術情報の記事、更新情報、およびライブラリの記事が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-p119">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="f61f6-215">組織全体で更新プログラムをロールアウトする際には、Windows Analytics の更新プログラムのコンプライアンス機能を使用して、Windows 10 デバイスの OS 更新プログラムのコンプライアンス、展開の進行状況、およびエラーのトラブルシューティングの全体的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-215">During the rollout of updates across your organization, use the Update Compliance capability of Windows Analytics to provide a holistic view of OS update compliance, update deployment progress, and failure troubleshooting for Windows 10 devices.</span></span> <span data-ttu-id="f61f6-216">この新しいサービスは、インストールの進行状況、Windows 更新プログラムの構成、その他の情報を含む診断データを使用して、そのような洞察を追加のコストや追加のインフラストラクチャ要件を伴わずに提供します。</span><span class="sxs-lookup"><span data-stu-id="f61f6-216">This new service uses diagnostic data including installation progress, Windows Update configuration and other information to provide such insights, at no extra cost and without additional infrastructure requirements.</span></span> <span data-ttu-id="f61f6-217">Business またはその他の管理ツール用の Windows Update で使用されているかどうかにかかわらず、デバイスが適切に更新されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-217">Whether it's used with Windows Update for Business or other management tools, you can be assured that your devices are properly updated.</span></span>

<span data-ttu-id="f61f6-218">詳細については、「 [windows の更新プログラムの監視」および「更新プログラムのコンプライアンスを使用した Windows Defender ウイルス対策](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)」を参照し、更新プログラムのコンプライアンスをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f61f6-218">See [Monitor Windows Updates and Windows Defender Antivirus with Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) to learn more, get started, and use Update Compliance.</span></span>

<span data-ttu-id="f61f6-219">中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step2)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f61f6-219">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f61f6-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="f61f6-220">Next step</span></span>

|||
|:-------|:-----|
|![手順 3](./media/stepnumbers/Step3.png)| [<span data-ttu-id="f61f6-222">Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="f61f6-222">Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
