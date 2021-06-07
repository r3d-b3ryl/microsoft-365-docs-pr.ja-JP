---
title: セキュリティ/コンプライアンス センター Office 365コンプライアンス センターからコンプライアンス センターにユーザー Microsoft 365リダイレクトする
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: セキュリティ とコンプライアンス センターのOffice 365コンプライアンス センターに自動的にリダイレクトする方法Microsoft 365します。
ms.collection: M365-security-compliance
ms.openlocfilehash: fb667e8f19b26cbe229b3aceffe194a86133c261
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772481"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="43e1e-103">セキュリティ/コンプライアンス センター Office 365コンプライアンス センターからコンプライアンス センターにユーザー Microsoft 365リダイレクトする</span><span class="sxs-lookup"><span data-stu-id="43e1e-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="43e1e-104">この記事では、Office 365 セキュリティ とコンプライアンス センター (protection.office.com) から Microsoft 365 コンプライアンス センター (compliance.microsoft.com) へのコンプライアンス ソリューションにアクセスするユーザーの自動リダイレクトのしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43e1e-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="43e1e-105">想定される変化</span><span class="sxs-lookup"><span data-stu-id="43e1e-105">What to expect</span></span>

<span data-ttu-id="43e1e-106">自動リダイレクトは、セキュリティとコンプライアンス (Office 365) で次のコンプライアンス関連のソリューションにアクセスしているすべてのユーザーに対して既定 protection.office.com。</span><span class="sxs-lookup"><span data-stu-id="43e1e-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="43e1e-107">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="43e1e-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="43e1e-108">分類</span><span class="sxs-lookup"><span data-stu-id="43e1e-108">Classification</span></span>
- <span data-ttu-id="43e1e-109">情報ガバナンス</span><span class="sxs-lookup"><span data-stu-id="43e1e-109">Information governance</span></span>
- <span data-ttu-id="43e1e-110">レコード管理</span><span class="sxs-lookup"><span data-stu-id="43e1e-110">Records management</span></span>
- <span data-ttu-id="43e1e-111">コミュニケーションコンプライアンス (以前は '監督')</span><span class="sxs-lookup"><span data-stu-id="43e1e-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="43e1e-112">ユーザーは、コンプライアンス センター (Microsoft 365) で同 compliance.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="43e1e-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

>[!NOTE]
><span data-ttu-id="43e1e-113">Office 365 セキュリティとコンプライアンス センターに含まれる他のコンプライアンス ソリューションについては、Microsoft 365 コンプライアンス センターまたは Office 365 セキュリティ とコンプライアンス センターでこれらのソリューションを管理し続けます。</span><span class="sxs-lookup"><span data-stu-id="43e1e-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="43e1e-114">これらのコンプライアンス ソリューションの自動リダイレクトは、近日利用可能になります。\*</span><span class="sxs-lookup"><span data-stu-id="43e1e-114">The automatic redirection for these compliance solutions will be available soon.\*</span></span>

<span data-ttu-id="43e1e-115">この機能と関連付けられたコントロールでは、Microsoft Defender のセキュリティ機能の自動リダイレクトが有効Office 365。</span><span class="sxs-lookup"><span data-stu-id="43e1e-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="43e1e-116">セキュリティ機能のリダイレクトを有効にするには[、「Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)からアカウントをリダイレクトする」を参照Office 365セキュリティ センター Microsoft 365を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43e1e-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="43e1e-117">以前のポータルを使用して戻ってみませんか?</span><span class="sxs-lookup"><span data-stu-id="43e1e-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="43e1e-118">何かが機能していない場合、または Microsoft 365 コンプライアンス センター ポータルで完了できない場合は、すべてのユーザーの自動リダイレクトを一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="43e1e-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

>[!IMPORTANT]
><span data-ttu-id="43e1e-119">コンプライアンス Microsoft 365は、現在、セキュリティ/コンプライアンス センターで管理されているコンプライアンス ソリューションのOffice 365管理ポータルです。</span><span class="sxs-lookup"><span data-stu-id="43e1e-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="43e1e-120">すべてのMicrosoft 365ソリューションは、コンプライアンス センターでのみMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="43e1e-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="43e1e-121">コンプライアンス センターへのリダイレクトMicrosoft 365無効にするには、短期的なソリューションを使用する必要があります。\*</span><span class="sxs-lookup"><span data-stu-id="43e1e-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.\*</span></span>

<span data-ttu-id="43e1e-122">すべてのユーザーの Office 365 およびコンプライアンス センター (protection.microsoft.com) に切り替えるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43e1e-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="43e1e-123">グローバル管理者として[、Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターにサインインするか、Azure Active directory でコンプライアンス管理者のアクセス許可を持つ任意のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="43e1e-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="43e1e-124">コンプライアンス センターの **設定**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="43e1e-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="43e1e-125">[自動リダイレクト] 設定を [オフ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="43e1e-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="43e1e-126">プロンプトが **表示されたら、[** フィードバックを無効にして共有する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43e1e-126">Select **Disable** and share feedback when prompted.</span></span>

<span data-ttu-id="43e1e-127">無効にすると、ユーザーは compliance.microsoft.com にルーティングされ、Office 365 セキュリティ とコンプライアンス センター (protection.microsoft.com) に protection.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="43e1e-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="43e1e-128">この設定は、グローバル管理者またはコンプライアンス管理者がいつでも再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="43e1e-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="43e1e-129">関連情報</span><span class="sxs-lookup"><span data-stu-id="43e1e-129">Related information</span></span>

- [<span data-ttu-id="43e1e-130">Microsoft 365センターの概要</span><span class="sxs-lookup"><span data-stu-id="43e1e-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
