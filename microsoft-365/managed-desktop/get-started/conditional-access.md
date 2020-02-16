---
title: 条件付きアクセスを調整する
description: 特定の Microsoft アカウントを除外する方法
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085808"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="6bb35-104">条件付きアクセスを調整する</span><span class="sxs-lookup"><span data-stu-id="6bb35-104">Adjust conditional access</span></span>

<span data-ttu-id="6bb35-105">[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシーを組織で使用する場合は、Microsoft 管理デスクトップが正常に動作するように、特定のアカウントを除外するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bb35-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="6bb35-106">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bb35-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="6bb35-107">「[[方法] Azure Active Directory での条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps)」の「ロールバック手順」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bb35-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="6bb35-108">この手順に従って、すべてのポリシーの*モダン Workplace Service アカウント*グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="6bb35-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="6bb35-109">条件付きアクセスに問題がある場合は、管理者[サポート](../working-with-managed-desktop/admin-support.md)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6bb35-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="6bb35-110">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="6bb35-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="6bb35-111">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="6bb35-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="6bb35-112">条件付きアクセスを調整する (このトピック)</span><span class="sxs-lookup"><span data-stu-id="6bb35-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="6bb35-113">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="6bb35-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="6bb35-114">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="6bb35-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="6bb35-115">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="6bb35-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="6bb35-116">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="6bb35-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="6bb35-117">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="6bb35-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="6bb35-118">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="6bb35-118">Deploy apps</span></span>](deploy-apps.md)
