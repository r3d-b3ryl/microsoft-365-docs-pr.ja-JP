---
title: 登録後に設定を調整する
description: 特定の Microsoft アカウントを除外する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527699"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="0de35-104">登録後に設定を調整する</span><span class="sxs-lookup"><span data-stu-id="0de35-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="0de35-105">Microsoft マネージドデスクトップでの登録を完了した後、特定の Microsoft Intune および Azure Active Directory (Azure AD) の設定を調整して、セキュリティを管理および管理できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0de35-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="0de35-106">次の設定を設定して、Microsoft Managed Desktop デバイスとユーザーを含む Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="0de35-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="0de35-107">グループを除外する手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="0de35-108">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="0de35-108">Microsoft Intune settings</span></span>

- <span data-ttu-id="0de35-109">自動操縦展開プロファイル: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="0de35-109">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0de35-110">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-110">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="0de35-111">条件付きアクセスポリシー: **モダン Workplace Service アカウント** の Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="0de35-111">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="0de35-112">手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-112">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="0de35-113">多元的な認証: 多要素認証を必要とする条件付きアクセスポリシーでは、 **モダンワークプレースサービスアカウント** の Azure AD グループを除外してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-113">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="0de35-114">詳細については、「 [条件付きアクセスポリシー](../get-ready/readiness-assessment-fix.md#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-114">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="0de35-115">セキュリティベースライン: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="0de35-115">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0de35-116">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-116">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="0de35-117">Windows 10 更新リング: **モダン Workplace Devices-すべて**  の Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="0de35-117">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="0de35-118">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-118">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="0de35-119">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="0de35-119">Azure Active Directory settings</span></span>

<span data-ttu-id="0de35-120">セルフサービスによるパスワードのリセット: **選択した** 設定を選択し、[ **モダン Workplace Devices-すべての** Azure AD グループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0de35-120">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="0de35-121">詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0de35-121">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="0de35-122">Microsoft マネージドデスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="0de35-122">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="0de35-123">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="0de35-123">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="0de35-124">登録後に設定を調整する (この記事)</span><span class="sxs-lookup"><span data-stu-id="0de35-124">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="0de35-125">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0de35-125">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="0de35-126">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="0de35-126">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="0de35-127">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="0de35-127">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="0de35-128">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="0de35-128">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="0de35-129">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="0de35-129">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="0de35-130">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="0de35-130">Deploy apps</span></span>](deploy-apps.md)
