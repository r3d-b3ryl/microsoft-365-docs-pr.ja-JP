---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372005"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="5e531-104">Microsoft セキュア スコアの新機能</span><span class="sxs-lookup"><span data-stu-id="5e531-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="5e531-105">お客様により優れたセキュリティ体制を提供し、使いやすさを向上させるために、Microsoft セキュア スコアは近日中に変化が加えられます。</span><span class="sxs-lookup"><span data-stu-id="5e531-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="5e531-106">お客様のスコアと最大可能スコアが新しくなります。</span><span class="sxs-lookup"><span data-stu-id="5e531-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="5e531-107">ただし、これによりセキュリティ体制が変わるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="5e531-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="5e531-108">最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e531-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="5e531-109">2020 年 3 月 16 日</span><span class="sxs-lookup"><span data-stu-id="5e531-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="5e531-110">改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。</span><span class="sxs-lookup"><span data-stu-id="5e531-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="5e531-111">Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。</span><span class="sxs-lookup"><span data-stu-id="5e531-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="5e531-112">OneDrive for Business でユーザー ドキュメントを保存する</span><span class="sxs-lookup"><span data-stu-id="5e531-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="5e531-113">Office 365 ATP の安全な添付ファイルに関するポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="5e531-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="5e531-114">Office 365 の安全なリンクをセットアップして URL を確認する</span><span class="sxs-lookup"><span data-stu-id="5e531-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="5e531-115">メールボックスの委任を許可しない</span><span class="sxs-lookup"><span data-stu-id="5e531-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="5e531-116">サイトとドキュメントの匿名ゲストの共有リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="5e531-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="5e531-117">Cloud App Security コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="5e531-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="5e531-118">外部共有リンクの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="5e531-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="5e531-119">Azure AD の改善アクションに関するセキュリティの既定群をサポートする</span><span class="sxs-lookup"><span data-stu-id="5e531-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="5e531-120">Microsoft セキュア スコアは、[Azure AD のセキュリティの既定群](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションを更新します。これにより、構成済みのセキュリティ設定を使用して、一般的な攻撃から組織を保護することが簡単にできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5e531-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="5e531-121">これは、次の改善アクションに影響します。</span><span class="sxs-lookup"><span data-stu-id="5e531-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="5e531-122">安全なアクセスのため、すべてのユーザーが多要素認証を行えるようにする</span><span class="sxs-lookup"><span data-stu-id="5e531-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="5e531-123">管理者の役割に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="5e531-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="5e531-124">レガシ認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="5e531-124">Enable policy to block legacy authentication</span></span>
