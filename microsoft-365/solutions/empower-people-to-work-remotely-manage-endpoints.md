---
title: 手順 3. デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: Microsoft エンドポイント マネージャーを使用して、管理デバイス、PC、その他のエンドポイントを管理します。
ms.openlocfilehash: 388ac2b7f9f4a31d33c1f4551e215b2b32c8f85f
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160800"
---
# <a name="step-3-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="54608-104">手順 3.</span><span class="sxs-lookup"><span data-stu-id="54608-104">Step 3.</span></span> <span data-ttu-id="54608-105">デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する</span><span class="sxs-lookup"><span data-stu-id="54608-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="54608-106">リモート ワーカーは、増え続ける個人用デバイスをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54608-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="54608-107">エンドポイント管理は、デバイスでのリソースへのアクセスを許可する前に特定の基準に準拠する必要があるセキュリティに対するポリシーベースのアプローチです。</span><span class="sxs-lookup"><span data-stu-id="54608-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="54608-108">Microsoft エンドポイント マネージャーは、クラウドおよびオンプレミスでデータを安全に保つための最新の作業環境と管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="54608-108">Microsoft Endpoint Manager delivers a modern workplace and modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="54608-109">エンドポイント マネージャーは、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、およびサーバーを管理できるサービスおよびツールを提供します。これは、すでに使用している可能性のある次のサービスを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="54608-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![エンドポイント管理のコンポーネント](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="54608-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="54608-111">Microsoft Intune</span></span>

<span data-ttu-id="54608-112">Intune は、組織のデータへのアクセスに使用されるデバイスを管理していない場合にデータを保護できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="54608-112">Intune is designed to help you safeguard data when you don’t manage the devices used to access organization data.</span></span> <span data-ttu-id="54608-113">Azure AD 条件付きアクセスと組み合わせた Intune アプリ保護ポリシーにより、モバイル デバイス上のデータをきめ細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="54608-113">Intune app protection policies combined with Azure AD Conditional Access provide granular control over data on mobile devices.</span></span> <span data-ttu-id="54608-114">Intune では、適切な条件下で適切な人だけが会社のデータにアクセスできるようにする包括的なポリシーを定義し、Office、Outlook、およびその他のモバイル アプリ内でデータを使用する方法を制御することでデータを保護し続けます。</span><span class="sxs-lookup"><span data-stu-id="54608-114">Intune also enables you to define comprehensive policies that allow only the right people under the right conditions to access your company data and ensure the data stays protected by controlling how they use it within Office, Outlook and other mobile apps.</span></span>

<span data-ttu-id="54608-115">詳細については、「[Microsoft Intune の概要](https://docs.microsoft.com/intune/fundamentals/what-is-intune)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54608-115">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="54608-116">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="54608-116">Configuration Manager</span></span>

<span data-ttu-id="54608-117">Configuration Manager は、ネットワークまたはインターネットベースのデスクトップ、サーバー、ノート PC を管理できるオンプレミスの管理ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="54608-117">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="54608-118">クラウド対応にして、Intune、Azure AD、Microsoft Defender ATP、およびその他のクラウド サービスと統合できます。</span><span class="sxs-lookup"><span data-stu-id="54608-118">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> <span data-ttu-id="54608-119">Configuration Manager を使用して、アプリ、ソフトウェアの更新、およびオペレーティング システムを展開します。</span><span class="sxs-lookup"><span data-stu-id="54608-119">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="54608-120">また、コンプライアンスの状況を監視し、リアルタイムでクライアントに対してクエリの実行と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="54608-120">You can also monitor compliance, query and act on clients in real time, and much more.</span></span>

<span data-ttu-id="54608-121">詳細については、この「[Configuration Manager の概要](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54608-121">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="54608-122">共同管理</span><span class="sxs-lookup"><span data-stu-id="54608-122">Co-management</span></span>

<span data-ttu-id="54608-123">共同管理では、Intune などの Microsoft 365 クラウド サービスを使用して、既存のオンプレミスの Configuration Manager とクラウドを組み合わせて投資することができます。</span><span class="sxs-lookup"><span data-stu-id="54608-123">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="54608-124">7 つの異なるワークロード グループの管理権限を Configuration Manager または Intune のどちらにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="54608-124">You choose whether Configuration Manager or Intune is the management authority for the seven different workload groups.</span></span>

<span data-ttu-id="54608-125">エンドポイント マネージャーの一部として、共同管理は条件付きアクセスを含むクラウド機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="54608-125">As part of Endpoint Manager, co-management uses cloud features, including Conditional Access.</span></span> <span data-ttu-id="54608-126">一部のタスクはオンプレミスに保ち、他のタスクは Intune を使用してクラウドで実行します。</span><span class="sxs-lookup"><span data-stu-id="54608-126">You keep some tasks on-premises, while running other tasks in the cloud with Intune.</span></span>

<span data-ttu-id="54608-127">詳細については、「[共同管理の概要](https://docs.microsoft.com/mem/configmgr/comanage/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54608-127">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="54608-128">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="54608-128">Desktop Analytics</span></span>

<span data-ttu-id="54608-129">Desktop Analytics は、Configuration Manager と統合し、分析情報とインテリジェンスを提供するクラウドベースのサービスであり、Windows クライアントに関する情報に基づいて意思決定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="54608-129">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="54608-130">組織のデータと、Microsoft クラウド サービスに接続されている数百万のデバイスから収集されたデータを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="54608-130">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> <span data-ttu-id="54608-131">Desktop Analytics を使用すると、組織内で実行されているアプリのインベントリの作成、最新の Windows 10 機能の更新プログラムとアプリの互換性の評価、互換性の問題の特定、クラウド対応のデータの分析情報に基づく軽減案の提供、アプリケーション全体と最小限のデバイス セットのドライバーの資産を表すパイロット グループの作成、および Windows 10 のパイロットおよび運用管理デバイスへの展開が可能になります。</span><span class="sxs-lookup"><span data-stu-id="54608-131">With Desktop Analytics, you can create an inventory of apps running in your organization, assess app compatibility with the latest Windows 10 feature updates, identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights, create pilot groups that represent the entire application and driver estate across a minimal set of devices, and deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="54608-132">詳細については、「[Desktop Analytics の概要](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54608-132">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="54608-133">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="54608-133">Windows Autopilot</span></span>

<span data-ttu-id="54608-134">Windows Autopilot は、ゼロタッチでセルフサービスの Windows 展開プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="54608-134">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="54608-135">これは、新しいデバイスのセットアップと事前構成に使用されるテクノロジのコレクションで、生産性の高い使用ができるようにデバイスを準備するためのものです。</span><span class="sxs-lookup"><span data-stu-id="54608-135">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="54608-136">Windows Autopilot を使用してデバイスのリセット、転用、復元を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="54608-136">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> <span data-ttu-id="54608-137">この解決方法で、IT 部門は管理するインフラストラクチャがほとんどないかまったくない状態かつ簡単でシンプルなプロセスで上記の手順を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="54608-137">This solution enables an IT department to achieve the above with little to no infrastructure to manage, with a process that's easy and simple.</span></span> <span data-ttu-id="54608-138">ユーザーから見ると、デバイスを使用できるようにするための簡単な操作が数ステップあるだけです。</span><span class="sxs-lookup"><span data-stu-id="54608-138">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> <span data-ttu-id="54608-139">IT の観点からすると、エンド ユーザーに必要な唯一の操作は、ネットワークに接続し、資格情報を確認することです。</span><span class="sxs-lookup"><span data-stu-id="54608-139">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="54608-140">詳細については、「[Windows Autopilot の概要](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54608-140">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="54608-141">エンドポイント管理のための管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="54608-141">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="54608-142">セキュリティのために管理対象デバイスを登録し、非管理対象デバイスのアプリ設定を活用し、デバイスとアプリのポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="54608-142">Enroll managed devices for security, leverage app settings for unmanaged devices, and use device and app policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="54608-143">モバイル デバイス管理 (MDM) のためにさまざまな種類のデバイスを登録する方法</span><span class="sxs-lookup"><span data-stu-id="54608-143">How to enroll different types of devices for mobile device management (MDM)</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="54608-144">Microsoft Intune についてエンド ユーザーを教育する方法</span><span class="sxs-lookup"><span data-stu-id="54608-144">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="54608-145">手順 3 の結果</span><span class="sxs-lookup"><span data-stu-id="54608-145">Results of Step 3</span></span>

<span data-ttu-id="54608-146">エンドポイント マネージャーの一連の機能を使用して、モバイル デバイス、デスクトップ コンピューター、仮想マシン、組み込みデバイス、サーバーを管理しています。</span><span class="sxs-lookup"><span data-stu-id="54608-146">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="54608-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="54608-147">Next step</span></span>

<span data-ttu-id="54608-148">[手順 4](empower-people-to-work-remotely-teams-productivity-apps.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="54608-148">Continue with [Step 4](empower-people-to-work-remotely-teams-productivity-apps.md) to provide remote access to on-premises apps and services.</span></span>
