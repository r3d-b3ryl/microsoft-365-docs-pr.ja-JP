---
title: 安全な添付ファイルを管理する
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 安全な添付ファイルを管理する方法について学習します。
ms.openlocfilehash: 75146a05a091cf91a77ee3bc9bb63c813d84dce3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926104"
---
# <a name="manage-safe-attachments"></a><span data-ttu-id="a4c5f-103">安全な添付ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="a4c5f-103">Manage safe attachments</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

<span data-ttu-id="a4c5f-104">microsoft Defender for Office 365 (以前は Microsoft 365 ATP または Advanced Threat Protection と呼ばばがありました) は、Outlook、OneDrive、SharePoint、および Teams に悪意のあるコンテンツが含まれるファイルからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against files that contain malicious content in Outlook, OneDrive, SharePoint, and Teams.</span></span>

## <a name="try-it"></a><span data-ttu-id="a4c5f-105">演習</span><span class="sxs-lookup"><span data-stu-id="a4c5f-105">Try it!</span></span>

1. <span data-ttu-id="a4c5f-106">管理センターに [移動し、[](https://admin.microsoft.com)セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="a4c5f-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="a4c5f-108">[表示 **]、[\*\*\*\*管理]、ATP** の [安全な **添付ファイル] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-108">Select **View**, **Manage**, and then **ATP safe attachments**.</span></span>
1. <span data-ttu-id="a4c5f-109">安全な添付ファイルルールを選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-109">Select your safe attachments rule, and then choose the **Edit** icon.</span></span>
1. <span data-ttu-id="a4c5f-110">設定 **を選択** し、[ブロック] が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-110">Select **settings**, and then verify that Block is selected.</span></span>
1. <span data-ttu-id="a4c5f-111">下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-111">Scroll down.</span></span> <span data-ttu-id="a4c5f-112">Choose **Enable redirect,** and enter your email address or the address of the person you want to review the blocked attachments.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-112">Choose **Enable redirect**, and enter your email address or the address of the person you want to review the blocked attachments.</span></span>
1. <span data-ttu-id="a4c5f-113">Select **applied to,** and then select your domain name.</span><span class="sxs-lookup"><span data-stu-id="a4c5f-113">Select **applied to**, and then select your domain name.</span></span>
1. <span data-ttu-id="a4c5f-114">ルールを適用する追加のドメイン (onmicrosoft.com ドメインなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-114">Choose any additional domains you own (such as your onmicrosoft.com domain) that you would like the rule applied to.</span></span> <span data-ttu-id="a4c5f-115">[追加 **] を** 選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-115">Select **add**, and then **OK**.</span></span>
1. <span data-ttu-id="a4c5f-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-116">Select **Save**.</span></span>

<span data-ttu-id="a4c5f-117">ATP の安全添付ファイル ルールが更新されました。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-117">Your ATP safe attachments rule has been updated.</span></span>

<span data-ttu-id="a4c5f-118">これで保護が強化されたので、Outlook、OneDrive、SharePoint、または Teams から悪意のあるファイルを開くことになります。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-118">Now that protection is in place, you won't be able to open a malicious file from Outlook, OneDrive, SharePoint, or Teams.</span></span> <span data-ttu-id="a4c5f-119">影響を受けるファイルの横には赤い盾が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-119">Affected files will have red shields next to them.</span></span> <span data-ttu-id="a4c5f-120">ブロックされたファイルを開くしようとすると、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-120">If someone attempts to open a blocked file, they'll receive a warning message.</span></span>

<span data-ttu-id="a4c5f-121">ポリシーがしばらくの間適用された後、[レポート] ページにアクセスしてスキャンされた情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a4c5f-121">After your policy has been in place for a while, visit the Reports page to see what has been scanned.</span></span>