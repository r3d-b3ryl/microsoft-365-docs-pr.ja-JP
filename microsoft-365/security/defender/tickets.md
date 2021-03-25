---
title: ServiceNow チケットを Microsoft 365 セキュリティ センターとコンプライアンス センターに統合する
description: Microsoft 365 セキュリティ センターとコンプライアンス センターから ServiceNow でチケットを作成および追跡する方法について説明します。
keywords: セキュリティ、Microsoft 365、M365、コンプライアンス、コンプライアンス センター、セキュリティ センター、ServiceNow、チケット、タスク、SNOW、接続
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: b52b97bf33b2164a82906bec53bed361885facd5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068603"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="86c3e-104">ServiceNow チケットを Microsoft 365 セキュリティ センターとコンプライアンス センターに統合する</span><span class="sxs-lookup"><span data-stu-id="86c3e-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="86c3e-105">**ServiceNow コネクタのプレビュー期間が終了しました**</span><span class="sxs-lookup"><span data-stu-id="86c3e-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="86c3e-106">この機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="86c3e-106">This capability is no longer available.</span></span> <span data-ttu-id="86c3e-107">次の手順を決定する間、フィードバックと継続的なサポートに感謝します。</span><span class="sxs-lookup"><span data-stu-id="86c3e-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="86c3e-108">ServiceNow は、企業が企業の運用のためのデジタル ワークフローを管理するのに役立つ一般的なクラウド コンピューティング プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="86c3e-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="86c3e-109">Now プラットフォームには、IT ワークフロー、従業員ワークフロー、および顧客ワークフローがあります。</span><span class="sxs-lookup"><span data-stu-id="86c3e-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span>