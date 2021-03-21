---
title: Windows 10 位置情報サービス
description: デバイスで Windows 位置情報サービスを有効にする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929502"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="4e227-104">Windows 10 位置情報サービス</span><span class="sxs-lookup"><span data-stu-id="4e227-104">Windows 10 location service</span></span>

<span data-ttu-id="4e227-105">Microsoft Managed Desktop のデバイスは、Windows Autopilot を使用して登録されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="4e227-106">このプロセスでは、Azure Active Directory と Microsoft Intune を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="4e227-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="4e227-107">既定では、Windows 10 の位置情報サービスは、デバイスが初めて有効になっているときに無効になります。この機能が "箱から出た" エクスペリエンス中にプライバシー設定で有効になっていない限りです。</span><span class="sxs-lookup"><span data-stu-id="4e227-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="4e227-108">これらの設定は、Microsoft Managed Desktop での自動パイロット登録中に非表示になります。</span><span class="sxs-lookup"><span data-stu-id="4e227-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="4e227-109">Autopilot のセットアップ方法の詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="4e227-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="4e227-110">このため、Microsoft Managed Desktop デバイスはデバイスの場所を取得できません。これにより、タイム ゾーンなど、いくつかの Windows 機能の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="4e227-111">Windows 10 位置情報サービスの詳細については [、「Windows 10 location Service and privacy」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="4e227-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="4e227-112">Microsoft Managed Desktop に参加するために位置情報サービスを使用する必要は一方で、ユーザー エクスペリエンスは制限されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="4e227-113">たとえば、デバイスは、ユーザーが別のタイム ゾーンで作業するときに、自分のタイムゾーンを自動的に判断できません。</span><span class="sxs-lookup"><span data-stu-id="4e227-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="4e227-114">位置情報サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="4e227-114">Enable the location service</span></span>

<span data-ttu-id="4e227-115">デバイスを Microsoft Managed Desktop サービスに登録するときに、位置情報サービスの使用をオプトインするか、登録後にサービスをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="4e227-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="4e227-116">登録中にオプトインする</span><span class="sxs-lookup"><span data-stu-id="4e227-116">Opt in during enrollment</span></span>

<span data-ttu-id="4e227-117">Microsoft Managed Desktop サービスで位置情報サービスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4e227-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="4e227-118">登録シーケンス中に、Windows 10 の位置情報サービスをデバイスで有効にするかどうかを選択するかどうかを選択するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="4e227-119">登録後に位置情報サービスを制御する</span><span class="sxs-lookup"><span data-stu-id="4e227-119">Control the location service after enrollment</span></span>

<span data-ttu-id="4e227-120">管理ポータルからサポート要求を送信することで、いつでも位置情報サービスを有効 (または無効) [](../working-with-managed-desktop/admin-support.md) [にできます](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="4e227-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="4e227-121">Microsoft Managed Desktop が Windows 10 の場所サービスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="4e227-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="4e227-122">位置情報サービスの使用をオプトインする場合、ユーザーのプライバシーに影響を与えることなく、必要な最小設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e227-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="4e227-123">詳細については [、「Windows 10 Location Service and privacy」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="4e227-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="4e227-124">Microsoft Managed Desktop では **、Windows** 設定の **[場所の** プライバシー設定] を [このデバイス上の場所へのアクセスを許可 **する] を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="4e227-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="4e227-125">ユーザー インターフェイスは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Windows 設定の場所の設定":::

> [!NOTE]
> <span data-ttu-id="4e227-127">位置情報サービスの使用をオプトインする場合、これは Windows オペレーティング システム自体にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e227-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="4e227-128">アプリは位置情報サービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e227-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="4e227-129">各ユーザーは、アプリが自分の場所にアクセスできるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4e227-129">Each user can choose whether to allow apps to access their location.</span></span>