---
title: サード パーティのデータをアーカイブする
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 メールボックスにサードパーティのデータをインポートする方法について説明します。
ms.openlocfilehash: 2d011fcb63e0ec9804ade62f9fdcd1dd95fbf798
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210540"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="86a15-103">サード パーティのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="86a15-103">Archive third-party data</span></span>

<span data-ttu-id="86a15-104">Microsoft 365 では、管理者がソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="86a15-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="86a15-105">Microsoft 365 にインポートできるサードパーティのデータソースの例には、次のサービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="86a15-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="86a15-106">**ソーシャル:** Facebook、LinkedIn、Twitter、Yammer</span><span class="sxs-lookup"><span data-stu-id="86a15-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="86a15-107">**インスタントメッセージング:** Yahoo メッセンジャーと GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="86a15-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="86a15-108">**ドキュメントの共同作業:** Box および DropBox</span><span class="sxs-lookup"><span data-stu-id="86a15-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="86a15-109">**縦型の業種:** 顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など)</span><span class="sxs-lookup"><span data-stu-id="86a15-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="86a15-110">**SMS/テキストメッセージング:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="86a15-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="86a15-111">サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、通信コンプライアンス、およびアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="86a15-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="86a15-112">たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。</span><span class="sxs-lookup"><span data-stu-id="86a15-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="86a15-113">Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="86a15-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="86a15-114">また、Microsoft データの場合と同じように、アーカイブポリシーとアイテム保持ポリシーをサードパーティデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="86a15-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="86a15-115">簡単に言えば、Microsoft 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="86a15-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="86a15-116">Microsoft 365 でサードパーティのデータをインポートしてアーカイブする方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="86a15-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="86a15-117">**セキュリティ & コンプライアンスセンターで、サードパーティのデータコネクタを使用します。** Microsoft 365 コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="86a15-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="86a15-118">コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Microsoft 365 のメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="86a15-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="86a15-119">現時点では、Facebook ビジネスページ、企業 Twitter アカウント、LinkedIn、Instant Bloomberg、組織の人事 (HR) データのデータをインポートおよびアーカイブするためのコネクタを実装できます。</span><span class="sxs-lookup"><span data-stu-id="86a15-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="86a15-120">これらのコネクタの1つを設定するための詳しい手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86a15-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="86a15-121">**Facebook:** [コネクタを使用して facebook データをアーカイブする (プレビュー)](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="86a15-121">**Facebook:** [Use a connector to archive Facebook data (preview)](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="86a15-122">**Twitter:** [コネクタを使用して twitter データをアーカイブする (プレビュー)](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="86a15-122">**Twitter:** [Use a connector to archive Twitter data (preview)](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="86a15-123">**Linkedin:** [linkedin データをアーカイブするためのコネクタを設定する](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="86a15-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="86a15-124">**インスタント Bloomberg:** [インスタント Bloomberg データをアーカイブするためのコネクタの設定](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="86a15-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="86a15-125">**人事データ:** [hr データをインポートするためのコネクタを設定する (プレビュー)](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="86a15-125">**HR data:** [Set up a connector to import HR data (preview)](import-hr-data.md)</span></span>

- <span data-ttu-id="86a15-126">**Microsoft パートナーと連携する:** 組織は、サードパーティのデータソースからアイテムを定期的に抽出するように構成されるカスタムコネクタを提供する Microsoft パートナーと連携して、サードパーティの API によって Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="86a15-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="86a15-127">また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="86a15-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="86a15-128">この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「 [Microsoft 365 でサードパーティのデータをアーカイブするためにパートナーと連携する](work-with-partner-to-archive-third-party-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86a15-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
