---
title: Microsoft 365 Business Premium を使った Windows 10 Pro デバイス ポリシーの管理
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
description: Microsoft 365 Business Premium で Windows 10 Pro デバイス ポリシーを管理する方法について説明します。
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703189"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="18ef5-103">Windows 10 Pro デバイス ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="18ef5-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="18ef5-104">Microsoft 365 Business を使用すると、Windows 10 デバイスで Windows Defender ウイルス対策がアクティブ化され、Microsoft の更新プログラムがユーザーのデバイスに自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="18ef5-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="18ef5-105">演習</span><span class="sxs-lookup"><span data-stu-id="18ef5-105">Try it!</span></span>

1. <span data-ttu-id="18ef5-106">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="18ef5-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="18ef5-107">[ **ポリシー] で、[** ポリシーの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18ef5-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="18ef5-108">[ポリシー **の追加] ウィンドウ** で、[ポリシー名] に名前を入力し、[ポリシーの種類] で **[Windows 10 デバイスの構成**]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="18ef5-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="18ef5-109">[ **セキュリティで保護された Windows 10 デバイス] を選択** して、サブ設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="18ef5-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="18ef5-110">**Windows Defender** ウイルス対策を使用して PC をウイルスやその他の脅威から保護し **、Windows 10** デバイスを自動的に最新の状態に保つ方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="18ef5-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="18ef5-111">[**これらの設定を取得する** ユーザー] では、既定ですべてのユーザーが選択されますが、[変更] を選択して作成したセキュリティ グループを選択できます。</span><span class="sxs-lookup"><span data-stu-id="18ef5-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="18ef5-112">ポリシーの作成を完了するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="18ef5-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="18ef5-113">[ポリシーの **追加] ページで** 、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="18ef5-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="18ef5-114">管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー]ページでポリシーを確認して、新しいポリシーが追加された **のを確認** します。</span><span class="sxs-lookup"><span data-stu-id="18ef5-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="18ef5-115">ポリシーが有効にされたのを確認するには、ユーザーの Windows 10 デバイスで Windows Updateに移動し、[詳細オプション] を選択して、設定が灰色表示に表示されます。</span><span class="sxs-lookup"><span data-stu-id="18ef5-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="18ef5-116">次に、[更新プログラムの配信方法の選択] をクリックし、設定が灰色表示され、組織によって一部の設定が非表示または管理されているというメッセージが **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="18ef5-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

