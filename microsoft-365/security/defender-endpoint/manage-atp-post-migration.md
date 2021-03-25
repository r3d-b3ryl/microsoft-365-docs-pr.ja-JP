---
title: 移行後の Microsoft Defender for Endpoint の管理
description: Microsoft Defender for Endpoint への切り替えが行われたので、次に、脅威保護機能を管理します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Windows Defender Advanced Threat Protection、atp、edr
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
- m365solution-scenario
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 54302f38f0fd63560ecd1c5545efa4621c6b9bbd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185863"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a><span data-ttu-id="6e75a-104">Microsoft Defender for Endpoint の管理、移行後</span><span class="sxs-lookup"><span data-stu-id="6e75a-104">Manage Microsoft Defender for Endpoint, post migration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6e75a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6e75a-105">**Applies to:**</span></span>
- [<span data-ttu-id="6e75a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6e75a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6e75a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e75a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6e75a-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6e75a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6e75a-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6e75a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6e75a-110">以前のエンドポイント保護およびウイルス対策ソリューションから Microsoft Defender for Endpoint に移動した後、次に機能と機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="6e75a-110">After you have moved from your previous endpoint protection and antivirus solution to Microsoft Defender for Endpoint, your next step is to manage your features and capabilities.</span></span> <span data-ttu-id="6e75a-111">Microsoft Intune と[Microsoft Endpoint Configuration](https://docs.microsoft.com/mem/endpoint-manager-overview) [Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)を含む Microsoft [Endpoint](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) Manager を使用して、組織のデバイスとセキュリティ設定を管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e75a-111">We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), which includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction), to manage your organization's devices and security settings.</span></span> <span data-ttu-id="6e75a-112">ただし、Azure Active Directory ドメイン サービスのグループ ポリシー オブジェクトなど、他のツール/ [メソッドを使用できます](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-112">However, you can use other tools/methods, such as [Group Policy Objects in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy).</span></span> 

<span data-ttu-id="6e75a-113">次の表に、使用できるさまざまなツール/メソッドの一覧と、詳細へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="6e75a-113">The following table lists various tools/methods you can use, with links to learn more.</span></span> 
<br/><br/>

|<span data-ttu-id="6e75a-114">ツール/メソッド</span><span class="sxs-lookup"><span data-stu-id="6e75a-114">Tool/Method</span></span>  |<span data-ttu-id="6e75a-115">説明</span><span class="sxs-lookup"><span data-stu-id="6e75a-115">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6e75a-116">Microsoft Defender **[セキュリティ センターの脅威](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** と脆弱性管理ダッシュボードの分析情報 ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="6e75a-116">**[Threat and vulnerability management dashboard insights](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span> |<span data-ttu-id="6e75a-117">脆弱性管理ダッシュボード&脅威は、セキュリティ運用チームが使用して、露出を減らし、組織のセキュリティ体制を改善するために使用できる、アクション可能な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e75a-117">The threat & vulnerability management dashboard provides actionable information that your security operations team can use to reduce exposure and improve your organization's security posture.</span></span> <br/><br/><span data-ttu-id="6e75a-118">「 [脅威&の管理」および「Microsoft](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Defender セキュリティ センターの概要」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-118">See [Threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) and [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span></span>  |
|<span data-ttu-id="6e75a-119">**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (推奨)</span><span class="sxs-lookup"><span data-stu-id="6e75a-119">**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (recommended)</span></span>    |<span data-ttu-id="6e75a-120">Microsoft Endpoint Manager のコンポーネントである [Microsoft](https://docs.microsoft.com/mem/endpoint-manager-overview)Intune (Intune) は、モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) に重点を当てました。</span><span class="sxs-lookup"><span data-stu-id="6e75a-120">Microsoft Intune (Intune), a component of [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="6e75a-121">Intune では、携帯電話、タブレット、ラップトップなど、組織のデバイスの使用方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-121">With Intune, you control how your organization’s devices are used, including mobile phones, tablets, and laptops.</span></span> <span data-ttu-id="6e75a-122">特定のポリシーを構成して、アプリケーションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-122">You can also configure specific policies to control applications.</span></span> <br/><br/><span data-ttu-id="6e75a-123">[「Intune を使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-123">See [Manage Microsoft Defender for Endpoint using Intune](manage-atp-post-migration-intune.md).</span></span>         |
|<span data-ttu-id="6e75a-124">**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**</span><span class="sxs-lookup"><span data-stu-id="6e75a-124">**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**</span></span>     |<span data-ttu-id="6e75a-125">Microsoft Endpoint Manager (Configuration Manager) (以前は System Center Configuration Manager と呼ばれる) は [、Microsoft Endpoint Manager のコンポーネントです](https://docs.microsoft.com/mem/endpoint-manager-overview)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-125">Microsoft Endpoint Manager (Configuration Manager), formerly known as System Center Configuration Manager, is a component of [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview).</span></span> <span data-ttu-id="6e75a-126">Configuration Manager は、ユーザー、デバイス、ソフトウェアを管理するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="6e75a-126">Configuration Manager is a powerful tool to manage your users, devices, and software.</span></span><br/><br/><span data-ttu-id="6e75a-127">「Manage [Microsoft Defender for Endpoint with Configuration Manager」を参照してください](manage-atp-post-migration-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-127">See [Manage Microsoft Defender for Endpoint with Configuration Manager](manage-atp-post-migration-configuration-manager.md).</span></span>        |
|<span data-ttu-id="6e75a-128">**[Azure Active Directory ドメイン サービスのグループ ポリシー オブジェクト](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)**</span><span class="sxs-lookup"><span data-stu-id="6e75a-128">**[Group Policy Objects in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)**</span></span> |<span data-ttu-id="6e75a-129">[Azure Active Directory ドメイン サービスには、](https://docs.microsoft.com/azure/active-directory-domain-services/overview) ユーザーとデバイス用の組み込みのグループ ポリシー オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e75a-129">[Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/overview) includes built-in Group Policy Objects for users and devices.</span></span> <span data-ttu-id="6e75a-130">環境で必要に応じて組み込みのグループ ポリシー オブジェクトをカスタマイズし、カスタム グループ ポリシー オブジェクトと組織単位 (OUs) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-130">You can customize the built-in Group Policy Objects as needed for your environment, as well as create custom Group Policy Objects and organizational units (OUs).</span></span> <br/><br/><span data-ttu-id="6e75a-131">「 [グループ ポリシー オブジェクトを使用した Microsoft Defender for Endpoint の管理」を参照してください](manage-atp-post-migration-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-131">See [Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-atp-post-migration-group-policy-objects.md).</span></span> |
|<span data-ttu-id="6e75a-132">**[PowerShell、WMI、およびMPCmdRun.exe](manage-atp-post-migration-other-tools.md)**</span><span class="sxs-lookup"><span data-stu-id="6e75a-132">**[PowerShell, WMI, and MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**</span></span> |<span data-ttu-id="6e75a-133">*Microsoft Endpoint Manager (Intune と Configuration Manager を含む) を使用して、組織のデバイス上の脅威保護機能を管理することをお勧めします。ただし、PowerShell、WMI、またはデバイス ツールを使用して、個々のデバイス (エンドポイント) の Microsoft Defender ウイルス対策設定など、一部の設定MPCmdRun.exeできます。*</span><span class="sxs-lookup"><span data-stu-id="6e75a-133">*We recommend using Microsoft Endpoint Manager (which includes Intune and Configuration Manager) to manage threat protection features on your organization's devices. However, you can configure some settings, such as Microsoft Defender Antivirus settings on individual devices (endpoints) with PowerShell, WMI, or the MPCmdRun.exe tool.*</span></span><br/><br/><span data-ttu-id="6e75a-134">PowerShell を使用して、Microsoft Defender ウイルス対策、エクスプロイト保護、攻撃表面の縮小ルールを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-134">You can use PowerShell to manage Microsoft Defender Antivirus, exploit protection, and your attack surface reduction rules.</span></span> <span data-ttu-id="6e75a-135">「Configure [Microsoft Defender for Endpoint with PowerShell」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-135">See [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).</span></span><br/><br/><span data-ttu-id="6e75a-136">Windows 管理インストルメンテーション (WMI) を使用して、Microsoft Defender ウイルス対策と除外を管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-136">You can use Windows Management Instrumentation (WMI) to manage Microsoft Defender Antivirus and exclusions.</span></span> <span data-ttu-id="6e75a-137">「Configure [Microsoft Defender for Endpoint with WMI」を参照してください](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-137">See [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).</span></span><br/><br/><span data-ttu-id="6e75a-138">Microsoft Malware Protection Command-Line ユーティリティ (MPCmdRun.exe) を使用して、Microsoft Defender ウイルス対策と除外を管理し、ネットワークとクラウド間の接続を検証できます。</span><span class="sxs-lookup"><span data-stu-id="6e75a-138">You can use the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) to manage Microsoft Defender Antivirus and exclusions, as well as validate connections between your network and the cloud.</span></span> <span data-ttu-id="6e75a-139">「Configure [Microsoft Defender for Endpoint with MPCmdRun.exe」 を参照してください ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。</span><span class="sxs-lookup"><span data-stu-id="6e75a-139">See [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).</span></span> |

## <a name="see-also"></a><span data-ttu-id="6e75a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e75a-140">See also</span></span>

- [<span data-ttu-id="6e75a-141">エンドポイント向け Microsoft Defender で誤検知/負に対処する</span><span class="sxs-lookup"><span data-stu-id="6e75a-141">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)