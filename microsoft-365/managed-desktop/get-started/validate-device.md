---
title: 新しいデバイスを検証する
description: デバイスを注文する前に、各モデルの 1 つを取得してテストします。
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
ms.openlocfilehash: 772636fd72074c8fad30daa3eb25b785519e7772
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246197"
---
# <a name="validate-new-devices"></a><span data-ttu-id="09197-103">新しいデバイスを検証する</span><span class="sxs-lookup"><span data-stu-id="09197-103">Validate new devices</span></span>

<span data-ttu-id="09197-104">Microsoft マネージド デスクトップ を初めて使用する場合でも、長時間の購読者でも、サービスに初めて登録するデバイス モデルの例をテストしてください。</span><span class="sxs-lookup"><span data-stu-id="09197-104">Whether you're completely new to Microsoft Managed Desktop or a long-time subscriber, it's best to test an example of any device model you're enrolling in the service for the first time.</span></span> <span data-ttu-id="09197-105">これは、ブランドの新しいデバイスを注文する場合でも、既存のデバイスを再利用する場合でも当てはめ、ビジネス デバイス サイトの shop Microsoft マネージド デスクトップに推奨Windows 10 Proデバイスを含むデバイスも[含](https://www.microsoft.com/windowsforbusiness/view-all-devices)めて有効です。</span><span class="sxs-lookup"><span data-stu-id="09197-105">This is true whether you're ordering brand-new devices or reusing existing ones, including devices recommended for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span> <span data-ttu-id="09197-106">そのサイトで、[フィルター] 領域で [機能] を展開し、[サービス] を選択して、サービスで使用する推奨 **デバイスMicrosoft マネージド デスクトップ。**</span><span class="sxs-lookup"><span data-stu-id="09197-106">At that site, view the devices recommended for use with the service by expanding **Features** in the **Filter by** area, and then selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="09197-107">デバイスを検証すると、期待するユーザー エクスペリエンスが確実に提供されます。</span><span class="sxs-lookup"><span data-stu-id="09197-107">Validating devices ensures that they'll deliver the user experience you expect.</span></span>

## <a name="validate-devices"></a><span data-ttu-id="09197-108">デバイスの検証</span><span class="sxs-lookup"><span data-stu-id="09197-108">Validate devices</span></span>

1. <span data-ttu-id="09197-109">次の記事の手順に従って、新しいモデルの 1 つ以上の例を実行します。</span><span class="sxs-lookup"><span data-stu-id="09197-109">Take one or more examples of new models through the steps in the following articles:</span></span>
    - [<span data-ttu-id="09197-110">Microsoft マネージド デスクトップのデバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="09197-110">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
    - [<span data-ttu-id="09197-111">ユーザー エクスペリエンスをローカライズ</span><span class="sxs-lookup"><span data-stu-id="09197-111">Localize the user experience</span></span>](localization.md)
    - [<span data-ttu-id="09197-112">Autopilot と登録ステータス ページの初回実行時エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="09197-112">First-run experience with Autopilot and the Enrollment Status Page</span></span>](esp-first-run.md)
    - [<span data-ttu-id="09197-113">Windows 10 の位置情報サービス</span><span class="sxs-lookup"><span data-stu-id="09197-113">Windows 10 location service</span></span>](device-location.md)
    - [<span data-ttu-id="09197-114">アプリ制御の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="09197-114">Get started with app control</span></span>](get-started-app-control.md)
    - [<span data-ttu-id="09197-115">アプリをデバイスに展開する</span><span class="sxs-lookup"><span data-stu-id="09197-115">Deploy apps to devices</span></span>](deploy-apps.md)
2. <span data-ttu-id="09197-116">次のエクスペリエンスがエラー、エラー、またはプロンプトなしで動作するように確認します。</span><span class="sxs-lookup"><span data-stu-id="09197-116">Verify that the following experiences work without any failures, errors, or prompts:</span></span>
    - <span data-ttu-id="09197-117">ネットワークに参加してユーザーがサインインした後の自動パイロット エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="09197-117">The Autopilot experience after joining the network and the user signs in</span></span>
    - <span data-ttu-id="09197-118">[登録の状態] ページ [を有効にしている場合](esp-first-run.md)は、機能します。</span><span class="sxs-lookup"><span data-stu-id="09197-118">If you've enabled the [Enrollment Status Page](esp-first-run.md), it works.</span></span>
    - <span data-ttu-id="09197-119">ユーザーは、アプリケーションにサインインOfficeできます</span><span class="sxs-lookup"><span data-stu-id="09197-119">User can sign into to Office applications</span></span>
    - <span data-ttu-id="09197-120">OneDriveデスクトップ、ドキュメント、ピクチャなどのWindowsフォルダーの同期</span><span class="sxs-lookup"><span data-stu-id="09197-120">OneDrive folders sync, including Windows Desktop, Documents, and Pictures</span></span>
    - <span data-ttu-id="09197-121">デバイスが更新プログラム、ポリシー、および業務アプリケーションを受け取る</span><span class="sxs-lookup"><span data-stu-id="09197-121">Device receives updates, policies, and line-of-business applications</span></span>
3. <span data-ttu-id="09197-122">デバイス インベントリ レポートで報告されたデバイスとハードウェア要件を確認 [して](../working-with-managed-desktop/device-inventory-report.md) 、期待したデバイスと一致していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09197-122">Review the reported devices and hardware requirements in the [Device inventory report](../working-with-managed-desktop/device-inventory-report.md) to check that they match what you expect.</span></span>

<span data-ttu-id="09197-123">問題が発生した場合は、管理 [ポータルでサポート](../working-with-managed-desktop/admin-support.md) を要求できます。</span><span class="sxs-lookup"><span data-stu-id="09197-123">If any problems occur, you can [request support](../working-with-managed-desktop/admin-support.md) in the Admin portal.</span></span>

<span data-ttu-id="09197-124">すべてがうまくいった場合は、展開に必要な検証済みデバイスの残りの部分を注文する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="09197-124">If everything goes well, you're ready to order the rest of the validated devices you need for your deployment.</span></span>