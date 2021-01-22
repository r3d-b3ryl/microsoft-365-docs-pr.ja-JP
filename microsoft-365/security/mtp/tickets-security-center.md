---
title: Microsoft 365 セキュリティ センターで ServiceNow チケットを作成および追跡する
description: Microsoft 365 セキュリティ センターから ServiceNow でチケットを作成および追跡する方法について説明します。
keywords: セキュリティ, Microsoft 365, M365, セキュア スコア, セキュリティ センター, ServiceNow, チケット, タスク
ms.prod: m365-security
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
ms.custom:
- seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 3df24e01df0436f6b5824917c91dc4e7c4ee984c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925496"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="14267-104">Microsoft 365 セキュリティ センターで ServiceNow チケットを作成および追跡する</span><span class="sxs-lookup"><span data-stu-id="14267-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="14267-105">**ServiceNow コネクタのプレビュー期間が終了しました**</span><span class="sxs-lookup"><span data-stu-id="14267-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="14267-106">この機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="14267-106">This capability is no longer available.</span></span> <span data-ttu-id="14267-107">次の手順を決定する間、フィードバックと継続的なサポートに感謝します。</span><span class="sxs-lookup"><span data-stu-id="14267-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="14267-108">[Microsoft 365 セキュリティ](overview-security-center.md)センターは、ServiceNow でチケットをネイティブに作成および追跡する機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="14267-108">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="14267-109">ServiceNow の詳細</span><span class="sxs-lookup"><span data-stu-id="14267-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="14267-110">セキュリティ センターでは、セキュリティ管理者は Microsoft [セキュア](microsoft-secure-score.md) スコア向上アクションを ServiceNow に直接送信し、チケットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="14267-110">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="14267-111">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="14267-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="14267-112">セキュリティ センターのホーム ページと ServiceNow でチケットを追跡します。</span><span class="sxs-lookup"><span data-stu-id="14267-112">Track tickets in the security center home page and ServiceNow.</span></span>

