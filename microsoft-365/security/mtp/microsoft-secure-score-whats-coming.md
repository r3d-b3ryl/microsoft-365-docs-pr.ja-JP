---
title: Microsoft のセキュリティで保護されたスコアについて
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコア、詳細情報の計算方法、およびセキュリティ管理者が期待できるセキュリティについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティで保護されたスコア、セキュリティセンター、改善アクション
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372005"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="a6df4-104">Microsoft のセキュリティで保護されたスコアについて</span><span class="sxs-lookup"><span data-stu-id="a6df4-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="a6df4-105">Microsoft のセキュリティスコアをより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="a6df4-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="a6df4-106">スコアと可能な最大スコアが変わります。</span><span class="sxs-lookup"><span data-stu-id="a6df4-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="a6df4-107">ただし、これはセキュリティに関する姿勢の変化を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="a6df4-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="a6df4-108">最近の変更については、「 [Microsoft のセキュリティで保護されたスコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6df4-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="a6df4-109">2020年3月16日</span><span class="sxs-lookup"><span data-stu-id="a6df4-109">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="a6df4-110">信頼性の高い測定要件を満たしていない、またはセキュリティに関する有益な表現を提供していない改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="a6df4-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="a6df4-111">マイクロソフトのセキュリティスコアが意味があり、すべての改善アクションが測定可能で信頼性を備えていることを確認するために、次の改善アクションを削除しています。</span><span class="sxs-lookup"><span data-stu-id="a6df4-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="a6df4-112">OneDrive for business でユーザーのドキュメントを保存する</span><span class="sxs-lookup"><span data-stu-id="a6df4-112">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="a6df4-113">Office 365 の ATP の安全な添付ファイルポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a6df4-113">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="a6df4-114">Office 365 の安全なリンクを設定して Url を確認する</span><span class="sxs-lookup"><span data-stu-id="a6df4-114">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="a6df4-115">メールボックスの委任を許可しない</span><span class="sxs-lookup"><span data-stu-id="a6df4-115">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="a6df4-116">サイトおよびドキュメントの匿名ゲスト共有リンクを許可する</span><span class="sxs-lookup"><span data-stu-id="a6df4-116">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="a6df4-117">Cloud App Security コンソールを有効にする</span><span class="sxs-lookup"><span data-stu-id="a6df4-117">Turn on Cloud App Security Console</span></span>
- <span data-ttu-id="a6df4-118">外部共有リンクの有効期限を構成する</span><span class="sxs-lookup"><span data-stu-id="a6df4-118">Configure expiration time for external sharing links</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="a6df4-119">Azure AD 向上アクションのセキュリティの既定のサポート</span><span class="sxs-lookup"><span data-stu-id="a6df4-119">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="a6df4-120">Microsoft Secure Score は、強化された操作を更新して[AZURE AD のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートします。これにより、一般的な攻撃のために事前に構成されたセキュリティ設定を使用して組織を保護することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="a6df4-120">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="a6df4-121">次の改善アクションに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a6df4-121">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="a6df4-122">すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする</span><span class="sxs-lookup"><span data-stu-id="a6df4-122">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="a6df4-123">管理役割に MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="a6df4-123">Require MFA for administrative roles</span></span>
- <span data-ttu-id="a6df4-124">従来の認証をブロックするポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="a6df4-124">Enable policy to block legacy authentication</span></span>
