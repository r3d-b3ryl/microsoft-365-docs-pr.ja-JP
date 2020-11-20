---
title: Microsoft 365 for enterprise テスト環境に iOS/iPadOS と Android デバイスを登録する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテストラボガイドを使用して、Microsoft 365 テスト環境にデバイスを登録し、リモートで管理します。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367085"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6fe4c-103">Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6fe4c-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="6fe4c-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6fe4c-105">この記事では、Microsoft 365 for enterprise テスト環境で iOS/iPadOS と Android デバイス用の基本的なモバイルデバイス管理機能を登録してテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="6fe4c-106">テスト環境で iOS/iPadOS と Android デバイスを登録するには、3つのフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="6fe4c-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6fe4c-108">フェーズ 2: iOS/iPadOS と Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="6fe4c-109">フェーズ 3: iOS/iPadOS と Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="6fe4c-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6fe4c-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6fe4c-113">最小要件を持つ軽量な方法で iOS/iPadOS と Android デバイスを登録する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6fe4c-114">シミュレートされたエンタープライズに iOS/iPadOS と Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fe4c-115">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6fe4c-116">この記事は、自動ライセンスおよびグループメンバーシップをテストできるようにするためのオプションとして提供されており、一般的な組織を表す環境で試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="6fe4c-117">フェーズ 2: iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="6fe4c-118">デバイスを管理するためにモバイルデバイス管理 (MDM) ソリューションを検討している場合は、Microsoft Intune を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="6fe4c-119">Intune を含む MDM プロバイダーを使用している場合、デバイスは "登録済み" です。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="6fe4c-120">登録すると、構成した機能と設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="6fe4c-121">Intune では、iOS/iPadOS と Android デバイスを登録する方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="6fe4c-122">組織にとって最適な登録オプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="6fe4c-123">詳細とガイダンスについては、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="6fe4c-124">展開ガイド: Microsoft Intune での iOS と iPadOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="6fe4c-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="6fe4c-125">展開ガイド: Android デバイスを Microsoft Intune に登録する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="6fe4c-126">Intune をデバイスの管理に使用する準備ができていて、何らかのガイダンスが必要な場合は、次の情報が役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="6fe4c-127">デバイス管理の概要</span><span class="sxs-lookup"><span data-stu-id="6fe4c-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="6fe4c-128">チュートリアル: Microsoft エンドポイントマネージャーのチュートリアル Intune</span><span class="sxs-lookup"><span data-stu-id="6fe4c-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="6fe4c-129">展開ガイド: セットアップまたは Microsoft Intune への移動</span><span class="sxs-lookup"><span data-stu-id="6fe4c-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="6fe4c-130">フェーズ 3: iOS および Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="6fe4c-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="6fe4c-131">Microsoft Intune は、リモートロックとパスコードのリセット機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="6fe4c-132">他のユーザーがデバイスを失った場合は、デバイスをリモートでロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="6fe4c-133">他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="6fe4c-134">IOS/iPadOS または Android デバイスをリモートでロックするには、「 [Intune でデバイスをリモートロック](/mem/intune/remote-actions/device-remote-lock)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="6fe4c-135">パスコードをリモートでリセットするには、「 [Intune でデバイスのパスコードをリセットまたは削除](/mem/intune/remote-actions/device-passcode-reset)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="6fe4c-136">リモートで実行できるその他のタスクについては、「 [使用可能なデバイスの操作](/mem/intune/remote-actions/device-management#available-device-actions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="6fe4c-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="6fe4c-137">Next step</span></span>

<span data-ttu-id="6fe4c-138">テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fe4c-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fe4c-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fe4c-139">See Also</span></span>

[<span data-ttu-id="6fe4c-140">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="6fe4c-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="6fe4c-141">Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="6fe4c-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="6fe4c-142">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="6fe4c-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
