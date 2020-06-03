---
title: Microsoft の脅威保護のプレビュー機能
description: Microsoft 365 セキュリティの新機能について説明します。
keywords: preview、new、m365 security、security、365、capabilities
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0703aa14bee3d14d1c3ff4fe46ea9d72de73ce2
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515869"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="69f40-104">Microsoft Threat Protection のプレビュー機能</span><span class="sxs-lookup"><span data-stu-id="69f40-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="69f40-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="69f40-105">**Applies to:**</span></span>
- <span data-ttu-id="69f40-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="69f40-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="69f40-107">Microsoft Threat Protection サービスは、新しい機能の拡張と機能を含むように、絶えず更新されています。</span><span class="sxs-lookup"><span data-stu-id="69f40-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="69f40-108">Microsoft Threat Protection プレビューリリースの新機能について説明し、プレビューの操作をオンにして、最初に予定されている機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="69f40-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="69f40-109">一般的に利用可能な新機能の詳細については、「[Microsoft Threat Protection の新機能](whats-new.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f40-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="69f40-110">プレビュー機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="69f40-110">Turn on preview features</span></span>
<span data-ttu-id="69f40-111">機能が一般に利用可能になるまでの全体的な操作を改善するためにフィードバックできる、今後提供される機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="69f40-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="69f40-112">[プレビュー環境] 設定をオンにして、最初の機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="69f40-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="69f40-113">ナビゲーションウィンドウで、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f40-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="69f40-114">[ **Microsoft Threat Protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f40-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="69f40-115">[**プレビュー機能の選択]**  >  **プレビュー機能を有効に**します。</span><span class="sxs-lookup"><span data-stu-id="69f40-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="69f40-116">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69f40-116">Select **Save**.</span></span>

<span data-ttu-id="69f40-117">[**プレビュー機能を有効に**する] チェックボックスがオンになっている場合は、プレビュー機能が有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="69f40-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="69f40-118">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="69f40-118">Preview features</span></span>
<span data-ttu-id="69f40-119">現在、次の機能と拡張機能をプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="69f40-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="69f40-120">**[Id およびアプリテーブル](advanced-hunting-schema-tables.md)**—高度な検索スキーマにある、ユーザーの認証[イベント、Active](advanced-hunting-identityqueryevents-table.md)Directory クエリ、アプリ[関連のアクティビティ](advanced-hunting-identitylogonevents-table.md)に関する可視性を高める[AppFileEvents](advanced-hunting-appfileevents-table.md)ことができます。</span><span class="sxs-lookup"><span data-stu-id="69f40-120">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="69f40-121">**[Emailpostdeliveryevents テーブル](advanced-hunting-emailpostdeliveryevents-table.md)**-この表を使用して、受信者のメールボックスに配信された後に電子メールに対して実行されたアクションを確認する[高度な](advanced-hunting-overview.md)検索クエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="69f40-121">**[EmailPostDeliveryEvents table](advanced-hunting-emailpostdeliveryevents-table.md)** — use this table to create [advanced hunting](advanced-hunting-overview.md) queries that check for actions taken on emails after they have been delivered to recipient mailboxes.</span></span>

- <span data-ttu-id="69f40-122">**[Fileprofile () 関数](advanced-hunting-fileprofile-function.md)**:[高度な](advanced-hunting-overview.md)検索クエリで使用して、包括的なファイル情報を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="69f40-122">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
