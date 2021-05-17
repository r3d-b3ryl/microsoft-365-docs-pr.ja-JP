---
title: ゲスト アカウントの前提条件
description: ゲスト アカウントの構成ガイドラインと調整方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574609"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="f86ff-104">ゲスト アカウントの前提条件</span><span class="sxs-lookup"><span data-stu-id="f86ff-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="f86ff-105">Microsoft Managed Desktop では、ゲスト アカウント アクセス用に Azure AD設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="f86ff-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="f86ff-106">これらの設定は [、Azure portal](https://portal.azure.com) の [外部 **ID/ 外部コラボレーション] で調整できます**。</span><span class="sxs-lookup"><span data-stu-id="f86ff-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="f86ff-107">**ゲスト 招待者ロールの管理者とユーザーは、[はい** ] に設定して招待 **できます**</span><span class="sxs-lookup"><span data-stu-id="f86ff-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="f86ff-108">[ **コラボレーションの制限] で**、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f86ff-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="f86ff-109">[任意の **ドメインへの招待の** 送信を許可する ( 最も包括的な) ] を選択した場合、他の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f86ff-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="f86ff-110">[指定した **ドメインへの** 招待を拒否する] を選択した場合は、Microsoft.com ドメインに一覧が表示されません。</span><span class="sxs-lookup"><span data-stu-id="f86ff-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="f86ff-111">[指定した **ドメインへの** 招待のみを許可する ] (最も制限の厳しい) を *選択した場合* は、Microsoft.com がターゲット ドメインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f86ff-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="f86ff-112">これらの設定を操作する制限を設定する場合は、必ず Azure Active Directory Modern **Workplace Service アカウントを除外してください**。</span><span class="sxs-lookup"><span data-stu-id="f86ff-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="f86ff-113">たとえば、ゲスト アカウントによる Intune ポータルへのアクセスを妨げる条件付きアクセス ポリシーがある場合は、このポリシーからモダン **Workplace サービス** アカウント グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="f86ff-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="f86ff-114">準備の手順</span><span class="sxs-lookup"><span data-stu-id="f86ff-114">Steps to get ready</span></span>

1. <span data-ttu-id="f86ff-115">[Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。</span><span class="sxs-lookup"><span data-stu-id="f86ff-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="f86ff-116">[準備状況の評価ツール](readiness-assessment-tool.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f86ff-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="f86ff-117">[ゲスト アカウントの前提条件](guest-accounts.md) (この記事)</span><span class="sxs-lookup"><span data-stu-id="f86ff-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="f86ff-118">Microsoft マネージド デスクトップのネットワーク構成</span><span class="sxs-lookup"><span data-stu-id="f86ff-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="f86ff-119">Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する</span><span class="sxs-lookup"><span data-stu-id="f86ff-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="f86ff-120">Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する</span><span class="sxs-lookup"><span data-stu-id="f86ff-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="f86ff-121">Microsoft マネージド デスクトップのアプリ</span><span class="sxs-lookup"><span data-stu-id="f86ff-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="f86ff-122">Microsoft マネージド デスクトップ用に、マップされたドライブを準備する</span><span class="sxs-lookup"><span data-stu-id="f86ff-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="f86ff-123">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="f86ff-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)