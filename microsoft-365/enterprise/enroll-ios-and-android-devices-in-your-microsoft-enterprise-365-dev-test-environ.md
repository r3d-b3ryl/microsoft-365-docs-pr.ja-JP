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
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686012"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="91afe-103">Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="91afe-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="91afe-104">*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*</span><span class="sxs-lookup"><span data-stu-id="91afe-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="91afe-105">この記事に記載されている手順に従うことで、Microsoft 365 for enterprise テスト環境に iOS および Android デバイス用の基本的なモバイルデバイス管理機能を登録し、テストすることができます。</span><span class="sxs-lookup"><span data-stu-id="91afe-105">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="91afe-107">[ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="91afe-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="91afe-108">フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する</span><span class="sxs-lookup"><span data-stu-id="91afe-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="91afe-109">最小要件を使用して iOS および Android デバイスを軽量な方法で登録する場合は、「軽量な [基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="91afe-109">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="91afe-110">シミュレートされたエンタープライズに iOS および Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="91afe-110">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="91afe-111">自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91afe-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="91afe-112">この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="91afe-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="91afe-113">フェーズ 2: iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="91afe-113">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="91afe-114">最初に、インストールの手順を使用して、 [ポータルサイトアプリにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) し、テスト環境用の Microsoft Intune ポータルサイトアプリをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="91afe-114">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="91afe-115">次に、「 [セットアップアクセス権を会社のリソースに](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 登録する」の手順を使用して、iOS デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="91afe-115">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="91afe-116">次に、「 [Intune に android デバイスを登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) する」の手順を使用して android デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="91afe-116">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="91afe-117">フェーズ 3: iOS および Android デバイスをリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="91afe-117">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="91afe-118">Microsoft Intune には、リモート ロック機能とパスコードのリセット機能あります。</span><span class="sxs-lookup"><span data-stu-id="91afe-118">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="91afe-119">ユーザーがデバイスを紛失した場合は、デバイスをリモートからロックできます。</span><span class="sxs-lookup"><span data-stu-id="91afe-119">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="91afe-120">他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。</span><span class="sxs-lookup"><span data-stu-id="91afe-120">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="91afe-121">IOS または Android デバイスをリモートでロックするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="91afe-121">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="91afe-122">[https://portal.azure.com](https://portal.azure.com)全体管理者アカウントの資格情報を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="91afe-122">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="91afe-123">ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91afe-123">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="91afe-124">[ **デバイス > すべてのデバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91afe-124">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="91afe-125">デバイスの一覧で、iOS または Android デバイスをクリックし、[ **リモートロック** ] アクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91afe-125">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="91afe-126">パスコードをリモートからリセットするには、</span><span class="sxs-lookup"><span data-stu-id="91afe-126">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="91afe-127">必要に応じて、 [https://portal.azure.com](https://portal.azure.com) 全体管理者アカウントの資格情報を使用して Azure portal にサインインします。</span><span class="sxs-lookup"><span data-stu-id="91afe-127">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="91afe-128">ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91afe-128">On the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
3. <span data-ttu-id="91afe-129">[ **デバイス > すべてのデバイス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91afe-129">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="91afe-130">管理するデバイスのリストから、iOS または Android デバイスをクリックし、[...] を選択し **ます。詳細を参照**してください。</span><span class="sxs-lookup"><span data-stu-id="91afe-130">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="91afe-131">次に、[ **パスコード** デバイスのリモートアクションの削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91afe-131">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="91afe-132">その他の実験については、「 [使用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="91afe-132">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="91afe-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="91afe-133">Next step</span></span>

<span data-ttu-id="91afe-134">テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="91afe-134">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="91afe-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="91afe-135">See Also</span></span>

[<span data-ttu-id="91afe-136">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="91afe-136">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="91afe-137">Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="91afe-137">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="91afe-138">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="91afe-138">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

