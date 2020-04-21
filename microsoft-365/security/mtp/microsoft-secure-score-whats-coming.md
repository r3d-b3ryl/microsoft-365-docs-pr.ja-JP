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
ms.openlocfilehash: 234ae17ab31d56d1bbd65f1aa8ed29475e9cd155
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583717"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="049e0-104">Microsoft セキュア スコアの新機能</span><span class="sxs-lookup"><span data-stu-id="049e0-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="049e0-105">Microsoft のセキュリティ[スコア](microsoft-secure-score.md)をより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="049e0-105">To make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="049e0-106">お客様のスコアと最大可能スコアが新しくなります。</span><span class="sxs-lookup"><span data-stu-id="049e0-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="049e0-107">ただし、これによりセキュリティ体制が変わるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="049e0-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="049e0-108">最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="049e0-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="049e0-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="049e0-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="049e0-110">改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。</span><span class="sxs-lookup"><span data-stu-id="049e0-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="049e0-111">Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。</span><span class="sxs-lookup"><span data-stu-id="049e0-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="049e0-112">ドキュメントへの IRM による保護の適用</span><span class="sxs-lookup"><span data-stu-id="049e0-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="049e0-113">データ損失防止ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="049e0-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-to-preview"></a><span data-ttu-id="049e0-114">Azure AD 向上アクションをプレビューに追加する</span><span class="sxs-lookup"><span data-stu-id="049e0-114">Adding Azure AD improvement action to preview</span></span>

<span data-ttu-id="049e0-115">[Microsoft Secure Score のプレビューリリース](microsoft-secure-score-preview.md)に、次の Azure Active Directory 改善アクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="049e0-115">Adding the following Azure Active Directory improvement action to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="049e0-116">ユーザーが管理されていないアプリケーションに同意を付与できないようにする (現時点でリリースされているバージョンで利用可能)</span><span class="sxs-lookup"><span data-stu-id="049e0-116">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-to-preview"></a><span data-ttu-id="049e0-117">Azure ATP 向上アクションをプレビューに追加する</span><span class="sxs-lookup"><span data-stu-id="049e0-117">Adding Azure ATP improvement actions to preview</span></span>

<span data-ttu-id="049e0-118">[Microsoft Secure Score のプレビューリリース](microsoft-secure-score-preview.md)に、次の Azure Advanced Threat Protection の向上アクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="049e0-118">Adding the following Azure Advanced Threat Protection improvement actions to the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md):</span></span>

- <span data-ttu-id="049e0-119">ドメインコントローラーで印刷スプーラーサービスを無効にする</span><span class="sxs-lookup"><span data-stu-id="049e0-119">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="049e0-120">セキュリティで保護されていない Kerberos 委任を変更して偽装を防止する</span><span class="sxs-lookup"><span data-stu-id="049e0-120">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="049e0-121">Microsoft LAPS を使用してローカル管理者パスワードを保護および管理する</span><span class="sxs-lookup"><span data-stu-id="049e0-121">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="049e0-122">機密性の高いエンティティに対して、重要な移動パスリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="049e0-122">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="049e0-123">機密グループからの休止アカウントの削除</span><span class="sxs-lookup"><span data-stu-id="049e0-123">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="049e0-124">セキュリティ保護のない SID 履歴属性をエンティティから削除する</span><span class="sxs-lookup"><span data-stu-id="049e0-124">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="049e0-125">安全でないアカウントの属性を解決する</span><span class="sxs-lookup"><span data-stu-id="049e0-125">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="049e0-126">クリアテキストの資格情報の公開を停止する</span><span class="sxs-lookup"><span data-stu-id="049e0-126">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="049e0-127">従来のプロトコル通信を停止する</span><span class="sxs-lookup"><span data-stu-id="049e0-127">Stop legacy protocols communication</span></span>
- <span data-ttu-id="049e0-128">暗号使用率の低い停止</span><span class="sxs-lookup"><span data-stu-id="049e0-128">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-preview"></a><span data-ttu-id="049e0-129">プレビューでの Microsoft Defender ATP の脅威 & 脆弱性管理 (TVM) セキュリティに関する推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="049e0-129">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in preview</span></span>

<span data-ttu-id="049e0-130">また、TVM によって提供されるリリースされたすべてのセキュリティの推奨事項は、 [Microsoft セキュリティスコアのプレビューリリース](microsoft-secure-score-preview.md)でも利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="049e0-130">All released security recommendations supplied by TVM will now also be available the [preview release of Microsoft Secure Score](microsoft-secure-score-preview.md).</span></span>
