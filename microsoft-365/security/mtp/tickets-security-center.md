---
title: Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する
description: Microsoft 365 セキュリティセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
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
ms.openlocfilehash: f0aadbf2dbf8cb8d9815b4ef8b1c8d3d892c8b31
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588531"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="92a46-104">Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する</span><span class="sxs-lookup"><span data-stu-id="92a46-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="92a46-105">**ServiceNow コネクタのプレビュー期間が終了しました**</span><span class="sxs-lookup"><span data-stu-id="92a46-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="92a46-106">この機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="92a46-106">This capability is no longer available.</span></span> <span data-ttu-id="92a46-107">フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。</span><span class="sxs-lookup"><span data-stu-id="92a46-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="92a46-108">[Microsoft 365 セキュリティセンター](overview-security-center.md)は、ServiceNow のチケットをネイティブに作成および追跡する機能によって強化されました。</span><span class="sxs-lookup"><span data-stu-id="92a46-108">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="92a46-109">ServiceNow の詳細情報</span><span class="sxs-lookup"><span data-stu-id="92a46-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="92a46-110">セキュリティセンターでは、セキュリティ管理者が Microsoft のセキュリティ [で保護されたスコア](microsoft-secure-score.md) 向上アクションを ServiceNow に直接送信して、チケットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="92a46-110">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="92a46-111">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="92a46-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="92a46-112">セキュリティセンターのホームページと ServiceNow のチケットを追跡します。</span><span class="sxs-lookup"><span data-stu-id="92a46-112">Track tickets in the security center home page and ServiceNow.</span></span>

