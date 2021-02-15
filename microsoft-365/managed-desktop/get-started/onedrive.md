---
title: Microsoft OneDrive
description: Microsoft マネージド デスクトップで登録済みデバイス用に OneDrive をセットアップする方法
keywords: Microsoft マネージド デスクトップ, Microsoft 365, サービス, ドキュメント, アプリ, 業務アプリ, LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233924"
---
# <a name="microsoft-onedrive"></a><span data-ttu-id="8ca5d-104">Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="8ca5d-104">Microsoft OneDrive</span></span>

<span data-ttu-id="8ca5d-105">Microsoft マネージド デスクトップは、すべての Microsoft マネージド デスクトップ デバイスのクラウド ストレージ サービスとして [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) を使用して、デバイスが可能な限りステートレスな状態を確保します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-105">Microsoft Managed Desktop uses [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) as a cloud storage service for all Microsoft Managed Desktop devices to ensure that the devices are as stateless as possible.</span></span> <span data-ttu-id="8ca5d-106">ユーザーは、サインインするデバイスに関係なく、ファイルを見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-106">User will be able to find their files no matter which device they sign into.</span></span> <span data-ttu-id="8ca5d-107">たとえば、Microsoft マネージド デスクトップ デバイスを新しいデバイスに置き換える場合、ファイルは自動的に新しいデバイスと同期されます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-107">For example, if you replace a Microsoft Managed Desktop device with a new one, files will automatically sync to the new device.</span></span>

<span data-ttu-id="8ca5d-108">Microsoft マネージド デバイスでは、既定でこれらの設定が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-108">We automatically configure these settings by default on Microsoft Managed Devices:</span></span>

- <span data-ttu-id="8ca5d-109">OneDrive は、ユーザー アカウントを使用してサイレント モードで構成され、Windows へのサインインに使用されたユーザー アカウントに自動的にサインインします (ユーザーの操作は必要としません)。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-109">OneDrive is silently configured with the user account and automatically signed in (without user interaction) to the user account that was used to sign into Windows.</span></span> <span data-ttu-id="8ca5d-110">詳細については、「ユーザー アカウントの [サイレント構成 - OneDrive」を参照してください。](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span><span class="sxs-lookup"><span data-stu-id="8ca5d-110">For more information, see [Silently configure user accounts - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)</span></span>

- <span data-ttu-id="8ca5d-111">ファイル オンデマンド機能が有効になっているので、ユーザーはディスク領域を不必要に使わずに OneDrive のクラウド ストレージからファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-111">The Files-On-Demand feature is enabled so that users can access files from their cloud storage in OneDrive without having to use disk space unnecessarily.</span></span> <span data-ttu-id="8ca5d-112">詳しくは [、「Windows 10 用 OneDrive ファイル](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)オンデマンドでのディスク領域の節約」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-112">For more information, see [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).</span></span>

- <span data-ttu-id="8ca5d-113">既知のフォルダー移動機能は、クラウド内のユーザーのデータをバックアップするためにサイレント モードで有効になっています。これにより、ユーザーは任意のデバイスからファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-113">The Known Folder Move feature is enabled silently to back up users’ data in the cloud, which gives them access to their files from any device.</span></span> <span data-ttu-id="8ca5d-114">詳細については [、「OneDrive でドキュメント、](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)画像、デスクトップ フォルダーをバックアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-114">For more information, see [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).</span></span>

- <span data-ttu-id="8ca5d-115">ユーザーは、既知のフォルダー移動機能を無効にしたり、既知のフォルダーの場所を変更したりして、Microsoft マネージド デスクトップ デバイス間で一貫したエクスペリエンスを確保することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-115">Users cannot disable the Known Folder Move feature or change the location of known folders to ensure a consistent experience across Microsoft Managed Desktop devices.</span></span>

## <a name="user-experience"></a><span data-ttu-id="8ca5d-116">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="8ca5d-116">User experience</span></span>

<span data-ttu-id="8ca5d-117">Microsoft マネージド デスクトップのユーザーは、新しいデバイスを受け取ると、デバイスのセットアップ中に Azure 資格情報を入力して初回実行時のエクスペリエンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-117">When Microsoft Managed Desktop users receive a new device, they go through a first-run experience by entering their Azure credentials while setting up the device.</span></span> <span data-ttu-id="8ca5d-118">このプロセスが完了すると、ユーザーはデスクトップにアクセスして OneDrive エクスペリエンスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-118">After this process is completed, they can access their desktop and have the OneDrive experience.</span></span>

1. <span data-ttu-id="8ca5d-119">システムは、OneDrive が構成され、自動的に OneDrive にサインインされていることをユーザーに伝える。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-119">The system tells users that OneDrive has been configured and that they have been automatically signed into OneDrive.</span></span>

:::image type="content" source="media/onedrive-sync.png" alt-text="OneDrive を同期中で、OneDrive でファイルを編集できるという通知が表示されます。ファイルを表示するには、ここをクリックしてください":::

2. <span data-ttu-id="8ca5d-121">システムは、OneDrive の既知のフォルダー移動が構成されていることをユーザーに伝えます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-121">The system tells users that OneDrive Known Folder Move has been configured for them.</span></span>

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 部門が重要なフォルダーをバックアップしたという通知。フォルダーが OneDrive にバックアップされ、他のデバイスから利用できる":::

3. <span data-ttu-id="8ca5d-123">デバイスがリセットまたは再イメージ化されているときに、デスクトップ上の重複するアイコンが表示されるのを防ぐため、システムは、エクスプローラーのこのビューに示すように、OneDrive 同期から Microsoft Edge と Microsoft Teams のアイコンを自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-123">To prevent duplicate icons on the desktop when devices are being reset or reimaged, the system automatically removes Microsoft Edge and Microsoft Teams icons from the OneDrive sync, as shown in this view in File Explorer.</span></span>

:::image type="content" source="media/onedrive-teams.png" alt-text="オフのチェック ボックスとホバー テキストが表示された、Teams と Edge の一覧を表示するエクスプローラー (同期から除外)":::


## <a name="onedrive-sync-restrictions"></a><span data-ttu-id="8ca5d-125">OneDrive の同期の制限</span><span class="sxs-lookup"><span data-stu-id="8ca5d-125">OneDrive sync restrictions</span></span>

<span data-ttu-id="8ca5d-126">OneDrive の同期を制限する必要がある場合は、Azure Active Directory の条件付きアクセス ポリシーを使用してアクセスを制御することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-126">If you need to restrict OneDrive sync, we recommend that you control access with an Azure Active Directory conditional access policy.</span></span> <span data-ttu-id="8ca5d-127">詳細については [、「OneDrive 同期アプリで条件付きアクセスのサポートを有効にする」を参照してください](https://docs.microsoft.com/onedrive/enable-conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-127">For more information, see [Enable conditional access support in the OneDrive sync app](https://docs.microsoft.com/onedrive/enable-conditional-access).</span></span>

<span data-ttu-id="8ca5d-128">組織で Azure の条件付きアクセス ポリシー AD使用できない場合、IT 管理者は次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-128">If you can't use an Azure AD conditional access policy in your organization, your IT Admin should follow these steps:</span></span>

1. <span data-ttu-id="8ca5d-129">まだご存知ない場合は [、「Microsoft 365](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)テナント ID を検索する」の説明に従ってテナント ID を検索します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-129">If you don't already know it, look up your tenant ID, as described in [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>
2. <span data-ttu-id="8ca5d-130">OneDrive 管理センターにサインインし、左側のウィンドウで **[** 同期] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-130">Sign in to the OneDrive admin center, and then select **Sync** in the left pane.</span></span> <span data-ttu-id="8ca5d-131">[特定 **のドメイン** に参加している PC でのみ同期を許可する] チェック ボックスをオンにし、ドメインの一覧にテナント ID を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-131">Select the **Allow syncing only on PCs joined to specific domains** check box, and then add the tenant ID to the list of domains.</span></span> <span data-ttu-id="8ca5d-132">詳細については、「特定の [ドメインに参加しているコンピューターでのみ同期を許可する」を参照してください](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-132">For more information, see [Allow syncing only on computers joined to specific domains](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains).</span></span>

> [!NOTE]
> <span data-ttu-id="8ca5d-133">このガイダンスは、Microsoft マネージド デスクトップのテナントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-133">This guidance applies only to tenants in Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ca5d-134">この記事では説明していない他の設定も使用されています。</span><span class="sxs-lookup"><span data-stu-id="8ca5d-134">There are other settings in use that aren't discussed in this article.</span></span>
