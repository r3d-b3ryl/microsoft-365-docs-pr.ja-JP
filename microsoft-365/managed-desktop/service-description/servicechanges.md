---
title: サービスの変更と通信
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 00d1cb409364c017585c6afcd10a236ecbcdc3a0
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "37697901"
---
# <a name="service-changes-and-communication"></a><span data-ttu-id="16618-103">サービスの変更と通信</span><span class="sxs-lookup"><span data-stu-id="16618-103">Service changes and communication</span></span>

<span data-ttu-id="16618-104">Microsoft では、Microsoft Managed Desktop の動作方法に関する詳細を変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="16618-104">Sometimes, Microsoft might need to change details about the way Microsoft Managed Desktop works.</span></span> <span data-ttu-id="16618-105">同様に、サービスに影響する変更を行う必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="16618-105">Similarly, you might need to make changes that would affect the service as well.</span></span> <span data-ttu-id="16618-106">このような変更は、重要な方法に応じて異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="16618-106">We handle such changes differently depending on how significant they are.</span></span> <span data-ttu-id="16618-107">このトピックでは、主な変更点を定義し、その他の変更に対処する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16618-107">This topic defines the changes we consider major, and explains how we handle them versus other changes.</span></span>



## <a name="changes-made-by-microsoft"></a><span data-ttu-id="16618-108">Microsoft によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="16618-108">Changes made by Microsoft</span></span>

<span data-ttu-id="16618-109">アクションを必要とするすべての主要な変更について、少なくとも30日前に通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="16618-109">We'll give you notice at least 30 days ahead of time for any major change that requires action.</span></span> <span data-ttu-id="16618-110">Microsoft Managed Desktop Admin portal メッセージングシステムを使用してお知らせします。</span><span class="sxs-lookup"><span data-stu-id="16618-110">We’ll let you know by using the Microsoft Managed Desktop Admin portal messaging system.</span></span>

<span data-ttu-id="16618-111">**主な変更点**は、これらの領域に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16618-111">**Major changes** are those that might impact any of these areas:</span></span>
- <span data-ttu-id="16618-112">毎日の生産性に影響を与える変更</span><span class="sxs-lookup"><span data-stu-id="16618-112">Changes affecting daily productivity</span></span>
- <span data-ttu-id="16618-113">カスタマイズされた機能とアプリケーションに対する変更</span><span class="sxs-lookup"><span data-stu-id="16618-113">Changes to customized features and applications</span></span>
- <span data-ttu-id="16618-114">表示可能な容量の拡大または縮小</span><span class="sxs-lookup"><span data-stu-id="16618-114">Increase or decrease of visible capacity</span></span>
- <span data-ttu-id="16618-115">ヘルプデスクプロセスや参照資料または Url のユーザーの混乱や変更につながる可能性がある製品ブランド化の変更</span><span class="sxs-lookup"><span data-stu-id="16618-115">Changes in product branding that might cause user confusion or change in helpdesk processes and reference material or URLs</span></span>
- <span data-ttu-id="16618-116">日常の運用のためにサービスに必要なアクセス許可以外のアクセス許可を必要とする変更 (問題を防止または修正するアクションを除く)</span><span class="sxs-lookup"><span data-stu-id="16618-116">Changes requiring permissions beyond those required by the service for daily operations, excluding actions that prevent or fix issues</span></span>
- <span data-ttu-id="16618-117">データの保存場所への変更</span><span class="sxs-lookup"><span data-stu-id="16618-117">Changes to where your data is stored</span></span>
- <span data-ttu-id="16618-118">サービスのスコープに新しいコンポーネントサービスまたはアプリケーションを追加する</span><span class="sxs-lookup"><span data-stu-id="16618-118">Adding a new component service or application to the scope of the service</span></span>
- <span data-ttu-id="16618-119">サービスの範囲からのコンポーネントサービスまたはアプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="16618-119">Removal of a component service or application from the scope of the service</span></span>
- <span data-ttu-id="16618-120">サービスに新しい機能を追加する</span><span class="sxs-lookup"><span data-stu-id="16618-120">Adding new feature to the service</span></span>

> [!NOTE]
> <span data-ttu-id="16618-121">30日通知ポリシーから除外されるインシデントまたはセキュリティの問題を軽減するために変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="16618-121">We might have to make changes to mitigate incidents or security issues that would be excluded from the 30-day notification policy.</span></span>

<span data-ttu-id="16618-122">ユーザーの利便性、セキュリティ、信頼性、およびレポートを向上させるために、定期的にサービスに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="16618-122">We’ll routinely make other changes to the service to improve user experience, security, reliability, and reporting.</span></span> <span data-ttu-id="16618-123">これらの変更の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="16618-123">Some examples of these changes include:</span></span>

- <span data-ttu-id="16618-124">Windows および Office の更新プログラムのインストール</span><span class="sxs-lookup"><span data-stu-id="16618-124">Installation of Windows and Office updates</span></span>
- <span data-ttu-id="16618-125">デバイスに適用されるセキュリティベースラインの更新</span><span class="sxs-lookup"><span data-stu-id="16618-125">Updates to the security baseline applied to devices</span></span>
- [<span data-ttu-id="16618-126">Supported devices</span><span class="sxs-lookup"><span data-stu-id="16618-126">Supported devices</span></span>](device-list.md)

<span data-ttu-id="16618-127">これらの変更は、確立されたチャネルを使用して通知します。</span><span class="sxs-lookup"><span data-stu-id="16618-127">We'll communicate these changes by using established channels.</span></span> <span data-ttu-id="16618-128">変更についての質問がある場合は、Microsoft Managed Desktop [Operations team](../working-with-managed-desktop/admin-support.md)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="16618-128">If you have any questions about any changes, contact the Microsoft Managed Desktop [Operations team](../working-with-managed-desktop/admin-support.md).</span></span> <span data-ttu-id="16618-129">サービスへの変更は、必要に応じて[変更履歴](../change-history-managed-desktop.md)にも記載されています。</span><span class="sxs-lookup"><span data-stu-id="16618-129">Changes to the service are also documented as needed in the [change history](../change-history-managed-desktop.md).</span></span>

<span data-ttu-id="16618-130">Microsoft マネージドデスクトップの変更と通信は、次の2つの Microsoft ポリシーによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="16618-130">Microsoft Managed Desktop changes and communications are governed by two Microsoft policies:</span></span>
- [<span data-ttu-id="16618-131">モダンライフサイクルポリシー</span><span class="sxs-lookup"><span data-stu-id="16618-131">Modern Lifecycle Policy</span></span>](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [<span data-ttu-id="16618-132">Microsoft 365 Change Communication Policy</span><span class="sxs-lookup"><span data-stu-id="16618-132">Microsoft 365 Change Communication Policy</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?redirectSourcePath=%252fen-us%252farticle%252fMessage-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093&view=o365-worldwide)

## <a name="changes-you-make"></a><span data-ttu-id="16618-133">加えた変更</span><span class="sxs-lookup"><span data-stu-id="16618-133">Changes you make</span></span>

<span data-ttu-id="16618-134">環境によっては、Microsoft マネージドデスクトップに影響を与える変更があります。</span><span class="sxs-lookup"><span data-stu-id="16618-134">Some changes that you might make in your environment could impact Microsoft Managed Desktop.</span></span> <span data-ttu-id="16618-135">これらの主要な変更については、Microsoft Managed Desktop 管理ポータルでサービスリクエストを提出することによって、少なくとも30日の通知が送信されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="16618-135">For these major changes, we ask that you give us at least 30 days’ notice by submitting a service request in the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="16618-136">手順については、「 [Microsoft マネージドデスクトップの管理者サポート」を](../working-with-managed-desktop/admin-support.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="16618-136">See [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md) for instructions.</span></span> <span data-ttu-id="16618-137">これにより、変更を計画および準備するのに十分な時間が確保され、中断を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="16618-137">This allows us adequate time to plan and prepare for the change to avoid disruptions.</span></span>

<span data-ttu-id="16618-138">主な変更点は、これらの領域に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16618-138">Major changes are those that might impact any of these areas:</span></span>

- <span data-ttu-id="16618-139">Id システムおよびグループ</span><span class="sxs-lookup"><span data-stu-id="16618-139">Identity systems and groups</span></span>
- <span data-ttu-id="16618-140">ネットワークおよびネットワーク制御 (ファイアウォール、プロキシ、キャッシュ、VPN システムなど)</span><span class="sxs-lookup"><span data-stu-id="16618-140">Networking and network controls such as firewalls, proxy or caching, and VPN systems</span></span>
- <span data-ttu-id="16618-141">クラウドサービスの構成にアクセスするためのコントロール</span><span class="sxs-lookup"><span data-stu-id="16618-141">Controls for accessing cloud services configurations</span></span>
- <span data-ttu-id="16618-142">ネットワークサービスの id またはセキュリティ保護に使用されるユーザーまたはデバイスの証明書</span><span class="sxs-lookup"><span data-stu-id="16618-142">User or device certificates used for identity or securing of network services</span></span>
- <span data-ttu-id="16618-143">サービスを操作する管理システム</span><span class="sxs-lookup"><span data-stu-id="16618-143">Management systems that interact with the service</span></span>
- <span data-ttu-id="16618-144">サービスを操作するセキュリティシステムまたはエージェント</span><span class="sxs-lookup"><span data-stu-id="16618-144">Security systems or agents that interact with the service</span></span>
- <span data-ttu-id="16618-145">サービスに関連付けられている、またはで使用されているいずれかの Microsoft 365 クラウドサービスの構成</span><span class="sxs-lookup"><span data-stu-id="16618-145">Configuration of any of the Microsoft 365 cloud services associated with, or used by, the service</span></span>

<span data-ttu-id="16618-146">これらの変更は中断されない可能性があるため、事前に知らせる必要がありません。</span><span class="sxs-lookup"><span data-stu-id="16618-146">These changes aren’t likely to be disruptive, so you don’t need to let us know about them ahead of time:</span></span>

- <span data-ttu-id="16618-147">孤立したオブジェクトのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="16618-147">Orphaned object cleanup</span></span>
- <span data-ttu-id="16618-148">サービスに対するユーザーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="16618-148">Adding or removing users from the service</span></span>
- <span data-ttu-id="16618-149">Microsoft マネージドデスクトップの配信に重大な影響を与えないシステムの構成</span><span class="sxs-lookup"><span data-stu-id="16618-149">Configuration of system that does not have a material impact on the delivery of the Microsoft Managed Desktop</span></span>
- <span data-ttu-id="16618-150">アプリケーションバージョンの更新 (VPN またはプロキシアプリケーションを除く)</span><span class="sxs-lookup"><span data-stu-id="16618-150">Application version updates, with the exception of VPN or proxy applications</span></span>


