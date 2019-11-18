---
title: 'フェーズ 3: Windows 10 Enterprise のインフラストラクチャの終了条件'
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise の Windows 10 Enterprise の条件を満たしていることを確認します。
ms.openlocfilehash: 98dd4b71f1c2af6d72580066d73e75dfd4aa60ff
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627531"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="11e00-103">フェーズ 3: Windows 10 Enterprise のインフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="11e00-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![フェーズ 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="11e00-105">Windows 10 Enterprise インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮済みであることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="11e00-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="11e00-106">必須: Microsoft 365 のドメインが追加および検証されている</span><span class="sxs-lookup"><span data-stu-id="11e00-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="11e00-107">Office 365 サブスクリプションと Intune サブスクリプション用の Azure AD テナントは、“onmicrosoft.com” を含む単なるドメイン名ではなく、インターネット ドメイン名 (contoso.com など) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="11e00-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="11e00-p101">そうしないと、構成可能な認証方法に制限されます。たとえば、パススルー認証とフェデレーション認証では、“onmicrosoft.com” ドメイン名は使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e00-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="11e00-110">必要に応じて、[手順 1](windows10-prepare-your-org.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="11e00-111">省略可能: ユーザーが追加およびライセンス付与されている</span><span class="sxs-lookup"><span data-stu-id="11e00-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="11e00-112">ユーザーに対応するアカウントは、Office 365 サブスクリプションと Intune サブスクリプション用の Azure AD テナントに直接追加されるか、またはオンプレミスの Active Directory Domain Services (AD DS) のディレクトリ同期から直接追加されます。</span><span class="sxs-lookup"><span data-stu-id="11e00-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="11e00-113">ユーザーが追加されると、グローバル管理者またはユーザー管理者として直接、あるいはグループ メンバーシップを通して自動的に、Microsoft 365 Enterprise ライセンスをユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="11e00-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="11e00-114">必要に応じて、[手順 1](windows10-prepare-your-org.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="11e00-115">オプション: 診断が有効です</span><span class="sxs-lookup"><span data-stu-id="11e00-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="11e00-116">グループ ポリシー、Microsoft Intune、レジストリ エディター、またはコマンド プロンプトを使用して診断データの設定を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="11e00-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="11e00-117">必要に応じて、[手順 1](windows10-prepare-your-org.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="11e00-118">一括アップグレードに必須: オペレーティング システムの展開用に Configuration Manager のタスク シーケンスが作成されている</span><span class="sxs-lookup"><span data-stu-id="11e00-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="11e00-119">Windows 7 または Windows 8.1 を実行しているデバイス上で一括アップグレードを行うために Configuration Manager のタスク シーケンスを開始するには、以下の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e00-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="11e00-120">適切な Windows 診断データ レベルを設定する</span><span class="sxs-lookup"><span data-stu-id="11e00-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="11e00-121">Windows のアップグレードの準備状況を確認している</span><span class="sxs-lookup"><span data-stu-id="11e00-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="11e00-122">Windows 10 OS イメージを使用したデバイス コレクションとオペレーティング システムの展開を含む Configuration Manager のタスク シーケンスを作成している</span><span class="sxs-lookup"><span data-stu-id="11e00-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="11e00-p102">条件が満たされると、Windows のアップグレードの準備ができているデバイス上で一括インストールを実行できます。Microsoft 365 Enterprise のメリットを最大限に得るには、Windows 7 と Windows 8.1 を実行しているデバイスをできるだけ多くアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="11e00-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="11e00-p103">Windows 10 Enterprise を実行している各デバイスは、Microsoft 365 Enterprise の統合されたソリューションの特典に参加できます。Windows 7 または Windows 8.1 を実行している他のデバイスでは、クラウドに接続されたテクノロジおよび Windows 10 Enterprise の高度なセキュリティ機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="11e00-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="11e00-127">必要に応じて、[手順 2](windows10-deploy-inplaceupgrade.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="11e00-128">新しいデバイスに必須: Windows Autopilot が構成されている</span><span class="sxs-lookup"><span data-stu-id="11e00-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="11e00-129">Windows Autopilot を使用して、新しいデバイス上で Windows 10 Enterprise を展開してカスタマイズするには、以下の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e00-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="11e00-130">適切な Windows 診断データ レベルを構成している</span><span class="sxs-lookup"><span data-stu-id="11e00-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="11e00-131">Windows Autopilot の前提条件 (以下の条件を含む) を構成している</span><span class="sxs-lookup"><span data-stu-id="11e00-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="11e00-132">デバイスの登録と OOBE のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="11e00-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="11e00-133">OOBE 向けの会社のブランド化</span><span class="sxs-lookup"><span data-stu-id="11e00-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="11e00-134">Microsoft Intune での MDM の自動登録</span><span class="sxs-lookup"><span data-stu-id="11e00-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="11e00-135">Windows Autopilot で使用するクラウド サービスへのネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="11e00-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="11e00-136">Windows 10 バージョン 1703 以降を事前にインストールしたデバイス</span><span class="sxs-lookup"><span data-stu-id="11e00-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="11e00-137">組織の Windows Autopilot Deployment を選択している</span><span class="sxs-lookup"><span data-stu-id="11e00-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="11e00-138">Windows Autopilot の構成が完了したら、それを使用して Windows 10 Enterprise を構成およびカスタマイズし、以下の OOBE (Out-of-Box Experience) を実現できます。</span><span class="sxs-lookup"><span data-stu-id="11e00-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="11e00-139">新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="11e00-139">New devices</span></span>
- <span data-ttu-id="11e00-140">組織内の既定のセットアップを既に完了しているデバイス。</span><span class="sxs-lookup"><span data-stu-id="11e00-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="11e00-141">Windows Autopilot は、デバイスを構成し、Azure AD に接続します。</span><span class="sxs-lookup"><span data-stu-id="11e00-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="11e00-142">Windows Autopilot を使用しない場合、Azure AD への接続を含む、新しいデバイスを手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11e00-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="11e00-143">必要に応じて、[手順 3](windows10-deploy-autopilot.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="11e00-144">省略可能: Windows Analytics デバイスの正常性を利用して、Windows 10 Enterprise ベースのデバイスを監視している</span><span class="sxs-lookup"><span data-stu-id="11e00-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="11e00-p104">エンド ユーザーに影響を与える問題を検知して、修復するためにデバイスの正常性で、デバイスの正常性の監視の情報を使用しました。エンド ユーザーの問題を迅速に対処することで、サポート コストを削減し、Windows 10 Enterprise への IT コミットメントをユーザーに実証することができます。これにより、組織全体での導入の促進に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="11e00-147">必要に応じて、[手順 4](windows10-enable-windows-analytics.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="11e00-148">必須: Windows Defender ウイルス対策または独自のマルウェア対策ソリューションを使用している</span><span class="sxs-lookup"><span data-stu-id="11e00-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="11e00-p105">Windows 10 Enterprise を実行しているデバイスを悪意のあるソフトウェアから保護するために、Windows Defender ウイルス対策または独自のウイルス対策ソリューションを展開しました。Windows Defender ウイルス対策を展開した場合は、Microsoft Endpoint Configuration Manager または Microsoft Intune などのレポートの方法を実装して、ウイルス対策のイベントとアクティビティを監視します。</span><span class="sxs-lookup"><span data-stu-id="11e00-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="11e00-151">必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-av) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="11e00-152">必須: Windows Defender Exploit Guard を使用している</span><span class="sxs-lookup"><span data-stu-id="11e00-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="11e00-153">Windows 10 Enterprise を実行しているデバイスを侵入から保護するために、Windows Defender Exploit Guard を展開し、Configuration Manager または Microsoft Intune などのレポートの方法を実装しました。</span><span class="sxs-lookup"><span data-stu-id="11e00-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as System Center Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="11e00-154">必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-eg) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="11e00-155">必須: Microsoft Defender Advanced Threat Protection を使用している (Microsoft 365 Enterprise E5 のみ)</span><span class="sxs-lookup"><span data-stu-id="11e00-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="11e00-156">ネットワークと Windows 10 Enterprise を実行しているデバイスに対する高度な脅威を検出し、調査し、対応するために Microsoft Defender Advanced Threat Protection (ATP) を展開しました。</span><span class="sxs-lookup"><span data-stu-id="11e00-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="11e00-157">オプションとして、Microsoft Defender ATP を他のツールと統合し、その機能を拡張しました。</span><span class="sxs-lookup"><span data-stu-id="11e00-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="11e00-158">必要に応じて、[手順 5](windows10-enable-security-features.md#windows10-sec-atp) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="11e00-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="11e00-159">結果と次のステップ</span><span class="sxs-lookup"><span data-stu-id="11e00-159">Results and next steps</span></span>

<span data-ttu-id="11e00-160">Windows 10 Enterprise インフラストラクチャは、新しいデバイスでのインストールと以前のバージョンの Windows を実行しているデバイスでの一括アップグレードを開始する準備ができており、Windows 10 Enterprise の重要なセキュリティ機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="11e00-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![フェーズ 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="11e00-162">Microsoft 365 Enterprise のエンド ツー エンド展開のフェーズを実行している場合、次の手順は [Office 365 ProPlus](office365proplus-infrastructure.md) です。</span><span class="sxs-lookup"><span data-stu-id="11e00-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
