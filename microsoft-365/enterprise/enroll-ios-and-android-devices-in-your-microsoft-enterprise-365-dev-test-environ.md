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
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Microsoft 365 テスト環境でデバイスを登録し、それらをリモートで管理するには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869136"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e7144-103">Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="e7144-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e7144-104">によって、この資料に記載されている手順に従うことができます登録し、iOS および Android デバイス用の基本的なモバイル デバイス管理機能を Microsoft 365 エンタープライズ テスト環境でテストします。</span><span class="sxs-lookup"><span data-stu-id="e7144-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="e7144-106">[ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e7144-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e7144-107">フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。</span><span class="sxs-lookup"><span data-stu-id="e7144-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e7144-108">最小要件で軽量な方法で iOS および Android のデバイスを登録する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7144-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e7144-109">シミュレートされた企業であっを登録する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7144-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7144-p101">ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。</span><span class="sxs-lookup"><span data-stu-id="e7144-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="e7144-112">フェーズ 2: iOS および Android デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e7144-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="e7144-113">指示を使用して、最初に、[をインストールし、会社のポータル アプリケーションにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)、テスト環境を Microsoft Intune 会社のポータル アプリケーションをカスタマイズするのには。</span><span class="sxs-lookup"><span data-stu-id="e7144-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="e7144-114">次に、手順を使用[、会社のリソースへのアクセス権を設定](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)iOS デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e7144-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="e7144-115">次に、手順を使用[Intune に Android デバイスの登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)Android のデバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="e7144-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="e7144-116">フェーズ 3: は、iOS および Android のデバイスをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="e7144-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="e7144-p102">Microsoft Intune では、リモート ロックとパスコードの両方のリセット機能を提供します。他のユーザーを失った場合、デバイス、デバイスをリモートでロックできます。パスコードを忘れてしまった人の場合リモートでリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7144-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="e7144-120">IOS または Android デバイスをリモートでロック。</span><span class="sxs-lookup"><span data-stu-id="e7144-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="e7144-121">Azure ポータルにサインインするのに[https://portal.azure.com](https://portal.azure.com)のグローバル管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7144-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="e7144-122">**すべてのサービス**をクリックして、 **Intune**を入力し、 **Intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7144-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="e7144-123">クリックして**デバイス > のすべてのデバイス**。</span><span class="sxs-lookup"><span data-stu-id="e7144-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="e7144-124">デバイスの一覧で、iOS または Android デバイスをクリック**リモート ロック**の動作です。</span><span class="sxs-lookup"><span data-stu-id="e7144-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="e7144-125">パスコードをリモートからリセットするには、</span><span class="sxs-lookup"><span data-stu-id="e7144-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="e7144-126">必要な場合がある Azure ポータルにサインイン[https://portal.azure.com](https://portal.azure.com)のグローバル管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7144-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="e7144-127">**すべてのサービス**をクリックして、 **Intune**を入力し、 **Intune**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7144-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="e7144-128">クリックして**デバイス > のすべてのデバイス**。</span><span class="sxs-lookup"><span data-stu-id="e7144-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="e7144-p103">デバイスの一覧から管理、iOS または Android デバイスをクリックして**を選択.詳細**。**パスコードを削除する**デバイスのリモート操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7144-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="e7144-131">追加の実験を行うには、[利用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7144-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="e7144-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7144-132">Next step</span></span>

<span data-ttu-id="e7144-133">[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7144-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7144-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7144-134">See Also</span></span>

[<span data-ttu-id="e7144-135">Microsoft 365 Enterprise のテスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e7144-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="e7144-136">Microsoft 365 企業のコンプライアンス ポリシーをデバイスのテスト環境</span><span class="sxs-lookup"><span data-stu-id="e7144-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="e7144-137">Microsoft 365 Enterprise を展開する</span><span class="sxs-lookup"><span data-stu-id="e7144-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e7144-138">エンタープライズ モビリティとセキュリティ (EMS)</span><span class="sxs-lookup"><span data-stu-id="e7144-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
