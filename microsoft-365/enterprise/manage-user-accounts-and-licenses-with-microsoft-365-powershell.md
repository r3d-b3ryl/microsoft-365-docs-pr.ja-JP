---
title: Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: PowerShell を使用して Microsoft 365 のユーザーアカウント、ライセンス、グループを管理する方法について説明します。
ms.openlocfilehash: 0c6ca6a4165b616097405a9de178c254aa489a3c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429988"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="65455-103">Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する</span><span class="sxs-lookup"><span data-stu-id="65455-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="65455-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="65455-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="65455-105">Microsoft 365 管理者は、ユーザーアカウント、ライセンス、およびグループを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65455-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="65455-106">これらのタスクのほとんどは Microsoft 365 管理センターで行うことができますが、PowerShell の方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="65455-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="65455-107">詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65455-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="65455-108">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="65455-108">User accounts</span></span>

- [<span data-ttu-id="65455-109">ユーザー アカウントの作成</span><span class="sxs-lookup"><span data-stu-id="65455-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-110">ユーザー アカウントを表示する</span><span class="sxs-lookup"><span data-stu-id="65455-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-111">ユーザー アカウントのプロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="65455-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-112">ユーザー アカウントにロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="65455-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-113">ユーザー アカウントを削除および復元する</span><span class="sxs-lookup"><span data-stu-id="65455-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-114">ユーザー アカウントをブロックする</span><span class="sxs-lookup"><span data-stu-id="65455-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="65455-115">ライセンスおよびサービス</span><span class="sxs-lookup"><span data-stu-id="65455-115">Licenses and services</span></span>
- [<span data-ttu-id="65455-116">ライセンスおよびサービスを確認する</span><span class="sxs-lookup"><span data-stu-id="65455-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-117">ライセンスのあるユーザーとライセンスのないユーザーを表示する</span><span class="sxs-lookup"><span data-stu-id="65455-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-118">ユーザー アカウントにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="65455-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-119">アカウントのライセンスとサービスの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="65455-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-120">サービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="65455-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="65455-121">Sway へのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="65455-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="65455-122">ユーザー ライセンスを割り当てる間、サービスへのアクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="65455-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="65455-123">ユーザー アカウントからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="65455-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="65455-124">グループ</span><span class="sxs-lookup"><span data-stu-id="65455-124">Groups</span></span>
- [<span data-ttu-id="65455-125">グループ メンバーシップを管理する</span><span class="sxs-lookup"><span data-stu-id="65455-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="65455-126">Microsoft 365 グループを管理する</span><span class="sxs-lookup"><span data-stu-id="65455-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
