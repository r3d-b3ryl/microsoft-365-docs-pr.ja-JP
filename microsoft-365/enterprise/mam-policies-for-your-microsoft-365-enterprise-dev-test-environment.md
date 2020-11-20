---
title: Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境に Intune デバイスコンプライアンスポリシーを追加します。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367097"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c189f-103">Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="c189f-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c189f-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="c189f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c189f-105">この記事では、Windows 10 365 デバイスの Intune デバイスコンプライアンスポリシーを Microsoft 365 for enterprise テスト環境に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c189f-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="c189f-106">Intune デバイスコンプライアンスポリシーを追加するには、次の2つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="c189f-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="c189f-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c189f-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="c189f-108">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c189f-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c189f-110">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c189f-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="c189f-111">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="c189f-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="c189f-112">最小要件での軽量な方法で MAM ポリシーを構成する場合は、「 [簡易基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c189f-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c189f-113">シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c189f-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c189f-114">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c189f-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c189f-115">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="c189f-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c189f-116">フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c189f-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c189f-117">このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c189f-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="c189f-118">このフェーズでは、Microsoft Intune と [Microsoft エンドポイント管理センター](https://go.microsoft.com/fwlink/?linkid=2109431) を使用して、グループを追加し、コンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c189f-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="c189f-119">[Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、全体管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c189f-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="c189f-120">**エンドポイントマネージャー** 管理センターを選択します。</span><span class="sxs-lookup"><span data-stu-id="c189f-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="c189f-121">[エンドポイントマネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)が開きます。</span><span class="sxs-lookup"><span data-stu-id="c189f-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="c189f-122">[デバイス管理] が [ **有効になってい** ません] というメッセージが表示されている場合は、MDM authority として [Intune] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c189f-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="c189f-123">具体的な手順については、「 [モバイルデバイス管理機関を設定する](/mem/intune/fundamentals/mdm-authority-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c189f-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="c189f-124">エンドポイントマネージャー管理センターは、デバイスの管理とアプリの管理に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="c189f-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="c189f-125">この管理センターのツアーについては、「 [チュートリアル: Microsoft エンドポイントマネージャーのチュートリアル Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c189f-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="c189f-126">[**グループ**] で、メンバーシップの種類が **割り当てられ** た、新しい **Microsoft 365** または **Managed Windows 10 デバイスユーザー** という名前の **セキュリティ** グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="c189f-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="c189f-127">次の手順では、コンプライアンスポリシーをこのグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c189f-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="c189f-128">特定の手順、および **マイクロソフトの 365** または **セキュリティ** グループの詳細については、「 [ユーザーとデバイスを整理するためにグループを追加する](/mem/intune/fundamentals/groups-add)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c189f-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="c189f-129">[ **デバイス**] で、Windows 10 コンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c189f-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="c189f-130">作成した **管理 Windows 10 デバイスユーザー** グループにこのポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c189f-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="c189f-131">ポリシーでは、単純なパスワードをブロックしたり、ファイアウォールを必要としたり、Microsoft Defender マルウェア対策サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c189f-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="c189f-132">通常、コンプライアンスポリシーには、すべてのデバイスに必要な基本設定、または最小限の要件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c189f-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="c189f-133">具体的な手順、および構成できるコンプライアンス設定の詳細については、「 [コンプライアンスポリシーを使用して、管理するデバイスのルールを設定する](/mem/intune/protect/device-compliance-get-started)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c189f-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="c189f-134">完了したら、管理された **Windows 10 デバイスユーザー** グループのメンバーをテストするためのデバイスコンプライアンスポリシーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c189f-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c189f-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="c189f-135">Next step</span></span>

<span data-ttu-id="c189f-136">テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c189f-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c189f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c189f-137">See also</span></span>

<span data-ttu-id="c189f-138">[Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="c189f-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c189f-139">Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="c189f-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c189f-140">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="c189f-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c189f-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c189f-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
