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
description: コンテンツの書式設定時にテキストを変更し、フィールド変数を結合するには、Communications Editor を使用します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769162"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="4c422-103">通信エディターを使用する</span><span class="sxs-lookup"><span data-stu-id="4c422-103">Use the communications editor</span></span>

<span data-ttu-id="4c422-104">ポータル コンテンツのコンテンツ、法的情報保留通知、関連するリマインダー/エスカレーションを定義する場合、コミュニケーション エディターを使用してコンテンツの書式設定と動的なカスタマイズを行います。</span><span class="sxs-lookup"><span data-stu-id="4c422-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="4c422-105">リッチ テキスト エディター</span><span class="sxs-lookup"><span data-stu-id="4c422-105">Rich text editor</span></span>

<span data-ttu-id="4c422-106">コミュニケーション エディターを使用すると、ユーザーはエディターオプションを使用してテキストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4c422-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="4c422-107">たとえば、フォントの種類の変更、箇条書きの作成、コンテンツの強調表示などです。</span><span class="sxs-lookup"><span data-stu-id="4c422-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="4c422-108">フィールド変数を結合する</span><span class="sxs-lookup"><span data-stu-id="4c422-108">Merge field variables</span></span>

<span data-ttu-id="4c422-109">通信エディターの電子メールの差し込み変数を使用して、カスタマイズされた保管担当者の属性を通信の本文テキストに埋め込む方法があります。</span><span class="sxs-lookup"><span data-stu-id="4c422-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="4c422-110">カストディアンに送信すると、マージ フィールドに対応するフィールドが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4c422-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="4c422-111">たとえば、カストディアンの John Smith に送信すると、結合フィールド [保管担当者名] は対応する名前で翻訳されます。</span><span class="sxs-lookup"><span data-stu-id="4c422-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="4c422-112">リッチ テキスト エディター コントロールの上部にある[差し込み印刷] フィールド アイコンを選択すると、電子メールの差し込みフィールドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c422-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="4c422-113">プレースホルダーは、ユーザーのカーソルの位置に基づいて追加されます。</span><span class="sxs-lookup"><span data-stu-id="4c422-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="4c422-114">差し込み印刷フィールド変数のリスト</span><span class="sxs-lookup"><span data-stu-id="4c422-114">List of merge field variables</span></span>

| <span data-ttu-id="4c422-115">フィールド名</span><span class="sxs-lookup"><span data-stu-id="4c422-115">Field name</span></span>                  | <span data-ttu-id="4c422-116">フィールドの詳細</span><span class="sxs-lookup"><span data-stu-id="4c422-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="4c422-117">表示名</span><span class="sxs-lookup"><span data-stu-id="4c422-117">Display Name</span></span>  | <span data-ttu-id="4c422-118">カストディアンの名と名。</span><span class="sxs-lookup"><span data-stu-id="4c422-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="4c422-119">確認応答リンク</span><span class="sxs-lookup"><span data-stu-id="4c422-119">Acknowledgment Link</span></span> | <span data-ttu-id="4c422-120">各保管担当者の確認を記録するカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="4c422-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="4c422-121">ポータル リンク</span><span class="sxs-lookup"><span data-stu-id="4c422-121">Portal Link</span></span>     | <span data-ttu-id="4c422-122">カストディアンのコンプライアンス ポータル用にカスタマイズされたリンク。</span><span class="sxs-lookup"><span data-stu-id="4c422-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="4c422-123">発行責任者</span><span class="sxs-lookup"><span data-stu-id="4c422-123">Issuing Officer</span></span>                   | <span data-ttu-id="4c422-124">指定された発行者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="4c422-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="4c422-125">発行日</span><span class="sxs-lookup"><span data-stu-id="4c422-125">Issuing Date</span></span>                   | <span data-ttu-id="4c422-126">通知が発行された日付 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="4c422-126">The date that the notice was issued (UTC).</span></span>              |
|||
