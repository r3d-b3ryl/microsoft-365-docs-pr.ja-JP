---
title: ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する
description: Microsoft 365 セキュリティセンターおよびコンプライアンスセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, コンプライアンス, コンプライアンスセンター, セキュリティセンター, ServiceNow, チケット, tasks, 雪, connection
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
ms.openlocfilehash: 1d629de983e73258e491f18f7a34403d6f522520
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588543"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="e4bad-104">ServiceNow チケットを Microsoft 365 セキュリティセンターおよびコンプライアンスセンターに統合する</span><span class="sxs-lookup"><span data-stu-id="e4bad-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="e4bad-105">**ServiceNow コネクタのプレビュー期間が終了しました**</span><span class="sxs-lookup"><span data-stu-id="e4bad-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="e4bad-106">この機能は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e4bad-106">This capability is no longer available.</span></span> <span data-ttu-id="e4bad-107">フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。</span><span class="sxs-lookup"><span data-stu-id="e4bad-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="e4bad-108">ServiceNow は、企業がエンタープライズ運用のためにデジタルワークフローを管理するのに役立つ、よく使用されるクラウドコンピューティングプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="e4bad-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="e4bad-109">現在、プラットフォームは IT ワークフロー、従業員ワークフロー、および顧客ワークフローを備えています。</span><span class="sxs-lookup"><span data-stu-id="e4bad-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="e4bad-110">ServiceNow の詳細情報</span><span class="sxs-lookup"><span data-stu-id="e4bad-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="e4bad-111">Microsoft は、お客様が ServiceNow と提携して、IT 管理者が両方のプラットフォームでチケットとタスクを簡単に管理できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="e4bad-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="e4bad-112">[Microsoft 365 セキュリティセンター](overview-security-center.md) と [microsoft 365 コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) では、ServiceNow でチケットをネイティブに作成および追跡する機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="e4bad-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>
