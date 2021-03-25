---
title: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する
description: Configuration Manager を使用して Microsoft Defender for Endpoint を管理する方法について説明します。
keywords: 移行後、管理、運用、メンテナンス、使用率、Configuration Manager、Windows Defender Advanced Threat Protection、atp、edr
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
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185654"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="6f536-104">Configuration Manager を使用して Microsoft Defender for Endpoint を管理する</span><span class="sxs-lookup"><span data-stu-id="6f536-104">Manage Microsoft Defender for Endpoint with Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f536-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6f536-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f536-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f536-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f536-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f536-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6f536-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6f536-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6f536-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6f536-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="6f536-110">Microsoft Endpoint Manager [(Microsoft](https://docs.microsoft.com/mem) [Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) と Microsoft Endpoint [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) を使用して、デバイス (エンドポイントとも呼ばれます) の組織の脅威保護機能を管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f536-110">We recommend using We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), which includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) to manage your organization's threat protection features for devices (also referred to as endpoints).</span></span> 
- [<span data-ttu-id="6f536-111">エンドポイント マネージャーの詳細</span><span class="sxs-lookup"><span data-stu-id="6f536-111">Learn more about Endpoint Manager</span></span>](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [<span data-ttu-id="6f536-112">Windows 10 デバイス上の Microsoft Defender for Endpoint を Configuration Manager と Intune で共同管理する</span><span class="sxs-lookup"><span data-stu-id="6f536-112">Co-manage Microsoft Defender for Endpoint on Windows 10 devices with Configuration Manager and Intune</span></span>](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a><span data-ttu-id="6f536-113">Configuration Manager を使用して Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="6f536-113">Configure Microsoft Defender for Endpoint with Configuration Manager</span></span>

|<span data-ttu-id="6f536-114">タスク</span><span class="sxs-lookup"><span data-stu-id="6f536-114">Task</span></span>  |<span data-ttu-id="6f536-115">追加情報</span><span class="sxs-lookup"><span data-stu-id="6f536-115">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="6f536-116">**Configuration Manager コンソールをまだ** インストールしていない場合はインストールする</span><span class="sxs-lookup"><span data-stu-id="6f536-116">**Install the Configuration Manager console** if you don't already have it</span></span><br/><br/><span data-ttu-id="6f536-117">*Configuration Manger コンソールをまだ持ってない場合は、これらのリソースを使用してビットを取得してインストールします。*</span><span class="sxs-lookup"><span data-stu-id="6f536-117">*If you don't already have the Configuration Manger console, use these resources to get the bits and install it.*</span></span> |[<span data-ttu-id="6f536-118">インストール メディアの取得</span><span class="sxs-lookup"><span data-stu-id="6f536-118">Get the installation media</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[<span data-ttu-id="6f536-119">Configuration Manager コンソールのインストール</span><span class="sxs-lookup"><span data-stu-id="6f536-119">Install the Configuration Manager console</span></span>](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|<span data-ttu-id="6f536-120">**Configuration Manager を使用してデバイスを** Microsoft Defender for Endpoint にオンボードする</span><span class="sxs-lookup"><span data-stu-id="6f536-120">**Use Configuration Manager to onboard devices** to Microsoft Defender for Endpoint</span></span> <br/><br/> <span data-ttu-id="6f536-121">*デバイス (またはエンドポイント) が Microsoft Defender for Endpoint にまだオンボードされていない場合は、Configuration Manager を使用して実行できます。*</span><span class="sxs-lookup"><span data-stu-id="6f536-121">*If you have devices (or endpoints) not already onboarded to Microsoft Defender for Endpoint, you can do that with Configuration Manager.*</span></span>   |[<span data-ttu-id="6f536-122">Configuration Manager を使用して Microsoft Defender for Endpoint にオンボードする</span><span class="sxs-lookup"><span data-stu-id="6f536-122">Onboard to Microsoft Defender for Endpoint with Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|<span data-ttu-id="6f536-123">**クライアント コンピューター (エンドポイント) のマルウェア** 対策ポリシーと Windows ファイアウォール のセキュリティを管理する</span><span class="sxs-lookup"><span data-stu-id="6f536-123">**Manage antimalware policies and Windows Firewall security** for client computers (endpoints)</span></span><br/><br/><span data-ttu-id="6f536-124">*エンドポイント保護機能 (Microsoft Defender for Endpoint、Exploit Protection、アプリケーション制御、マルウェア対策、ファイアウォール設定など) を構成します。*</span><span class="sxs-lookup"><span data-stu-id="6f536-124">*Configure endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*</span></span>  |[<span data-ttu-id="6f536-125">Configuration Manager: Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="6f536-125">Configuration Manager: Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|<span data-ttu-id="6f536-126">**組織のデバイスでマルウェア対策更新プログラムを更新** する方法を選択する</span><span class="sxs-lookup"><span data-stu-id="6f536-126">**Choose methods for updating antimalware updates** on your organization's devices</span></span> <br/><br/><span data-ttu-id="6f536-127">*Configuration Manager の Endpoint Protection では、組織のデバイスでマルウェア対策定義を最新の状態に保つために、いくつかの方法から選択できます。*</span><span class="sxs-lookup"><span data-stu-id="6f536-127">*With Endpoint Protection in Configuration Manager, you can choose from several methods to keep antimalware definitions up to date on your organization's devices.*</span></span> |[<span data-ttu-id="6f536-128">エンドポイント保護の定義更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="6f536-128">Configure definition updates for Endpoint Protection</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[<span data-ttu-id="6f536-129">Configuration Manager を使用して定義の更新プログラムを配信する</span><span class="sxs-lookup"><span data-stu-id="6f536-129">Use Configuration Manager to deliver definition updates</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|<span data-ttu-id="6f536-130">**ネットワーク保護を有効** にして、従業員が悪意のあるコンテンツをインターネット上で使用するアプリを使用するのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="6f536-130">**Enable Network Protection** to help prevent employees from using apps that malicious content on the Internet</span></span> <br/><br/><span data-ttu-id="6f536-131">*テスト環境で [ネットワーク保護のために](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 監査モードを最初に使用して、展開前にブロックされるアプリを確認することをお勧めします。*</span><span class="sxs-lookup"><span data-stu-id="6f536-131">*We recommend using [audit mode](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) at first for network protection in a test environment to see which apps would be blocked before rolling out.*</span></span> |[<span data-ttu-id="6f536-132">Configuration Manager でネットワーク保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="6f536-132">Turn on network protection with Configuration Manager</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|<span data-ttu-id="6f536-133">**ランサムウェアから保護するためにフォルダー** アクセスの制御を構成する</span><span class="sxs-lookup"><span data-stu-id="6f536-133">**Configure controlled folder access** to protect against ransomware</span></span> <br/><br/><span data-ttu-id="6f536-134">*フォルダー アクセスの制御は、アンチランソイエムウェア保護とも呼ばれます。*</span><span class="sxs-lookup"><span data-stu-id="6f536-134">*Controlled folder access is also referred to as antiransomware protection.*</span></span>   |[<span data-ttu-id="6f536-135">エンドポイント保護: フォルダー アクセスの制御</span><span class="sxs-lookup"><span data-stu-id="6f536-135">Endpoint protection: Controlled folder access</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[<span data-ttu-id="6f536-136">Microsoft Endpoint Configuration Manage でフォルダー アクセスの制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="6f536-136">Enable controlled folder access in Microsoft Endpoint Configuration Manage</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a><span data-ttu-id="6f536-137">Microsoft Defender セキュリティ センターを構成する</span><span class="sxs-lookup"><span data-stu-id="6f536-137">Configure your Microsoft Defender Security Center</span></span>

<span data-ttu-id="6f536-138">まだ行っていない場合は **、Microsoft Defender Security Center** ( ) を構成して、アラートの表示、脅威保護機能の構成、組織の全体的なセキュリティ体制に関する詳細情報 [https://securitycenter.windows.com](https://securitycenter.windows.com) の表示を行います。</span><span class="sxs-lookup"><span data-stu-id="6f536-138">If you haven't already done so, **configure your Microsoft Defender Security Center** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) to view alerts, configure threat protection features, and view detailed information about your organization's overall security posture.</span></span> 

<span data-ttu-id="6f536-139">また、エンド ユーザーが Microsoft Defender セキュリティ センターで表示できる機能と機能を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f536-139">You can also configure whether and what features end users can see in the Microsoft Defender Security Center.</span></span>

- [<span data-ttu-id="6f536-140">Microsoft Defender セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="6f536-140">Overview of the Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [<span data-ttu-id="6f536-141">エンドポイント保護: Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="6f536-141">Endpoint protection: Microsoft Defender Security Center</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a><span data-ttu-id="6f536-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="6f536-142">Next steps</span></span>

- [<span data-ttu-id="6f536-143">脅威と脆弱性の管理の概要を確認する</span><span class="sxs-lookup"><span data-stu-id="6f536-143">Get an overview of threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [<span data-ttu-id="6f536-144">Microsoft Defender Security Center のセキュリティ操作ダッシュボードにアクセスする</span><span class="sxs-lookup"><span data-stu-id="6f536-144">Visit the Microsoft Defender Security Center security operations dashboard</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [<span data-ttu-id="6f536-145">Intune を使用してエンドポイント用 Microsoft Defender を管理する</span><span class="sxs-lookup"><span data-stu-id="6f536-145">Manage Microsoft Defender for Endpoint with Intune</span></span>](manage-atp-post-migration-intune.md)
