---
title: Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテストラボガイドを使用して、Microsoft 365 テスト環境にデバイスを登録し、リモートで管理します。
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487698"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69f13-103">Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="69f13-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69f13-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="69f13-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="69f13-105">この記事では、Microsoft 365 for enterprise テスト環境に iOS および Android デバイス用の基本的なモバイルデバイス管理機能を登録およびテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69f13-105">This article describes how to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="69f13-106">テスト環境に iOS および Android デバイスを登録するには、3つのフェーズが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69f13-106">Enrolling iOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="69f13-107">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="69f13-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="69f13-108">フェーズ 2: iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="69f13-108">Phase 2: Enroll your iOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="69f13-109">フェーズ 3: iOS および Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="69f13-109">Phase 3: Manage your iOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="69f13-111">Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f13-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="69f13-112">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="69f13-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="69f13-113">最小要件を持つ軽量な方法で iOS および Android デバイスを登録する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="69f13-113">If you want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="69f13-114">シミュレートされたエンタープライズに iOS および Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="69f13-114">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="69f13-115">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69f13-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="69f13-116">この記事は、自動ライセンスおよびグループメンバーシップをテストできるようにするためのオプションとして提供されており、一般的な組織を表す環境で試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="69f13-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="69f13-117">フェーズ 2: iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="69f13-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="69f13-118">最初に、インストールの手順を使用して、 [ポータルサイトアプリにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) し、テスト環境用の Microsoft Intune ポータルサイトアプリをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="69f13-118">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="69f13-119">次に、「 [セットアップアクセス権を会社のリソースに](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 登録する」の手順を使用して、iOS デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="69f13-119">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="69f13-120">次に、「 [Intune に android デバイスを登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) する」の手順を使用して android デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="69f13-120">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="69f13-121">フェーズ 3: iOS および Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="69f13-121">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="69f13-122">Microsoft Intune には、リモート ロック機能とパスコードのリセット機能あります。</span><span class="sxs-lookup"><span data-stu-id="69f13-122">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="69f13-123">他のユーザーがデバイスを失った場合は、デバイスをリモートでロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="69f13-123">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="69f13-124">他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。</span><span class="sxs-lookup"><span data-stu-id="69f13-124">If someone forgets their passcode, you can remotely reset it.</span></span>
  
<span data-ttu-id="69f13-125">IOS または Android デバイスをリモートでロックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="69f13-125">To remotely lock an iOS or Android device:</span></span>

1. <span data-ttu-id="69f13-126">[https://portal.azure.com](https://portal.azure.com)全体管理者アカウントの資格情報を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="69f13-126">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="69f13-127">Azure portal で、検索ボックスに「 **intune** 」と入力し、[ **intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f13-127">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="69f13-128">[ **デバイス > すべてのデバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69f13-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="69f13-129">デバイスの一覧で iOS または Android デバイスを選択し、[ **リモートロック** ] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="69f13-129">In the list of devices, select an iOS or Android device, and then select the **Remote lock** action.</span></span>
    
<span data-ttu-id="69f13-130">パスコードをリモートでリセットするには</span><span class="sxs-lookup"><span data-stu-id="69f13-130">To remotely reset the passcode:</span></span>

1. <span data-ttu-id="69f13-131">必要に応じて、 [https://portal.azure.com](https://portal.azure.com) 全体管理者アカウントの資格情報を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="69f13-131">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="69f13-132">Azure portal で、検索ボックスに「 **intune** 」と入力し、[ **intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f13-132">In the Azure portal, enter **Intune** in the search box, and then select **Intune**.</span></span>
3. <span data-ttu-id="69f13-133">[**デバイス**  >  **すべてのデバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f13-133">Select **Devices** > **All devices**.</span></span>
4. <span data-ttu-id="69f13-134">管理するデバイスのリストから、iOS または Android デバイスを選択し、[...] を選択し**ます。その後、[\*\*\*\*パスコード**デバイスのリモートアクションを削除する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f13-134">From the list of devices you manage, select an iOS or Android device, select **...More**, and then select the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="69f13-135">その他の実験については、「 [使用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="69f13-135">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="69f13-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="69f13-136">Next step</span></span>

<span data-ttu-id="69f13-137">テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="69f13-137">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="69f13-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="69f13-138">See Also</span></span>

[<span data-ttu-id="69f13-139">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="69f13-139">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="69f13-140">Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="69f13-140">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="69f13-141">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="69f13-141">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
