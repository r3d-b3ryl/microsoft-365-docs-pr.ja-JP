---
title: 高度な検索スキーマの EmailPostDeliveryEvents テーブル
description: 高度な検索スキーマの EmailPostDeliveryEvents テーブルで Microsoft 365 メールに対して実行された配信後の処理について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、EmailPostDeliveryEvents、network message id、sender、recipient、attachment id、添付ファイル名、マルウェア verdict、フィッシング verdict
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198015"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="01d45-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="01d45-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01d45-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="01d45-105">**Applies to:**</span></span>
- <span data-ttu-id="01d45-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="01d45-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="01d45-107">`EmailPostDeliveryEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft 365 によって処理された電子メールメッセージに対して実行された配信後の処理に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="01d45-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="01d45-108">このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="01d45-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="01d45-109">テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="01d45-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="01d45-110">個々の電子メールメッセージに関する詳細情報を取得するには、、、およびの表を使用することもでき [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) ます。</span><span class="sxs-lookup"><span data-stu-id="01d45-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="01d45-111">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01d45-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="01d45-112">列名</span><span class="sxs-lookup"><span data-stu-id="01d45-112">Column name</span></span> | <span data-ttu-id="01d45-113">データ型</span><span class="sxs-lookup"><span data-stu-id="01d45-113">Data type</span></span> | <span data-ttu-id="01d45-114">説明</span><span class="sxs-lookup"><span data-stu-id="01d45-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="01d45-115">日付型</span><span class="sxs-lookup"><span data-stu-id="01d45-115">datetime</span></span> | <span data-ttu-id="01d45-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="01d45-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="01d45-117">文字列</span><span class="sxs-lookup"><span data-stu-id="01d45-117">string</span></span> | <span data-ttu-id="01d45-118">イベントの一意識別子</span><span class="sxs-lookup"><span data-stu-id="01d45-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="01d45-119">文字列</span><span class="sxs-lookup"><span data-stu-id="01d45-119">string</span></span> | <span data-ttu-id="01d45-120">Microsoft 365 によって生成される電子メールの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="01d45-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="01d45-121">string</span><span class="sxs-lookup"><span data-stu-id="01d45-121">string</span></span> | <span data-ttu-id="01d45-122">送信メール システムにより設定された、メールの一般向けの識別子</span><span class="sxs-lookup"><span data-stu-id="01d45-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="01d45-123">string</span><span class="sxs-lookup"><span data-stu-id="01d45-123">string</span></span> | <span data-ttu-id="01d45-124">エンティティに対して実行されたアクション</span><span class="sxs-lookup"><span data-stu-id="01d45-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="01d45-125">文字列</span><span class="sxs-lookup"><span data-stu-id="01d45-125">string</span></span> | <span data-ttu-id="01d45-126">イベントをトリガーしたアクティビティの種類: 手動による修復、フィッシング ZAP、マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="01d45-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="01d45-127">文字列</span><span class="sxs-lookup"><span data-stu-id="01d45-127">string</span></span> | <span data-ttu-id="01d45-128">アクションが管理者によってトリガーされたかどうか (手動または保留中の自動アクションの承認)、または ZAP または動的配信などの特別なメカニズムによって発生したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="01d45-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="01d45-129">文字列</span><span class="sxs-lookup"><span data-stu-id="01d45-129">string</span></span> | <span data-ttu-id="01d45-130">アクションの結果</span><span class="sxs-lookup"><span data-stu-id="01d45-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="01d45-131">string</span><span class="sxs-lookup"><span data-stu-id="01d45-131">string</span></span> | <span data-ttu-id="01d45-132">受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス</span><span class="sxs-lookup"><span data-stu-id="01d45-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="01d45-133">string</span><span class="sxs-lookup"><span data-stu-id="01d45-133">string</span></span> | <span data-ttu-id="01d45-134">メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム</span><span class="sxs-lookup"><span data-stu-id="01d45-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="01d45-135">サポートされるイベントの種類</span><span class="sxs-lookup"><span data-stu-id="01d45-135">Supported event types</span></span>
<span data-ttu-id="01d45-136">このテーブルは、次の値を持つイベントをキャプチャし `ActionType` ます。</span><span class="sxs-lookup"><span data-stu-id="01d45-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="01d45-137">**手動による修復** –管理者は、ユーザーのメールボックスに配信された後に、電子メールメッセージに対して手動でアクションを実行していました。</span><span class="sxs-lookup"><span data-stu-id="01d45-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="01d45-138">これには、 [脅威エクスプローラー](../office-365-security/threat-explorer.md) を使用して手動で行う操作や、自動化された [調査と応答 (AIR) アクション](mtp-autoir-actions.md)の承認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01d45-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="01d45-139">**フィッシング ZAP** – [ゼロ時間自動削除 (ZAP)](../office-365-security/zero-hour-auto-purge.md) は、配信後にフィッシング電子メールに対してアクションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="01d45-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="01d45-140">**マルウェア ZAP** –ゼロ時間自動削除 (ZAP) は、配信後にマルウェアを含む電子メールメッセージに対してアクションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="01d45-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01d45-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="01d45-141">Related topics</span></span>
- [<span data-ttu-id="01d45-142">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="01d45-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01d45-143">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="01d45-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="01d45-144">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="01d45-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="01d45-145">デバイス、メール、アプリ、ID 間での捜索</span><span class="sxs-lookup"><span data-stu-id="01d45-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="01d45-146">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="01d45-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="01d45-147">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="01d45-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
