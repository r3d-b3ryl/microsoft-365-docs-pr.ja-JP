---
title: ポータル内のMicrosoft 365 Defender
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
localization_priority: Normal
search.appverid:
- MOE150
- MET150
- BCS160
ms.assetid: 2bb4e7c0-5f7f-4144-b647-cc6a956aaa53
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 詳細なアラートの管理など、Microsoft 365 Defenderポータルでアラート機能を使用してアラートを表示および管理する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44009ac90dddf9a8f901fdcc5d46496e4bc78338
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108285"
---
# <a name="alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="0cb7e-103">ポータル内のMicrosoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cb7e-103">Alerts in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0cb7e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0cb7e-104">**Applies to**</span></span>
- [<span data-ttu-id="0cb7e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0cb7e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0cb7e-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0cb7e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="0cb7e-107">Microsoft 365 Defender ポータルのアラート機能を使用して、組織のアラートを表示および管理します。詳細な通知は、組織の概要の一部としてMicrosoft Cloud App Security[します](/cloud-app-security/what-is-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-107">Use the alerts features in the Microsoft 365 Defender portal to view and manage alerts for your organization, including managing advanced alerts as part of [Microsoft Cloud App Security overview](/cloud-app-security/what-is-cloud-app-security).</span></span>

## <a name="how-to-get-to-the-alerts-features"></a><span data-ttu-id="0cb7e-108">アラート機能を取得する方法</span><span class="sxs-lookup"><span data-stu-id="0cb7e-108">How to get to the alerts features</span></span>

<span data-ttu-id="0cb7e-109">アラートは、Microsoft 365 Defenderポータル ( ) に表示されます <https://security.microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-109">Alerts are in the Microsoft 365 Defender portal (<https://security.microsoft.com>).</span></span> <span data-ttu-id="0cb7e-110">ページにアクセスする方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-110">Here's how to get to the page:</span></span>

<span data-ttu-id="0cb7e-111">ポータルで **、[Microsoft 365 Defender]** に **移動します**。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-111">In the **Microsoft 365 Defender portal**, go to **Alerts**.</span></span> <span data-ttu-id="0cb7e-112">または、[アラート] ページに直接移動 **するには** 、 を使用します <https://security.microsoft.com/alerts> 。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-112">Or, to go direct to the **Alerts** page, use <https://security.microsoft.com/alerts>.</span></span>

## <a name="alerts-features"></a><span data-ttu-id="0cb7e-113">アラート機能</span><span class="sxs-lookup"><span data-stu-id="0cb7e-113">Alerts features</span></span>

<span data-ttu-id="0cb7e-114">次の表に、ポータルの [アラート] で **使用できるツール** Microsoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-114">The following table describes the tools that are available under **Alerts** in the Microsoft 365 Defender portal.</span></span>

<br>

****

|<span data-ttu-id="0cb7e-115">ツール</span><span class="sxs-lookup"><span data-stu-id="0cb7e-115">Tool</span></span>|<span data-ttu-id="0cb7e-116">説明</span><span class="sxs-lookup"><span data-stu-id="0cb7e-116">Description</span></span>|
|---|---|
|[<span data-ttu-id="0cb7e-117">アラートの管理</span><span class="sxs-lookup"><span data-stu-id="0cb7e-117">Manage alerts</span></span>](../../compliance/create-activity-alerts.md)|<span data-ttu-id="0cb7e-118">アクティビティ通知を使用して、ユーザーが特定のアクティビティを実行するときに、ユーザーまたは他の管理者に電子メール通知を送信Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-118">Use activity alerts to send email notifications to yourself or other admins when users perform specific activities in Microsoft 365.</span></span> <span data-ttu-id="0cb7e-119">アクティビティアラートは、イベントの監査ログの検索に似ていますが、アラートを作成したイベントが発生すると電子メール メッセージが送信される点を除きます。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-119">Activity alerts are similar to searching the audit log for events, except that you'll be sent an email message when an event that you've created an alert for occurs.</span></span>|
|[<span data-ttu-id="0cb7e-120">高度なアラートの管理</span><span class="sxs-lookup"><span data-stu-id="0cb7e-120">Manage advanced alerts</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="0cb7e-121">Microsoft 365 Cloud App Security **の** 高度なアラートの管理機能を使用して、疑わしいアクティビティや異常なアクティビティを通知するポリシーをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-121">Use the **Manage advanced alerts** feature of Microsoft 365 Cloud App Security to set up policies that can alert you to suspicious and anomalous activity in Microsoft 365.</span></span> <span data-ttu-id="0cb7e-122">警告が表示された後は、問題が発生する可能性がある状況を調査し、必要に応じてセキュリティの問題に対処するアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0cb7e-122">After you're alerted, you can investigate situations that are potentially problematic and, if needed, take action to address security issues.</span></span>|
|
