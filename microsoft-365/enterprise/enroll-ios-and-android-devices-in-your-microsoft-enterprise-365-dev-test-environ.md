---
title: Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテストラボガイドを使用して、Microsoft 365 テスト環境にデバイスを登録し、リモートで管理します。
ms.openlocfilehash: e653b3e6cafb6ee2eb492709a2d060c7b92a6904
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281252"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d32aa-103">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="d32aa-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d32aa-104">この記事に記載されている手順に従って、Microsoft 365 エンタープライズテスト環境で iOS および Android デバイス用の基本的なモバイルデバイス管理機能を登録し、テストすることができます。</span><span class="sxs-lookup"><span data-stu-id="d32aa-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="d32aa-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d32aa-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="d32aa-107">フェーズ 1: Microsoft 365 Enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="d32aa-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="d32aa-108">最小要件を使用して iOS および Android デバイスを軽量な方法で登録する場合は、「軽量な[基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d32aa-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d32aa-109">シミュレートされたエンタープライズに iOS および Android デバイスを登録する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d32aa-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d32aa-110">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d32aa-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d32aa-111">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="d32aa-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="d32aa-112">フェーズ 2: iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="d32aa-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="d32aa-113">最初に、インストールの手順を使用して、[ポータルサイトアプリにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)し、テスト環境用の Microsoft Intune ポータルサイトアプリをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="d32aa-114">次に、「[セットアップアクセス権を会社のリソースに](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)登録する」の手順を使用して、iOS デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="d32aa-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="d32aa-115">次に、「 [Intune に android デバイスを登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)する」の手順を使用して android デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="d32aa-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="d32aa-116">フェーズ 3: iOS および Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="d32aa-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="d32aa-117">Microsoft Intune には、リモート ロック機能とパスコードのリセット機能あります。</span><span class="sxs-lookup"><span data-stu-id="d32aa-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="d32aa-118">ユーザーがデバイスを紛失した場合は、デバイスをリモートからロックできます。</span><span class="sxs-lookup"><span data-stu-id="d32aa-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="d32aa-119">他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。</span><span class="sxs-lookup"><span data-stu-id="d32aa-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="d32aa-120">iOS または Android デバイスをリモートでロックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d32aa-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="d32aa-121">全体管理者アカウントの資格情報[https://portal.azure.com](https://portal.azure.com)を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="d32aa-122">[**すべてのサービス**] をクリックし、「 **intune**」と入力して、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="d32aa-123">[ **devices > All devices**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="d32aa-124">デバイスの一覧で、iOS または Android デバイスをクリックし、[**リモートロック**] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="d32aa-125">パスコードをリモートからリセットするには、</span><span class="sxs-lookup"><span data-stu-id="d32aa-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="d32aa-126">必要に応じて、全体管理者アカウントの[https://portal.azure.com](https://portal.azure.com)資格情報を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="d32aa-127">[**すべてのサービス**] をクリックし、「 **intune**」と入力して、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="d32aa-128">[ **devices > All devices**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d32aa-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="d32aa-129">管理するデバイスのリストから、iOS または Android デバイスをクリックし、[...] を選択し**ます。詳細を参照**してください。</span><span class="sxs-lookup"><span data-stu-id="d32aa-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="d32aa-130">次に、[**パスコード**デバイスのリモートアクションの削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d32aa-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="d32aa-131">その他の実験については、「[使用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="d32aa-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="d32aa-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="d32aa-132">Next step</span></span>

<span data-ttu-id="d32aa-133">テスト環境での[モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d32aa-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d32aa-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="d32aa-134">See Also</span></span>

[<span data-ttu-id="d32aa-135">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="d32aa-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="d32aa-136">Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="d32aa-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="d32aa-137">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="d32aa-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d32aa-138">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d32aa-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
