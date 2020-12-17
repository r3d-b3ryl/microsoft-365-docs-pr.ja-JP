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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 安全な添付ファイルを管理する方法について学習します。
ms.openlocfilehash: ea1dc20b8e9e51701730a72b8e8194d2abbfac99
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702451"
---
# <a name="manage-safe-attachments"></a><span data-ttu-id="55527-103">安全な添付ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="55527-103">Manage safe attachments</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

<span data-ttu-id="55527-104">microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection と呼ばばがありました) は、Outlook、OneDrive、SharePoint、Teams に悪意のあるコンテンツが含まれているファイルからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="55527-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against files that contain malicious content in Outlook, OneDrive, SharePoint, and Teams.</span></span>

## <a name="try-it"></a><span data-ttu-id="55527-105">演習</span><span class="sxs-lookup"><span data-stu-id="55527-105">Try it!</span></span>

1. <span data-ttu-id="55527-106">管理センターに [移動し、[](https://admin.microsoft.com)セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="55527-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="55527-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="55527-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="55527-108">[表示 **]、[\*\*\*\*管理]、ATP** の [安全な **添付ファイル] の順に選択します**。</span><span class="sxs-lookup"><span data-stu-id="55527-108">Select **View**, **Manage**, and then **ATP safe attachments**.</span></span>
1. <span data-ttu-id="55527-109">安全な添付ファイルルールを選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="55527-109">Select your safe attachments rule, and then choose the **Edit** icon.</span></span>
1. <span data-ttu-id="55527-110">設定 **を選択** し、[ブロック] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="55527-110">Select **settings**, and then verify that Block is selected.</span></span>
1. <span data-ttu-id="55527-111">下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="55527-111">Scroll down.</span></span> <span data-ttu-id="55527-112">Choose **Enable redirect,** and enter your email address or the address of the person you want to review the blocked attachments.</span><span class="sxs-lookup"><span data-stu-id="55527-112">Choose **Enable redirect**, and enter your email address or the address of the person you want to review the blocked attachments.</span></span>
1. <span data-ttu-id="55527-113">Select **applied to,** and then select your domain name.</span><span class="sxs-lookup"><span data-stu-id="55527-113">Select **applied to**, and then select your domain name.</span></span>
1. <span data-ttu-id="55527-114">ルールを適用する追加のドメイン (onmicrosoft.com ドメインなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="55527-114">Choose any additional domains you own (such as your onmicrosoft.com domain) that you would like the rule applied to.</span></span> <span data-ttu-id="55527-115">[追加 **] を** 選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="55527-115">Select **add**, and then **OK**.</span></span>
1. <span data-ttu-id="55527-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55527-116">Select **Save**.</span></span>

<span data-ttu-id="55527-117">ATP の安全な添付ファイル ルールが更新されました。</span><span class="sxs-lookup"><span data-stu-id="55527-117">Your ATP safe attachments rule has been updated.</span></span>

<span data-ttu-id="55527-118">これで保護が強化されたので、Outlook、OneDrive、SharePoint、または Teams から悪意のあるファイルを開くことになります。</span><span class="sxs-lookup"><span data-stu-id="55527-118">Now that protection is in place, you won't be able to open a malicious file from Outlook, OneDrive, SharePoint, or Teams.</span></span> <span data-ttu-id="55527-119">影響を受けるファイルの横には赤い盾が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55527-119">Affected files will have red shields next to them.</span></span> <span data-ttu-id="55527-120">ブロックされたファイルを開くしようとすると、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55527-120">If someone attempts to open a blocked file, they'll receive a warning message.</span></span>

<span data-ttu-id="55527-121">ポリシーがしばらくの間適用された後、[レポート] ページにアクセスしてスキャンされた情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="55527-121">After your policy has been in place for a while, visit the Reports page to see what has been scanned.</span></span>