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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541109"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="d5a11-104">Microsoft セキュア スコアの新機能</span><span class="sxs-lookup"><span data-stu-id="d5a11-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="d5a11-105">お客様により優れたセキュリティ体制を提供し、使いやすさを向上させるために、Microsoft セキュア スコアは近日中に変化が加えられます。</span><span class="sxs-lookup"><span data-stu-id="d5a11-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="d5a11-106">お客様のスコアと最大可能スコアが新しくなります。</span><span class="sxs-lookup"><span data-stu-id="d5a11-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="d5a11-107">ただし、これによりセキュリティ体制が変わるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d5a11-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="d5a11-108">最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5a11-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="april-21st-2020"></a><span data-ttu-id="d5a11-109">2020年4月21日</span><span class="sxs-lookup"><span data-stu-id="d5a11-109">April 21st 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="d5a11-110">改善アクションのうち、信頼できる測定としての条件を満たさないもの、またはセキュリティ体制の形として有用でないものは、削除しています。</span><span class="sxs-lookup"><span data-stu-id="d5a11-110">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="d5a11-111">Microsoft セキュリティ スコアが有意義であり、すべての改善アクションが測定可能かつ信頼性の高いものになるよう、次の改善アクションについては削除します。</span><span class="sxs-lookup"><span data-stu-id="d5a11-111">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="d5a11-112">ドキュメントへの IRM による保護の適用</span><span class="sxs-lookup"><span data-stu-id="d5a11-112">Apply IRM protections to documents</span></span>
- <span data-ttu-id="d5a11-113">データ損失防止ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="d5a11-113">Apply Data Loss Prevention policies</span></span>

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a><span data-ttu-id="d5a11-114">プレビューバージョンでの Azure AD 向上アクションの追加</span><span class="sxs-lookup"><span data-stu-id="d5a11-114">Adding Azure AD improvement action in the preview version</span></span>

- <span data-ttu-id="d5a11-115">ユーザーが管理されていないアプリケーションに同意を付与できないようにする (現時点でリリースされているバージョンで利用可能)</span><span class="sxs-lookup"><span data-stu-id="d5a11-115">Do not allow users to grant consent to unmanaged applications (currently available in released version)</span></span>

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a><span data-ttu-id="d5a11-116">プレビューバージョンでの Azure ATP 向上アクションの追加</span><span class="sxs-lookup"><span data-stu-id="d5a11-116">Adding Azure ATP improvement actions in the preview version</span></span>

- <span data-ttu-id="d5a11-117">ドメインコントローラーで印刷スプーラーサービスを無効にする</span><span class="sxs-lookup"><span data-stu-id="d5a11-117">Disable Print spooler service on domain controllers</span></span>
- <span data-ttu-id="d5a11-118">セキュリティで保護されていない Kerberos 委任を変更して偽装を防止する</span><span class="sxs-lookup"><span data-stu-id="d5a11-118">Modify unsecure Kerberos delegations to prevent impersonation</span></span>
- <span data-ttu-id="d5a11-119">Microsoft LAPS を使用してローカル管理者パスワードを保護および管理する</span><span class="sxs-lookup"><span data-stu-id="d5a11-119">Protect and manage local admin passwords with Microsoft LAPS</span></span>
- <span data-ttu-id="d5a11-120">機密性の高いエンティティに対して、重要な移動パスリスクを軽減する</span><span class="sxs-lookup"><span data-stu-id="d5a11-120">Reduce lateral movement path risk to sensitive entities</span></span>
- <span data-ttu-id="d5a11-121">機密グループからの休止アカウントの削除</span><span class="sxs-lookup"><span data-stu-id="d5a11-121">Remove dormant accounts from sensitive groups</span></span>
- <span data-ttu-id="d5a11-122">セキュリティ保護のない SID 履歴属性をエンティティから削除する</span><span class="sxs-lookup"><span data-stu-id="d5a11-122">Remove unsecure SID history attributes from entities</span></span>
- <span data-ttu-id="d5a11-123">安全でないアカウントの属性を解決する</span><span class="sxs-lookup"><span data-stu-id="d5a11-123">Resolve unsecure account attributes</span></span>
- <span data-ttu-id="d5a11-124">クリアテキストの資格情報の公開を停止する</span><span class="sxs-lookup"><span data-stu-id="d5a11-124">Stop clear text credentials exposure</span></span>
- <span data-ttu-id="d5a11-125">従来のプロトコル通信を停止する</span><span class="sxs-lookup"><span data-stu-id="d5a11-125">Stop legacy protocols communication</span></span>
- <span data-ttu-id="d5a11-126">暗号使用率の低い停止</span><span class="sxs-lookup"><span data-stu-id="d5a11-126">Stop weak cipher usage</span></span>

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a><span data-ttu-id="d5a11-127">プレビューバージョンでの Microsoft Defender ATP & 脆弱性管理 (TVM) セキュリティ推奨事項のサポート</span><span class="sxs-lookup"><span data-stu-id="d5a11-127">Support for Microsoft Defender ATP Threat & Vulnerability Management (TVM) security recommendations in the preview version</span></span>

- <span data-ttu-id="d5a11-128">リリースされた TVM で提供されるすべてのセキュリティの推奨事項は、Microsoft セキュリティスコアでも利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d5a11-128">All released security recommendations supplied by TVM will now also be available in Microsoft Secure Score</span></span>
