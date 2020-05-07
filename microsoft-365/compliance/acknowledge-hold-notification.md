---
title: 保留通知を確認する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 上級電子情報開示を使用して、電子メール経由で法的情報開示通知を送信およびフォローアップしたり、責務の状態を監視したりする方法について説明します。
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034887"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="68e1b-103">保留通知を確認する</span><span class="sxs-lookup"><span data-stu-id="68e1b-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="68e1b-104">法的な要求または調査に対応する際には、保管担当者に、電子情報 (ESI) と、アクティブまたは差し迫った法的事項に関連する可能性がある材料を保持する義務があることを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e1b-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="68e1b-105">送信された法律チームは、各保管担当者が、特定の指示を受信、読み取り、理解し、同意することを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68e1b-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="68e1b-106">高度な電子情報開示は、保管担当者を使用してフォローアップする時間、コスト、労力を減らすために、電子メールで法的情報保持通知を送信してフォローアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="68e1b-107">電子メール通知に加えて、各保管担当者は個別のコンプライアンスポータルにアクセスできるようになり、保管担当者に義務状態の変更を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="68e1b-108">メール通知</span><span class="sxs-lookup"><span data-stu-id="68e1b-108">Email notifications</span></span>

<span data-ttu-id="68e1b-109">法的情報保持通知が発行されると、各保管担当者は、定義された法的情報保留通知および追加の手順を含む固有の個人用の電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="68e1b-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="68e1b-110">組み込みの[コミュニケーションエディター](using-communications-editor.md)を使用して、保管担当者が自分の通知を確認したり、電子メールからコンプライアンスポータルに直接アクセスしたりできるようにする方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e1b-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="68e1b-111">法的情報保留通知の構成に基づいて、保管担当者に次の通知が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="68e1b-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="68e1b-112">**発行通知:** 保管担当者に送信された最初の通知。</span><span class="sxs-lookup"><span data-stu-id="68e1b-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="68e1b-113">この通知には、発行手順と、メッセージの最後に保留通知が追加されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="68e1b-114">通知 **:** 有効にすると、指定された頻度と間隔に基づいて、保管担当者に通知通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="68e1b-115">保管担当者が通知を認知するか、または通知の数が不足するまで、アラームは引き続き送信されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="68e1b-116">**エスカレーションに関する通知:** 有効にした場合、保管担当者にエスカレーション通知が送信され、通知が使用された後に上司に通知されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="68e1b-117">システムは、指定された数のエスカレーションが完了するまで、または保管担当者が保留通知を確認するまで、エスカレーション通知を自動的に送信します。</span><span class="sxs-lookup"><span data-stu-id="68e1b-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="68e1b-118">**再発行通知:** 調査の過程で、保留通知の内容が更新されると、更新された通知が保管担当者に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="68e1b-119">**リリース通知:** 保管担当者がケースからリリースされると、リリース通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="68e1b-120">コンプライアンスポータル</span><span class="sxs-lookup"><span data-stu-id="68e1b-120">Compliance Portal</span></span>

<span data-ttu-id="68e1b-121">電子メール通知に加えて、各保管担当者は固有のコンプライアンスポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="68e1b-122">ポータルを通じて、各保管担当者はアクティブな保留通知を表示、アクセス、および認識できます。</span><span class="sxs-lookup"><span data-stu-id="68e1b-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![保管担当者のコンプライアンスポータル](../media/CustodianPortal.jpg)
