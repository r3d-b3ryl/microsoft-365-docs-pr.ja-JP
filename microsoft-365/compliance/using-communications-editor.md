---
title: 通信エディターを使用する
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
description: コミュニケーションエディターを使用して、コンテンツの書式設定時にテキストと差し込みフィールドの変数を変更します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034479"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="dc192-103">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="dc192-103">Use the communications editor</span></span>

<span data-ttu-id="dc192-104">ポータルコンテンツ、法的情報保留通知、および関連する事前通知/エスカレーションの内容を定義する際に、コミュニケーションエディターを活用して、コンテンツの書式設定や動的なカスタマイズを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dc192-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="dc192-105">リッチテキストエディター</span><span class="sxs-lookup"><span data-stu-id="dc192-105">Rich text editor</span></span> 

<span data-ttu-id="dc192-106">コミュニケーションエディターを使用すると、ユーザーはエディターのオプションを使用してテキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="dc192-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="dc192-107">たとえば、ユーザーはフォントの種類を変更したり、箇条書きのリストを作成したり、コンテンツを強調表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc192-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="dc192-108">差し込みフィールドの変数</span><span class="sxs-lookup"><span data-stu-id="dc192-108">Merge field variables</span></span>

<span data-ttu-id="dc192-109">コミュニケーションエディターから電子メールの宛名差し込み変数を活用して、カスタマイズされた保管担当者属性をコミュニケーションの本文テキストに埋め込むことができます。</span><span class="sxs-lookup"><span data-stu-id="dc192-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="dc192-110">保管担当者に送信されると、対応するフィールドが差し込み印刷フィールドに設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc192-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="dc192-111">たとえば、保管担当者 John Smith に送信された場合、差し込み印刷フィールド [保管担当者 Name] は対応する名前に変換されます。</span><span class="sxs-lookup"><span data-stu-id="dc192-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="dc192-112">電子メールの宛名差し込みフィールドを使用するには、リッチテキストエディターコントロールの上部にある**差し込み印刷フィールド**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc192-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="dc192-113">プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。</span><span class="sxs-lookup"><span data-stu-id="dc192-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="dc192-114">差し込みフィールドの変数の一覧</span><span class="sxs-lookup"><span data-stu-id="dc192-114">List of merge field variables</span></span>

| <span data-ttu-id="dc192-115">フィールド名</span><span class="sxs-lookup"><span data-stu-id="dc192-115">Field name</span></span>                  | <span data-ttu-id="dc192-116">フィールドの詳細</span><span class="sxs-lookup"><span data-stu-id="dc192-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="dc192-117">表示名</span><span class="sxs-lookup"><span data-stu-id="dc192-117">Display Name</span></span>  | <span data-ttu-id="dc192-118">保管担当者の姓と名。</span><span class="sxs-lookup"><span data-stu-id="dc192-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="dc192-119">確認のリンク</span><span class="sxs-lookup"><span data-stu-id="dc192-119">Acknowledgement Link</span></span> | <span data-ttu-id="dc192-120">各保管担当者の受信確認を記録するためのカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="dc192-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="dc192-121">ポータルリンク</span><span class="sxs-lookup"><span data-stu-id="dc192-121">Portal Link</span></span>     | <span data-ttu-id="dc192-122">保管担当者のコンプライアンスポータル用のカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="dc192-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="dc192-123">発行責任者</span><span class="sxs-lookup"><span data-stu-id="dc192-123">Issuing Officer</span></span>                   | <span data-ttu-id="dc192-124">指定した発行担当者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="dc192-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="dc192-125">発行日</span><span class="sxs-lookup"><span data-stu-id="dc192-125">Issuing Date</span></span>                   | <span data-ttu-id="dc192-126">通知が発行された日付 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="dc192-126">The date that the notice was issued (UTC).</span></span>              |
