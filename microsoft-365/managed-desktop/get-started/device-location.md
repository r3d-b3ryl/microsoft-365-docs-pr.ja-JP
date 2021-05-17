---
title: Windows 10 の位置情報サービス
description: デバイスの位置情報Windowsを有効にする方法
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
# <a name="windows-10-location-service"></a><span data-ttu-id="ed3e2-104">Windows 10 の位置情報サービス</span><span class="sxs-lookup"><span data-stu-id="ed3e2-104">Windows 10 location service</span></span>

<span data-ttu-id="ed3e2-105">デバイスはMicrosoft マネージド デスクトップ自動パイロットを使用Windowsされます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="ed3e2-106">このプロセスでは、ユーザーとユーザーのAzure Active Directory管理Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="ed3e2-107">既定では、Windows 10が初めて有効になっている場合、この機能が "箱から出た" エクスペリエンス中にプライバシー設定で有効になっていない限り、Windows 10 位置情報サービスは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="ed3e2-108">これらの設定は、自動パイロット登録時に非表示Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ed3e2-109">Autopilot のセットアップ方法の詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="ed3e2-110">このため、Microsoft マネージド デスクトップデバイスはデバイスの場所を取得できません。これにより、タイム ゾーンなどの複数のWindows機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="ed3e2-111">位置情報サービスの詳細についてはWindows 10位置情報サービスとWindows 10[を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="ed3e2-112">位置情報サービスを使用してサービスに参加する必要はMicrosoft マネージド デスクトップ、ユーザー エクスペリエンスは制限されます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="ed3e2-113">たとえば、デバイスは、ユーザーが別のタイム ゾーンで作業するときに、自分のタイムゾーンを自動的に判断できません。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="ed3e2-114">位置情報サービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="ed3e2-114">Enable the location service</span></span>

<span data-ttu-id="ed3e2-115">デバイスを Microsoft マネージド デスクトップ サービスに登録するときに、位置情報サービスの使用をオプトインするか、登録後にサービスをオンまたはオフにできます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="ed3e2-116">登録中にオプトインする</span><span class="sxs-lookup"><span data-stu-id="ed3e2-116">Opt in during enrollment</span></span>

<span data-ttu-id="ed3e2-117">位置情報サービスを有効Microsoft マネージド デスクトップサービスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="ed3e2-118">登録シーケンス中に、デバイスで位置情報サービスを有効にするかどうかを選択Windows 10求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="ed3e2-119">登録後に位置情報サービスを制御する</span><span class="sxs-lookup"><span data-stu-id="ed3e2-119">Control the location service after enrollment</span></span>

<span data-ttu-id="ed3e2-120">管理ポータルからサポート要求を送信することで、いつでも位置情報サービスを有効 (または無効) [](../working-with-managed-desktop/admin-support.md) [にできます](access-admin-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="ed3e2-121">場所Microsoft マネージド デスクトップサービスを構成するWindows 10方法</span><span class="sxs-lookup"><span data-stu-id="ed3e2-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="ed3e2-122">位置情報サービスの使用をオプトインする場合、ユーザーのプライバシーに影響を与えることなく、必要な最小設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="ed3e2-123">詳細については、「位置情報サービス[Windows 10プライバシー」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="ed3e2-124">Microsoft マネージド デスクトップ **デバイスの場所** へのアクセスを許可するWindows **設定** で [場所のプライバシー]**設定を有効にします**。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="ed3e2-125">ユーザー インターフェイスは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="[場所の設定] Windows設定":::

> [!NOTE]
> <span data-ttu-id="ed3e2-127">位置情報サービスの使用をオプトインする場合、これはオペレーティング システム自体Windows適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="ed3e2-128">アプリは位置情報サービスを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="ed3e2-129">各ユーザーは、アプリが自分の場所にアクセスできるかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ed3e2-129">Each user can choose whether to allow apps to access their location.</span></span>