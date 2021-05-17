---
title: Microsoft OneDrive
description: Microsoft Managed Desktop が登録済みデバイス用に OneDrive をセットアップする方法
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904842"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="32267-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="32267-104">Microsoft OneDrive</span></span>

<span data-ttu-id="32267-105">Microsoft Managed Desktop は [、すべての Microsoft Managed Desktop](/onedrive/plan-onedrive-enterprise) デバイスのクラウド ストレージ サービスとして OneDrive for Business を使用して、デバイスが可能な限りステートレスな状態を確保します。</span><span class="sxs-lookup"><span data-stu-id="32267-105">Microsoft Managed Desktop uses [OneDrive for Business](/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="32267-106">ユーザーは、サインインするデバイスに関係なく、ファイルを見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32267-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="32267-107">たとえば、Microsoft Managed Desktop デバイスを新しいデバイスに置き換える場合、ファイルは自動的に新しいデバイスに同期されます。</span><span class="sxs-lookup"><span data-stu-id="32267-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="32267-108">Microsoft Managed Devices では、既定でこれらの設定が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="32267-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="32267-109">OneDrive は、ユーザー アカウントを使用してサイレントモードで構成され、Windows へのサインインに使用されたユーザー アカウントに (ユーザーの操作なしで) 自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="32267-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="32267-110">詳細については、「ユーザー アカウントの [サイレント構成 - OneDrive」を参照してください。](/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="32267-110">For more information, see [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="32267-111">Files-On-Demand 機能が有効になっているので、ユーザーはディスク領域を不必要に使わずに OneDrive のクラウド ストレージからファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="32267-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="32267-112">詳細については [、「Windows 10 用 OneDrive Files On-Demand](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)でディスク領域を節約する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32267-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="32267-113">既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="32267-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="32267-114">詳細については [、「OneDrive を使用して](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)ドキュメント、ピクチャ、デスクトップ フォルダーをバックアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32267-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="32267-115">ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更したりして、Microsoft Managed Desktop デバイス全体で一貫性のあるエクスペリエンスを確保することはできません。</span><span class="sxs-lookup"><span data-stu-id="32267-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="32267-116">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="32267-116">User experience</span></span>

<span data-ttu-id="32267-117">Microsoft Managed Desktop ユーザーが新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して初回実行エクスペリエンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="32267-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="32267-118">このプロセスが完了すると、デスクトップにアクセスして OneDrive エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="32267-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="32267-119">システムは、OneDrive が構成され、OneDrive に自動的にサインインされていることをユーザーに伝える。</span><span class="sxs-lookup"><span data-stu-id="32267-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="通知の読み取りで OneDrive を同期し、OneDrive でファイルを編集できます。ファイルを表示するには、ここをクリックしてください":::

2. <span data-ttu-id="32267-121">システムは、OneDrive 既知のフォルダー移動が構成されていることをユーザーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="32267-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知を読み取ります。フォルダーは OneDrive にバックアップされ、他のデバイスから利用できます。":::

3. <span data-ttu-id="32267-123">デバイスがリセットまたは再イメージ化されている場合にデスクトップ上の重複アイコンを防止するために、エクスプローラーのこのビューに示すように、システムは OneDrive 同期から Microsoft Edge アイコンと Microsoft Teams アイコンを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="32267-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="チェック ボックスがオフの Teams と Edge のリストを表示し、同期から除外されたテキストをホバーします。":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="32267-125">OneDrive 同期の制限</span><span class="sxs-lookup"><span data-stu-id="32267-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="32267-126">OneDrive 同期を制限する必要がある場合は、Azure Active Directory 条件付きアクセス ポリシーを使用してアクセスを制御することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32267-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="32267-127">詳細については [、「OneDrive 同期アプリで条件付きアクセスのサポートを有効にする」を参照してください](/onedrive/enable-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="32267-127">For more information, see [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="32267-128">組織で Azure ADポリシーを使用できない場合、IT 管理者は次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32267-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="32267-129">まだ分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id)テナント ID の検索」の説明に従って、テナント ID を検索します。</span><span class="sxs-lookup"><span data-stu-id="32267-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="32267-130">OneDrive 管理センターにサインインし、左側のウィンドウで **[同期** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="32267-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="32267-131">[特定 **のドメイン** に参加している PC でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。</span><span class="sxs-lookup"><span data-stu-id="32267-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="32267-132">詳細については、「特定のドメインに参加しているコンピューターでのみ同期を許可 [する」を参照してください](/onedrive/allow-syncing-only-on-specific-domains)。</span><span class="sxs-lookup"><span data-stu-id="32267-132">For more information, see [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="32267-133">このガイダンスは、Microsoft Managed Desktop のテナントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="32267-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="32267-134">この記事では説明していない他の設定が使用されています。</span><span class="sxs-lookup"><span data-stu-id="32267-134">There are other settings in use that aren't discussed in this article.</span></span>