---
title: セキュリティとコンプライアンス センター Office 365ユーザーをサーバーにリダイレクトMicrosoft 365 コンプライアンス センター
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: セキュリティとコンプライアンス センターのOffice 365ユーザーを自動的にユーザーにリダイレクトする方法Microsoft 365 コンプライアンス センター。。
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339408"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="74149-103">セキュリティとコンプライアンス センター Office 365ユーザーをサーバーにリダイレクトMicrosoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="74149-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="74149-104">この記事では、Office 365 セキュリティ とコンプライアンス センター (protection.office.com) から Microsoft 365 コンプライアンス センター (compliance.microsoft.com) へのコンプライアンス ソリューションにアクセスするユーザーの自動リダイレクトのしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="74149-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="74149-105">想定される変化</span><span class="sxs-lookup"><span data-stu-id="74149-105">What to expect</span></span>

<span data-ttu-id="74149-106">自動リダイレクトは、セキュリティとコンプライアンス (Office 365) で次のコンプライアンス関連のソリューションにアクセスしているすべてのユーザーに対して既定 protection.office.com。</span><span class="sxs-lookup"><span data-stu-id="74149-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="74149-107">データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="74149-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="74149-108">分類</span><span class="sxs-lookup"><span data-stu-id="74149-108">Classification</span></span>
- <span data-ttu-id="74149-109">情報ガバナンス</span><span class="sxs-lookup"><span data-stu-id="74149-109">Information governance</span></span>
- <span data-ttu-id="74149-110">レコード管理</span><span class="sxs-lookup"><span data-stu-id="74149-110">Records management</span></span>
- <span data-ttu-id="74149-111">コミュニケーションコンプライアンス (以前は '監督')</span><span class="sxs-lookup"><span data-stu-id="74149-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="74149-112">ユーザーは自動的に同じコンプライアンス ソリューションにルーティングされます (Microsoft 365 コンプライアンス センター (compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="74149-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="74149-113">Office 365 セキュリティとコンプライアンス センターに含まれる他のコンプライアンス ソリューションについては、ユーザーは引き続き Microsoft 365 コンプライアンス センター または Office 365 セキュリティ とコンプライアンス センターでこれらのソリューションを管理します。</span><span class="sxs-lookup"><span data-stu-id="74149-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="74149-114">これらのコンプライアンス ソリューションの自動リダイレクトは、近日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="74149-114">The automatic redirection for these compliance solutions will be available soon.</span></span>

<span data-ttu-id="74149-115">この機能と関連付けられたコントロールでは、Microsoft Defender のセキュリティ機能の自動リダイレクトが有効Office 365。</span><span class="sxs-lookup"><span data-stu-id="74149-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="74149-116">セキュリティ機能のリダイレクトを有効にするには[、「Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)からアカウントをリダイレクトする」を参照Office 365セキュリティ センター Microsoft 365を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74149-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="74149-117">以前のポータルを使用して戻ってみませんか?</span><span class="sxs-lookup"><span data-stu-id="74149-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="74149-118">何かが機能していない場合、または Microsoft 365 コンプライアンス センター ポータルで完了できない場合は、すべてのユーザーの自動リダイレクトを一時的に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="74149-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74149-119">このMicrosoft 365 コンプライアンス センターは、セキュリティとコンプライアンス センターで現在管理されているコンプライアンス ソリューションOffice 365管理ポータルです。</span><span class="sxs-lookup"><span data-stu-id="74149-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="74149-120">すべてのMicrosoft 365コンプライアンス ソリューションは、ユーザーが管理するMicrosoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="74149-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="74149-121">サーバーへのリダイレクトを無効Microsoft 365 コンプライアンス センター短期的な解決策である必要があります。</span><span class="sxs-lookup"><span data-stu-id="74149-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.</span></span>

<span data-ttu-id="74149-122">すべてのユーザーの Office 365 およびコンプライアンス センター (protection.microsoft.com) に切り替えるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="74149-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="74149-123">グローバル管理者[としてMicrosoft 365 コンプライアンス センター、](https://compliance.microsoft.com)または Azure Active directory のコンプライアンス管理者のアクセス許可を持つ任意のアカウントを使用して、管理者にサインインします。</span><span class="sxs-lookup"><span data-stu-id="74149-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="74149-124">コンプライアンス センターの **設定**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="74149-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="74149-125">[自動リダイレクト] 設定を [オフ] に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="74149-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="74149-126">メッセージが **表示されたら、[** オフにし、フィードバックを共有する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="74149-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="74149-127">無効にすると、ユーザーは compliance.microsoft.com にルーティングされ、Office 365 セキュリティ とコンプライアンス センター (protection.microsoft.com) に protection.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="74149-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="74149-128">この設定は、グローバル管理者またはコンプライアンス管理者がいつでも再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="74149-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="74149-129">関連情報</span><span class="sxs-lookup"><span data-stu-id="74149-129">Related information</span></span>

- [<span data-ttu-id="74149-130">Microsoft 365 コンプライアンス センター概要</span><span class="sxs-lookup"><span data-stu-id="74149-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
