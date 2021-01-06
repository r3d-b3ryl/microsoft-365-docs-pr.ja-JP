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
ms.openlocfilehash: d7fe410f114d43d4f6c983aaf23d949298635318
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760105"
---
# <a name="adjust-settings-after-enrollment"></a><span data-ttu-id="9058d-104">登録後に設定を調整する</span><span class="sxs-lookup"><span data-stu-id="9058d-104">Adjust settings after enrollment</span></span>

<span data-ttu-id="9058d-105">Microsoft マネージド デスクトップへの登録が完了したら、特定の Microsoft Intune と Azure Active Directory (Azure AD) の設定を調整して、セキュリティを管理および維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9058d-105">After you've completed enrollment in Microsoft Managed Desktop, you need to adjust certain Microsoft Intune and Azure Active Directory (Azure AD) settings to allow for management and maintain security.</span></span> <span data-ttu-id="9058d-106">Microsoft マネージド デスクトップ デバイスとユーザーを含む Azure ADグループを除外するには、次の設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="9058d-106">Set the following settings to exclude the Azure AD groups that contain Microsoft Managed Desktop devices and users.</span></span> <span data-ttu-id="9058d-107">グループを除外する手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。</span><span class="sxs-lookup"><span data-stu-id="9058d-107">For steps to exclude groups, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users).</span></span>

> [!NOTE]
> <span data-ttu-id="9058d-108">Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーへの登録後に変更を加えた場合、Microsoft マネージド デスクトップの正常な動作が停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9058d-108">If you make any changes after enrollment to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, it's possible that Microsoft Managed Desktop could stop operating properly.</span></span> <span data-ttu-id="9058d-109">Microsoft マネージド デスクトップの操作で問題が発生しないようにするには、「準備状況評価[](../get-ready/readiness-assessment-fix.md)ツールで見つかった問題を修正する」で説明されている特定の設定を確認してから、ポリシーを変更してください。</span><span class="sxs-lookup"><span data-stu-id="9058d-109">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in [Fix issues found by the readiness assessment tool](../get-ready/readiness-assessment-fix.md) before you change any policies.</span></span>


## <a name="microsoft-intune-settings"></a><span data-ttu-id="9058d-110">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="9058d-110">Microsoft Intune settings</span></span>

- <span data-ttu-id="9058d-111">Autopilot 展開プロファイル: **Modern Workplace Devices -All**  Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="9058d-111">Autopilot deployment profile: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="9058d-112">手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="9058d-112">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span>
- <span data-ttu-id="9058d-113">条件付きアクセス ポリシー: **モダン ワーク** プレース サービス アカウント Azure AD除外します。</span><span class="sxs-lookup"><span data-stu-id="9058d-113">Conditional Access policies: exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="9058d-114">手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="9058d-114">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>
- <span data-ttu-id="9058d-115">多要素認証: 多要素認証を必要とする条件付きアクセス ポリシーで、 **モダン Workplace Service アカウント** Azure ADしてください。</span><span class="sxs-lookup"><span data-stu-id="9058d-115">Multifactor authentication: make sure any conditional access policies that require multifactor authentication exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="9058d-116">詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](../get-ready/readiness-assessment-fix.md#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="9058d-116">For more information, see [Conditional access policies](../get-ready/readiness-assessment-fix.md#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>
- <span data-ttu-id="9058d-117">セキュリティベースライン: **モダン Workplace Devices -All**  Azure ADグループを除外します。</span><span class="sxs-lookup"><span data-stu-id="9058d-117">Security baseline: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="9058d-118">手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="9058d-118">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>
- <span data-ttu-id="9058d-119">Windows 10 更新リング: **Modern Workplace Devices -All**  Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="9058d-119">Windows 10 update ring: exclude the **Modern Workplace Devices -All**  Azure AD group.</span></span> <span data-ttu-id="9058d-120">手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="9058d-120">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="9058d-121">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="9058d-121">Azure Active Directory settings</span></span>

<span data-ttu-id="9058d-122">セルフサービスによるパスワードのリセット: **[選択** した設定] を選択し、[ **モダン Workplace Devices] -All** Azure ADします。</span><span class="sxs-lookup"><span data-stu-id="9058d-122">Self-service password reset: choose **Selected** setting, and then select **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="9058d-123">詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="9058d-123">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="9058d-124">Microsoft マネージド デスクトップの使用を開始する手順</span><span class="sxs-lookup"><span data-stu-id="9058d-124">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="9058d-125">管理ポータルで管理者の連絡先を追加および確認する</span><span class="sxs-lookup"><span data-stu-id="9058d-125">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="9058d-126">登録後に設定を調整する (この記事)</span><span class="sxs-lookup"><span data-stu-id="9058d-126">Adjust settings after enrollment (this article)</span></span>
3. [<span data-ttu-id="9058d-127">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9058d-127">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="9058d-128">Intune 会社ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="9058d-128">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="9058d-129">Enterprise State Roaming を有効にする</span><span class="sxs-lookup"><span data-stu-id="9058d-129">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="9058d-130">デバイスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="9058d-130">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="9058d-131">ユーザーがデバイスを使えるようにする</span><span class="sxs-lookup"><span data-stu-id="9058d-131">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="9058d-132">アプリを展開する</span><span class="sxs-lookup"><span data-stu-id="9058d-132">Deploy apps</span></span>](deploy-apps.md)
