---
title: 手順 4. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Microsoft エンドポイント マネージャーを使用して、管理デバイス、PC、その他のエンドポイントを管理します。
ms.openlocfilehash: bca3e8e79264a2218dd1036e50be1c9ab29d2b8a
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749601"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="6e7c0-104">手順 4.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-104">Step 4.</span></span> <span data-ttu-id="6e7c0-105">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="6e7c0-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="6e7c0-106">リモート ワーカーは、増え続ける個人用デバイスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="6e7c0-107">エンドポイント管理は、デバイスでのリソースへのアクセスを許可する前に特定の基準に準拠する必要があるセキュリティに対するポリシーベースのアプローチです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="6e7c0-108">Microsoft エンドポイント マネージャーは、クラウドとオンプレミスでデータを安全に保つための最新の管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="6e7c0-109">[Microsoft エンドポイント マネージャー](https://docs.microsoft.com/mem/endpoint-manager-overview)は、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、およびサーバーを管理できるサービスおよびツールを提供します。これは、すでに使用している可能性のある次のサービスを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-109">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![Microsoft 365 のエンドポイント管理のコンポーネント](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="6e7c0-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6e7c0-111">Microsoft Intune</span></span>

<span data-ttu-id="6e7c0-112">Microsoft Intune は、Microsoft 365 に付属しているモバイル デバイス管理 (MDM) およびモバイル アプリケーション管理 (MAM) に重点を置いた、クラウドベースのサービスです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="6e7c0-113">**MDM:** 組織所有のデバイスについては、設定、機能、およびセキュリティを含むフル コントロールを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="6e7c0-114">デバイスは、ルールと設定で Intune ポリシーを受信するようにすることで 「登録」 されます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="6e7c0-115">たとえば、パスワードや PIN の要件を設定したり、VPN 接続を作成したり、脅威の保護を設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="6e7c0-116">**MAM:** リモート ワーカーは個人のデバイス、いわゆる、「Bring-Your-Own Device (BYOD)」 にフル コントロールが必要でないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="6e7c0-117">リモート ワーカーに選択肢を提示しながら、組織を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="6e7c0-118">たとえば、リモート ワーカーが組織のリソースにフル アクセスすることを希望する場合、使用するデバイスを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="6e7c0-119">または、これらのユーザーが電子メールや Microsoft Teams にのみアクセスできるようにする場合は、これらのアプリを使用できるように多要素認証 (MFA) を必要とするアプリ保護ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="6e7c0-120">詳細については、「[Microsoft Intune の概要](https://docs.microsoft.com/intune/fundamentals/what-is-intune)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="6e7c0-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="6e7c0-121">Configuration Manager</span></span>

<span data-ttu-id="6e7c0-122">Configuration Manager は、ネットワークまたはインターネットベースのデスクトップ、サーバー、ノート PC を管理できるオンプレミスの管理ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="6e7c0-123">Configuration Manager を使用して、アプリ、ソフトウェアの更新、およびオペレーティング システムを展開します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="6e7c0-124">また、コンプライアンスの状況を監視し、リアルタイムでクライアントに対してクエリの実行と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="6e7c0-125">クラウド対応にして、Intune、Azure AD、Microsoft Defender for Endpoint、およびその他のクラウド サービスと統合できます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender for Endpoint, and other cloud services.</span></span> 

<span data-ttu-id="6e7c0-126">詳細については、この「[Configuration Manager の概要](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="6e7c0-127">共同管理</span><span class="sxs-lookup"><span data-stu-id="6e7c0-127">Co-management</span></span>

<span data-ttu-id="6e7c0-128">共同管理では、Intune などの Microsoft 365 クラウド サービスを使用して、既存のオンプレミスの Configuration Manager とクラウドを組み合わせて投資することができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="6e7c0-129">異なるワークロードの管理権限を Configuration Manager または Intune のどちらにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="6e7c0-130">共同管理では、条件付きアクセスやデバイス コンプライアンスの強化を含む、Intune ベースのクラウド機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="6e7c0-131">一部のタスクはオンプレミスに保ち、他のタスクはクラウドで実行します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="6e7c0-132">詳細については、「[共同管理の概要](https://docs.microsoft.com/mem/configmgr/comanage/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="6e7c0-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="6e7c0-133">Desktop Analytics</span></span>

<span data-ttu-id="6e7c0-134">Desktop Analytics は、Configuration Manager と統合し、分析情報とインテリジェンスを提供するクラウドベースのサービスであり、Windows クライアントに関する情報に基づいて意思決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="6e7c0-135">組織のデータと、Microsoft クラウド サービスに接続されている他の数百万のデバイスから収集されたデータを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-135">It combines data from your organization with data aggregated from millions of other devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="6e7c0-136">Desktop Analytics では、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="6e7c0-137">組織内で実行されているアプリのインベントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="6e7c0-138">最新の Windows 10 機能更新プログラムの互換性を評価します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="6e7c0-139">互換性の問題を特定し、クラウドに対応したデータ インサイトに基づいて対策の提案を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-139">Identify compatibility issues and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="6e7c0-140">最小単位のデバイスでアプリケーションとドライバーの全体を表すパイロット グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="6e7c0-141">Windows 10 をパイロットおよび運用管理デバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="6e7c0-142">詳細については、「[Desktop Analytics の概要](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="6e7c0-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="6e7c0-143">Windows Autopilot</span></span>

<span data-ttu-id="6e7c0-144">Windows Autopilot は、ゼロタッチでセルフサービスの Windows 展開プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="6e7c0-145">これは、新しいデバイスのセットアップと事前構成に使用されるテクノロジのコレクションで、生産性の高い使用ができるようにデバイスを準備するためのものです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-145">It includes a collection of technologies you use to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="6e7c0-146">Windows Autopilot を使用してデバイスのリセット、転用、復元を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="6e7c0-147">Windows Autopilot で、IT 部門は管理するインフラストラクチャがほとんどないかまったくない状態かつ簡単でシンプルなプロセスでデバイスを事前に構成できます。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="6e7c0-148">ユーザーから見ると、デバイスを使用できるようにするための簡単な操作が数ステップあるだけです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="6e7c0-149">IT の観点からすると、エンド ユーザーに必要な唯一の操作は、ネットワークに接続し、資格情報を確認することです。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="6e7c0-150">詳細については、「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="6e7c0-151">エンドポイント管理のための管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="6e7c0-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="6e7c0-152">Microsoft 365 のデバイス管理ロードマップ</span><span class="sxs-lookup"><span data-stu-id="6e7c0-152">Device management roadmap for Microsoft 365</span></span>](../enterprise/device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="6e7c0-153">モバイル デバイス管理のためにさまざまな種類のデバイスを登録する方法</span><span class="sxs-lookup"><span data-stu-id="6e7c0-153">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="6e7c0-154">Microsoft Intune についてエンド ユーザーを教育する方法</span><span class="sxs-lookup"><span data-stu-id="6e7c0-154">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-4"></a><span data-ttu-id="6e7c0-155">手順 4 の結果</span><span class="sxs-lookup"><span data-stu-id="6e7c0-155">Results of Step 4</span></span>

<span data-ttu-id="6e7c0-156">エンドポイント マネージャーの一連の機能を使用して、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、サーバーを管理しています。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-156">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="6e7c0-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="6e7c0-157">Next step</span></span>

<span data-ttu-id="6e7c0-158">[![手順 5: リモート ワーカー向けの生産性向上アプリとサービスを展開する](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span><span class="sxs-lookup"><span data-stu-id="6e7c0-158">[![Step 5: Deploy remote worker productivity apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-5.png)](empower-people-to-work-remotely-teams-productivity-apps.md)</span></span>

<span data-ttu-id="6e7c0-159">リモート ワーカーが、Microsoft Teams などの Microsoft 365 の生産性を高めるアプリを使用する方法については [手順 5](empower-people-to-work-remotely-teams-productivity-apps.md) を続けてください。</span><span class="sxs-lookup"><span data-stu-id="6e7c0-159">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
