---
title: '手順 13: テナントとサインイン アクティビティを監視する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD のアクセスと利用状況レポートについて理解し、構成します。
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868985"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="1fe75-103">手順 13: テナントとサインイン アクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="1fe75-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="1fe75-104">*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="1fe75-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="1fe75-p101">この手順では、Azure AD のレポートを使用して監査ログおよびサインイン アクティビティを確認します。2 種類のレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1fe75-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="1fe75-p102">**監査ログ アクティビティ レポート**には、Azure AD テナントで実行されたすべてのタスクの履歴が記録されます。このレポートから、次のような情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1fe75-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="1fe75-109">管理者グループにユーザーを追加したユーザー</span><span class="sxs-lookup"><span data-stu-id="1fe75-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="1fe75-110">特定のアプリにサインインしたユーザー</span><span class="sxs-lookup"><span data-stu-id="1fe75-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="1fe75-111">パスワード リセットの実行回数</span><span class="sxs-lookup"><span data-stu-id="1fe75-111">How many password resets are happening?</span></span>

<span data-ttu-id="1fe75-p103">**サインイン アクティビティ レポート**には、監査ログ レポートで報告されたタスクを実行したユーザーが記録されます。このレポートから、次のような情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1fe75-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="1fe75-114">調査中の特定のユーザーのサインイン パターン</span><span class="sxs-lookup"><span data-stu-id="1fe75-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="1fe75-115">日、週、月あたりのサインインの回数</span><span class="sxs-lookup"><span data-stu-id="1fe75-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="1fe75-116">失敗したサインインの回数とそのアカウント</span><span class="sxs-lookup"><span data-stu-id="1fe75-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="1fe75-117">レポートとレポートへのアクセス方法の詳細については、「[Azure Active Directory レポート](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe75-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="1fe75-118">この手順を実行すると、これらのレポートを認識でき、また計画とセキュリティの目的でレポートを使用して Azure AD のイベントとアクティビティに関する情報を把握する方法を理解できます。</span><span class="sxs-lookup"><span data-stu-id="1fe75-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="1fe75-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="1fe75-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="1fe75-120">ユーザーが各自のグループを作成および管理できるようにする</span><span class="sxs-lookup"><span data-stu-id="1fe75-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
