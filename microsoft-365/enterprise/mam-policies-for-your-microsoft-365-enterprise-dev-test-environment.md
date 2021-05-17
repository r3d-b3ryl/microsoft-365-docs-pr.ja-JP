---
title: エンタープライズ テスト環境Microsoft 365デバイス コンプライアンス ポリシー
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
description: このテスト ラボ ガイドを使用して、Intune デバイス コンプライアンス ポリシーをエンタープライズ テスト環境Microsoft 365に追加します。
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367097"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6b564-103">エンタープライズ テスト環境Microsoft 365デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6b564-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6b564-104">*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="6b564-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6b564-105">この記事では、エンタープライズ テスト環境用に、デバイスとデバイスの Intune Windows 10ポリシー Microsoft 365 Apps for enterpriseをMicrosoft 365する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b564-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="6b564-106">Intune デバイスコンプライアンス ポリシーを追加するには、次の 2 つのフェーズが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b564-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="6b564-107">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="6b564-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6b564-108">フェーズ 2: デバイスコンプライアンス ポリシーを作成して、Windows 10する</span><span class="sxs-lookup"><span data-stu-id="6b564-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6b564-110">エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="6b564-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6b564-111">フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する</span><span class="sxs-lookup"><span data-stu-id="6b564-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6b564-112">最小要件で軽量な方法でのみ MAM ポリシーを構成する場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="6b564-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6b564-113">シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、「パススルー認証」の [手順に従います](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="6b564-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b564-114">ライセンスとグループ の自動メンバーシップをテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。</span><span class="sxs-lookup"><span data-stu-id="6b564-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6b564-115">ここではオプションとして提供され、一般的な組織を表す環境で、自動ライセンスとグループ メンバーシップをテストして実験できます。</span><span class="sxs-lookup"><span data-stu-id="6b564-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="6b564-116">フェーズ 2: デバイスコンプライアンス ポリシーを作成して、Windows 10する</span><span class="sxs-lookup"><span data-stu-id="6b564-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="6b564-117">このフェーズでは、デバイスのコンプライアンス ポリシーを作成し、Windows 10します。</span><span class="sxs-lookup"><span data-stu-id="6b564-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="6b564-118">このフェーズでは、Microsoft Intune管理センター Microsoft エンドポイント マネージャー[を使用](https://go.microsoft.com/fwlink/?linkid=2109431)してグループを追加し、コンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b564-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="6b564-119">管理者センターに[Microsoft 365](https://admin.microsoft.com)し、グローバル管理者アカウントでテスト ラボMicrosoft 365にサインインします。</span><span class="sxs-lookup"><span data-stu-id="6b564-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="6b564-120">管理センター **エンドポイント マネージャー** 選択します。</span><span class="sxs-lookup"><span data-stu-id="6b564-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="6b564-121">管理[エンドポイント マネージャーが開](https://go.microsoft.com/fwlink/?linkid=2109431)きます。</span><span class="sxs-lookup"><span data-stu-id="6b564-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="6b564-122">[デバイス管理を有効にしていない] に似たメッセージがまだ表示 **されている** 場合は、MDM 機関として [Intune] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b564-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="6b564-123">具体的な手順については、「モバイル デバイス管理 [機関の設定」を参照してください](/mem/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="6b564-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="6b564-124">管理エンドポイント マネージャーは、デバイス管理とアプリ管理に重点を当て、</span><span class="sxs-lookup"><span data-stu-id="6b564-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="6b564-125">この管理センターのツアーについては、「チュートリアル: チュートリアル Intune in Microsoft エンドポイント マネージャー」[を参照してください](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="6b564-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="6b564-126">[**グループ]** で、[割り当てられたMicrosoft 365の種類を持つ **、Managed** Windows 10という名前の新しいグループまたはセキュリティ グループ **を** 追加します。</span><span class="sxs-lookup"><span data-stu-id="6b564-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="6b564-127">次の手順では、コンプライアンス ポリシーをこのグループに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="6b564-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="6b564-128">特定の手順、およびセキュリティ グループまたはセキュリティ **Microsoft 365については**、「グループを追加してユーザー **とデバイスを** 整理する [」を参照してください](/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="6b564-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="6b564-129">[**デバイス]** で、コンプライアンス ポリシー Windows 10作成します。</span><span class="sxs-lookup"><span data-stu-id="6b564-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="6b564-130">作成したデバイス ユーザー グループの **管理Windows 10に** このポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="6b564-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="6b564-131">ポリシーでは、単純なパスワードをブロックし、ファイアウォールを要求し、Microsoft Defender Antimalware サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b564-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="6b564-132">コンプライアンス ポリシーには、通常、すべてのデバイスに必要な基本設定または最低限の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b564-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="6b564-133">具体的な手順、および構成できるコンプライアンス設定の詳細については、「コンプライアンス ポリシーを使用して管理するデバイスのルールを設定する」 [を参照してください](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="6b564-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="6b564-134">完了すると、Managed Windows 10デバイス ユーザー グループのメンバー **をテストするデバイス コンプライアンス ポリシーがあります**。</span><span class="sxs-lookup"><span data-stu-id="6b564-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="6b564-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="6b564-135">Next step</span></span>

<span data-ttu-id="6b564-136">テスト環境 [で、その他の](m365-enterprise-test-lab-guides.md#mobile-device-management) モバイル デバイス管理機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b564-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b564-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b564-137">See also</span></span>

<span data-ttu-id="6b564-138">[Microsoft 365テスト ラボ ガイドの詳細](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="6b564-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="6b564-139">エンタープライズ テスト環境用に iOS Microsoft 365 Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6b564-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="6b564-140">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="6b564-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6b564-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="6b564-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
