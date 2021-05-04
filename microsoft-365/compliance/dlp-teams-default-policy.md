---
title: Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: このページの既定のデータ損失防止ポリシーについてMicrosoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114145"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="34403-103">Microsoft Teams の既定のデータ損失防止ポリシーについて学ぶ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="34403-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="34403-104">[データ損失防止機能](dlp-learn-about-dlp.md)は、プライベート チャネル メッセージを含むMicrosoft Teamsチャネル メッセージを含む拡張されました。</span><span class="sxs-lookup"><span data-stu-id="34403-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="34403-105">このリリースの一環として、コンプライアンス センターに初めてお客様向け既定の DLP ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="34403-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="34403-106">適用対象</span><span class="sxs-lookup"><span data-stu-id="34403-106">Applies to</span></span>

<span data-ttu-id="34403-107">以下の 1 つ以上のライセンスでライセンスを取得し、アクティブなユーザーを持Teamsテナント</span><span class="sxs-lookup"><span data-stu-id="34403-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="34403-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="34403-108">ME5,</span></span> 
- <span data-ttu-id="34403-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="34403-109">MA5,</span></span> 
- <span data-ttu-id="34403-110">E5/A5 コンプライアンス、</span><span class="sxs-lookup"><span data-stu-id="34403-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="34403-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="34403-111">IP+G,</span></span> 
- <span data-ttu-id="34403-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="34403-112">OE5,</span></span> 
- <span data-ttu-id="34403-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="34403-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="34403-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="34403-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="34403-115">既定のポリシーは何をしますか?</span><span class="sxs-lookup"><span data-stu-id="34403-115">What does the default policy do?</span></span>

<span data-ttu-id="34403-116">既定の DLP ポリシーは、組織に内部および外部で共有されるクレジット カード番号を追跡します。</span><span class="sxs-lookup"><span data-stu-id="34403-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="34403-117">このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="34403-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="34403-118">エンド ユーザーのポリシー ヒントは生成されませんが、Alert イベントを生成し、管理者 (ポリシーに追加) への重大度の低い電子メールもトリガーします。</span><span class="sxs-lookup"><span data-stu-id="34403-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="34403-119">管理者は、コンプライアンス センターにログインして、アクティビティを表示し、ポリシーの詳細を編集できます。</span><span class="sxs-lookup"><span data-stu-id="34403-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="34403-120">管理者は、コンプライアンス センターの [データ損失防止ポリシー] [ページ>](https://compliance.microsoft.com/compliancesettings) ポリシーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="34403-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="34403-121">![既定Teams DLP ポリシー](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="34403-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="34403-122">既定のポリシーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="34403-122">Edit or delete the default policy</span></span>

<span data-ttu-id="34403-123">パフォーマンス [を向上するために既定のポリシーを](create-test-tune-dlp-policy.md#tune-a-dlp-policy)編集したり、削除したりするには **、DLP コンプライアンス** 管理のアクセス許可を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="34403-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="34403-124">詳細については、「アクセス許可」 [を参照してください](create-test-tune-dlp-policy.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="34403-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

