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
description: 電子メールを介してAdvanced eDiscoveryホールド通知を送信およびフォローアップする方法、および義務の状態を監視する方法について学習します。
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034887"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="05360-103">保留通知を確認する</span><span class="sxs-lookup"><span data-stu-id="05360-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="05360-104">規制の要求や調査に対応する場合、電子的に保存された情報 (ESI) と、アクティブまたは差し迫った法的問題に関連する可能性のある資料を保管担当者に通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05360-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="05360-105">送信後、法務チームは、各保管担当者が指定された指示に従って受け取り、読み取り、理解し、同意したと知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="05360-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="05360-106">保管担当者のフォローアップの時間、コスト、労力を削減するために、Advanced eDiscovery を使用すると、電子メールを介して法的ホールド通知を送信およびフォローアップできます。</span><span class="sxs-lookup"><span data-stu-id="05360-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="05360-107">電子メール通知に加えて、各保管担当者は個別のコンプライアンス ポータルにアクセスでき、保管担当者は自分の義務状態の変更を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="05360-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="05360-108">メール通知</span><span class="sxs-lookup"><span data-stu-id="05360-108">Email notifications</span></span>

<span data-ttu-id="05360-109">法的保持通知が発行された後、各保管担当者は、定義された法的保持通知と追加された手順を含む、一意でパーソナライズされた電子メールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="05360-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="05360-110">組み込みのコミュニケーション エディターを使用[](using-communications-editor.md)して、保管担当者が通知を確認したり、メールから直接コンプライアンス ポータルにアクセスしたりする方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="05360-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="05360-111">法的保持通知の構成に基づいて、保管担当者は次の通知を受け取る場合があります。</span><span class="sxs-lookup"><span data-stu-id="05360-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="05360-112">**発行通知:** 保管担当者に送信された最初の通知。</span><span class="sxs-lookup"><span data-stu-id="05360-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="05360-113">この通知には、メッセージの最後に発行手順と保留通知が追加されます。</span><span class="sxs-lookup"><span data-stu-id="05360-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="05360-114">**アラーム通知:** 有効にすると、指定した頻度と間隔に基づいて、保管担当者に通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="05360-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="05360-115">リマインダーは、保管担当者が通知を確認するまで、またはリマインダーの数が使い果たされるまで送信されます。</span><span class="sxs-lookup"><span data-stu-id="05360-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="05360-116">**エスカレーション通知:** 有効にすると、アラーム通知が使い果たされた後、エスカレーション通知が保管担当者とそのマネージャーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="05360-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="05360-117">エスカレーションが完了するまで、または保管担当者が保留通知を承認するまで、システムはエスカレーション通知を自動的に送信します。</span><span class="sxs-lookup"><span data-stu-id="05360-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="05360-118">**再発行に関する通知:** 調査の過程で、保留通知の内容が更新された場合、更新された通知は自動的に保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="05360-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="05360-119">**リリース通知:** カストディアンがケースから解放されると、リリース通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="05360-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="05360-120">コンプライアンス ポータル</span><span class="sxs-lookup"><span data-stu-id="05360-120">Compliance Portal</span></span>

<span data-ttu-id="05360-121">電子メール通知に加えて、各保管担当者は一意のコンプライアンス ポータルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="05360-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="05360-122">ポータルを通じて、各保管担当者はアクティブな保留通知を表示、アクセス、および確認できます。</span><span class="sxs-lookup"><span data-stu-id="05360-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![保管担当者のコンプライアンス ポータル](../media/CustodianPortal.jpg)
