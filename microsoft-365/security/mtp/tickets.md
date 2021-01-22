---
title: ServiceNow チケットを Microsoft 365 セキュリティ センターとコンプライアンス センターに統合する
description: Microsoft 365 セキュリティ センターとコンプライアンス センターから ServiceNow でチケットを作成および追跡する方法について説明します。
keywords: セキュリティ, Microsoft 365, M365, コンプライアンス, コンプライアンス センター, セキュリティ センター, ServiceNow, チケット, タスク,NOW, 接続
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
ms.openlocfilehash: 4e647c2e526bb5cf99b1f40c07fc542315ebcd01
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925484"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="52062-104">ServiceNow チケットを Microsoft 365 セキュリティ センターとコンプライアンス センターに統合する</span><span class="sxs-lookup"><span data-stu-id="52062-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="52062-105">**ServiceNow コネクタのプレビュー期間が終了しました**</span><span class="sxs-lookup"><span data-stu-id="52062-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="52062-106">この機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="52062-106">This capability is no longer available.</span></span> <span data-ttu-id="52062-107">次の手順を決定する間、フィードバックと継続的なサポートに感謝します。</span><span class="sxs-lookup"><span data-stu-id="52062-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="52062-108">ServiceNow は、企業がエンタープライズ運用のデジタル ワークフローを管理するのに役立つ、人気のあるクラウド コンピューティング プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="52062-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="52062-109">現在のプラットフォームには、IT ワークフロー、従業員ワークフロー、および顧客ワークフローがあります。</span><span class="sxs-lookup"><span data-stu-id="52062-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="52062-110">ServiceNow の詳細</span><span class="sxs-lookup"><span data-stu-id="52062-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="52062-111">Microsoft は ServiceNow と提携して、IT 管理者が両方のプラットフォームでチケットとタスクを簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="52062-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="52062-112">[Microsoft 365](overview-security-center.md) セキュリティ センターと [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターは、ServiceNow でチケットをネイティブに作成および追跡する機能によって強化されています。</span><span class="sxs-lookup"><span data-stu-id="52062-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>
