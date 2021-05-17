---
title: iOS の Office アプリをセキュリティで保護する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: アプリを使用して iOS Officeアプリをセキュリティで保護するMicrosoft 365 Business Premium。
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580464"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="c6dc3-103">iOS の Office アプリをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="c6dc3-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="c6dc3-104">モバイル ユーザーがサインインする PIN または指紋を入力する必要があるユーザー アクセス ポリシーを設定し、デバイスに保存されている作業ファイルも暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="c6dc3-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="c6dc3-105">Try it!</span></span>

1. <span data-ttu-id="c6dc3-106">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="c6dc3-107">[ポリシー **] で、[** ポリシーの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="c6dc3-108">[ポリシーの **追加] ウィンドウ** で、[ポリシー名] に名前を入力し、[ポリシーの種類] で必要なポリシーの種類 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="c6dc3-109">[ユーザーが **モバイル デバイス上のOfficeファイル** にアクセスする方法を管理する] をオンにし、次の 3 つの設定がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="c6dc3-110">**Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**</span><span class="sxs-lookup"><span data-stu-id="c6dc3-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="c6dc3-111">**デバイスが紛失または盗まれたときに作業ファイルを保護する**</span><span class="sxs-lookup"><span data-stu-id="c6dc3-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="c6dc3-112">**仕事用ファイルを暗号化する**</span><span class="sxs-lookup"><span data-stu-id="c6dc3-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="c6dc3-113">[**これらのアプリのファイルが保護されます]** で、モバイル Office保護するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="c6dc3-114">[Whoこれらの設定が表示されます **。** 既定ではすべてのユーザーが選択されますが、[変更] を選択して、作成したセキュリティ グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="c6dc3-115">ポリシーの作成を完了するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="c6dc3-116">[ポリシーの **追加] ページで** 、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="c6dc3-117">管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー]ページでポリシーを確認して、新しいポリシーが **追加されたと確認** します。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>