---
title: Microsoft のセキュリティで保護されたスコア
description: Microsoft 365 セキュリティセンターで Microsoft セキュリティスコアに追加された新しい変更内容について説明します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
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
ms.openlocfilehash: e42c65fdb4d409c1da7b85fbe7eca13170b9b974
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409235"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="40847-104">Microsoft のセキュリティで保護されたスコア</span><span class="sxs-lookup"><span data-stu-id="40847-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="40847-105">Microsoft セキュリティスコアは https://security.microsoft.com/securescore 、 [microsoft 365 セキュリティセンター](overview-security-center.md)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="40847-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="40847-106">Proposed changes</span><span class="sxs-lookup"><span data-stu-id="40847-106">Proposed changes</span></span>

<span data-ttu-id="40847-107">弊社では、セキュリティ上の姿勢をより良いものにするために、近日中に変更を行っており、利便性を向上 [さ](microsoft-secure-score.md) せています。</span><span class="sxs-lookup"><span data-stu-id="40847-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="40847-108">スコアと可能な最大スコアは変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40847-108">Your score and the maximum possible score may change.</span></span>

### <a name="december-2020"></a><span data-ttu-id="40847-109">2020年12月</span><span class="sxs-lookup"><span data-stu-id="40847-109">December 2020</span></span>

<span data-ttu-id="40847-110">エンドポイント (以前の Microsoft Defender ATP) に対する Microsoft Defender のアカウント関連の改善アクションを6つ追加します。</span><span class="sxs-lookup"><span data-stu-id="40847-110">Adding 6 accounts-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="40847-111">' Minimum password length ' を ' 14 以上の文字 ' に設定します</span><span class="sxs-lookup"><span data-stu-id="40847-111">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="40847-112">[パスワードの履歴を強制する] を [24 以上のパスワード] に設定します。</span><span class="sxs-lookup"><span data-stu-id="40847-112">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="40847-113">' 最大パスワードの有効期間 ' を ' 60 以下に設定し、0以外の日数を設定します。</span><span class="sxs-lookup"><span data-stu-id="40847-113">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="40847-114">' Minimum password age ' を ' 1 またはそれ以上 ' 日 ' に設定します</span><span class="sxs-lookup"><span data-stu-id="40847-114">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="40847-115">組み込みの管理者アカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="40847-115">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="40847-116">組み込みのゲストアカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="40847-116">Disable the built-in Guest account</span></span>

### <a name="november-2020"></a><span data-ttu-id="40847-117">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="40847-117">November 2020</span></span>

#### <a name="removing-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="40847-118">セキュリティで保護されたスコアで ServiceNow チケットを作成する機能を削除する</span><span class="sxs-lookup"><span data-stu-id="40847-118">Removing the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="40847-119">**> servicenow を共有** することによって、セキュリティで保護されたスコアで servicenow チケットを作成する機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="40847-119">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** will be removed.</span></span>

<span data-ttu-id="40847-120">ServiceNow コネクタのプレビュー期間が終了します。</span><span class="sxs-lookup"><span data-stu-id="40847-120">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="40847-121">この機能は、2020の終わりまでは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="40847-121">This capability will no longer be available by the end of 2020.</span></span> <span data-ttu-id="40847-122">フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。</span><span class="sxs-lookup"><span data-stu-id="40847-122">Thank you for your feedback and continued support while we determine next steps.</span></span>

## <a name="related-resources"></a><span data-ttu-id="40847-123">関連リソース</span><span class="sxs-lookup"><span data-stu-id="40847-123">Related resources</span></span>

- [<span data-ttu-id="40847-124">Microsoft セキュリティスコアの概要</span><span class="sxs-lookup"><span data-stu-id="40847-124">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="40847-125">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="40847-125">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="40847-126">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="40847-126">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="40847-127">新機能</span><span class="sxs-lookup"><span data-stu-id="40847-127">What's new</span></span>](microsoft-secure-score-whats-new.md)
