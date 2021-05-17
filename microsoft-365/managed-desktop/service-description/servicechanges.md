---
title: サービスの変更とコミュニケーション
description: サービスに対する変更が発生して通信される方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20af244d14f8f29e0175fb5e8efdabff94ff9a2b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244106"
---
# <a name="service-changes-and-communication"></a><span data-ttu-id="78d87-104">サービスの変更とコミュニケーション</span><span class="sxs-lookup"><span data-stu-id="78d87-104">Service changes and communication</span></span>

<span data-ttu-id="78d87-105">Microsoft では、アプリケーションの動作方法に関する詳細を変更Microsoft マネージド デスクトップ場合があります。</span><span class="sxs-lookup"><span data-stu-id="78d87-105">Sometimes, Microsoft might need to change details about the way Microsoft Managed Desktop works.</span></span> <span data-ttu-id="78d87-106">同様に、サービスにも影響を与える変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="78d87-106">Similarly, you might need to make changes that would affect the service as well.</span></span> <span data-ttu-id="78d87-107">このような変更は、重要な内容に応じて異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="78d87-107">We handle such changes differently depending on how significant they are.</span></span> <span data-ttu-id="78d87-108">このトピックでは、メジャーと見なす変更を定義し、その変更と他の変更の処理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="78d87-108">This topic defines the changes we consider major, and explains how we handle them versus other changes.</span></span>



## <a name="changes-made-by-microsoft"></a><span data-ttu-id="78d87-109">Microsoft によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="78d87-109">Changes made by Microsoft</span></span>

<span data-ttu-id="78d87-110">アクションが必要な大きな変更については、少なくとも 30 日前に通知します。</span><span class="sxs-lookup"><span data-stu-id="78d87-110">We'll give you notice at least 30 days ahead of time for any major change that requires action.</span></span> <span data-ttu-id="78d87-111">管理者ポータル メッセージング システムを使用してMicrosoft マネージド デスクトップお知らせします。</span><span class="sxs-lookup"><span data-stu-id="78d87-111">We’ll let you know by using the Microsoft Managed Desktop Admin portal messaging system.</span></span>

<span data-ttu-id="78d87-112">**主な変更** 点は、次の領域に影響を与える可能性がある変更点です。</span><span class="sxs-lookup"><span data-stu-id="78d87-112">**Major changes** are those that might impact any of these areas:</span></span>
- <span data-ttu-id="78d87-113">毎日の生産性に影響を与える変更</span><span class="sxs-lookup"><span data-stu-id="78d87-113">Changes affecting daily productivity</span></span>
- <span data-ttu-id="78d87-114">カスタマイズされた機能とアプリケーションへの変更</span><span class="sxs-lookup"><span data-stu-id="78d87-114">Changes to customized features and applications</span></span>
- <span data-ttu-id="78d87-115">表示される容量の増減</span><span class="sxs-lookup"><span data-stu-id="78d87-115">Increase or decrease of visible capacity</span></span>
- <span data-ttu-id="78d87-116">ヘルプデスク プロセスや参照資料または URL でユーザーの混乱や変更を引き起こす可能性がある製品ブランド化の変更</span><span class="sxs-lookup"><span data-stu-id="78d87-116">Changes in product branding that might cause user confusion or change in helpdesk processes and reference material or URLs</span></span>
- <span data-ttu-id="78d87-117">サービスが日常業務で必要とするアクセス許可を超えるアクセス許可を必要とする変更 (問題を防止または修正するアクションを除く)</span><span class="sxs-lookup"><span data-stu-id="78d87-117">Changes requiring permissions beyond those required by the service for daily operations, excluding actions that prevent or fix issues</span></span>
- <span data-ttu-id="78d87-118">データの保存場所の変更</span><span class="sxs-lookup"><span data-stu-id="78d87-118">Changes to where your data is stored</span></span>
- <span data-ttu-id="78d87-119">新しいコンポーネント サービスまたはアプリケーションをサービスのスコープに追加する</span><span class="sxs-lookup"><span data-stu-id="78d87-119">Adding a new component service or application to the scope of the service</span></span>
- <span data-ttu-id="78d87-120">サービスのスコープからのコンポーネント サービスまたはアプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="78d87-120">Removal of a component service or application from the scope of the service</span></span>
- <span data-ttu-id="78d87-121">サービスへの新機能の追加</span><span class="sxs-lookup"><span data-stu-id="78d87-121">Adding new feature to the service</span></span>

> [!NOTE]
> <span data-ttu-id="78d87-122">30 日間の通知ポリシーから除外されるインシデントやセキュリティの問題を軽減するために、変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="78d87-122">We might have to make changes to mitigate incidents or security issues that would be excluded from the 30-day notification policy.</span></span>

<span data-ttu-id="78d87-123">ユーザー エクスペリエンス、セキュリティ、信頼性、レポートを向上させるために、サービスに対して他の変更を定期的に行います。</span><span class="sxs-lookup"><span data-stu-id="78d87-123">We’ll routinely make other changes to the service to improve user experience, security, reliability, and reporting.</span></span> <span data-ttu-id="78d87-124">これらの変更の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="78d87-124">Some examples of these changes include:</span></span>

- <span data-ttu-id="78d87-125">更新プログラムWindowsインストールOfficeする</span><span class="sxs-lookup"><span data-stu-id="78d87-125">Installation of Windows and Office updates</span></span>
- <span data-ttu-id="78d87-126">デバイスに適用されるセキュリティ 基準の更新</span><span class="sxs-lookup"><span data-stu-id="78d87-126">Updates to the security baseline applied to devices</span></span>
- <span data-ttu-id="78d87-127">サポートされているデバイス。</span><span class="sxs-lookup"><span data-stu-id="78d87-127">Supported devices.</span></span> <span data-ttu-id="78d87-128">推奨されるデバイスを表示するには、ビジネス Microsoft マネージド デスクトップサイトで[Windows 10 Proをフィルター](https://www.microsoft.com/windowsforbusiness/view-all-devices)処理します。</span><span class="sxs-lookup"><span data-stu-id="78d87-128">To see recommended devices, filter for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span>

<span data-ttu-id="78d87-129">これらの変更については、確立されたチャネルを使用して伝達します。</span><span class="sxs-lookup"><span data-stu-id="78d87-129">We'll communicate these changes by using established channels.</span></span> <span data-ttu-id="78d87-130">変更に関する質問がある場合は、運用チームMicrosoft マネージド デスクトップ[問い合わせください](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="78d87-130">If you have any questions about any changes, contact the Microsoft Managed Desktop [Operations team](../working-with-managed-desktop/admin-support.md).</span></span> <span data-ttu-id="78d87-131">サービスへの変更は、必要に応じて変更履歴にも [記録されます](../change-history-managed-desktop.md)。</span><span class="sxs-lookup"><span data-stu-id="78d87-131">Changes to the service are also documented as needed in the [change history](../change-history-managed-desktop.md).</span></span>

<span data-ttu-id="78d87-132">Microsoft マネージド デスクトップ変更と通信は、次の 2 つの Microsoft ポリシーによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="78d87-132">Microsoft Managed Desktop changes and communications are governed by two Microsoft policies:</span></span>
- [<span data-ttu-id="78d87-133">最新のライフサイクル ポリシー</span><span class="sxs-lookup"><span data-stu-id="78d87-133">Modern Lifecycle Policy</span></span>](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [<span data-ttu-id="78d87-134">Microsoft 365通信ポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="78d87-134">Microsoft 365 Change Communication Policy</span></span>](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a><span data-ttu-id="78d87-135">加えた変更</span><span class="sxs-lookup"><span data-stu-id="78d87-135">Changes you make</span></span>

<span data-ttu-id="78d87-136">環境で行う可能性がある一部の変更は、環境に影響をMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="78d87-136">Some changes that you might make in your environment could impact Microsoft Managed Desktop.</span></span> <span data-ttu-id="78d87-137">これらの大きな変更については、管理者ポータルでサービス要求を送信して、少なくとも 30 日後に通知Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="78d87-137">For these major changes, we ask that you give us at least 30 days’ notice by submitting a service request in the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="78d87-138">手順については[、「管理者向けサポートMicrosoft マネージド デスクトップ」](../working-with-managed-desktop/admin-support.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78d87-138">See [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md) for instructions.</span></span> <span data-ttu-id="78d87-139">これにより、中断を回避するために、変更を計画して準備するための十分な時間を確保できます。</span><span class="sxs-lookup"><span data-stu-id="78d87-139">This allows us adequate time to plan and prepare for the change to avoid disruptions.</span></span>

<span data-ttu-id="78d87-140">主な変更点は、次の領域に影響を与える可能性がある変更点です。</span><span class="sxs-lookup"><span data-stu-id="78d87-140">Major changes are those that might impact any of these areas:</span></span>

- <span data-ttu-id="78d87-141">ID システムとグループ</span><span class="sxs-lookup"><span data-stu-id="78d87-141">Identity systems and groups</span></span>
- <span data-ttu-id="78d87-142">ファイアウォール、プロキシまたはキャッシュ、VPN システムなどのネットワークおよびネットワークコントロール</span><span class="sxs-lookup"><span data-stu-id="78d87-142">Networking and network controls such as firewalls, proxy or caching, and VPN systems</span></span>
- <span data-ttu-id="78d87-143">クラウド サービス構成にアクセスするコントロール</span><span class="sxs-lookup"><span data-stu-id="78d87-143">Controls for accessing cloud services configurations</span></span>
- <span data-ttu-id="78d87-144">ネットワーク サービスの ID またはセキュリティ保護に使用されるユーザー証明書またはデバイス証明書</span><span class="sxs-lookup"><span data-stu-id="78d87-144">User or device certificates used for identity or securing of network services</span></span>
- <span data-ttu-id="78d87-145">サービスと対話する管理システム</span><span class="sxs-lookup"><span data-stu-id="78d87-145">Management systems that interact with the service</span></span>
- <span data-ttu-id="78d87-146">サービスと対話するセキュリティ システムまたはエージェント</span><span class="sxs-lookup"><span data-stu-id="78d87-146">Security systems or agents that interact with the service</span></span>
- <span data-ttu-id="78d87-147">サービスに関連付けられているMicrosoft 365、またはサービスによって使用されるクラウド サービスの構成</span><span class="sxs-lookup"><span data-stu-id="78d87-147">Configuration of any of the Microsoft 365 cloud services associated with, or used by, the service</span></span>

<span data-ttu-id="78d87-148">これらの変更は中断される可能性が高くないので、前もってそれらの変更についてお知らせする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="78d87-148">These changes aren’t likely to be disruptive, so you don’t need to let us know about them ahead of time:</span></span>

- <span data-ttu-id="78d87-149">孤立したオブジェクトのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="78d87-149">Orphaned object cleanup</span></span>
- <span data-ttu-id="78d87-150">サービスへのユーザーの追加または削除</span><span class="sxs-lookup"><span data-stu-id="78d87-150">Adding or removing users from the service</span></span>
- <span data-ttu-id="78d87-151">システムの配信に大きな影響を与えるシステムの構成Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="78d87-151">Configuration of system that does not have a material impact on the delivery of the Microsoft Managed Desktop</span></span>
- <span data-ttu-id="78d87-152">VPN またはプロキシ アプリケーションを除く、アプリケーションのバージョンの更新</span><span class="sxs-lookup"><span data-stu-id="78d87-152">Application version updates, with the exception of VPN or proxy applications</span></span>