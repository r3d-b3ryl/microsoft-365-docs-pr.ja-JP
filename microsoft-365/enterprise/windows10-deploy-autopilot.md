---
title: Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する
description: Windows Autopilot を使用して Windows 10 Enterprise を構成および展開するためのガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開、Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 0d85bc51ac3f224b396281ff4e8414541097ed22
ms.sourcegitcommit: 2aeafb631aaabc53eea0a8029711eb891e48d249
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37746543"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a><span data-ttu-id="65ef8-104">手順 3: Windows Autopilot を使用して新しいデバイスに Windows 10 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="65ef8-104">Step 3: Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>

<span data-ttu-id="65ef8-105">*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*</span><span class="sxs-lookup"><span data-stu-id="65ef8-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="65ef8-p101">新しい Windows 10 PC では、Windows Autopilot を使用して、組織の OOBE (out-of-box-experience) をカスタマイズし、すでに構成されているアプリや設定を使用して新しいシステムを展開できます。イメージの展開や挿入するドライバー、管理するインフラストラクチャはありません。各ユーザーは IT 管理者に問い合わせる必要なく、展開プロセスを個別に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p101">If you have new Windows 10 PCs, you can use Windows Autopilot to customize the out-of-box-experience (OOBE) for your organization and deploy a new system with apps and settings already configured. There are no images to deploy, no drivers to inject, and no infrastructure to manage. Users can go through the deployment process independently, without the need consult their IT administrator.</span></span>

<span data-ttu-id="65ef8-p102">Windows Autopilot を使用して、新しい Windows 10 デバイスをセットアップして事前構成し、使用準備を整えることができます。Windows Autopilot の利点やシナリオについての詳細情報は、「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)」を参照してください。準備が完了したら、次のパートに従って設定を開始します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p102">You can set up and pre-configure new Windows 10 devices and get them ready for productive use using Windows Autopilot. To learn more about Windows Autopilot, including benefits and Windows Autopilot scenarios, see [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot). When ready, follow these parts to start setting up new devices.</span></span>

## <a name="the-windows-autopilot-deployment-process-poster"></a><span data-ttu-id="65ef8-113">Windows 自動操縦の展開プロセスのポスター</span><span class="sxs-lookup"><span data-stu-id="65ef8-113">The Windows Autopilot deployment process poster</span></span>

<span data-ttu-id="65ef8-114">Windows 自動操縦ポスターは、縦置きモード (11x17) の2ページです。</span><span class="sxs-lookup"><span data-stu-id="65ef8-114">The Windows Autopilot poster is two pages in portrait mode (11x17).</span></span> <span data-ttu-id="65ef8-115">ブラウザーに PDF を表示するには、以下の画像をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65ef8-115">Click the image below to view a PDF in your browser.</span></span> 

<span data-ttu-id="65ef8-116">[![Autopilot ポスターを使用した Windows 10 の展開](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=bfzlEl8SrShCQyj8E2QUf6LJfxlKre6ortODE4qHjrc%3D&st=2019-10-24T22%3A18%3A33Z&se=2019-10-25T22%3A28%3A33Z&sp=r)</span><span class="sxs-lookup"><span data-stu-id="65ef8-116">[![Deploy Windows 10 with Autopilot poster](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=bfzlEl8SrShCQyj8E2QUf6LJfxlKre6ortODE4qHjrc%3D&st=2019-10-24T22%3A18%3A33Z&se=2019-10-25T22%3A28%3A33Z&sp=r)</span></span>

<span data-ttu-id="65ef8-117">このポスターは、 [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf)または[Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx)形式でダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-117">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx) format.</span></span>

## <a name="part-1-start-windows-autopilot-deployment"></a><span data-ttu-id="65ef8-118">パート 1: Windows Autopilot 展開を開始する</span><span class="sxs-lookup"><span data-stu-id="65ef8-118">Part 1: Start Windows Autopilot deployment</span></span>
<span data-ttu-id="65ef8-119">「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot)」を参照して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="65ef8-119">See [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) to:</span></span>

1. <span data-ttu-id="65ef8-p104">Windows Autopilot 展開についての詳細情報を参照し、前提条件を完了します。前提条件は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p104">Learn about and complete the prerequisites for Windows Autopilot deployment. The prerequisites include:</span></span>
    - <span data-ttu-id="65ef8-122">**デバイスの登録と OOBE のカスタマイズ**</span><span class="sxs-lookup"><span data-stu-id="65ef8-122">**Device registration and OOBE customization**</span></span>

        <span data-ttu-id="65ef8-p105">デバイスを登録するには、ハードウェア ID を取得し、それを登録する必要があります。Microsoft はさまざまなハードウェア ベンダーと協力して、必要な情報をユーザーに提供したり、ユーザーの代わりにアップロードしたりできるよう積極的に取り組んでいます。また、デバイスのハードウェア ID を CSV ファイルに生成する PowerShell スクリプトを使用してこの情報を自分で取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p105">To register devices, you need to acquire their hardware ID and register it. We are actively working with various hardware vendors to enable them to provide the required information to you, or upload it on your behalf. You also have the option to capture this information by yourself using a PowerShell script that generates a .csv file with the device's hardware ID.</span></span>

        <span data-ttu-id="65ef8-126">デバイスを登録すると、プライバシーの設定や使用許諾契約書をスキップするなどの、OOBE のカスタマイズ オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-126">Once devices are registered, there are OOBE customization options that you can configure including skipping privacy settings and EULA.</span></span>

    - <span data-ttu-id="65ef8-127">**OOBE の企業ブランド化**</span><span class="sxs-lookup"><span data-stu-id="65ef8-127">**Company branding for OOBE**</span></span>

        <span data-ttu-id="65ef8-128">これにより、デバイス OOBE 中に表示するブランドを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-128">This allows you to add branding to appear during device OOBE.</span></span>

    - <span data-ttu-id="65ef8-129">**Microsoft Intune での MDM の自動登録**</span><span class="sxs-lookup"><span data-stu-id="65ef8-129">**MDM auto-enrollment in Microsoft Intune**</span></span>
        
        <span data-ttu-id="65ef8-p106">自動登録では、ユーザーが自分の Windows 10 デバイスを Azure AD に接続するときに、Intune のに登録してデバイス管理を行うことができます。登録するには、個人用デバイスに職場アカウントを追加するか、企業が所有するデバイスを Azure AD に参加させます。バックグラウンドでは、デバイスが Intune で管理ができるように登録されます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p106">Automatic enrollment lets users enroll their Windows 10 devices in Intune for device management when they connect their devices to Azure AD. To enroll, users add their work account to their personally-owned devices or join corporate-owned devices to Azure AD. In the background, the device is also enrolled for management with Intune.</span></span>

    - <span data-ttu-id="65ef8-133">**Windows Autopilot で使用するクラウド サービスへのネットワーク接続**</span><span class="sxs-lookup"><span data-stu-id="65ef8-133">**Network connectivity to cloud services used by Windows Autopilot**</span></span>

        <span data-ttu-id="65ef8-134">Windows Autopilot 展開プログラムは、多数のクラウド サービスを使用してデバイスを準備完了の状態にするため、Windows Autopilot デバイスとして登録されたデバイスからそれらのサービスにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="65ef8-134">The Windows Autopilot Deployment Program uses a number of cloud services to get your devices to a productive state and these services must be accessible from devices registered as Windows Autopilot devices.</span></span> 

    - <span data-ttu-id="65ef8-135">**デバイスに Windows 10 バージョン 1703 以降がプレインストールされている必要がある**</span><span class="sxs-lookup"><span data-stu-id="65ef8-135">**Devices must be pre-installed with Windows 10, version 1703 or later**</span></span>

2. <span data-ttu-id="65ef8-p107">Windows Autopilot 展開プログラムについての詳細を参照し、組織に最適な展開プログラムを選択します。次の展開プログラムから選択できます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p107">Learn about and select the Windows Autopilot Deployment Program for your organization. You can select from these deployment programs:</span></span>
    - <span data-ttu-id="65ef8-138">**ビジネス向け Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="65ef8-138">**Microsoft Store for Business**</span></span>
    - <span data-ttu-id="65ef8-139">**Microsoft Intune**</span><span class="sxs-lookup"><span data-stu-id="65ef8-139">**Microsoft Intune**</span></span>
    - <span data-ttu-id="65ef8-140">**パートナー センター**</span><span class="sxs-lookup"><span data-stu-id="65ef8-140">**Partner Center**</span></span>

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a><span data-ttu-id="65ef8-141">パート 2: Microsoft 365 向け Windows 10 デバイスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="65ef8-141">Part 2: Set up a Windows 10 device for Microsoft 365</span></span>
<span data-ttu-id="65ef8-142">Microsoft 365 ユーザーに Windows デバイスを設定する前に、すべての Windows デバイスが Windows 10 バージョン 1703 (Creators Update) 以降を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65ef8-142">Before you can set up Windows devices for Microsoft 365 users, make sure all the Windows devices are running Windows 10, version 1703 (Creators Update) or later.</span></span>

<span data-ttu-id="65ef8-143">組織内のすべての Windows デバイスが Windows 10 Creators Update に更新された後、またはすでに Windows 10 Creators Updat を使用している場合、これらのデバイスを組織の Azure Active Directory に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-143">After all Windows devices in your organization have either been upgraded to Windows 10 Creators Update or are already running Windows 10 Creators Update, you can join these devices to your organization’s Azure Active Directory.</span></span>

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a><span data-ttu-id="65ef8-144">新しい、または新しくアップグレードした Windows 10 デバイスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="65ef8-144">Set up a brand new or newly-upgraded Windows 10 device</span></span>
<span data-ttu-id="65ef8-145">Windows 10 Creators Update 以降を使用している新しいデバイス、または Windows 10 Creators Update 以降にアップグレードしたけれども OOBE 設定をしなかったデバイスで、Windows 10 OOBE を使用してデバイスをセットアップするには以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="65ef8-145">Follow these steps to set up a device using the Windows 10 OOBE on a brand new device running Windows 10 Creators Update (or later) or on a device that was upgrade to Windows 10 Creators Update (or later) but has not gone through out-of-box setup.</span></span>

1. <span data-ttu-id="65ef8-146">ワイヤレス ネットワークが構成されていない場合は、有線接続またはイーサネット接続を使用してデバイスをインターネットに接続してください。</span><span class="sxs-lookup"><span data-stu-id="65ef8-146">If you don't have a wireless network configured, make sure you connect the device to the internet through a wired or Ethernet connection.</span></span>
2. <span data-ttu-id="65ef8-p108">Windows デバイスのセットアップを行います。新規またはリセットされたデバイスで、[**お住まいの地域はこちらでよろしいですか?**] 画面から始まります。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p108">Go through the Windows device setup experience. On a new or reset device, the setup experience starts with the **Let's start with region. Is this right?** screen.</span></span>
3. <span data-ttu-id="65ef8-p109">Windows 10 デバイスのセットアップを続け、[**設定する方法を指定してください。**] のページまで進みます。ここで、[**組織用に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p109">Go through Windows 10 device setup until you get to the **How would you like to set up?** page. Here, select **Set up for an organization**.</span></span>
4. <span data-ttu-id="65ef8-p110">Microsoft 365 ユーザーのアカウントとパスワードでサインインします。ユーザー パスワードの設定によっては、パスワードの更新を求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p110">Sign in using the Microsoft 365 user's account and password. Depending on the user password setting, you may be prompted to update the password.</span></span> 
5. <span data-ttu-id="65ef8-153">Windows 10 デバイスのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-153">Finish Windows 10 device setup.</span></span>

<span data-ttu-id="65ef8-154">完了後、デバイスは組織の Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-154">After you’re done, the device will be connected to your organization’s Azure AD.</span></span>

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a><span data-ttu-id="65ef8-155">OOBE セットアップが完了しているデバイスの設定</span><span class="sxs-lookup"><span data-stu-id="65ef8-155">Set up a device that has already completed out-of-box setup</span></span>
<span data-ttu-id="65ef8-156">デバイスで Windows 10 Creators Update (またはそれ以降) を使用していて、OOBE セットアップを完了している場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="65ef8-156">If your device has Windows 10 Creators Update (or later) and has already gone through the out-of-box setup, follow these steps.</span></span>

1. <span data-ttu-id="65ef8-157">Windows 10 バージョン 1703 (Creators Update) を使用しているユーザーの Windows PC で、[**Windows**] ロゴを選択し [**設定**] アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-157">On your user's Windows PC that is running Windows 10, version 1703 (Creators Update), select the **Windows** logo, and then select the **Settings** icon.</span></span>
2. <span data-ttu-id="65ef8-158">[**設定**] で、[**アカウント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-158">In **Settings**, go to **Accounts**.</span></span>
3. <span data-ttu-id="65ef8-159">[**情報**] ページで、[**職場または学校にアクセス**]  >  [**接続**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-159">On the **Your info** page, select **Access work or school** > **Connect**.</span></span>
4. <span data-ttu-id="65ef8-160">[**職場または学校アカウントの設定**] ダイアログ ボックスの [**ほかの操作**] の下にある、[**このデバイスを Azure Active Directory に参加させる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65ef8-160">On the **Set up a work or school account** dialog, under **Alternate actions**, select **Join this device to Azure Active Directory**.</span></span>
5. <span data-ttu-id="65ef8-161">[**サインインしましょう**] ページで、職場または学校のアカウントを入力し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-161">On the **Let's get you signed in** page, enter your work or school account, and select **Next**.</span></span>
6. <span data-ttu-id="65ef8-162">[**パスワードの入力**] ページで、パスワードを入力し、[**サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-162">On the **Enter password** page, enter your password, and select **Sign in**.</span></span>
7. <span data-ttu-id="65ef8-163">[**組織の確認**] ページの情報が正しいことを確認し、[**参加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-163">On the **Make sure this is your organization** page, verify that the information is correct, and select **Join**.</span></span>
8. <span data-ttu-id="65ef8-p111">[**準備が完了しました!**] ページで、[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p111">On the **You're all set!** page, select **Done**.</span></span>

<span data-ttu-id="65ef8-166">完了後、ユーザーが組織の Azure AD に接続されます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-166">After you're done, the user will be connected to your organization's Azure AD.</span></span>

### <a name="verify-the-device-is-connected-to-azure-ad"></a><span data-ttu-id="65ef8-167">デバイスが Azure AD に接続されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="65ef8-167">Verify the device is connected to Azure AD</span></span>
<span data-ttu-id="65ef8-168">Azure AD で、デバイスの同期状態を確認し、デバイス上で Microsoft 365 アカウントの使用を開始するには次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="65ef8-168">Follow these steps to verify the device’s sync status with Azure AD, and then start using your Microsoft 365 account on the device.</span></span> 

1. <span data-ttu-id="65ef8-169">[**設定**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-169">Open **Settings**.</span></span>
2. <span data-ttu-id="65ef8-170">[**職場または学校にアクセス**] ページで、[**<organization name>に接続**] を選択し、[**情報**] および [**切断**] ボタンを表示します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-170">On the **Access work or school** page, select the **Connected to <organization name>** area to expose the buttons **Info** and **Disconnect**.</span></span>
3. <span data-ttu-id="65ef8-171">[**情報**] を選択すると、同期状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-171">Select **Info** to get your synchronization status.</span></span>
4. <span data-ttu-id="65ef8-172">[**同期の状態**] ページで [**同期**] を選択すると、最新のモバイル デバイス管理ポリシーを PC に取得することができます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-172">On the **Sync status** page, select **Sync** to get the latest mobile device management policies onto the PC.</span></span>
5. <span data-ttu-id="65ef8-173">Microsoft 365 アカウントを使用するには、Windows の [**スタート**] ボタンをクリックし、現在のアカウントの画像を右クリックし、[ユーザーの**切り替え**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65ef8-173">To start using the Microsoft 365 account, go to the Windows **Start** button, right-click your current account picture and then select **Switch** account.</span></span>
6. <span data-ttu-id="65ef8-174">組織のメール アドレスとパスワードを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="65ef8-174">Sign in by using your organization email and password.</span></span>

<span data-ttu-id="65ef8-p112">エンタープライズ環境で Windows 10 を使用するときに問題が発生した場合、「[最も一般的な問題に対する上位の Microsoft サポート ソリューション](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)」 を参照してください。これらのリソースには、サポート技術情報の記事、更新情報、およびライブラリの記事が含まれます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-p112">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="65ef8-177">中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step3)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="65ef8-177">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="65ef8-178">次の手順</span><span class="sxs-lookup"><span data-stu-id="65ef8-178">Next step</span></span>

|||
|:-------|:-----|
|![手順 4](./media/stepnumbers/Step4.png)| [<span data-ttu-id="65ef8-180">デバイスの正常性とコンプライアンスを監視する</span><span class="sxs-lookup"><span data-stu-id="65ef8-180">Monitor device health and compliance</span></span>](windows10-enable-windows-analytics.md) |
