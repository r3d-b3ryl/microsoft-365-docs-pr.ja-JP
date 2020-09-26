---
title: データ調査のアクセス許可を割り当てる (プレビュー)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: この記事では、Microsoft 365 でデータ調査ツールを使用するために必要なアクセス許可を設定する方法について説明します。
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285443"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="775e8-103">データ調査のアクセス許可を割り当てる (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="775e8-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="775e8-104">Office 365 または Microsoft 365 コンプライアンスセンターでデータの調査にアクセスするには、データ捜査役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="775e8-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="775e8-105">役割グループにメンバーを追加するには、組織の管理役割グループのメンバーであるか、セキュリティ & コンプライアンスセンターで役割管理の役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="775e8-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="775e8-106">ユーザーがデータ調査者の役割グループのメンバーになると、メンバーであるデータ調査で調査を作成、アクセス、および実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="775e8-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="775e8-107">データ調査のアクセス許可を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="775e8-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="775e8-108">に移動 [https://protection.office.com](https://protection.office.com) し、組織内の管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="775e8-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="775e8-109">[セキュリティ & コンプライアンスセンター] で、[ **アクセス許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="775e8-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="775e8-110">[ **データ** 調査担当者] 役割グループをクリックし、ポップアップページの [ **メンバー** ] の横にある [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="775e8-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="775e8-111">[ **メンバーの選択** ] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="775e8-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="775e8-112">データ捜査として追加するユーザーを選択し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="775e8-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="775e8-113">すべてのユーザーを追加した後、[ **完了** ] をクリックし、[ **保存** ] をクリックして、役割グループへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="775e8-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="775e8-114">データ調査者の役割グループに割り当てられているデータ調査管理役割は、Office 365 または Microsoft 365 コンプライアンスセンターのデータ調査ツールにアクセスするために必要なアクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="775e8-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="775e8-115">既定では、この役割は組織の管理役割グループに割り当てられていません。つまり、組織内のグローバル管理者が既定でデータ調査ツールにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="775e8-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="775e8-116">この問題を解決するには、グローバル管理者をデータ捜査役割グループに追加するか、または "データ調査" 管理役割を "Organization Management/組織の管理" 役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="775e8-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="775e8-117">3番目のオプションは、カスタム役割グループを作成し、データ調査管理役割 (およびその他の役割) を割り当ててから、適切なメンバーを追加することです。</span><span class="sxs-lookup"><span data-stu-id="775e8-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="775e8-118">役割グループと役割の詳細については、「 [セキュリティ & コンプライアンスセンター」の「アクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="775e8-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
