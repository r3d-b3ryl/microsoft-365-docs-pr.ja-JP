---
title: McAfee to Microsoft Defender for Endpoint - Onboard
description: これは、McAfee から Microsoft Defender for Endpoint に移行するフェーズ 3 オンボードです。
keywords: 移行、 Windows Defender Advanced Threat Protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 77ce0edc5b81bd54653c2aea0a32f4e358e75ebe
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185625"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c031a-104">McAfee から移行する - フェーズ 3: オンボードから Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c031a-104">Migrate from McAfee - Phase 3: Onboard to Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="c031a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c031a-105">**Applies to:**</span></span>
- [<span data-ttu-id="c031a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c031a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c031a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c031a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


|<span data-ttu-id="c031a-108">[![フェーズ 1: 準備](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="c031a-108">[![Phase 1: Prepare](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)</span></span><br/>[<span data-ttu-id="c031a-109">フェーズ 1: 準備</span><span class="sxs-lookup"><span data-stu-id="c031a-109">Phase 1: Prepare</span></span>](mcafee-to-microsoft-defender-prepare.md) |<span data-ttu-id="c031a-110">[![フェーズ 2: セットアップ](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="c031a-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="c031a-111">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="c031a-111">Phase 2: Set up</span></span>](mcafee-to-microsoft-defender-setup.md) |![フェーズ 3: オンボード](images/phase-diagrams/onboard.png)<br/><span data-ttu-id="c031a-113">フェーズ 3: オンボード</span><span class="sxs-lookup"><span data-stu-id="c031a-113">Phase 3: Onboard</span></span> |
|--|--|--|
|| |<span data-ttu-id="c031a-114">*お前はここにいる!*</span><span class="sxs-lookup"><span data-stu-id="c031a-114">*You are here!*</span></span> |

<span data-ttu-id="c031a-115">**McAfee Endpoint [Security (McAfee) から Microsoft Defender Advanced Threat Protection (Microsoft Defender for Endpoint)](mcafee-to-microsoft-defender-migration.md#the-migration-process)** への移行フェーズ 3 へようこそ。</span><span class="sxs-lookup"><span data-stu-id="c031a-115">**Welcome to Phase 3 of [migrating from McAfee Endpoint Security (McAfee) to Microsoft Defender Advanced Threat Protection (Microsoft Defender for Endpoint)](mcafee-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> <span data-ttu-id="c031a-116">この移行フェーズには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c031a-116">This migration phase includes the following steps:</span></span>

1. <span data-ttu-id="c031a-117">[デバイスを Microsoft Defender for Endpoint にオンボードします](#onboard-devices-to-microsoft-defender-for-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="c031a-117">[Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).</span></span>
2. <span data-ttu-id="c031a-118">[検出テストを実行します](#run-a-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="c031a-118">[Run a detection test](#run-a-detection-test).</span></span>
3. <span data-ttu-id="c031a-119">[McAfee をアンインストールします](#uninstall-mcafee)。</span><span class="sxs-lookup"><span data-stu-id="c031a-119">[Uninstall McAfee](#uninstall-mcafee).</span></span>
4. <span data-ttu-id="c031a-120">[Microsoft Defender for Endpoint がアクティブ モードに設定されている必要があります](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)。</span><span class="sxs-lookup"><span data-stu-id="c031a-120">[Make sure Microsoft Defender for Endpoint is in active mode](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).</span></span>

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="c031a-121">デバイスを Microsoft Defender for Endpoint にオンボードする</span><span class="sxs-lookup"><span data-stu-id="c031a-121">Onboard devices to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="c031a-122">Microsoft Defender セキュリティ センター ( ) に移動 [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c031a-122">Go to the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) and sign in.</span></span>

2. <span data-ttu-id="c031a-123">[設定 **]**  >  **[デバイス管理**  >  **オンボーディング] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c031a-123">Choose **Settings** > **Device management** > **Onboarding**.</span></span> 

3. <span data-ttu-id="c031a-124">[オンボード **プロセスを開始するオペレーティング システムの選択] ボックスの一覧で** 、オペレーティング システムを選択します。</span><span class="sxs-lookup"><span data-stu-id="c031a-124">In the **Select operating system to start onboarding process** list, select an operating system.</span></span> 

4. <span data-ttu-id="c031a-125">[ **展開方法] で**、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c031a-125">Under **Deployment method**, select an option.</span></span> <span data-ttu-id="c031a-126">リンクとプロンプトに従って、組織のデバイスをオンボードします。</span><span class="sxs-lookup"><span data-stu-id="c031a-126">Follow the links and prompts to onboard your organization's devices.</span></span> <span data-ttu-id="c031a-127">サポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="c031a-127">Need help?</span></span> <span data-ttu-id="c031a-128">[「Onboarding メソッド (この](#onboarding-methods)記事)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c031a-128">See [Onboarding methods](#onboarding-methods) (in this article).</span></span>

### <a name="onboarding-methods"></a><span data-ttu-id="c031a-129">オンボーディングメソッド</span><span class="sxs-lookup"><span data-stu-id="c031a-129">Onboarding methods</span></span>
 
<span data-ttu-id="c031a-130">展開方法は、選択されているオペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c031a-130">Deployment methods vary, depending on which operating system is selected.</span></span> <span data-ttu-id="c031a-131">オンボーディングのヘルプについては、以下の表に示すリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c031a-131">Refer to the resources listed in the table below to get help with onboarding.</span></span>

|<span data-ttu-id="c031a-132">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="c031a-132">Operating system</span></span>  |<span data-ttu-id="c031a-133">メソッド</span><span class="sxs-lookup"><span data-stu-id="c031a-133">Method</span></span>  |
|---------|---------|
|<span data-ttu-id="c031a-134">Windows 10</span><span class="sxs-lookup"><span data-stu-id="c031a-134">Windows 10</span></span>     |<span data-ttu-id="c031a-135">- [グループ ポリシー](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span><span class="sxs-lookup"><span data-stu-id="c031a-135">- [Group Policy](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span></span><br/><span data-ttu-id="c031a-136">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="c031a-136">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span><br/><span data-ttu-id="c031a-137">- [モバイル デバイス管理 (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)</span><span class="sxs-lookup"><span data-stu-id="c031a-137">- [Mobile Device Management (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)</span></span><br/><span data-ttu-id="c031a-138">- [ローカル スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span><span class="sxs-lookup"><span data-stu-id="c031a-138">- [Local script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span></span> <br/><br/><span data-ttu-id="c031a-139">**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。</span><span class="sxs-lookup"><span data-stu-id="c031a-139">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="c031a-140">実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c031a-140">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>         |
|<span data-ttu-id="c031a-141">- Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c031a-141">- Windows 8.1 Enterprise</span></span> <br/><span data-ttu-id="c031a-142">- Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="c031a-142">- Windows 8.1 Pro</span></span> <br/><span data-ttu-id="c031a-143">- Windows 7 SP1エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="c031a-143">- Windows 7 SP1 Enterprise</span></span> <br/><span data-ttu-id="c031a-144">- Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="c031a-144">- Windows 7 SP1 Pro</span></span>     | [<span data-ttu-id="c031a-145">Microsoft 監視エージェント</span><span class="sxs-lookup"><span data-stu-id="c031a-145">Microsoft Monitoring Agent</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/><span data-ttu-id="c031a-146">**注**: Microsoft 監視エージェントは Azure Log Analytics エージェントです。</span><span class="sxs-lookup"><span data-stu-id="c031a-146">**NOTE**: Microsoft Monitoring Agent is now Azure Log Analytics agent.</span></span> <span data-ttu-id="c031a-147">詳細については [、「Log Analytics エージェントの概要」を参照してください](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)。</span><span class="sxs-lookup"><span data-stu-id="c031a-147">To learn more, see [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>        |
|<span data-ttu-id="c031a-148">- Windows Server 2019 以降</span><span class="sxs-lookup"><span data-stu-id="c031a-148">- Windows Server 2019 and later</span></span> <br/><span data-ttu-id="c031a-149">- Windows Server 2019 コア エディション</span><span class="sxs-lookup"><span data-stu-id="c031a-149">- Windows Server 2019 core edition</span></span> <br/><span data-ttu-id="c031a-150">- Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="c031a-150">- Windows Server version 1803 and later</span></span> |<span data-ttu-id="c031a-151">- [ローカル スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span><span class="sxs-lookup"><span data-stu-id="c031a-151">- [Local script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span></span> <br/><span data-ttu-id="c031a-152">- [グループ ポリシー](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span><span class="sxs-lookup"><span data-stu-id="c031a-152">- [Group Policy](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span></span> <br/><span data-ttu-id="c031a-153">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="c031a-153">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> <br/><span data-ttu-id="c031a-154">- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="c031a-154">- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager)</span></span> <br/><span data-ttu-id="c031a-155">- [永続的でないデバイスの VDI オンボーディング スクリプト](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi)</span><span class="sxs-lookup"><span data-stu-id="c031a-155">- [VDI onboarding scripts for non-persistent devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi)</span></span> <br/><br/><span data-ttu-id="c031a-156">**注**: ローカル スクリプトは概念実証に適していますが、実稼働環境での展開には使用できません。</span><span class="sxs-lookup"><span data-stu-id="c031a-156">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="c031a-157">実稼働展開の場合は、グループ ポリシー、Microsoft Endpoint Configuration Manager、または Intune を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c031a-157">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>    |
|<span data-ttu-id="c031a-158">- Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c031a-158">- Windows Server 2016</span></span> <br/><span data-ttu-id="c031a-159">- Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c031a-159">- Windows Server 2012 R2</span></span> <br/><span data-ttu-id="c031a-160">- Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c031a-160">- Windows Server 2008 R2 SP1</span></span>  |<span data-ttu-id="c031a-161">- [Microsoft Defender セキュリティ センター](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="c031a-161">- [Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)</span></span><br/><span data-ttu-id="c031a-162">- [Azure セキュリティ センター](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="c031a-162">- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span></span> |
|<span data-ttu-id="c031a-163">macOS</span><span class="sxs-lookup"><span data-stu-id="c031a-163">macOS</span></span><br/><span data-ttu-id="c031a-164">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="c031a-164">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="c031a-165">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="c031a-165">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="c031a-166">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="c031a-166">- 10.13 (High Sierra)</span></span><br/><br/><span data-ttu-id="c031a-167">iOS</span><span class="sxs-lookup"><span data-stu-id="c031a-167">iOS</span></span><br/><br/><span data-ttu-id="c031a-168">Linux:</span><span class="sxs-lookup"><span data-stu-id="c031a-168">Linux:</span></span><br/><span data-ttu-id="c031a-169">- RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="c031a-169">- RHEL 7.2+</span></span><br/><span data-ttu-id="c031a-170">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="c031a-170">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="c031a-171">- Ubuntu 16 LTS 以上の LTS</span><span class="sxs-lookup"><span data-stu-id="c031a-171">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="c031a-172">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="c031a-172">- SLES 12+</span></span><br/><span data-ttu-id="c031a-173">- Debian 9+</span><span class="sxs-lookup"><span data-stu-id="c031a-173">- Debian 9+</span></span><br/><span data-ttu-id="c031a-174">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="c031a-174">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="c031a-175">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="c031a-175">Onboard non-Windows devices</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a><span data-ttu-id="c031a-176">検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="c031a-176">Run a detection test</span></span>

<span data-ttu-id="c031a-177">オンボードデバイスが Microsoft Defender for Endpoint に正しく接続されていることを確認するには、検出テストを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c031a-177">To verify that your onboarded devices are properly connected to Microsoft Defender for Endpoint, you can run a detection test.</span></span>


|<span data-ttu-id="c031a-178">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="c031a-178">Operating system</span></span>  |<span data-ttu-id="c031a-179">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="c031a-179">Guidance</span></span>  |
|---------|---------|
|<span data-ttu-id="c031a-180">- Windows 10</span><span class="sxs-lookup"><span data-stu-id="c031a-180">- Windows 10</span></span> <br/><span data-ttu-id="c031a-181">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c031a-181">- Windows Server 2019</span></span> <br/><span data-ttu-id="c031a-182">- Windows Server バージョン 1803</span><span class="sxs-lookup"><span data-stu-id="c031a-182">- Windows Server, version 1803</span></span> <br/><span data-ttu-id="c031a-183">- Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="c031a-183">- Windows Server 2016</span></span> <br/><span data-ttu-id="c031a-184">- Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c031a-184">- Windows Server 2012 R2</span></span>     |<span data-ttu-id="c031a-185">「 [検出テストを実行する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="c031a-185">See [Run a detection test](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> <br/><br/><span data-ttu-id="c031a-186">Microsoft Defender for Endpoint デモ シナリオ サイト ( ) にアクセス [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) し、1 つ以上のシナリオを試してください。</span><span class="sxs-lookup"><span data-stu-id="c031a-186">Visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) and try one or more of the scenarios.</span></span> <span data-ttu-id="c031a-187">たとえば、クラウド配信の **保護デモ シナリオを** 試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c031a-187">For example, try the **Cloud-delivered protection** demo scenario.</span></span>         |
|<span data-ttu-id="c031a-188">macOS</span><span class="sxs-lookup"><span data-stu-id="c031a-188">macOS</span></span><br/><span data-ttu-id="c031a-189">- 10.15 (Catalina)</span><span class="sxs-lookup"><span data-stu-id="c031a-189">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="c031a-190">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="c031a-190">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="c031a-191">- 10.13 (High Sierra)</span><span class="sxs-lookup"><span data-stu-id="c031a-191">- 10.13 (High Sierra)</span></span>     |<span data-ttu-id="c031a-192">で DIY アプリをダウンロードして使用します [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) 。</span><span class="sxs-lookup"><span data-stu-id="c031a-192">Download and use the DIY app at [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy).</span></span> <br/><br/><span data-ttu-id="c031a-193">詳細については [、「Microsoft Defender ATP for Mac」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。</span><span class="sxs-lookup"><span data-stu-id="c031a-193">For more information, see [Microsoft Defender ATP for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>        |
|<span data-ttu-id="c031a-194">Linux:</span><span class="sxs-lookup"><span data-stu-id="c031a-194">Linux:</span></span><br/><span data-ttu-id="c031a-195">- RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="c031a-195">- RHEL 7.2+</span></span><br/><span data-ttu-id="c031a-196">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="c031a-196">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="c031a-197">- Ubuntu 16 LTS 以上の LTS</span><span class="sxs-lookup"><span data-stu-id="c031a-197">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="c031a-198">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="c031a-198">- SLES 12+</span></span><br/><span data-ttu-id="c031a-199">- Debian 9+</span><span class="sxs-lookup"><span data-stu-id="c031a-199">- Debian 9+</span></span><br/><span data-ttu-id="c031a-200">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="c031a-200">- Oracle Linux 7.2</span></span> |<span data-ttu-id="c031a-201">1. 次のコマンドを実行し、1 の結果 **を探します**。</span><span class="sxs-lookup"><span data-stu-id="c031a-201">1. Run the following command, and look for a result of **1**:</span></span> <br/><span data-ttu-id="c031a-202">`mdatp health --field real_time_protection_enabled`.</span><span class="sxs-lookup"><span data-stu-id="c031a-202">`mdatp health --field real_time_protection_enabled`.</span></span> <br/><br/><span data-ttu-id="c031a-203">2. ターミナル ウィンドウを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c031a-203">2. Open a Terminal window, and run the following command:</span></span> <br/><span data-ttu-id="c031a-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span><span class="sxs-lookup"><span data-stu-id="c031a-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span></span> <br/><br/><span data-ttu-id="c031a-205">3. 次のコマンドを実行して、検出された脅威を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c031a-205">3. Run the following command to list any detected threats:</span></span> <br/><span data-ttu-id="c031a-206">`mdatp threat list`.</span><span class="sxs-lookup"><span data-stu-id="c031a-206">`mdatp threat list`.</span></span> <br/><br/><span data-ttu-id="c031a-207">詳細については [、「Microsoft Defender ATP for Linux」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux)。</span><span class="sxs-lookup"><span data-stu-id="c031a-207">For more information, see [Microsoft Defender ATP for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux).</span></span> |

## <a name="uninstall-mcafee"></a><span data-ttu-id="c031a-208">McAfee のアンインストール</span><span class="sxs-lookup"><span data-stu-id="c031a-208">Uninstall McAfee</span></span>

<span data-ttu-id="c031a-209">組織のデバイスを Microsoft Defender for Endpoint にオンボードしたので、次にマカフィーをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c031a-209">Now that you have onboarded your organization's devices to Microsoft Defender for Endpoint, your next step is to uninstall McAfee.</span></span>

<span data-ttu-id="c031a-210">この手順のヘルプを表示するには、McAfee ServicePortal ( ) に移動します [http://mysupport.mcafee.com](http://mysupport.mcafee.com) 。</span><span class="sxs-lookup"><span data-stu-id="c031a-210">To get help with this step, go to your McAfee ServicePortal ([http://mysupport.mcafee.com](http://mysupport.mcafee.com)).</span></span>

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a><span data-ttu-id="c031a-211">Microsoft Defender for Endpoint がアクティブ モードにあるか確認する</span><span class="sxs-lookup"><span data-stu-id="c031a-211">Make sure Microsoft Defender for Endpoint is in active mode</span></span>

<span data-ttu-id="c031a-212">McAfee をアンインストールしたので、次の手順は、Microsoft Defender ウイルス対策とエンドポイントの検出と応答が有効でアクティブ モードで行なう方法です。</span><span class="sxs-lookup"><span data-stu-id="c031a-212">Now that you have uninstalled McAfee, your next step is to make sure that Microsoft Defender Antivirus and endpoint detection and response are enabled and in active mode.</span></span>

<span data-ttu-id="c031a-213">これを行うには、Microsoft Defender for Endpoint デモ シナリオ サイト () をご覧ください [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="c031a-213">To do this, visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)).</span></span> <span data-ttu-id="c031a-214">少なくとも次を含む、そのページで 1 つ以上のデモ シナリオを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="c031a-214">Try one or more of the demo scenarios on that page, including at least the following:</span></span>
- <span data-ttu-id="c031a-215">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="c031a-215">Cloud-delivered protection</span></span>
- <span data-ttu-id="c031a-216">望ましくない可能性のあるアプリケーション (PUA)</span><span class="sxs-lookup"><span data-stu-id="c031a-216">Potentially Unwanted Applications (PUA)</span></span>
- <span data-ttu-id="c031a-217">ネットワーク保護 (NP)</span><span class="sxs-lookup"><span data-stu-id="c031a-217">Network Protection (NP)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c031a-218">Windows Server 2016 を使用している場合は、Microsoft Defender ウイルス対策を手動で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c031a-218">If you are using Windows Server 2016, you might have to start Microsoft Defender Antivirus manually.</span></span> <span data-ttu-id="c031a-219">これを行うには、デバイスで PowerShell コマンドレット `mpcmdrun.exe -wdenable` を使用します。</span><span class="sxs-lookup"><span data-stu-id="c031a-219">You can do this by using the PowerShell cmdlet `mpcmdrun.exe -wdenable` on the device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c031a-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="c031a-220">Next steps</span></span>

<span data-ttu-id="c031a-221">**おめでとう** ございます!</span><span class="sxs-lookup"><span data-stu-id="c031a-221">**Congratulations**!</span></span> <span data-ttu-id="c031a-222">McAfee から [Microsoft Defender for Endpoint への移行が完了しました](mcafee-to-microsoft-defender-migration.md#the-migration-process)。</span><span class="sxs-lookup"><span data-stu-id="c031a-222">You have completed your [migration from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!</span></span> 

- <span data-ttu-id="c031a-223">Microsoft Defender[セキュリティ センター ()](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)のセキュリティ操作ダッシュボードにアクセスします [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) 。</span><span class="sxs-lookup"><span data-stu-id="c031a-223">[Visit your security operations dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) in the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 
- <span data-ttu-id="c031a-224">[Microsoft Defender Advanced Threat Protection の管理、移行後](manage-atp-post-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="c031a-224">[Manage Microsoft Defender Advanced Threat Protection, post migration](manage-atp-post-migration.md).</span></span>