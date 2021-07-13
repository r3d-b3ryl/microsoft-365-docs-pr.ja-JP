---
title: Microsoft 365 Lighthouse[ユーザー] ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseユーザー ページについて説明します。
ms.openlocfilehash: 795e387850bd2945c4019cbb467de87fecc15f86
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395315"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a><span data-ttu-id="98aae-103">Microsoft 365 Lighthouse[ユーザー] ページの概要</span><span class="sxs-lookup"><span data-stu-id="98aae-103">Microsoft 365 Lighthouse Users page overview</span></span> 

> [!NOTE]
> <span data-ttu-id="98aae-104">この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98aae-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="98aae-105">組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。</span><span class="sxs-lookup"><span data-stu-id="98aae-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="98aae-106">Microsoft 365 Lighthouse左側のナビゲーション ウィンドウで [ユーザー] を選択して [ユーザー] ページを開き、テナント アカウント間でユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="98aae-106">Microsoft 365 Lighthouse lets you manage users across tenant accounts by selecting **Users** in the left navigation pane to open the Users page.</span></span> <span data-ttu-id="98aae-107">このページから、ユーザーを検索し、ユーザー アカウントのセキュリティ状態を評価して実行できます。</span><span class="sxs-lookup"><span data-stu-id="98aae-107">From this page, you can search for users and assess and act on the security state of your user accounts.</span></span> <span data-ttu-id="98aae-108">リスクの高いユーザーと、多要素認証とセルフサービス パスワードのリセットの状態に関する分析情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="98aae-108">You can also view insights into risky users and the status of multifactor authentication and self-service password reset.</span></span>  
  
## <a name="search-users-tab"></a><span data-ttu-id="98aae-109">[ユーザーの検索] タブ</span><span class="sxs-lookup"><span data-stu-id="98aae-109">Search users tab</span></span>  
  
<span data-ttu-id="98aae-110">[ユーザーの検索] タブでは、テナント間で特定のユーザーをすばやく検索し、アカウント パスワードのリセットなどの基本的なユーザー管理アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="98aae-110">From the Search users tab, you can quickly search across tenants for specific users and perform basic user management actions such as resetting an account password.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="[ユーザーの検索] タブのスクリーンショット。":::

## <a name="risky-users-tab"></a><span data-ttu-id="98aae-112">[危険なユーザー] タブ</span><span class="sxs-lookup"><span data-stu-id="98aae-112">Risky users tab</span></span>

<span data-ttu-id="98aae-113">[危険なユーザー] タブには、リスクの高い動作のフラグが設定されているテナント全体のユーザー アカウントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98aae-113">The Risky Users tab shows user accounts across your tenants that have been flagged for risky behavior.</span></span> <span data-ttu-id="98aae-114">検出されたリスクに関する詳細を表示したり、ユーザーのパスワードをリセットしたり、サインインをブロックしたりしてリスクを軽減するには、任意のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="98aae-114">Select any of the users to view more information on a detected risk or to mitigate a risk by resetting a user's password or blocking sign-in.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="[危険なユーザー] タブのスクリーンショット。":::

## <a name="multifactor-authentication-tab"></a><span data-ttu-id="98aae-116">[多要素認証] タブ</span><span class="sxs-lookup"><span data-stu-id="98aae-116">Multifactor Authentication tab</span></span>

<span data-ttu-id="98aae-117">[多要素認証] タブには、テナント全体の多要素認証 (MFA) 有効化の状態に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98aae-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span></span> <span data-ttu-id="98aae-118">一覧で任意のテナントを選択すると、MFA を必要とする条件付きアクセス ポリシーが既に構成されている場合や、MFA にまだ登録していないユーザーなど、そのテナントの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98aae-118">Select any tenant in the list to see more details for that tenant, including which Conditional Access policies requiring MFA are already configured and which users have not yet registered for MFA.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="[多要素認証] タブのスクリーンショット。":::

## <a name="password-reset-tab"></a><span data-ttu-id="98aae-120">[パスワードのリセット] タブ</span><span class="sxs-lookup"><span data-stu-id="98aae-120">Password reset tab</span></span>

<span data-ttu-id="98aae-121">[パスワードのリセット] タブには、テナント全体のセルフサービス パスワードリセット有効化の状態に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98aae-121">The Password reset tab shows detailed information on the status of self-service password reset enablement across your tenants.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="[パスワードのリセット] タブのスクリーンショット。":::

## <a name="related-content"></a><span data-ttu-id="98aae-123">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="98aae-123">Related content</span></span>

<span data-ttu-id="98aae-124">[Microsoft 365 Lighthouseコンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md)(記事)</span><span class="sxs-lookup"><span data-stu-id="98aae-124">[Microsoft 365 Lighthouse device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="98aae-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)</span><span class="sxs-lookup"><span data-stu-id="98aae-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
