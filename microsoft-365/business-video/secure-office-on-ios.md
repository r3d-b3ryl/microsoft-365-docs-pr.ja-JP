---
title: iOS Officeアプリのセキュリティ保護
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Microsoft 365 Business Premium Officeアプリをセキュリティで保護する方法について説明します。
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702651"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="98a43-103">iOS Officeアプリのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="98a43-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="98a43-104">サインインするためにモバイル ユーザーが PIN または指紋を入力する必要があるユーザー アクセス ポリシーを設定したり、デバイスに保存されている作業ファイルを暗号化したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="98a43-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="98a43-105">演習</span><span class="sxs-lookup"><span data-stu-id="98a43-105">Try it!</span></span>

1. <span data-ttu-id="98a43-106">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="98a43-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="98a43-107">[ **ポリシー] で、[** ポリシーの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98a43-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="98a43-108">[ポリシー **の追加]** ウィンドウで、[ポリシー名] に名前を入力し、[ポリシーの種類] で必要なポリシーの種類 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98a43-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="98a43-109">ユーザーが **モバイル デバイス上のファイルにOfficeする** 方法を管理するをオンにし、次の 3 つの設定がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="98a43-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="98a43-110">**Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**</span><span class="sxs-lookup"><span data-stu-id="98a43-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="98a43-111">**デバイスの紛失時や盗難時に作業ファイルを保護する**</span><span class="sxs-lookup"><span data-stu-id="98a43-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="98a43-112">**仕事用ファイルを暗号化する**</span><span class="sxs-lookup"><span data-stu-id="98a43-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="98a43-113">[ **これらのアプリのファイルが** 保護されます] で、モバイル Office保護するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="98a43-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="98a43-114">[**これらの設定を取得する** ユーザー] では、既定ですべてのユーザーが選択されますが、[変更] を選択して作成したセキュリティ グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="98a43-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="98a43-115">ポリシーの作成を完了するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98a43-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="98a43-116">[ポリシーの **追加] ページで** 、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98a43-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="98a43-117">管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー]ページでポリシーを確認して、新しいポリシーが追加された **のを確認** します。</span><span class="sxs-lookup"><span data-stu-id="98a43-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>