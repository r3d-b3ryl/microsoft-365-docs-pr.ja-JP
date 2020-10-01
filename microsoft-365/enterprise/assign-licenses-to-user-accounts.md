---
title: ユーザーアカウントに Microsoft 365 ライセンスを割り当てる
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Microsoft 365 ライセンスを個別に、またはグループメンバーシップに基づいてユーザーアカウントに割り当てる方法について説明します。
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326509"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="baf6c-103">ユーザーアカウントに Microsoft 365 ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="baf6c-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="baf6c-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="baf6c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="baf6c-105">クラウド専用の id モデルの場合は、作成方法に応じて、ユーザーアカウントの作成時に Microsoft 365 ライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="baf6c-106">ハイブリッド id モデルでは、Active Directory ドメインサービス (AD DS) ユーザーアカウントが初めて同期されるときに、場所または Microsoft 365 ライセンスが自動的に割り当てられることはありません。</span><span class="sxs-lookup"><span data-stu-id="baf6c-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="baf6c-107">**各ユーザーアカウントは、ライセンスを割り当てる前またはユーザーの場所で構成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="baf6c-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="baf6c-108">どちらの場合も、ユーザーが Microsoft 365 サービス (電子メールや Microsoft Teams など) にアクセスできるように、ユーザーアカウントにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf6c-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="baf6c-109">ユーザーアカウントには、個別に、またはグループメンバーシップを使用して、自動的にライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="baf6c-110">Microsoft 365 ライセンスを個々のユーザーアカウントに割り当てるには、次のものを使用できます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="baf6c-111">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="baf6c-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="baf6c-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="baf6c-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="baf6c-113">Azure AD 管理センター</span><span class="sxs-lookup"><span data-stu-id="baf6c-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="baf6c-114">グループベースのライセンス</span><span class="sxs-lookup"><span data-stu-id="baf6c-114">Group-based licensing</span></span>

<span data-ttu-id="baf6c-115">Azure AD のセキュリティグループを構成して、サブスクリプションのセットからグループのすべてのメンバーにライセンスを自動的に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="baf6c-116">これは*グループベースのライセンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="baf6c-117">グループでユーザー アカウントを追加または削除すると、そのグループのサブスクリプションのライセンスが自動的にユーザー アカウントに追加または削除されます。</span><span class="sxs-lookup"><span data-stu-id="baf6c-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="baf6c-118">すべてのグループ メンバーに十分なライセンスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="baf6c-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="baf6c-119">ライセンスが不足している場合、ライセンスが使用可能になるまで、新しいユーザーにはライセンスが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="baf6c-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="baf6c-120">Azure B2B (企業間) アカウントが含まれているグループに対してはグループベースのライセンスを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="baf6c-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="baf6c-121">Informaion の詳細については、「 [AZURE AD でのグループベースのライセンス](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf6c-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="baf6c-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="baf6c-122">Next steps</span></span>

<span data-ttu-id="baf6c-123">ライセンスが割り当てられている適切なユーザーアカウントのセットにより、次の準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="baf6c-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="baf6c-124">セキュリティを実装する</span><span class="sxs-lookup"><span data-stu-id="baf6c-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="baf6c-125">Microsoft 365 アプリなどのクライアントソフトウェアを展開する</span><span class="sxs-lookup"><span data-stu-id="baf6c-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="baf6c-126">デバイス管理をセットアップする</span><span class="sxs-lookup"><span data-stu-id="baf6c-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="baf6c-127">サービスとアプリケーションを構成する</span><span class="sxs-lookup"><span data-stu-id="baf6c-127">Configure services and applications</span></span>](configure-services-and-applications.md)
