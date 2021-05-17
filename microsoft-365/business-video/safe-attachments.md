---
title: 安全な添付ファイルを管理する
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 安全な添付ファイルを管理する方法について学習します。
ms.openlocfilehash: 9afbdef2c7b400cf0bee5ae1e1ac3a9de6588cb8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578713"
---
# <a name="manage-safe-attachments"></a><span data-ttu-id="06fa3-103">安全な添付ファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="06fa3-103">Manage safe attachments</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

<span data-ttu-id="06fa3-104">microsoft Defender for Office 365 (以前は Microsoft 365 ATP、または Advanced Threat Protection) は、Outlook、OneDrive、SharePoint、および Teams の悪意のあるコンテンツを含むファイルからビジネスを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="06fa3-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against files that contain malicious content in Outlook, OneDrive, SharePoint, and Teams.</span></span>

## <a name="try-it"></a><span data-ttu-id="06fa3-105">お試しください!</span><span class="sxs-lookup"><span data-stu-id="06fa3-105">Try it!</span></span>

1. <span data-ttu-id="06fa3-106">管理センターに移動 [し、[セットアップ](https://admin.microsoft.com)] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="06fa3-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="06fa3-107">下にスクロールして **高度な脅威からの保護を強化します**。</span><span class="sxs-lookup"><span data-stu-id="06fa3-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="06fa3-108">[表示 **] 、[\*\*\*\*管理] の順** に選択し **、[ATP の安全な添付ファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="06fa3-108">Select **View**, **Manage**, and then **ATP safe attachments**.</span></span>
1. <span data-ttu-id="06fa3-109">安全な添付ファイルルールを選択し、[編集] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-109">Select your safe attachments rule, and then choose the **Edit** icon.</span></span>
1. <span data-ttu-id="06fa3-110">[ **設定]** を選択し、[ブロック] が選択されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-110">Select **settings**, and then verify that Block is selected.</span></span>
1. <span data-ttu-id="06fa3-111">下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="06fa3-111">Scroll down.</span></span> <span data-ttu-id="06fa3-112">[ **リダイレクトを有効にする**] を選択し、メール アドレスまたはブロックされた添付ファイルを確認するユーザーのアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-112">Choose **Enable redirect**, and enter your email address or the address of the person you want to review the blocked attachments.</span></span>
1. <span data-ttu-id="06fa3-113">[ **適用] を** 選択し、ドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-113">Select **applied to**, and then select your domain name.</span></span>
1. <span data-ttu-id="06fa3-114">ルールを適用する追加のドメイン (onmicrosoft.com ドメインなど) を選択します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-114">Choose any additional domains you own (such as your onmicrosoft.com domain) that you would like the rule applied to.</span></span> <span data-ttu-id="06fa3-115">[追加 **] を** 選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="06fa3-115">Select **add**, and then **OK**.</span></span>
1. <span data-ttu-id="06fa3-116">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-116">Select **Save**.</span></span>

<span data-ttu-id="06fa3-117">ATP の安全な添付ファイルルールが更新されました。</span><span class="sxs-lookup"><span data-stu-id="06fa3-117">Your ATP safe attachments rule has been updated.</span></span>

<span data-ttu-id="06fa3-118">これで保護が完了すると、悪意のあるファイルを Outlook、OneDrive、SharePoint、または Teams から開くTeams。</span><span class="sxs-lookup"><span data-stu-id="06fa3-118">Now that protection is in place, you won't be able to open a malicious file from Outlook, OneDrive, SharePoint, or Teams.</span></span> <span data-ttu-id="06fa3-119">影響を受けるファイルの横に赤いシールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06fa3-119">Affected files will have red shields next to them.</span></span> <span data-ttu-id="06fa3-120">ブロックされたファイルを開くしようとすると、警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06fa3-120">If someone attempts to open a blocked file, they'll receive a warning message.</span></span>

<span data-ttu-id="06fa3-121">しばらくポリシーが適用された後、[レポート] ページにアクセスして、スキャンされた情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="06fa3-121">After your policy has been in place for a while, visit the Reports page to see what has been scanned.</span></span>