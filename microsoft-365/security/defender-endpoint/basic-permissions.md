---
title: 基本的なアクセス許可を使用してアクセスMicrosoft Defender セキュリティ センター
description: 基本的なアクセス許可を使用して Microsoft Defender for Endpoint ポータルにアクセスする方法について説明します。
keywords: ユーザー ロールの割り当て、読み取りおよび書き込みアクセスの割り当て、読み取り専用アクセスの割り当て、ユーザー、ユーザー の役割、役割
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cb5762d2a9e4b62432aba6dacd1033ddc3c7daf2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163673"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="390e8-104">基本的なアクセス許可を使用してポータルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="390e8-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="390e8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="390e8-105">**Applies to:**</span></span>
- <span data-ttu-id="390e8-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="390e8-106">Azure Active Directory</span></span>
- [<span data-ttu-id="390e8-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="390e8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="390e8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="390e8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="390e8-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="390e8-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="390e8-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="390e8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="390e8-111">基本的なアクセス許可管理を使用するには、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="390e8-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="390e8-112">次のいずれかのソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="390e8-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="390e8-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="390e8-113">Azure PowerShell</span></span>
- <span data-ttu-id="390e8-114">Azure portal</span><span class="sxs-lookup"><span data-stu-id="390e8-114">Azure portal</span></span>

<span data-ttu-id="390e8-115">アクセス許可を詳細に制御するには [、役割ベースのアクセス制御に切り替えます](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="390e8-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="390e8-116">ユーザー アクセスを割り当てるには、Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="390e8-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="390e8-117">次のいずれかのレベルのアクセス許可を持つユーザーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="390e8-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="390e8-118">フル アクセス (読み取りおよび書き込み)</span><span class="sxs-lookup"><span data-stu-id="390e8-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="390e8-119">読み取り専用アクセス</span><span class="sxs-lookup"><span data-stu-id="390e8-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="390e8-120">はじめに</span><span class="sxs-lookup"><span data-stu-id="390e8-120">Before you begin</span></span>

- <span data-ttu-id="390e8-121">Azure PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="390e8-121">Install Azure PowerShell.</span></span> <span data-ttu-id="390e8-122">詳細については、「How to install and configure Azure PowerShell」[を参照してください](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。</span><span class="sxs-lookup"><span data-stu-id="390e8-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="390e8-123">管理者特権のコマンド ラインで PowerShell コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="390e8-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="390e8-124">ConnectにAzure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="390e8-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="390e8-125">詳細については[、「Connect-MsolService」を参照してください](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="390e8-125">For more information, see [Connect-MsolService](https://docs.microsoft.com/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="390e8-126">**フル アクセス**</span><span class="sxs-lookup"><span data-stu-id="390e8-126">**Full access**</span></span> <br>
<span data-ttu-id="390e8-127">フル アクセスのユーザーは、ログインし、すべてのシステム情報を表示し、アラートを解決し、ファイルを送信して詳細な分析を行い、オンボーディング パッケージをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="390e8-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="390e8-128">フル アクセス権を割り当てるには、ユーザーを "セキュリティ管理者" または "グローバル管理者" AAD 組み込みロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="390e8-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="390e8-129">**読み取り専用アクセス**</span><span class="sxs-lookup"><span data-stu-id="390e8-129">**Read-only access**</span></span> <br>
<span data-ttu-id="390e8-130">読み取り専用アクセス権を持つユーザーは、ログイン、すべての通知、および関連情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="390e8-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="390e8-131">アラートの状態を変更したり、詳細な分析のためにファイルを送信したり、状態の変更操作を実行したりできない。</span><span class="sxs-lookup"><span data-stu-id="390e8-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="390e8-132">読み取り専用アクセス権を割り当てるには、ユーザーを "Security Reader" Azure AD組み込みロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="390e8-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="390e8-133">セキュリティ ロールを割り当てるには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="390e8-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="390e8-134">読 **み取りおよび書き込** みアクセスの場合は、次のコマンドを使用してセキュリティ管理者の役割にユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="390e8-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="390e8-135">読 **み取り専用アクセスの** 場合は、次のコマンドを使用してユーザーをセキュリティ リーダー ロールに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="390e8-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="390e8-136">詳細については、「グループ メンバーを使用してグループ メンバーを追加または削除する」[を参照Azure Active Directory。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="390e8-136">For more information, see [Add or remove group members using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="390e8-137">Azure portal を使用してユーザー アクセスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="390e8-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="390e8-138">詳細については、「管理者と管理者以外の役割[を](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)ユーザーに割り当てる」を参照Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="390e8-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="390e8-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="390e8-139">Related topic</span></span>

- [<span data-ttu-id="390e8-140">RBAC を使用してポータル アクセスを管理する</span><span class="sxs-lookup"><span data-stu-id="390e8-140">Manage portal access using RBAC</span></span>](rbac.md)
