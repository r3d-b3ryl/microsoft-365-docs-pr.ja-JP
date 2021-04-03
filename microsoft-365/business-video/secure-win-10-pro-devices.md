---
title: Microsoft 365 Business Premium を使用して Windows 10 Pro デバイス ポリシーを管理する
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
description: Microsoft 365 Business Premium を使用して Windows 10 Pro デバイス ポリシーを管理する方法について説明します。
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578689"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="e587e-103">Windows 10 Pro デバイス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="e587e-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="e587e-104">Microsoft 365 Business を使用して、Windows 10 デバイスWindows Defenderウイルス対策がアクティブ化され、Microsoft の更新プログラムがユーザーのデバイスに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="e587e-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="e587e-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="e587e-105">Try it!</span></span>

1. <span data-ttu-id="e587e-106">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e587e-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="e587e-107">[ポリシー **] で、[** ポリシーの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e587e-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="e587e-108">[ポリシーの **追加] ウィンドウ** で、[ポリシー名] に名前を入力し、[ポリシーの種類] の **[Windows 10 デバイス構成]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e587e-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="e587e-109">[Windows **10 デバイスのセキュリティ保護] を選択** して、サブ設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="e587e-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="e587e-110">ウイルス対策を **使用して PC** をウイルスやその他の脅威から保護Windows Defender Windows **10** デバイスを自動的に最新の状態に保つ] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e587e-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="e587e-111">[**これらの設定を取得するユーザー]** で、すべてのユーザーが既定で選択されますが、[変更] を選択して、作成したセキュリティ グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e587e-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="e587e-112">ポリシーの作成を完了するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e587e-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="e587e-113">[ポリシーの **追加] ページで** 、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e587e-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="e587e-114">管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー]ページでポリシーを確認して、新しいポリシーが **追加されたと確認** します。</span><span class="sxs-lookup"><span data-stu-id="e587e-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="e587e-115">ポリシーが有効に設定されたと確認するには、ユーザーの Windows 10 デバイスで[Windows Update]に移動し、[詳細設定] を選択し、設定が灰色で表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="e587e-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="e587e-116">次に、[更新プログラムの配信方法を選択する] をクリックし、設定がグレー表示され、次のメッセージが表示されます。一部の設定は非表示または組織によって **管理されます**。</span><span class="sxs-lookup"><span data-stu-id="e587e-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

