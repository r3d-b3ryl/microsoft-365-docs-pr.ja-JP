---
title: 基本的なモビリティとセキュリティでモバイルデバイスをワイプする
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
description: 組み込みの基本的なモビリティとセキュリティを使用して、登録されているデバイスから情報を削除します。
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336967"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="0c847-103">基本的なモビリティとセキュリティでモバイルデバイスをワイプする</span><span class="sxs-lookup"><span data-stu-id="0c847-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="0c847-104">Microsoft 365 の組み込みの基本的なモビリティとセキュリティを使用して、組織情報のみを削除したり、出荷時のリセットを実行してモバイルデバイスからすべての情報を削除したり、出荷時の設定に戻したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0c847-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0c847-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="0c847-105">Before you begin</span></span>

<span data-ttu-id="0c847-106">モバイルデバイスでは、機密の組織情報を格納し、組織の Microsoft 365 リソースへのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="0c847-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="0c847-107">組織の情報を保護するために、工場のリセットまたは会社のデータの削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0c847-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="0c847-108">**出荷時のリセット**: インストールされているアプリケーション、写真、個人情報など、ユーザーのモバイルデバイス上のすべてのデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="0c847-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="0c847-109">ワイプが完了すると、デバイスは出荷時の設定に復元されます。</span><span class="sxs-lookup"><span data-stu-id="0c847-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="0c847-110">**会社データの削除**: 組織データのみを削除し、インストールされているアプリケーション、写真、および個人情報をユーザーのモバイルデバイスに残します。</span><span class="sxs-lookup"><span data-stu-id="0c847-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="0c847-111">**デバイスがワイプされると (工場出荷時のリセットまたは会社データの削除)**、デバイスは管理対象デバイスのリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="0c847-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="0c847-112">**デバイスを自動的にリセット**する: ユーザーが特定の回数だけデバイスのパスワードを入力しようとして失敗した場合に、自動的に工場でリセットされる基本的なモビリティおよびセキュリティポリシーをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="0c847-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="0c847-113">これを行うには、「 [basic mobility and security でのデバイスセキュリティポリシーの作成](create-device-security-policies-in-basic-mmobility-and-security.md)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c847-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="0c847-114">デバイスをワイプするときの**ユーザーの利便性を知りたい場合**は、[  [ユーザーとデバイスの影響]](#whats-the-user-and-device-impact)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c847-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="0c847-115">モバイルデバイスをワイプする</span><span class="sxs-lookup"><span data-stu-id="0c847-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="0c847-116"> [Microsoft 365 管理センター](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)に移動します。</span><span class="sxs-lookup"><span data-stu-id="0c847-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="0c847-117">[検索] フィールドに「モバイルデバイスの管理」と入力し、結果の一覧から [ **モバイルデバイスの管理** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本的なモビリティと Secん。モバイルデバイス管理オプション":::

3. <span data-ttu-id="0c847-119">[ **デバイスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="0c847-120">ワイプを実行するデバイスを選びます。</span><span class="sxs-lookup"><span data-stu-id="0c847-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="0c847-121">[ **管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-121">Select **Manage**.</span></span>

6. <span data-ttu-id="0c847-122">実行するリモートワイプのタイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="0c847-123">完全なワイプを行い、デバイスを出荷時の設定に戻すには、[ **出荷時**の設定に戻す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="0c847-124">Microsoft 365 組織情報のみを選択して削除するには、[ **会社のデータを削除**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="0c847-125">組織からデバイスを削除するには、[ **デバイスの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c847-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="0c847-126">[**はい**] を選択して確認します。</span><span class="sxs-lookup"><span data-stu-id="0c847-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="0c847-127">動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0c847-127">How do I know it worked?</span></span>

<span data-ttu-id="0c847-128">管理対象デバイスの一覧にモバイルデバイスが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0c847-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="0c847-129">デバイスをワイプする理由</span><span class="sxs-lookup"><span data-stu-id="0c847-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="0c847-130">次の理由から、デバイスをワイプします。</span><span class="sxs-lookup"><span data-stu-id="0c847-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="0c847-131">スマートフォンやタブレットなどのモバイルデバイスは、常に完全に機能するようになりつつあります。</span><span class="sxs-lookup"><span data-stu-id="0c847-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="0c847-132">これは、ユーザーが個人情報や機密情報などの機密性の高い企業情報を保存して、外出先でアクセスするのが容易になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c847-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="0c847-133">これらのモバイルデバイスのいずれかが紛失または盗難にあった場合は、デバイスをワイプすることで、組織の情報が正しくない手で終わるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0c847-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="0c847-134">基本的なモビリティとセキュリティに登録されている個人デバイスをユーザーが組織から離れた場合、出荷時のリセットを実行することによって、組織の情報がそのユーザーとの通信を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="0c847-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="0c847-135">組織がモバイルデバイスをユーザーに提供している場合は、デバイスを随時再割り当てする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c847-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="0c847-136">デバイスを新しいユーザーに割り当てる前に工場でリセットを実行すると、以前の所有者からの機密情報がすべて削除されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0c847-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="0c847-137">ユーザーとデバイスに与える影響</span><span class="sxs-lookup"><span data-stu-id="0c847-137">What's the user and device impact?</span></span>

<span data-ttu-id="0c847-138">ワイプはすぐにモバイルデバイスに送信され、デバイスは Azure active directory に準拠していないとマークされます。</span><span class="sxs-lookup"><span data-stu-id="0c847-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="0c847-139">デバイスが出荷時の既定値にリセットされるときにすべてのデータが削除されますが、次の表では、会社のデータを削除するときにデバイスの種類ごとに削除されるコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0c847-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="0c847-140">**コンテンツ impace**</span><span class="sxs-lookup"><span data-stu-id="0c847-140">**Content impace**</span></span>|<span data-ttu-id="0c847-141">**iOS 10 以降**</span><span class="sxs-lookup"><span data-stu-id="0c847-141">**iOS 10 and later**</span></span>|<span data-ttu-id="0c847-142">**Android 5 以降**</span><span class="sxs-lookup"><span data-stu-id="0c847-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c847-143">Microsoft 365 アプリデータは、デバイスが Intune アプリ保護ポリシーによって保護されている場合はワイプされます。</span><span class="sxs-lookup"><span data-stu-id="0c847-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="0c847-144">アプリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="0c847-144">The apps aren't removed.</span></span> <span data-ttu-id="0c847-145">モバイルアプリケーション管理 (MAM) ポリシーによって保護されていないデバイスの場合、Outlook および OneDrive はキャッシュされたデータを削除しません。</span><span class="sxs-lookup"><span data-stu-id="0c847-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="0c847-146">**メモ** Intune アプリ保護ポリシーを適用するには、Intune ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0c847-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="0c847-147">はい</span><span class="sxs-lookup"><span data-stu-id="0c847-147">Yes</span></span>|<span data-ttu-id="0c847-148">はい</span><span class="sxs-lookup"><span data-stu-id="0c847-148">Yes</span></span>|
|<span data-ttu-id="0c847-149">基本的なモビリティおよびデバイスへのセキュリティによって適用されるポリシー設定は適用されなくなりました。ユーザーは、設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0c847-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="0c847-150">はい</span><span class="sxs-lookup"><span data-stu-id="0c847-150">Yes</span></span>|<span data-ttu-id="0c847-151">はい</span><span class="sxs-lookup"><span data-stu-id="0c847-151">Yes</span></span>|
|<span data-ttu-id="0c847-152">基本的なモビリティとセキュリティによって作成された電子メールプロファイルが削除され、デバイス上の電子メールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0c847-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="0c847-153">はい</span><span class="sxs-lookup"><span data-stu-id="0c847-153">Yes</span></span>|<span data-ttu-id="0c847-154">該当なし</span><span class="sxs-lookup"><span data-stu-id="0c847-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="0c847-155">会社のポータルアプリは、iOS 用アプリストアおよび Android 用の再生用ストアから入手できます。</span><span class="sxs-lookup"><span data-stu-id="0c847-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c847-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c847-156">Related topics</span></span>

[<span data-ttu-id="0c847-157">基本的なモビリティとセキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="0c847-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)