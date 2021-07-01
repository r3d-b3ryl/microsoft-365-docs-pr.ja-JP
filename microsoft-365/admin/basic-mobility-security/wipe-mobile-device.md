---
title: Basic Mobility and Security でモバイル デバイスをワイプする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 組み込みの Basic Mobility and Security を使用して、登録済みデバイスから情報を削除します。
ms.openlocfilehash: c3cc547ce5e135ccdabf9a09b0d572f1b2530f47
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228149"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="ccf8f-103">Basic Mobility and Security でモバイル デバイスをワイプする</span><span class="sxs-lookup"><span data-stu-id="ccf8f-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="ccf8f-104">Microsoft 365 の組み込みの Basic Mobility and Security を使用して、組織情報のみを削除したり、出荷時のリセットを実行してモバイル デバイスからすべての情報を削除し、工場出荷時の設定に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ccf8f-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="ccf8f-105">Before you begin</span></span>

<span data-ttu-id="ccf8f-106">モバイル デバイスは、機密性の高い組織情報を保存し、組織のリソースにアクセスMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="ccf8f-107">組織の情報を保護するために、出荷時のリセットまたは会社データの削除を行います。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="ccf8f-108">**出荷時の** リセット: インストールされているアプリケーション、写真、個人情報など、ユーザーのモバイル デバイス上のすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="ccf8f-109">ワイプが完了すると、デバイスは工場出荷時の設定に復元されます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="ccf8f-110">**会社のデータを削除** する: 組織データのみを削除し、ユーザーのモバイル デバイスにインストールされているアプリケーション、写真、および個人情報を残します。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="ccf8f-111">**デバイスがワイプされると (出荷** 時のリセットまたは会社のデータの削除)、デバイスは管理対象デバイスの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="ccf8f-112">**デバイスを自動的** にリセットする: ユーザーがデバイス パスワードを特定の回数入力しようとして失敗した後、デバイスを自動的に出荷時にリセットする Basic Mobility and Security ポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="ccf8f-113">これを行うには、「基本モビリティとセキュリティでデバイス セキュリティ ポリシーを [作成する」の手順に従います](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="ccf8f-114">**デバイスをワイプするときにユーザー エクスペリエンス** を知りたい場合は、「ユーザーとデバイスの影響   [について」を参照してください](#whats-the-user-and-device-impact)。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="ccf8f-115">モバイル デバイスをワイプする</span><span class="sxs-lookup"><span data-stu-id="ccf8f-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="ccf8f-116">[ファイル] に移動 [Microsoft 365 管理センター。](../../admin/admin-overview/about-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="ccf8f-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="ccf8f-117">[モバイル デバイスの管理] を検索フィールドに入力し、結果の一覧から [モバイル デバイス **の管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本モビリティと Secruity モバイル デバイス管理オプション":::

3. <span data-ttu-id="ccf8f-119">[デバイス **の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="ccf8f-120">ワイプを実行するデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="ccf8f-121">[管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-121">Select **Manage**.</span></span>

6. <span data-ttu-id="ccf8f-122">実行するリモートワイプのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="ccf8f-123">フル ワイプを実行し、デバイスを工場出荷時の設定に復元するには、[出荷時のリセット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="ccf8f-124">組織情報のみを選択的にワイプして削除するには、[Microsoft 365削除]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="ccf8f-125">組織からデバイスを削除するには、[デバイスの削除] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="ccf8f-126">[**はい**] を選択して確認します。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="ccf8f-127">どのように機能したのか?</span><span class="sxs-lookup"><span data-stu-id="ccf8f-127">How do I know it worked?</span></span>

<span data-ttu-id="ccf8f-128">管理対象デバイスの一覧にモバイル デバイスが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="ccf8f-129">デバイスをワイプする理由</span><span class="sxs-lookup"><span data-stu-id="ccf8f-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="ccf8f-130">次の理由でデバイスをワイプします。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="ccf8f-131">スマートフォンやタブレットなどのモバイル デバイスは、多くの場合、フル機能になりつつある。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="ccf8f-132">つまり、ユーザーは、個人識別や機密通信などの機密情報を保存し、移動中にアクセスする方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="ccf8f-133">これらのモバイル デバイスの 1 つが紛失または盗難に遭った場合、デバイスをワイプすると、組織の情報が間違った手で終わるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="ccf8f-134">ユーザーが Basic Mobility and Security に登録されている個人用デバイスを使用して組織を離れる場合、工場出荷時の状態にリセットを実行することで、組織の情報がユーザーと一緒に行かされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="ccf8f-135">組織がユーザーにモバイル デバイスを提供している場合は、デバイスを一度に再割り当てする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="ccf8f-136">デバイスを新しいユーザーに割り当てる前にデバイスで出荷時のリセットを実行すると、以前の所有者からの機密情報が確実に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="ccf8f-137">ユーザーとデバイスに与える影響</span><span class="sxs-lookup"><span data-stu-id="ccf8f-137">What's the user and device impact?</span></span>

<span data-ttu-id="ccf8f-138">ワイプはモバイル デバイスに直ちに送信され、デバイスは Azure Active Directory で非準拠としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="ccf8f-139">デバイスが出荷時の既定値にリセットされると、すべてのデータが削除されます。次の表は、デバイスが会社のデータを削除するときにデバイスの種類ごとに削除されるコンテンツを示しています。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="ccf8f-140">**コンテンツへの影響**</span><span class="sxs-lookup"><span data-stu-id="ccf8f-140">**Content impact**</span></span>|<span data-ttu-id="ccf8f-141">**iOS 10 以降**</span><span class="sxs-lookup"><span data-stu-id="ccf8f-141">**iOS 10 and later**</span></span>|<span data-ttu-id="ccf8f-142">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="ccf8f-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ccf8f-143">Microsoft 365 Intune アプリ保護ポリシーでデバイスが保護されている場合、アプリ データはワイプされます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="ccf8f-144">アプリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-144">The apps aren't removed.</span></span> <span data-ttu-id="ccf8f-145">モバイル アプリケーション管理 (MAM) ポリシーで保護されていないデバイスの場合、OutlookとOneDriveデータは削除されません。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="ccf8f-146">**メモ** Intune アプリ保護ポリシーを適用するには、Intune ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="ccf8f-147">はい</span><span class="sxs-lookup"><span data-stu-id="ccf8f-147">Yes</span></span>|<span data-ttu-id="ccf8f-148">はい</span><span class="sxs-lookup"><span data-stu-id="ccf8f-148">Yes</span></span>|
|<span data-ttu-id="ccf8f-149">Basic Mobility と Security によってデバイスに適用されるポリシー設定は適用されなくなりました。ユーザーは設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="ccf8f-150">はい</span><span class="sxs-lookup"><span data-stu-id="ccf8f-150">Yes</span></span>|<span data-ttu-id="ccf8f-151">はい</span><span class="sxs-lookup"><span data-stu-id="ccf8f-151">Yes</span></span>|
|<span data-ttu-id="ccf8f-152">Basic Mobility and Security によって作成されたメール プロファイルが削除され、デバイス上のキャッシュされたメールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="ccf8f-153">はい</span><span class="sxs-lookup"><span data-stu-id="ccf8f-153">Yes</span></span>|<span data-ttu-id="ccf8f-154">該当なし</span><span class="sxs-lookup"><span data-stu-id="ccf8f-154">N/A</span></span>|

> [!NOTE]
> <span data-ttu-id="ccf8f-155">ポータル サイトアプリは、iOS 用アプリ ストアと Android デバイス向け Play ストアで利用できます。</span><span class="sxs-lookup"><span data-stu-id="ccf8f-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
