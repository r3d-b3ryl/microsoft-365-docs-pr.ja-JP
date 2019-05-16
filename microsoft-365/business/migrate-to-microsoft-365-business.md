---
title: Office 365 Business Premium からの Microsoft 365 Business への移行
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business にビジネスを移行する方法について説明します。
ms.openlocfilehash: e4bb18904355663f9f26f58a3fd3aaf7420e5378
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072742"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="36add-103">Office 365 Business Premium からの Microsoft 365 Business への移行</span><span class="sxs-lookup"><span data-stu-id="36add-103">Migrate to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="36add-104">一般法人向け Office 365 サブスクリプション (Office 365 Business Premium など) が既にインストールされている場合は、ライセンスを Microsoft 365 Business に簡単に追加して、それらを一部またはすべてのユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="36add-104">If you already have an Office 365 for business subscription, for example, Office 365 Business Premium, you can easily add licenses to Microsoft 365 Business, and assign them to some, or all users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36add-105">[[プランの切り替え](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton)] ボタンを使用して、Microsoft 365 Business へのアップグレードを完了することはできません。</span><span class="sxs-lookup"><span data-stu-id="36add-105">You can't use the [Switch plans](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) button to upgrade to Microsoft 365 Business yet.</span></span> 
  
## <a name="add-microsoft-365-business-licenses"></a><span data-ttu-id="36add-106">Microsoft 365 Business のライセンスを追加する</span><span class="sxs-lookup"><span data-stu-id="36add-106">Add Microsoft 365 Business licenses</span></span>

<span data-ttu-id="36add-107">Microsoft 365 Business を入手する方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="36add-107">You have two ways to get Microsoft 365 Business.</span></span> <span data-ttu-id="36add-108">パートナーがいる場合は、microsoft[パートナーセンター](get-microsoft-365-business.md)から Microsoft 365 Business を購入することができます。</span><span class="sxs-lookup"><span data-stu-id="36add-108">If you have a partner, he or she can purchase Microsoft 365 Business for you from [Microsoft Partner Center](get-microsoft-365-business.md).</span></span> <span data-ttu-id="36add-109">パートナーは、Microsoft 365 Business への移行を支援することもできます。</span><span class="sxs-lookup"><span data-stu-id="36add-109">Your partner can also help you transition to Microsoft 365 Business.</span></span>
  
<span data-ttu-id="36add-110">独自のサブスクリプションを管理する場合は、Microsoft 365 Business ライセンスを購入するために[sales に連絡](https://www.microsoft.com/microsoft-365/business)することができます。</span><span class="sxs-lookup"><span data-stu-id="36add-110">If you manage your own subscription, you can [contact sales](https://www.microsoft.com/microsoft-365/business) to purchase Microsoft 365 Business licenses.</span></span> 
  
<span data-ttu-id="36add-111">パートナーとの作業を開始する方法については、「[サブスクリプションアドバイザーパートナーを追加、変更、または削除](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36add-111">See [Add, change, or delete a subscription advisor partner](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) to find out how you can start working with a partner.</span></span> 
  
<span data-ttu-id="36add-112">ライセンスを購入するためのリンクが提供されている場合は、次のようなウィザードを順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="36add-112">If you are given a link to purchase your licences, you will walk through a wizard like the one below.</span></span> <span data-ttu-id="36add-113">[**はい、アカウントに追加**します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-113">Choose **Yes, add it to my account**.</span></span> <span data-ttu-id="36add-114">ライセンスの数と支払方法を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="36add-114">You can also pick the number of licences and the method of payment.</span></span>
  
![Microsoft 365 Business の直接購入リンクで、現在のアカウントに追加するか、新しいアカウントにサインアップします。](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a><span data-ttu-id="36add-116">Microsoft 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="36add-116">Assign Microsoft 365 licenses</span></span>

1. <span data-ttu-id="36add-117">新しいライセンスを購入すると、これが初めての場合は、Microsoft 365 Business のセットアップバナーが管理センターの一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="36add-117">Once you have purchased new licenses, and this is the first time you did, the setup banner for Microsoft 365 Business will display on top of the admin center.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36add-118">セットアップバナーは新しいユーザーを追加し、新しいドメインを追加して、新しいユーザーのメールを移行する機会です。</span><span class="sxs-lookup"><span data-stu-id="36add-118">The setup banner is an opportunity to add new users, a new domain, and migrate email for new users.</span></span> <span data-ttu-id="36add-119">この操作を行わない場合でも、ウィザードを使用して [既定のオプション] を選択し、管理者のホームページから非表示にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36add-119">If you don't plan to do any, you should still go through the wizard and choose default options to make it disappear from the admin home page.</span></span> 
  
   ![Microsoft 365 Business で [セットアップの開始] を選択して、バナーをセットアップする準備ができました。](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    <span data-ttu-id="36add-121">[ **セットアップの開始**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36add-121">Choose **Start setup**.</span></span>
    
2. <span data-ttu-id="36add-122">[**サインインとメールのカスタマイズ**] ページで、この機会を使用してサブスクリプションに別のドメインを追加する場合は、[**既に所有し**ているドメインの接続] を選択してドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="36add-122">On the **Personalize your sign-in and email** page, you can add a domain by choosing **Connect a domain you already own** if you want to use this opportunity to add another domain to your subscription.</span></span> 
    
    <span data-ttu-id="36add-123">既にドメインを設定している場合は、2番目のフィールドには、**メールの**_ドメイン名_\> **を使用し続けて** \<サインインするように指示します。  </span><span class="sxs-lookup"><span data-stu-id="36add-123">If you have already set up a domain, the second field will indicate that and will say **Continue using** \<  _your domain name_\> **for email and signing in**.</span></span> <span data-ttu-id="36add-124">サブスクリプションを使用してドメインをセットアップしていない場合は **、引き続き** \<_会社の name.onmicrosoft.com_ \>を使用して**電子メールを送信**し、サインインしてください。  </span><span class="sxs-lookup"><span data-stu-id="36add-124">If you haven't set up a domain with you subscription, it will say **Continue using** \<  _your company name.onmicrosoft.com_\> **for email and signing in**.</span></span>
    
    <span data-ttu-id="36add-125">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-125">Choose **Next**.</span></span>
    
    ![[サインインとメールのカスタマイズ] ページで、ドメインを追加するか、使用しているドメインを使用するかを選択します。](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. <span data-ttu-id="36add-127">[新しい**ユーザーの追加**] ページで、新しいユーザーを追加することができます。これには、Microsoft 365 Business のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="36add-127">On the **Add new users** page, you can add new users, if you have new employees that you want to assign the Microsoft 365 Business licenses to.</span></span> 
    
    <span data-ttu-id="36add-128">新しい従業員を追加して、既存のユーザーにライセンスを割り当てる場合は、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-128">If you don't have new employees to add and want to assign licences to existing users, choose **Next**.</span></span>
    
4. <span data-ttu-id="36add-129">[\* \* 電子メールメッセージの移行 \* \*] ページで、手順3で追加した新しいユーザーのいずれかについて電子メールを移行することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="36add-129">On the \*\* Migrate email messages \*\* page you can choose to migrate email for any of the new users you added in step 3.</span></span> <span data-ttu-id="36add-130">この手順は省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="36add-130">You can skip this step also.</span></span> <span data-ttu-id="36add-131">**次へ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-131">Choose **Next**.</span></span>
    
5. <span data-ttu-id="36add-132">最後のページで [**管理センターに移動**します] を選択して、セットアップを続行します。</span><span class="sxs-lookup"><span data-stu-id="36add-132">On the last page, choose **go to the admin center**, and continue setup there.</span></span>
    
6. <span data-ttu-id="36add-133">管理センターで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="36add-133">In the admin center, go to **Users** \> **Active users**.</span></span>
    
7. <span data-ttu-id="36add-134">**Microsoft 365 Business** license を割り当てるユーザーを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-134">Select the user to whom you want to assign the **Microsoft 365 Business** license to, and then choose **Edit** next to **Product Licenses**.</span></span>
    
    ![ユーザーカードで、[製品ライセンス] の横にある [編集] を選択します。](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. <span data-ttu-id="36add-136">[**製品ライセンス**] で、 **Microsoft 365 Business**を **[** \> **保存**] にスライドし、を**閉じ**ます。</span><span class="sxs-lookup"><span data-stu-id="36add-136">In **Product licenses** slide **Microsoft 365 Business** to **On** \> **Save**, and then **Close**.</span></span>
    
<span data-ttu-id="36add-137">Microsoft 365 Business の初期ライセンスを購入すると、**請求** \> **書購入サービス**でさらに追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36add-137">Once you have purchased the initial license for Microsoft 365 Business, you can now also add more in **Billing** \> **Purchase services**.</span></span> <span data-ttu-id="36add-138">[**サービスを購入**する] ページで、 **Microsoft 365 の名刺**の省略記号をクリックし、[ライセンスの数量の**変更**] を選択してさらに購入することができます。</span><span class="sxs-lookup"><span data-stu-id="36add-138">On the **Purchase services** page you can click on the ellipses on the **Microsoft 365 Business** card, and choose **Change license quantity** to purchase more.</span></span> 
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="36add-139">ユーザーのデバイスとファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="36add-139">Protect user devices and files</span></span>

<span data-ttu-id="36add-140">Microsoft 365 Business にライセンスを割り当てたら、ユーザーのデバイスとファイルの保護を開始できます。</span><span class="sxs-lookup"><span data-stu-id="36add-140">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>
  
1. <span data-ttu-id="36add-141">管理センターの左側のナビゲーションで、[**デバイス** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="36add-141">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="36add-142">[**デバイスポリシー** ] ページで、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-142">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="36add-143">[**ポリシーの追加**] ウィンドウで、ポリシーの名前を指定し、ドロップダウンから**ポリシーの種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="36add-143">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="36add-144">Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="36add-144">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="36add-145">詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36add-145">See the following links for details:</span></span>
    
  - [<span data-ttu-id="36add-146">Android または iOS デバイスのアプリ保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="36add-146">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="36add-147">Windows 10 デバイスのアプリケーション保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="36add-147">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="36add-148">Windows 10 Pc のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="36add-148">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
   ![[ポリシーの追加] ウィンドウで、名前を入力し、ドロップダウンメニューからポリシーの種類を選択します。](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. <span data-ttu-id="36add-150">ポリシーを設定すると、従業員はデバイスをセットアップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="36add-150">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="36add-151">Windows Pro Creator の更新プログラムを適用していない場合は、windows pro Creator update に[アップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36add-151">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="36add-152">Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36add-152">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="36add-153">Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36add-153">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
    
5. <span data-ttu-id="36add-154">Office クライアントアプリを自動的にインストールするには、「 [Microsoft 365 Business による office クライアントの展開を準備](prepare-for-office-client-deployment.md)する」および「 [Windows 10 デバイスで Office を自動的にインストールまたはアンインストール](auto-install-or-uninstall-office.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36add-154">To automatically install Office client apps, see [Prepare for Office client deployment by Microsoft 365 Business](prepare-for-office-client-deployment.md) and [Automatically install or uninstall Office on Windows 10 devices](auto-install-or-uninstall-office.md).</span></span>
    


