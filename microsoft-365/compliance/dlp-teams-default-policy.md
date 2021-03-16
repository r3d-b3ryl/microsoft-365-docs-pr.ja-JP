---
title: Microsoft Teams の既定のデータ損失防止ポリシー (プレビュー) について説明します。
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
description: Microsoft Teams の既定のデータ損失防止ポリシーについて説明します。
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826248"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="03059-103">Microsoft Teams の既定のデータ損失防止ポリシー (プレビュー) について説明します。</span><span class="sxs-lookup"><span data-stu-id="03059-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="03059-104">[データ損失防止](data-loss-prevention-policies.md) (DLP) 機能が拡張され、Microsoft Teams のチャット メッセージとチャネル メッセージ (プライベート チャネル メッセージを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="03059-104">[Data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="03059-105">このリリースの一環として、コンプライアンス センターに初めてお客様向け既定の DLP ポリシーを作成しました。</span><span class="sxs-lookup"><span data-stu-id="03059-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="03059-106">適用対象</span><span class="sxs-lookup"><span data-stu-id="03059-106">Applies to</span></span>

<span data-ttu-id="03059-107">以下の 1 つ以上のライセンスでライセンスを取得し、アクティブな Teams ユーザーを持つテナント</span><span class="sxs-lookup"><span data-stu-id="03059-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="03059-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="03059-108">ME5,</span></span> 
- <span data-ttu-id="03059-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="03059-109">MA5,</span></span> 
- <span data-ttu-id="03059-110">E5/A5 コンプライアンス、</span><span class="sxs-lookup"><span data-stu-id="03059-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="03059-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="03059-111">IP+G,</span></span> 
- <span data-ttu-id="03059-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="03059-112">OE5,</span></span> 
- <span data-ttu-id="03059-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="03059-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="03059-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="03059-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="03059-115">既定のポリシーは何をしますか?</span><span class="sxs-lookup"><span data-stu-id="03059-115">What does the default policy do?</span></span>

<span data-ttu-id="03059-116">既定の DLP ポリシーは、組織に内部および外部で共有されるクレジット カード番号を追跡します。</span><span class="sxs-lookup"><span data-stu-id="03059-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="03059-117">このポリシーは、テナントのすべてのユーザーに対して既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="03059-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="03059-118">エンド ユーザーのポリシー ヒントは生成されませんが、Alert イベントを生成し、管理者 (ポリシーに追加) への重大度の低い電子メールもトリガーします。</span><span class="sxs-lookup"><span data-stu-id="03059-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="03059-119">管理者は、コンプライアンス センターにログインして、アクティビティを表示し、ポリシーの詳細を編集できます。</span><span class="sxs-lookup"><span data-stu-id="03059-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="03059-120">管理者は、コンプライアンス センターの [データ損失防止ポリシー] [ページ>](https://compliance.microsoft.com/compliancesettings) ポリシーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="03059-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="03059-121">![既定の Teams DLP ポリシー](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="03059-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="03059-122">既定のポリシーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="03059-122">Edit or delete the default policy</span></span>

<span data-ttu-id="03059-123">パフォーマンス [を向上するために既定のポリシーを](create-test-tune-dlp-policy.md#tune-a-dlp-policy)編集したり、削除したりするには **、DLP コンプライアンス** 管理のアクセス許可を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="03059-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="03059-124">詳細については、「アクセス許可」 [を参照してください](create-test-tune-dlp-policy.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="03059-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

